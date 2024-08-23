---
title: Så här spelar du upp
description: Förstå begreppet"replay" i enhetsövergripande analys
exl-id: 0b7252ff-3986-4fcf-810a-438d9a51e01f
feature: CDA
role: Admin
source-git-commit: cfa5cc02ba3a7349b51a904f29bab533c0f1c603
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 0%

---

# Så här spelar du upp

{{available-existing-customers}}

Enhetsövergripande analys gör att data kan skickas vidare i en virtuell rapportserie:

* **Live-stitching**: CDA försöker sy ihop varje träff när den kommer in. Nya Net-enheter i rapportsviten som aldrig har loggat in sammanfogas vanligtvis inte på den här nivån. Enheter som redan känns igen sammanfogas omedelbart.
* **Spela upp**: CDA&quot;spelar upp&quot; data ungefär en gång i veckan baserat på unika identifierare som den har lärt sig. I det här skedet sammanfogas nya enheter i rapportsviten.

## Exempeltabell

Följande tabeller visar hur både CDA-metoder ([Fältbaserad sammanfogning](field-based-stitching.md) och [Enhetsdiagram](device-graph.md)) beräknar antalet unika personer:

### Live-syn

Så snart en träff har samlats försöker CDA sy ihop den till kända enheter. Titta på följande exempel där Bob använder två enheter.

*Data som de visas den dag de samlas in:*

| Tidsstämpel | ECID | eVar1 eller CustomerID | Förklaring av träffen | Personmått (kumulativt) med Device Graph | Personmått (kumulativt) med fältbaserad sytning |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob på sin dator, oautentiserad | `1` (246) | `1` (246) |
| `2` | `246` | `Bob` | Bob loggar in på sitt skrivbord | `1` (246) | `2` (246 och Bob) |
| `3` | `3579` | - | Bob på sin mobila enhet, oautentiserad | `2` (246 och 3579) | `3` (246, Bob och 3579) |
| `4` | `3579` | `Bob` | Bob loggar in på mobilen | `2` (246 och 3579) | `3` (246, Bob och 3579) |
| `5` | `246` | - | Bob kommer åt din webbplats på skrivbordet igen, oautentiserad | `2` (246 och 3579) | `3` (246, Bob och 3579) |
| `6` | `246` | `Bob` | Bob loggar in igen via skrivbordet | `2` (246 och 3579) | `3` (246, Bob och 3579) |
| `7` | `3579` | - | Bob kommer åt din webbplats igen på mobilen | `2` (246 och 3579) | `3` (246, Bob och 3579) |
| `8` | `3579` | `Bob` | Bob loggar in igen via mobilen | `2` (246 och 3579) | `3` (246, Bob och 3579) |

Både oautentiserade och autentiserade träffar på nya enheter räknas som separata personer (tillfälligt).

* **Om du använder enhetsgrafen** aktiveras oautentiserade träffar på identifierade enheter när ett kluster publiceras av enhetsgrafen. Klusterpublicering tar allt från tre timmar till två veckor.

  En tredje kumulativ person läggs också till när ett kluster publiceras. Den här tredje personen representerar själva klustret, förutom de enskilda enheterna. Den tredje &quot;personen&quot; finns kvar tills data spelas upp.

  Attribuering fungerar inte på alla enheter förrän ett kluster har publicerats, och till och med så har det bara sytts live från den punkten framåt. I exemplet ovan sammanfogas inga träffar på enheter ännu. Enhetsövergripande attribuering i befintliga träffar fungerar inte förrän du har repeterat sammanfogningen.
* **Om du använder fältbaserad sammanfogning kommer** oautentiserade träffar på identifierade enheter att sammanfogas från den punkten framåt.

  Attribution fungerar så snart den identifierande anpassade variabeln kopplar till en enhet. I exemplet ovan är alla träffar utom träffar 1 och 3 sammansydda (alla använder identifieraren `Bob`). Attribution works on hits 1 and 3 after replay stitching.

>[!NOTE]
>
>Tidsstämplade träffar som är äldre än 12 timmar sammanfogas inte i liveflödet. Dessa träffar inkluderas dock i Repetition stitching, så länge de inte visas i uppspelningsfönstret.

### Spela upp sammanfogning

Uppspelningen sker antingen varje dag eller varje vecka, beroende på hur du har begärt att CDA ska konfigureras. Under uppspelning försöker CDA att omfördela historiska data inom ett definierat uppslagsfönster:

* Daglig uppspelning använder ett 1-dagars uppslagsfönster
* Veckovis omspelning använder ett 7-dagars uppslagsfönster.

Om en enhet till att börja med skickar data utan att vara autentiserad och sedan loggar in, binder CDA dessa oautentiserade träffar till rätt person. Följande tabell representerar samma data som ovan, men visar olika tal baserat på hur data spelas upp.

*Samma data efter uppspelning:*

| Tidsstämpel | ECID | eVar1 eller CustomerID | Förklaring av träffen | Personmått (kumulativt) med Device Graph | Personmått (kumulativt) med fältbaserad sytning |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob på sin dator, oautentiserad | `1` (kluster1) | `1` (Bob) |
| `2` | `246` | `Bob` | Bob loggar in på sitt skrivbord | `1` (kluster1) | `1` (Bob) |
| `3` | `3579` | - | Bob på sin mobila enhet, oautentiserad | `1` (kluster1) | `1` (Bob) |
| `4` | `3579` | `Bob` | Bob loggar in på mobilen | `1` (kluster1) | `1` (Bob) |
| `5` | `246` | - | Bob kommer åt din webbplats på skrivbordet igen, oautentiserad | `1` (kluster1) | `1` (Bob) |
| `6` | `246` | `Bob` | Bob loggar in igen via skrivbordet | `1` (kluster1) | `1` (Bob) |
| `7` | `3579` | - | Bob kommer åt din webbplats igen på mobilen | `1` (kluster1) | `1` (Bob) |
| `8` | `3579` | `Bob` | Bob loggar in igen via mobilen | `1` (kluster1) | `1` (Bob) |
