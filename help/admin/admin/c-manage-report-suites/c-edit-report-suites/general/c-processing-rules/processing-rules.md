---
description: Bearbetningsregler förenklar datainsamling och hantering av innehåll när det skickas till rapportering.
subtopic: Processing rules
title: Översikt över behandlingsregler
feature: Processing Rules
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 2%

---

# Översikt över behandlingsregler

Bearbetningsregler förenklar datainsamling och hantering av innehåll när det skickas till rapportering. Bearbetningsreglerna förenklar interaktionen med IT-grupper och webbutvecklare genom ett gränssnitt för att

* Ange en händelse på produktöversiktssidan
* Fyll i kampanj med en frågesträngsparameter
* Sammanfoga kategori- och sidnamn i ett utkast för enklare rapportering
* Kopiera en eVar till en svällning för att se banor
* Rensa felstavade webbplatsavsnitt
* Hämta interna söktermer eller ett kampanj-ID från frågesträngen till en eVar

>[!VIDEO](https://video.tv.adobe.com/v/26124/?quality=12&learn=on)

## Bearbetar regelbehörigheter {#section_8A4846688050453784DAE4D89355169A}

Administratörer har behörighet att använda bearbetningsregler **som standard**. Administratörer kan även ge dessa rättigheter till icke-administratörer via gränssnittet Administratörsverktyg. Instruktioner finns i []

![Behandlingsregler](assets/processing-rules.png)

## Använd kontextdata för att förenkla datainsamling {#section_09EEA03612D24C15839631AA9E9668D8}

Sammanhangsdatavariabler är en typ av variabler som bara är tillgängliga för bearbetning av regler. Om du vill använda kontextdatavariabler skickas nyckeldatapar/värdepar in av implementeringen, och bearbetningsregler används för att hämta dessa värden i vanliga Analytics-variabler. Detta frigör programmerare från att förstå exakt vilka prop och/eller eVar som ska innehålla vilket värde.

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

När du har angett värden i koden kan du ange bearbetningsregler för att tilldela värden till variabler. Exempel:

1. Karta `author` till `eVar2`
2. Karta `section` till `prop1` och `eVar3`
3. If `author` och `section` exists, set `event5`

Se [contextData](/help/implement/vars/page-vars/contextdata.md) i Implementera användarhandboken för mer information.

## Använd bearbetningsregler för att omforma träff- och utlösarhändelser {#section_8284E72E999244E091CD7FB1A22342B6}

Bearbetningsregler kan övervaka inkommande värden för att omforma vanliga typer och ange händelser baserat på rapporterade data. Props kan kopieras till eVars. Värden kan sammanfogas för rapporter och händelser kan anges.

## Använda kontextdatavariabler i rapporter {#section_BD098BC503024A0B8703596628071134}

När kontextdatavariabler definieras i implementeringen måste de kopieras till variabler som eVars för att användas vid rapportering.

Se [Kopiera en kontextdatavariabel till en eVar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) och [Ange en händelse med hjälp av en kontextdatavariabel](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md) för mer information.

## Kända begränsningar

**Användning av varukorgar (^) i bearbetningsregler.** Om du vill använda karatter i bearbetningsregler som avgränsare eller för andra ändamål, måste varje karat representeras av två karatter. Du kan till exempel representera en enskild vagn som ^^, en dubbel vagn som ^^^^,