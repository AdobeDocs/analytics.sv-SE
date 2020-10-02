---
description: Bearbetningsregler förenklar datainsamling och hantering av innehåll när det skickas till rapportering.
subtopic: Processing rules
title: Översikt över behandlingsregler
topic: Admin tools
uuid: 6b4ee7c9-2b86-47a6-b64c-c8d644fff67d
translation-type: tm+mt
source-git-commit: 4cacd06d268c501ade05487c594bc68aa22e9f4c
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 1%

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

Sammanhangsdatavariabler är en typ av variabler som bara är tillgängliga för bearbetning av regler. Om du vill använda kontextdatavariabler skickas nyckeldatapar/värdepar in av implementeringen, och bearbetningsregler används för att hämta dessa värden i vanliga Analytics-variabler. Detta frigör programmerare från att förstå exakt vilka prop och/eller eVar som ska innehålla vilket värde.

![](assets/evar-context-map.png)

Se [Kontextdatavariabler](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) i implementeringshjälpen.

## Använd bearbetningsregler för att omforma träff- och utlösarhändelser {#section_8284E72E999244E091CD7FB1A22342B6}

Bearbetningsregler kan övervaka inkommande värden för att omforma vanliga typer och ange händelser baserat på rapporterade data. Props kan kopieras till eVars. Värden kan sammanfogas för rapporter och händelser kan anges.

## Använda kontextdatavariabler i rapporter {#section_BD098BC503024A0B8703596628071134}

När kontextdatavariabler definieras i implementeringen måste de kopieras till variabler som eVars för att användas vid rapportering.

Mer information finns [här](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) och [här](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md).
