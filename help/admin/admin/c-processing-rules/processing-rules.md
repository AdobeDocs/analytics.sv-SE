---
description: Bearbetningsregler förenklar datainsamling och hantering av innehåll när det skickas till rapportering.
subtopic: Processing rules
title: Översikt över behandlingsregler
feature: Admin Tools
uuid: 6b4ee7c9-2b86-47a6-b64c-c8d644fff67d
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '396'
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

![](assets/processing-rules.png)

>[!IMPORTANT]
>
>Eftersom bearbetningsregler permanent påverkar Analytics-data rekommenderar Adobe att regeladministratörer får certifieringsutbildning i Adobe Analytics och känner till alla datakällor för rapportsviterna (standardwebbplatser, mobilwebbplatser, mobilappar, API för datainfogning och så vidare). Kunskap om kontextdatavariabler och standardvariabler som är ifyllda på olika plattformar hjälper till att förhindra oavsiktlig radering eller ändring av data.

## Använd kontextdata för att förenkla datainsamling {#section_09EEA03612D24C15839631AA9E9668D8}

Sammanhangsdatavariabler är en typ av variabler som bara är tillgängliga för bearbetning av regler. Om du vill använda kontextdatavariabler skickas nyckeldatapar/värdepar in av din implementering, och bearbetningsregler används för att hämta dessa värden i vanliga Analytics-variabler. Detta frigör programmerare från att förstå exakt vilka prop och/eller eVar som ska innehålla vilket värde.

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

När du har angett värden i koden kan du ange bearbetningsregler för att tilldela värden till variabler. Exempel:

1. Mappa `author` till `eVar2`
2. Mappa `section` till `prop1` och `eVar3`
3. Om `author` och `section` finns anger du `event5`

Mer information finns i [contextData](/help/implement/vars/page-vars/contextdata.md) i Användarhandboken för implementering.

## Använd bearbetningsregler för att omforma träff- och utlösarhändelser {#section_8284E72E999244E091CD7FB1A22342B6}

Bearbetningsregler kan övervaka inkommande värden för att omforma vanliga typer och ange händelser baserat på rapporterade data. Props kan kopieras till eVars. Värden kan sammanfogas för rapporter och händelser kan anges.

## Använda kontextdatavariabler i rapportering {#section_BD098BC503024A0B8703596628071134}

När kontextdatavariabler definieras i implementeringen måste de kopieras till variabler som eVars för att användas vid rapportering.

Mer information finns i [Kopiera en kontextdatavariabel till en eVar](processing-rules-examples/processing-rules-copy-context-data.md) och [Ange en händelse med hjälp av en kontextdatavariabel](processing-rules-examples/processing-rules-copy-context-data-event.md).
