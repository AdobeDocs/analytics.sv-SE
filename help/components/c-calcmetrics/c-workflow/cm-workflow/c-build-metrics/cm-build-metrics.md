---
description: I verktyget Calculated Metrics Builder finns en arbetsyta där du kan dra och släppa Dimensioner, mått, segment och funktioner för att skapa anpassade mätvärden baserade på behållarhierarkilogik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla beräknade mätvärden eller komplexa avancerade beräknade mätvärden.
title: Bygg mätvärden
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: 7722a2f01ff77dfec8ce110fd04fe977f6c627c6
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 2%

---

# Bygg mätvärden

Adobe Analytics har en arbetsyta där du kan dra och släppa dimensioner, mätvärden, segment och funktioner för att skapa anpassade mätvärden baserade på behållarhierarkilogik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla eller komplexa beräknade mätvärden.

## Börja skapa ett beräknat mått

Du kan börja skapa ett beräknat mått på något av följande sätt:

* Öppna ett projekt i Analysis Workspace och välj **[!UICONTROL Components]** > **[!UICONTROL Create metric]**.
* Öppna ett projekt i Analysis Workspace och välj sedan **Plus** -ikonen bredvid [!UICONTROL **Mått**] till vänster.
* I [!DNL Analytics], gå till **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]** väljer **[!UICONTROL + Add]** högst upp på sidan Beräknade mått.

## Områden i verktyget för beräknade värden

I följande bild och medföljande tabell förklaras några av huvudområdena och funktionerna i verktyget för beräkning av mätvärden.

![](assets/cm_builder_ui.png)

| Plats i bild | Namn och funktion |
|---|---|
| 1 | **Titel:** Det är obligatoriskt att namnge måttet. Du kan inte spara måttet om det inte har ett namn. |
| 2 | **Beskrivning:** Ge den en användarvänlig beskrivning för att visa vad den används för och skilja den från liknande. <p>Beskrivningen visas också i en rapport. Det är bäst att INTE placera formeln i beskrivningen. Beskriv i stället vad det här måttet ska och inte ska användas för. (Formeln genereras när du bygger måttet, under rubriken Sammanfattning. Därför behöver du inte lägga till formeln i beskrivningen.) </p> |
| 3 | **Format:** Du kan välja Decimal, Time, Percent och Currency. |
| 4 | **Decimaler:** Visar hur många decimaler som ska visas i rapporten. Det maximala antalet decimaler som du kan ange är 10. |
| 5 | **Visa uppåttrend som:** Den här inställningen för metrisk polaritet visar om Analytics bör ta hänsyn till en uppåtgående trend i mätvärdet som god (grön) eller dålig (röd). Därför visas rapportens diagram som grönt eller rött när det går upp. |
| 6 | **Taggar:** Taggning är ett bra sätt att ordna mätvärden. Alla användare kan skapa taggar och använda en eller flera taggar i ett mätresultat. Men du kan bara se taggar för de segment som du äger eller som har delats med dig. Vilka typer av taggar ska du skapa? Här följer några förslag på användbara taggar:<ul><li>**Teamnamn**, som social marknadsföring, mobilmarknadsföring.</li><li>**Projekt** (analystaggar), t.ex. på ingångssidan.</li><li>**Kategorier**, t.ex. Kvinnor. Geografi.</li><li>**Arbetsflöden** som ska godkännas, Kuraterad för (en specifik affärsenhet)</li></ul> |
| 7 | **Sammanfattning:** <p>Sammanfattningsformeln uppdateras när du ändrar måttdefinitionen. Formeln visas också i måttfältet till vänster när du håller muspekaren över ett mätresultat och klickar på <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> ikon. </p> |
| 8 | **Definition:** Här drar du i mått/beräknade mått, segment och/eller funktioner för att skapa det beräknade måttet. <ul><li>Om du drar i ett beräknat mått expanderas måttdefinitionen automatiskt. </li> <li>Du kan kapsla definitioner med behållare. Till skillnad från segmentbehållare fungerar dessa behållare som ett matematiskt uttryck och avgör ordningen på åtgärderna. </li> </ul> |
| 9 | **Operatör:** dividerat med ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) är standardoperatorn och det finns operatorerna +, - och x. |
| 10 | **Förhandsgranska:** Ger en snabb läsning av eventuella fel. Förhandsvisningen täcker de senaste 90 dagarna. Det här är ett sätt att först mäta om du har valt rätt komponenter för måttet. Ett oväntat resultat skulle innebära att du måste ta en andra titt på måttdefinitionen. |
| 11 | **Produktkompatibilitet:** Produktkompatibiliteten visar om mätvärdena är kompatibla med <a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html"  > Aktuella data </a>, med fullständigt bearbetade data, eller endast med marknadsföringskanalrapporter (första-touch-allokering). <p>Obs! Aktuella data stöder inte alla mått. Mätvärden som innehåller segment eller funktioner är inte kompatibla med aktuella data. <a href="/help/components/c-calcmetrics/cm-compatibility.md"  > Mer... </a> </p> </p> |
| 12 | **Lägg till:** För alla typer av beräknade värden kan du lägga till behållare och statiska tal i definitionen. För avancerade beräknade mätvärden kan du även lägga till segment och funktioner. <ul><li>Behållare fungerar som ett matematiskt uttryck och avgör ordningen på operationerna. Allt i en behållare bearbetas alltså före nästa åtgärd.</li><li>När du drar ett segment till en behållare segmenteras allt i behållaren. (Endast avancerade beräknade värden)</li><li>Du kan stapla flera segment i en behållare.</li></ul> |
| 13 | **Kugghjulsikon (Måtttyp, Attribution):** Om du väljer kugghjulsikonen bredvid ett mätresultat kan du ange <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  > metrisk typ och attribueringsmodeller </a>. |
| 14 | **Nytt:** Skapa en ny komponent, till exempel ett nytt segment (som tar dig till <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  > Segment Builder </a>.) |
| 15 | **Sökkomponenter:** Med det här sökfältet kan du söka efter dimensioner, mått, segment (endast avancerade beräknade värden) och funktioner (endast avancerade beräknade värden). |
| 16 | **Lista över Dimensioner:** Istället för att lämna beräkningsverktyget för att skapa ett enkelt segment (i segmentbyggaren), t.ex. &quot;Page = Homepage&quot; kan du dra i Page och välja Homepage direkt från Calculated Metric Builder.<p>Detta ger ett mycket effektivare arbetsflöde för att skapa segmenterade beräknade mätvärden.</p> |
| 17 | **Lista över mått:** Mätvärden finns i tre kategorier: <ul> <li>Standardvärden (<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>Beräknade värden ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li><li id="li_8735E76637ED4C3F983731A66E04C93E">Mätningsmallar ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />) - längst ned i listan. </li> </ul> <p>När du hovrar över ett mätresultat visas ikonen Info till höger om det: <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Om du klickar på den här ikonen visas följande information: </p><ul> <li>Formeln för hur den beräknas. </li><li>En förgranskningstrend för måttet. </li><li>En redigeringsikon (penna) <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> överst till höger på Calculated Metrics Builder där du kan redigera det beräknade måttet. </li></ul> |
| 18 | **Segmentlista:** (Endast avancerade beräknade värden) Som administratör visar den här listan alla segment som har skapats i ditt inloggningsföretag. Om du inte är administratör visas de segment du äger och de som delas med dig i den här listan. <a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html"  > Mer... </a> |
| 19 | **Lista över funktioner:** (Endast avancerade beräknade mätvärden) Funktionerna är uppdelade i två listor: <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  > Grundläggande </a> (används oftast) och <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  > Avancerat </a>. |
| 20 | **Report Suite-väljare:** Växla till en annan rapportserie. |

{style="table-layout:auto"}
