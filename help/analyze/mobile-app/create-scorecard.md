---
description: Skapa och dela Adobe Analytics instrumentpaneler med hjälp av styrkort
title: Skapa och dela mobilstyrkort
feature: Analytics Dashboards
role: User, Admin
exl-id: ebe6d83d-bbae-43de-bf85-35258bf6c1d0
source-git-commit: f2e040cfc6dcb67fbb1b995e38eede78943c66f7
workflow-type: tm+mt
source-wordcount: '2428'
ht-degree: 0%

---

# Skapa ett mobilstyrkort

Följande information instruerar de som arbetar med Adobe Analytics data om hur man konfigurerar och presenterar mobila styrkort för företagsanvändare. Börja med att titta på videon Adobe Analytics dashboards scorecard builder:

>[!VIDEO](https://video.tv.adobe.com/v/34544)

Ett Adobe Analytics-styrkort visar viktiga datavisualiseringar för chefsanvändare i en sidindelad layout, vilket visas nedan:

![Exempelstyrkort](assets/intro_scorecard.png)

Som kurator för det här styrkortet kan du använda styrkortsverktyget för att konfigurera vilka rutor som ska visas på styrkortet för den verkställande konsumenten. Du kan också konfigurera hur detaljerade vyer, eller delningarna, kan justeras när användaren trycker på plattorna. Styrkortbyggargränssnittet visas nedan:

![Styrkortbyggaren](assets/scorecard_builder.png)

Om du vill skapa styrkortet måste du göra följande:

1. Öppna mallen [!UICONTROL Blank Mobile Scorecard].
1. Konfigurera styrkortet med data och spara det.

## Åtkomst till mallen [!UICONTROL Blank Mobile Scorecard] {#template}

Du kan komma åt mallen [!UICONTROL Blank Mobile Scorecard] antingen genom att skapa ett nytt projekt eller via Verktyg-menyn.

### Skapa ett nytt projekt {#create}

1. Öppna Adobe Analytics och klicka på fliken **[!UICONTROL Workspace]**.
1. Klicka på **[!UICONTROL Create project]** och välj projektmallen **[!UICONTROL Blank Mobile Scorecard]**.
1. Klicka på **[!UICONTROL Create]**.

![Styrkortsmall](assets/new_template.png)

### Verktyg-menyn

1. Välj **[!UICONTROL Analytics dashboards (Mobile App)]** på menyn **[!UICONTROL Tools]**.
1. Klicka på **[!UICONTROL Create new scorecard]** på den följande skärmen.

## Konfigurera styrkortet med data och spara det {#configure}

Så här implementerar du styrkortsmallen:

1. Under **[!UICONTROL Properties]** (i den högra listen) anger du **[!UICONTROL Project report suite]** som du vill använda data från.

   ![Rapportera val av programsvit](assets/properties_save.png)

1. Om du vill lägga till en ny platta i styrkortet drar du en måttenhet från den vänstra panelen och släpper den i zonen **[!UICONTROL Drag and Drop Metrics Here]**. Du kan också infoga ett mätvärde mellan två rutor med ett liknande arbetsflöde.

   ![Lägg till paneler](assets/build_list.png)


1. Från varje ruta kan du visa en detaljerad vy som visar ytterligare information om måttet, till exempel de översta objekten för en lista med relaterade dimensioner.

## Lägg till mått eller mätvärden {#dimsmetrics}

Om du vill lägga till en relaterad dimension till ett mått drar du det från den vänstra panelen och släpper det på en platta.

Du kan till exempel lägga till lämpliga dimensioner (som **[!DNL Marketing Channel]**, i det här exemplet) till måttet **[!UICONTROL Unique Visitors]** genom att dra och släppa det på plattan. Uppdelningar av Dimensioner visas under avsnittet [!UICONTROL Drill Ins] i detaljbildrutespecifikt **[!UICONTROL Properties]**. Du kan lägga till flera dimensioner till varje platta.

![Lägg till dimensioner](assets/layer_dimensions.png)

## Använd segment {#segments}

Om du vill använda segment på enskilda plattor drar du ett segment från den vänstra panelen och släpper det direkt ovanpå plattan.

Om du vill använda segmentet på alla plattor i styrkortet, släpper du plattan ovanpå styrkortet. Du kan också tillämpa segment genom att markera segment på filtermenyn under datumintervallen. Du [konfigurerar och tillämpar filter för styrkort](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html) på samma sätt som i Adobe Analytics Workspace.

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

### Visa/dölj datumintervall för jämförelse {#show-comparison-dates}

Om du vill visa eller dölja datumintervall för jämförelse växlar du till inställningen **Inkludera jämförelsedatum**.

![Inkludera jämförelsedatum](assets/include-comparison-dates.png)

Inställningen är som standard *på*. Avmarkera alternativet om du inte vill visa jämförelsedatum.

![Avmarkerad inställning för jämförelsedatum](assets/no-comparison-dates.png)

## Använd visualiseringar {#viz}

Se en video om visualiseringar för mobilstyrkort:

>[!VIDEO](https://video.tv.adobe.com/v/337570/?quality=12&learn=on)

Kontrollpanelerna för analyser erbjuder fyra visualiseringar som ger er insikt i dimensionsobjekt och mätvärden. Ändra till en annan visualisering genom att ändra [!UICONTROL chart type] för en rutas [!UICONTROL Properties]. Markera bara den högra rutan och ändra sedan diagramtypen.

![Egenskaper för paneler](assets/properties.png)

Du kan också klicka på ikonen [!UICONTROL Visualizations] i den vänstra listen och dra och släppa den högra visualiseringen på plattan:

![Visualiseringar](assets/vizs.png)

### [!UICONTROL Summary Number]

Använd visualisering av sammanfattningsnummer för att markera ett stort tal som är viktigt i ett projekt.

![Sammanfattningsnummer](assets/summary-number.png)

### [!UICONTROL Donut]

På samma sätt som ett cirkeldiagram visar den här visualiseringen data som delar eller segment av en helhet. Använd ett mundiagram när du jämför procentandelar av en summa. Låt oss till exempel säga att du vill se vilken annonsplattform som har bidragit till det totala antalet unika besökare:

![Visa inte](assets/donut-viz.png)

### [!UICONTROL Line]

Radvisualiseringen representerar mätvärden som använder en rad för att visa hur värden ändras under en tidsperiod. Ett linjediagram visar måtten över tiden men fungerar med alla visualiseringar. Du visualiserar produktkategoridimensionen i det här exemplet.

![Radvisualisering](assets/line.png)


### [!UICONTROL Horizontal Bar]

Den här visualiseringen visar vågräta staplar som representerar olika värden för ett eller flera mätvärden. Om du till exempel enkelt vill se vilka dina bästa produkter är kan du använda [!UICONTROL Horizontal Bar] som visualisering.

![vågrätt fält](assets/horizontal.png)

### Ta bort [!UICONTROL Unspecified] dimensionsobjekt

Om du vill ta bort [!UICONTROL Unspecified] dimensionsobjekt från dina data gör du följande:

1. Välj rätt platta.
1. I den högra listen, under **[!UICONTROL Drill ins]**, väljer du högerpilen bredvid dimensionsobjektet vars **[!UICONTROL Unspecified]** objekt du vill ta bort.

   ![ospecificerad](assets/unspecified.png)

1. Klicka på ikonen bredvid **[!UICONTROL Unspecified]** för att ta bort ospecificerade data från din rapportering. (Du kan även ta bort andra dimensionsobjekt.)

## Visa och konfigurera egenskaper för paneler {#tiles}

När du klickar på en platta i styrkortsverktyget visas egenskaperna och egenskaperna för plattan och dess detaljbild i den högra listen. I den här rälsen kan du ange en ny **titel** för plattan och alternativt konfigurera plattan genom att använda segment.

![Egenskapspanel](assets/properties-tile-new.png)

## Visa detaljbilder {#view-detail-slides}

När du klickar på paneler visas i ett dynamiskt popup-fönster hur detaljbilden visas för den verkställande användaren i appen. Du kan lägga till dimensioner för att dela upp dina data efter dina specifika behov. Om en dimension inte har tillämpats är fördelningsdimensionen **timme** eller **dagar**, beroende på standarddatumintervallet.

Uppdelningar förfinar analysen genom att dela upp mätvärden efter dimensionsobjekt som exempelvis följande:

* Unika besökarvärden uppdelade efter annonsplattform (AMO-ID)
* Besök uppdelade efter produktkategori (detaljhandel)
* Total intäkt uppdelad efter produktnamn

![Breakdown_view](assets/break_view.png)

Varje dimension som läggs till i detaljbilden visas i en nedrullningsbar lista i vyn för detaljbilden i appen. Den verkställande användaren kan sedan välja bland alternativen i listrutan.

## Anpassa detaljbilder {#customize-detail-slide}

Med skräddarsydda detaljbilder kan ni målinrikta er ännu mer om vilken information ni delar med er målgrupp.

>[!VIDEO](https://video.tv.adobe.com/v/3410002)

Du kan ändra layouten för varje detaljbild och lägga till text som bättre förklarar vad slutanvändaren kan se i informationen. Du kan också ändra diagramtyp med hjälp av den nedrullningsbara menyn.

![Anpassad detaljbild](assets/custom-detail-slide.png)

### Ändra bildrutelayout

Ändra bildrutelayouten så att den fokuserar på den viktigaste informationen. Du kan till exempel ändra layouten så att bara ett diagram eller en tabell visas. Om du vill ändra bildrutelayouten väljer du ett av de fördesignade formaten.

![Bildlayout](assets/layout.png)

Du kan också ändra bildrutelayouten genom att dra och släppa visualiseringskomponenter från den vänstra listen på arbetsytan. Varje detaljbild kan endast innehålla två visualiseringar åt gången.

![Ändring av bildlayout](assets/slide-layout-change.png)

### Lägga till beskrivande text i en bildruta

Du kan lägga till text för att ge meningsfull information om vad som finns i diagrammen eller nyanserna om data.

Om du vill lägga till text i en detaljbildruta väljer du en layout som visar symbolen `T` eller drar och släpper textvisualiseringskomponenten från den vänstra listen. Textredigeraren öppnas automatiskt när du lägger till en ny textvisualisering eller väljer en bildlayout med text. I textredigeraren finns alla standardalternativ för formatering av texten. Du kan använda textformat som stycke, rubriker och underrubriker och använda fet och kursiv stil. Du kan justera text, lägga till punktlistor och numrerade listor samt lägga till länkar. När du är klar med redigeringen klickar du på minimeringsknappen i det övre högra hörnet av textredigeraren för att stänga den. Om du vill redigera text som du redan har lagt till väljer du pennikonen och öppnar textredigeraren igen.

![Ändring av bildlayout](assets/add-descriptive-text.png)

## Ta bort komponenter {#remove}

Om du vill ta bort en komponent som har tillämpats på hela styrkortet klickar du var som helst på styrkortet utanför rutorna och tar sedan bort den genom att klicka på **x** som visas när du håller muspekaren över komponenten, så som visas nedan för segmentet **Första gången du besöker** :

![Remove_components](assets/new_remove.png)

## Skapa dataartiklar {#create-data-story}

En databerättelse är en samling datapunkter, kontext och relaterade mått som bygger på ett centralt tema eller mätvärden.

Om du till exempel fokuserar på webbtrafik kan det vara dina viktigaste mätvärden, men du kanske också är intresserad av nya besökare, unika besökare, och du kanske vill se data uppdelade efter webbsida eller efter vilken typ av enhet som trafiken kommer från. Med hjälp av datarubriker i mobilstyrningsprojekt kan du placera dina viktigaste mätvärden i centrum samtidigt som du berättar hela artikeln bakom mätvärdena med flera detaljbilder.

Titta på videon och lär dig mer om hur du skapar databerättelser i mobilstyrkortsprojekt i Analysis Workspace.

>[!VIDEO](https://video.tv.adobe.com/v/3416392/?quality=12&learn=on)

**Så här skapar du en dataartikel**

Bygg din databerättelse genom att lägga till flera detaljbilder i en ruta.

1. Börja med ett mobilstyrningsprojekt.
1. Välj en platta som du vill skapa en artikel från.

   ![Skapa en dataartikel](assets/data-story1.png)

   ![Skapa ikoner för databerättelse](assets/create-data-story.png){width=".50%"}

1. Lägg till bilder för att skapa din databerättelse. Den första bilden genereras som standard.

   Om du vill lägga till nya bildrutor håller du markören över eller klickar på en bildruta och väljer sedan bland de tillgängliga alternativen:

   * Tryck på [!UICONTROL +]-tecknet för att skapa en ny bildruta.

   * Tryck på ikonen Duplicera om du vill duplicera den befintliga bildrutan.

1. Om du skapar en tom bildruta drar och släpper du komponenter från den vänstra listen, eller väljer en layout som automatiskt fyller bildrutan med data från den.

   ![Skapa en dataartikel](assets/data-story2.png)

Om du vill ta bort en bildruta trycker du på papperskorgsikonen.

### Anpassa en dataartikel {#customize-data-story}

Med hjälp av dataartiklar kan du anpassa allt så att du kan dela information som du vill dela och utesluta allt som du inte behöver. Du kan anpassa plattor och enskilda bildrutor för att lägga till filter, visa uppdelningar, ändra layout och ändra visualiseringar.

**Anpassa rutor**

1. Tryck på en platta. Den markerade plattan visas med blå konturer och den högra panelen visar rutans egenskaper.
1. Ändra alternativ för rubrik, diagramtyp och annan ruta.
1. Dra en komponent till plattan.

   ![Skapa en dataartikel](assets/data-story3.png)

   När du drar och släpper en komponent, t.ex. en visualisering, på en platta används komponenten på alla bilder i en dataartikel.

1. Om du bara vill ändra titeln håller du ned Skift-tangenten för att tillämpa ändringen.

   ![Skapa en dataartikel](assets/data-story4.png)

>[!NOTE]
>Bilder ärver komponenter från plattan, men rutor ärver inte komponenter från bildrutor.

**Anpassa enskilda bilder**

Du kan ändra visualiseringen för enskilda bilder i en dataartikel. Du kan till exempel ändra ett vågrätt fält till ett ringdiagram för en viss bildruta. Du kan också ändra layouten. Se [Anpassa detaljbilder](#customize-detail-slide).

### Förhandsgranska en dataartikel {#preview-data-story}

När du har skapat en dataartikel använder du knappen **Förhandsgranska** för att visa och interagera med en dataartikel som om du var en appanvändare. Mer information om hur du förhandsgranskar din dataartikel finns i [Förhandsgranska ett styrkort](#preview)

### Navigera mellan rutor och bilder {#navigate-tiles-slides}

I navigeringsfältet visas ikoner som representerar vad som finns på varje bildruta. Navigeringsfältet gör det enkelt att navigera till en viss bildruta om du har många bildrutor.

Om du vill flytta mellan plattan och bildrutorna trycker du på navigeringsfältet.

![Skapa en dataartikel](assets/data-story5.png)

![Skapa en dataartikel](assets/data-story-nav.png){width="25%"}

Du kan också navigera fram och tillbaka genom att använda pilarna på tangentbordet eller genom att markera en komponent och hålla den till vänster eller höger på skärmen för att rulla.


## Styrkort för förhandsgranskning {#preview}

Du kan förhandsgranska hur styrkortet kommer att se ut och fungera när det har publicerats i kontrollpanelsappen för Analytics.

1. Klicka på **[!UICONTROL Preview]** i skärmens övre högra hörn.

   ![Preview_scorecards](assets/preview.png)

1. Om du vill visa hur styrkortet kommer att se ut på olika enheter väljer du en enhet i listrutan [!UICONTROL Device preview].

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

1. Klicka på menyn **[!UICONTROL Share]** och välj **[!UICONTROL Share scorecard]**.

1. Fyll i fälten i formuläret **[!UICONTROL Share mobile scorecard]** genom att:

   * Ange namnet på styrkortet
   * Ange en beskrivning av styrkortet
   * Lägga till relevanta taggar
   * Ange mottagare för styrkortet

1. Klicka på **[!UICONTROL Share]**.

![Share_Scorecards](assets/new_share.png)

När du har delat ett styrkort kan mottagarna komma åt det på sina kontrollpaneler i Analytics. Om du gör efterföljande ändringar av styrkortet i styrkortsverktyget uppdateras de automatiskt i det delade styrkortet. Chefsanvändare ser sedan ändringarna när de har uppdaterat styrkortet i sin app.

Om du uppdaterar styrkortet genom att lägga till nya komponenter kanske du vill dela styrkortet igen (och markera alternativet **[!UICONTROL Share embedded components]**) för att se till att dina chefsanvändare har tillgång till dessa ändringar.

### Dela styrkort med hjälp av en delbar länk {#shareable-link}

Genom att använda en delbar länk är det enkelt att dela ett styrkort i ett e-postprogram, dokument eller textmeddelandeprogram. Med den delbara länken kan mottagarna öppna styrkortet på sina datorer eller i kontrollpanelernas mobilapp. Enkel, djup länkning gör det ännu enklare att dela projekt och öka engagemanget med era intressenter.

Dela ett styrkort med hjälp av en delbar länk

1. Klicka på menyn **[!UICONTROL Share]** och välj **[!UICONTROL Share scorecard]**.

   ![Share_Scorecards](assets/share-scorecard.png)

1. Kopiera länken och klistra in den i ett e-postmeddelande, dokument eller en snabbmeddelandeapp.

   När en mottagare använder en datorapp eller en webbläsare för att öppna länken öppnas ett mobilstyrkortsprojekt i Workspace.

   När en mottagare öppnar länken på en mobil enhet öppnas styrkortet direkt i kontrollpanelsappen för Analytics.

   Om en mottagare inte har laddat ned mobilappen dirigeras han/hon till applistan i App Store eller Google Play Store där han/hon kan ladda ned den.

