---
description: Skapa ett Adobe Analytics-styrkort
title: Skapa ett mobilstyrkort
feature: Analytics Dashboards
role: User, Admin
exl-id: ebe6d83d-bbae-43de-bf85-35258bf6c1d0
source-git-commit: 7f630839ae7d75730f93588877a172f3590d5a5e
workflow-type: tm+mt
source-wordcount: '1391'
ht-degree: 0%

---

# Skapa ett mobilstyrkort

Följande information instruerar de som arbetar med Adobe Analytics data om hur man konfigurerar och presenterar mobila styrkort för företagsanvändare. Börja med att titta på videon Adobe Analytics dashboards Scorecard Builder:

>[!VIDEO](https://video.tv.adobe.com/v/34544)

Ett Adobe Analytics-styrkort visar viktiga datavisualiseringar för chefsanvändare i en sidindelad layout, vilket visas nedan:

![Exempelstyrkort](assets/intro_scorecard.png)

Som kurator för det här styrkortet kan du använda styrkortsverktyget för att konfigurera vilka rutor som ska visas på styrkortet för den verkställande konsumenten. Du kan också konfigurera hur detaljerade vyer, eller delningarna, kan justeras när användaren trycker på plattorna. Gränssnittet i Scorecard Builder visas nedan:

![Styrkortbyggaren](assets/scorecard_builder.png)

Om du vill skapa styrkortet måste du göra följande:

1. Öppna [!UICONTROL Blank Mobile Scorecard] mall.
2. Konfigurera styrkortet med data och spara det.

## Öppna [!UICONTROL Blank Mobile Scorecard] mall {#template}

Du kommer åt [!UICONTROL Blank Mobile Scorecard] mall antingen genom att skapa ett nytt projekt eller från Verktyg-menyn.

### Skapa ett nytt projekt {#create}

1. Öppna Adobe Analytics och klicka på **[!UICONTROL Workspace]** -fliken.
1. Klicka **[!UICONTROL Create project]** och väljer **[!UICONTROL Blank mobile scorecard]** projektmall.
1. Klicka på **[!UICONTROL Create]**.

![Styrkortsmall](assets/new_template.png)

### Verktyg-menyn

1. Från **[!UICONTROL Tools]** meny, välja **[!UICONTROL Analytics dashboards (Mobile App)]**.
1. På nästa skärm klickar du på **[!UICONTROL Create new scorecard]**.

## Konfigurera styrkortet med data och spara det {#configure}

Så här implementerar du styrkortsmallen:

1. Under **[!UICONTROL Properties]** (i den högra listen), ange en **[!UICONTROL Project report suite]** som du vill använda data från.

   ![Val av rapportsvit](assets/properties_save.png)

1. Om du vill lägga till en ny platta i styrkortet drar du ett mått från den vänstra panelen och släpper det i **[!UICONTROL Drag and Drop Metrics Here]** zon. Du kan också infoga ett mätvärde mellan två rutor med ett liknande arbetsflöde.

   ![Lägg till rutor](assets/build_list.png)


1. Från varje ruta kan du visa en detaljerad vy som visar ytterligare information om måttet, till exempel de översta objekten för en lista med relaterade dimensioner.

## Lägg till mått eller mätvärden {#dimsmetrics}

Om du vill lägga till en relaterad dimension till ett mått drar du det från den vänstra panelen och släpper det på en platta.

Du kan till exempel lägga till lämpliga dimensioner (som **[!DNL Marketing Channel]**, i det här exemplet) till **[!UICONTROL Unique Visitors]** genom att dra och släppa det på plattan. Dimensioner visas under [!UICONTROL Drill Ins] (uppdelning) i den rutspecifika delen **[!UICONTROL Properties]**. Du kan lägga till flera dimensioner till varje platta.

![Lägg till dimensioner](assets/layer_dimensions.png)

## Använd segment {#segments}

Om du vill använda segment på enskilda plattor drar du ett segment från den vänstra panelen och släpper det direkt ovanpå plattan.

Om du vill använda segmentet på alla plattor i styrkortet, släpper du rutan ovanpå styrkortet. Du kan också tillämpa segment genom att markera segment på filtermenyn under datumintervallen. Du [konfigurera och använda filter för styrkort](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html) på samma sätt som i Adobe Analytics Workspace.

![Skapa segment för filter](assets/segment_ui.png)

## Lägg till datumintervall {#dates}

Lägg till och ta bort datumintervallkombinationer som kan väljas i styrkortet genom att markera listrutan för datumintervall.

![Nytt poängkort](assets/new_score_card.png)

Varje nytt styrkort börjar med 6 kombinationer av datumintervall som fokuserar på data från idag och igår. Du kan ta bort onödiga datumintervall genom att klicka på x eller redigera varje datumintervallkombination genom att klicka på pennan.

![Nytt poängkort2](assets/new_score_card2.png)

Om du vill skapa eller ändra ett primärt datum använder du listrutan för att välja bland tillgängliga datumintervall eller drar och släpper en datumkomponent från den högra listen i släppzonen.

![Nytt poängkort3](assets/new_score_card3.png)

Om du vill skapa ett jämförelsedatum kan du välja bland praktiska förinställningar för vanliga tidsjämförelser i listrutan. Du kan också dra och släppa en datumkomponent från den högra listen.

![Nytt poängkort4](assets/new_score_card4.png)

Om det datumintervall du vill använda inte har skapats ännu kan du skapa ett nytt genom att klicka på kalenderikonen.

![Nytt poängkort5](assets/new_score_card5.png)

Du kommer då till datumintervallsverktyget där du kan skapa och spara en ny datumintervallkomponent.

## Använd visualiseringar {#viz}

Se en video om visualiseringar för mobilstyrkort:

>[!VIDEO](https://video.tv.adobe.com/v/337570/?quality=12&learn=on)

Kontrollpanelerna för analyser erbjuder fyra visualiseringar som ger er insikt i dimensionsobjekt och mätvärden. Byt till en annan visualisering genom att ändra [!UICONTROL chart type] av en bricka [!UICONTROL Properties]. Markera bara den högra rutan och ändra sedan diagramtypen.

![Egenskaper för rutor](assets/properties.png)

Eller klicka på [!UICONTROL Visualizations] ikonen i den vänstra listen och dra och släpp den högra visualiseringen på plattan:

![Visualiseringar](assets/vizs.png)

### [!UICONTROL Summary Number]

Använd visualisering av sammanfattningsnummer för att markera ett stort tal som är viktigt i ett projekt.

![Sammanfattningsnummer](assets/summary-number.png)

### [!UICONTROL Donut]

På samma sätt som ett cirkeldiagram visar den här visualiseringen data som delar eller segment av en helhet. Använd ett mundiagram när du jämför procentandelar av en summa. Låt oss till exempel säga att du vill se vilken annonsplattform som har bidragit till det totala antalet unika besökare:

![Visualisering av ring](assets/donut-viz.png)

### [!UICONTROL Line]

Radvisualiseringen representerar mätvärden som använder en rad för att visa hur värden ändras under en tidsperiod. Ett linjediagram visar måtten över tiden men fungerar med alla visualiseringar. Du visualiserar produktkategoridimensionen i det här exemplet.

![Radvisualisering](assets/line.png)


### [!UICONTROL Horizontal Bar]

Den här visualiseringen visar vågräta staplar som representerar olika värden för ett eller flera mätvärden. Om du till exempel vill se vad dina bästa produkter är kan du använda [!UICONTROL Horizontal Bar] för din egen visualisering.

![vågrätt streck](assets/horizontal.png)

### Ta bort [!UICONTROL Unspecified] dimensionsposter

Om du vill ta bort [!UICONTROL Unspecified] dimensionsobjekt från dina data, gör följande:

1. Välj rätt platta.
1. I rätt spår, under **[!UICONTROL Drill ins]** markerar du högerpilen bredvid dimensionsobjektet vars **[!UICONTROL Unspecified]** objekt som du vill ta bort.

   ![ospecificerad](assets/unspecified.png)

1. Klicka på ikonen bredvid **[!UICONTROL Unspecified]** för att ta bort ospecificerade data från din rapportering. (Du kan även ta bort andra dimensionsobjekt.)

## Visa och konfigurera egenskaper för paneler {#tiles}

När du klickar på en platta i Styrkortbyggaren visas egenskaperna och egenskaperna för plattan i den högra listen. På den här listen kan du ange en ny **[!UICONTROL Title]** för plattan och konfigurera plattan genom att ange komponenter i stället för att dra och släppa dem från den vänstra listen.

![Egenskapspanelen](assets/properties_tile.png)

När du klickar på paneler visas ett dynamiskt popup-fönster med information om hur vyn Drill in (uppdelning) ser ut för den verkställande användaren i appen. Om ingen dimension har tillämpats på plattan kommer detaljdimensionen att **timme** eller **dagar**, beroende på standarddatumintervallet.

Uppdelningar förfinar analysen genom att bokstavligen dela upp mätvärden och dimensioner med andra mått och mått, som i det här exemplet:

* Unika besökarvärden uppdelade efter annonsplattform (AMO-ID)
* Besök uppdelade efter produktkategori (detaljhandel)
* Total intäkt uppdelad efter produktnamn

![Brytningsvy](assets/break_view.png)

Varje dimension som läggs till i rutan visas i en nedrullningsbar lista i appens detaljerade vy. Den verkställande användaren kan sedan välja bland alternativen i listrutan.

## Ta bort komponenter {#remove}

Om du vill ta bort en komponent som har tillämpats på hela styrkortet klickar du var som helst på styrkortet utanför rutorna och tar sedan bort den genom att klicka på **x** som visas när du hovrar över komponenten, som visas nedan för **Första gången du besöker** segment:

![Remove_components](assets/new_remove.png)

## Styrkort för förhandsgranskning {#preview}

Du kan förhandsgranska hur styrkortet kommer att se ut och fungera när det har publicerats i kontrollpanelsappen för Analytics.

1. Klicka **[!UICONTROL Preview]** i skärmens övre högra hörn.

   ![Preview_scorecards](assets/preview.png)

1. Om du vill visa hur styrkortet kommer att se ut på olika enheter väljer du en enhet på menyn [!UICONTROL Device preview] nedrullningsbar meny.

   ![Device_preview](assets/device-preview.png)

1. Om du vill interagera med förhandsgranskningen kan du:

   * Vänsterklicka för att simulera knackning på telefonskärmen.

   * Använd datorns rullningsfunktion för att simulera rullning av telefonskärmen med fingret.

   * Klicka och håll ned för att simulera att du trycker och håller fingret på telefonskärmen. Detta är användbart när du vill interagera med visualiseringarna i den detaljerade vyn.

## Namnge ett styrkort {#name}

Om du vill namnge styrkortet klickar du på namnutrymmet längst upp till vänster på skärmen och skriver det nya namnet.

![Naming_Scorecards](assets/new_name.png)

## Dela ett styrkort {#share}

Så här delar du styrkortet med en verkställande användare:

1. Klicka på **[!UICONTROL Share]** meny och välj **[!UICONTROL Share scorecard]**.

1. I **[!UICONTROL Share mobile scorecard]** fylla i fälten med:

   * Ange namnet på styrkortet
   * Ange en beskrivning av styrkortet
   * Lägga till relevanta taggar
   * Ange mottagare för styrkortet

1. Klicka på **[!UICONTROL Share]**.

![Dela_styrkort](assets/new_share.png)

När du har delat ett styrkort kan mottagarna komma åt det på sina kontrollpaneler i Analytics. Om du gör senare ändringar i styrkortet i Styrkortbyggaren uppdateras de automatiskt i det delade styrkortet. Chefsanvändare ser sedan ändringarna när styrkortet har uppdaterats i sin app.

Om du uppdaterar styrkortet genom att lägga till nya komponenter kanske du vill dela styrkortet igen (och kontrollera **[!UICONTROL Share embedded components]** för att se till att dina chefsanvändare har tillgång till dessa ändringar.
