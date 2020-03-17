---
description: Bearbetningsregler förenklar datainsamling och hantering av innehåll när det skickas till rapportering.
subtopic: Processing rules
title: Översikt över bearbetningsregler
topic: Admin tools
uuid: 6b4ee7c9-2b86-47a6-b64c-c8d644fff67d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Översikt över bearbetningsregler

Bearbetningsregler förenklar datainsamling och hantering av innehåll när det skickas till rapportering. Bearbetningsreglerna förenklar interaktionen med IT-grupper och webbutvecklare genom ett gränssnitt för att

* Ange en händelse på produktöversiktssidan
* Fyll i kampanj med en frågesträngsparameter
* Sammanfoga kategori- och sidnamn i ett utkast för enklare rapportering
* Kopiera en eVar till ett utkast för att se banor
* Rensa felstavade webbplatsavsnitt
* Hämta interna söktermer eller ett kampanj-ID från frågesträngen till en eVar

>[!VIDEO](https://tv.adobe.com/embed/1181/16506/)

*Titta på översikten över bearbetningsreglerna och kursen från Adobe Summit för att få reda på varför du bör använda bearbetningsregler.*

## Få behörighet att använda bearbetningsregler {#section_8A4846688050453784DAE4D89355169A}

Före den 20 april 2017 var alla användare (inklusive administratörer) tvungna att genomgå en tentamen och få tillstånd att använda bearbetningsreglerna av Adobes kundtjänst.

Nu har administratörer behörighet att använda bearbetningsregler **som standard**. Tentamen behövs inte längre. Administratörer kan även ge dessa rättigheter till icke-administratörer via gränssnittet Administratörsverktyg. Så här:

1. Om du inte redan har gjort det [skapar du en grupp](/help/admin/user-management2/c-user-groups/groups.md) som bara innehåller de icke-administratörer som bör ha behörighet att använda bearbetningsregler.
1. [Lägg till icke-administratörer i den gruppen](/help/admin/user-management2/c-user-management/t-add-user-to-group.md).
1. Gå sedan till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL-[gruppnamn]]** > **[!UICONTROL Edit]** > **[!UICONTROL Report Access]** **[!UICONTROL Report Suite Tools]** **[!UICONTROL Customize]** **[!UICONTROL Report Suite Management]**>¥ >¥ >¥.
1. Markera rutan intill [!UICONTROL Processing Rules] och klicka **[!UICONTROL OK]**.

![](assets/processing-rules.png)

>[!IMPORTANT]
>
>Eftersom bearbetningsregler påverkar Analytics-data permanent rekommenderar vi att regeladministratörer får certifieringsutbildning i Adobe Analytics och känner till alla datakällor för rapportsviterna (standardwebbplatser, mobilwebbplatser, mobilappar, API för datainfogning och så vidare). Kunskap om kontextdatavariabler och standardvariabler som är ifyllda på olika plattformar hjälper till att förhindra oavsiktlig radering eller ändring av data.

## Använd kontextdata för att förenkla datainsamling {#section_09EEA03612D24C15839631AA9E9668D8}

Sammanhangsdatavariabler är en ny typ av variabler som bara är tillgängliga för bearbetning av regler. Om du vill använda kontextdatavariabler skickas nyckeldatapar/värdepar in av implementeringen, och bearbetningsregler används för att hämta dessa värden i vanliga Analytics-variabler. Detta frigör programmerare från att förstå exakt vilket prop och/eller eVar som ska innehålla vilket värde.

![](assets/evar-context-map.png)

Se [Kontextdatavariabler](https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html) i implementeringshjälpen.

## Använd bearbetningsregler för att omforma träff- och utlösarhändelser {#section_8284E72E999244E091CD7FB1A22342B6}

Bearbetningsregler kan övervaka inkommande värden för att omforma vanliga typer och ange händelser baserat på rapporterade data. Props kan kopieras till eVars. Värden kan sammanfogas för rapporter och händelser kan anges.

## Använda kontextdatavariabler i rapporter {#section_BD098BC503024A0B8703596628071134}

När kontextdatavariabler definieras i implementeringen måste de kopieras till variabler som eVars för att användas vid rapportering.

Mer information finns [här](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) och [här](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md).
