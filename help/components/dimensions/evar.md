---
title: eVar
description: En anpassad dimension som du kan använda vid rapportering.
translation-type: tm+mt
source-git-commit: 10e157e370367374b55ee9c87c0e5c7ca9e99c1a
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 0%

---


# eVar

*Den här hjälpsidan beskriver hur eVars fungerar som en dimension. Mer information om hur du implementerar eVars finns i[eVars](/help/implement/vars/page-vars/evar.md)i användarhandboken för Implementera.*

Variabler är anpassade variabler som du kan använda hur du vill. Om du har ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md)blir de flesta dimensioner som är specifika för din organisation eVars. Som standard kvarstår eVars utanför den träff de är inställda på. Du kan anpassa deras förfallodatum och allokering under [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) i inställningarna för rapportsviten.

Antalet tillgängliga eVars-variabler beror på ditt avtal med Adobe. Upp till 250 eVars är tillgängliga om ditt avtal med Adobe ger stöd för det.

## Fyll i eVars med data

Varje eVar samlar in data från frågesträngen [`v1` - `v250` i bildbegäranden](/help/implement/validate/query-parameters.md) . Frågesträngsparametern samlar till exempel in data för eVar1, medan frågesträngsparametern samlar in data för eVar22 `v1` `v222` .

AppMeasurement, som kompilerar JavaScript-variabler till en bildbegäran för datainsamling, använder variablerna `eVar1` - `eVar250`. Mer information om implementeringsriktlinjer finns i [eVar](/help/implement/vars/page-vars/evar.md) i Implementeringsanvändarhandboken.

## Dimensionsvärden

Eftersom eVars innehåller anpassade strängar i implementeringen avgör organisationen vilka dimensionsvärden som finns för varje eVar. Se till att du registrerar syftet med varje eVar och typiska dimensionsvärden i ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md).

## Hur eVars fungerar

När ni skickar data till Adobe Analytics översätter datainsamlingsservrarna träffen till en enda rad med hundratals kolumner. Två kolumner är dedikerade till varje eVar; en för direkt datainsamling och den andra för beständiga värden.

* En standardkolumn innehåller data som skickats till Adobe från bildbegäran.
* En post-kolumn innehåller beständiga data, vilket beror på eVar-filens förfallodatum och allokering.

Under nästan alla omständigheter används kolumnen `post_evar` i rapporter.

### Hur eVars knyter till mätvärden

Framgångshändelser och eVars definieras ofta i olika bildbegäranden. I kolumnen kan eVar-värden knytas till händelser och data visas i rapporter. `post_evar` Ta till exempel följande besök:

1. En besökare kommer till din webbplats på din hemsida.
2. De söker efter &quot;katter&quot; med hjälp av webbplatsens interna sökning. Implementeringen använder eVar1 för intern sökning.
3. De visar en produkt och går igenom utcheckningsprocessen.

En förenklad version av rådata skulle se ut ungefär så här:

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* Kolumnen `visitor_id` är knuten till samma besökare. I faktiska rådata bestämmer de sammanfogade värdena för `visid_high` och `visid_low` besökar-ID.
* Kolumnen `pagename` fyller i siddimensionen.
* Kolumnen avgör `evar` träffar när eVar1 angavs explicit.
* Det föregående värdet `post_evar1` överförs beroende på variabelns allokering och förfallodatum som anges under rapportsvitens inställningar.
* Kolumnen `event_list` innehåller alla måttdata. I det här exemplet `event1` är sökningar och de andra händelserna är standardvärden för kundvagn. I faktiska rådata innehåller `event_list` en kommaavgränsad siduppsättning med en uppslagstabell som kopplar dessa siffror till ett mätvärde.

### Översätta datainsamling till rapportering

Verktyg i Adobe Analytics, t.ex. Analysis Workspace, arbetar med den här insamlade informationen. Om du till exempel har dragit en rapport med eVar1 som mått och order visas en rapport som ser ut ungefär så här:

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analysis Workspace hämtar den här rapporten med följande logik:

* Titta igenom alla `event_list` värden och välj ut alla träffar `purchase` i dem.
* Visa `post_evar1` värdet av de träffarna.

### Betydelsen av tilldelning och förfallodatum

Eftersom allokering och förfallodatum avgör vilka värden som kvarstår är de avgörande för att få ut så mycket som möjligt av en analysimplementering. Adobe rekommenderar att du diskuterar inom organisationen hur flera värden för varje eVar hanteras (allokering) och när eVars stoppar beständiga data (förfallodatum).

* Som standard använder en eVar den senaste allokeringen. Nya värden skriver över beständiga värden.
* Som standard används en eVar-variabel som sista giltighetsdag för besöket. När ett besök avslutas slutar värdena att kopieras från rad till rad i `post_evar` kolumnen.

Du kan ändra eVar-allokering och förfallodatum under [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) i inställningarna för rapportsviten.

## Värdet av eVars över props

Adobe rekommenderar att du använder eVars i de flesta fall, vilket stöds av följande:

* eVars har en gräns på 255 byte i rapporter. Props har en gräns på 100 byte.
* Som standard kvarstår inte uttryck efter den träff de ställs in. eVars har en anpassad förfallotid, vilket gör att du kan avgöra när en eVar inte längre får kredit för en efterföljande händelse. Om du däremot använder [rapporttidsbearbetning](/help/components/vrs/vrs-report-time-processing.md)kan både props och eVars använda en anpassad attribueringsmodell.
* Adobe stöder upp till 250 eVars och endast 75 props.

Se [prop](prop.md) för fler jämförelser mellan utkast och eVars.
