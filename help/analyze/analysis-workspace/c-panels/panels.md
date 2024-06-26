---
description: En panel är en samling tabeller och visualiseringar
title: Paneler - översikt
feature: Panels
role: User, Admin
exl-id: dd1a3c40-8b5b-47dd-86d9-da766575ee46
source-git-commit: aacba26d0eb612146a9e0bf6386f9e755a9e8f07
workflow-type: tm+mt
source-wordcount: '1551'
ht-degree: 0%

---

# Paneler - översikt

A [!UICONTROL panel] är en samling tabeller och visualiseringar. Du kommer åt panelerna från den övre vänstra ikonen i Workspace eller en [tom panel](blank-panel.md). Paneler är användbara när du vill ordna dina projekt efter tidsperioder, rapportsviter eller användningsfall för analyser.

## Paneltyper

Följande paneltyper är tillgängliga i Analysis Workspace:

| Panelnamn | Beskrivning |
| --- | --- |
| [Tom panel](blank-panel.md) | Välj bland tillgängliga paneler och visualiseringar för att starta analysen. |
| [Panelen Snabbinsikter](quickinsight.md) | Bygg snabbt ett frihandsbord och en medföljande visualisering för att analysera och hitta insikter snabbare. |
| [Analyser för målpanelen](a4t-panel.md) | Analysera Target-aktiviteter och -upplevelser i Analysis Workspace. |
| [Attributionspanelen](attribution.md) | Jämför och visualisera snabbt valfritt antal attribueringsmodeller med alla mått och konverteringsvärden. |
| [Frihandspanel](freeform-panel.md) | Utför obegränsade jämförelser och uppdelningar och lägg sedan till visualiseringar för att berätta en utförlig databerättelse. |
| [Panelen Mediegenomsnitt för miniatyrmålgrupp](average-minute-audience-panel.md) | Analysera den genomsnittliga minuten-publiken över tiden, med information om toppvyer och möjlighet att dela upp och jämföra. |
| [Panelen för samtidiga medieanvändare](media-concurrent-viewers.md) | Analysera samtidiga tittare över tid, med information om maximal samtidighet och möjlighet att dela upp och jämföra. |
| [Panelen Medieuppspelning - tidsfördröjning](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) | Analysera samtidiga tittare över tid, med information om maximal samtidighet och möjlighet att dela upp och jämföra. |
| [Segmentjämförelsepanel](c-segment-comparison/segment-comparison.md) | Jämför snabbt två segment över alla datapunkter för att automatiskt hitta relevanta skillnader. |

![](assets/panel-overview.png)

[!UICONTROL Quick Insights], [!UICONTROL Blank] och [!UICONTROL Freeform] paneler är bra att använda för att starta analysen, medan [!UICONTROL Analytics for Target], [!UICONTROL Attribution], [!UICONTROL Media Concurrent Viewers] och [!UICONTROL Segment Comparison] Utnyttja mer avancerade analyser. A `"+"` -knappen är tillgänglig i projekt så att du kan lägga till tomma paneler när som helst.

Standardstartpanelen är [!UICONTROL Freeform] men du kan göra [tom panel](/help/analyze/analysis-workspace/c-panels/blank-panel.md) även din standard.

## Rapportsvit {#report-suite}

Tabeller och visualiseringar i en panel hämtar data från [!UICONTROL report suite] i panelens övre högra hörn. Rapportsviten avgör också vilka komponenter som är tillgängliga i den vänstra listen. Inom ett projekt kan du använda ett eller [många rapportsviter](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) beroende på dina analysexempel. Om du vill använda en enda rapportserie för alla paneler i ett projekt, **högerklicka på panelhuvudet > Tillämpa rapportsviten på alla paneler**.

Listan med rapportsviter sorteras efter relevans, som Adobe definierar utifrån hur nyligen och ofta sviten har använts av den aktuella användaren och hur ofta sviten används i organisationen.

![](assets/panel-report-suite.png)

## Kalender {#calendar}

Panelkalendern styr rapporteringsintervallet för tabeller och visualiseringar inom en panel.

>[!NOTE]
>Om en (lila) datumintervallkomponent används i en tabell, visualisering eller panelsläppzon åsidosätts panelkalendern.

![](assets/panel-calendar.png)

Du kan använda ett datumintervall på minutnivå under de avancerade inställningarna i panelkalendern. Om du rapporterar i ett datumintervall som sträcker sig över många dagar, gäller starttiden den första dagen och sluttiden den sista dagen i intervallet.

## Släppzon {#dropzone}

Med panelens listzon kan du tillämpa segment- och listrutefilter på alla tabeller och visualiseringar i en panel. Du kan använda ett eller flera filter på en panel.

### Segmentfilter

Dra och släpp segment från den vänstra listen i panelens släppzon för att börja filtrera panelen. Upprepa den här processen om du vill lägga till fler filter på panelen. Filter visas sida vid sida högst upp på panelen.

![Filter](assets/segment-filter.png)

### Ad hoc-segmentfilter

Komponenter som inte är segmentkomponenter kan också dras direkt till släppzonen för att skapa ad hoc-segment, vilket sparar tid och arbete med att gå till segmentbyggaren. Segment som skapas på det här sättet definieras automatiskt som träffnivåsegment. Du kan ändra den här definitionen genom att klicka på informationsikonen (i) bredvid segmentet, sedan den pennformade redigeringsikonen och redigera den i segmentbyggaren.

Ad hoc-segment är en typ av snabbsegment och är lokala för projektet. De visas inte i den vänstra listen om du inte gör dem offentliga.

Mer information finns i [Snabbsegment](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

### Statiska rullgardinssegment

Med statiska rullgardinssegment kan du interagera med data på ett kontrollerat sätt. Du kan till exempel lägga till ett nedrullningsbart segment för mobila enhetstyper så att du kan segmentera panelen via Surfplatta, Mobiltelefon eller Skrivbord.

Statiska rullgardinssegment kan också användas för att konsolidera många projekt till ett. Om du till exempel har många versioner av samma projekt med olika landssegment tillämpade, kan du konsolidera alla versioner till ett enda projekt och lägga till ett nedrullningsbart landssegment.

![](assets/dropdown-filter-intro.png)

#### Skapa statiska rullgardinssegment

* För rullgardinsmenyer som använder dimensionsobjekt väljer du en dimension från den vänstra listen och släpper den i panelens listruta **samtidigt som du håller`[Shift]`**. Detta skapar ett nedrullningsbart segment med alla dimensionsobjekt som är kopplade till den dimensionen.

  Om du vill att listrutesegmentet endast ska innehålla specifika dimensionsobjekt som är kopplade till en dimension, klickar du på högerpilsikonen bredvid önskad dimension i den vänstra listen. Den här åtgärden visar alla tillgängliga dimensionsobjekt. Välj flera dimensionsobjekt från den här listan med `[Shift + Click]` eller `[Ctrl + Click]`och sedan släppa dem i panelens dropzone **samtidigt som du håller** `[Shift]`.

* För rullgardinsmenyer som använder en enda komponenttyp (t.ex. bara dimensioner, eller endast segment, eller endast mått), väljer du flera objekt av samma typ i den vänstra listen med `[Shift + Click]` eller `[Ctrl + Click]`och sedan släppa dem i panelens dropzone **samtidigt som du håller`[Shift]`**.

  Ett enskilt nedrullningsbart segment skapas med de komponenter som du har valt.

* För nedrullningsbara segment som använder en blandning av komponenttyper (till exempel 2 mätvärden och 3 filter) väljer du flera komponenter med `[Shift + Click]` eller `[Ctrl + Click]`. Släpp markeringen i panelens dropzone **samtidigt som du håller`[Shift]`**. I det här sammanhanget behandlas alla komponenttyper som separata nedrullningsbara segment. Om du till exempel inkluderar både mått och dimensionsobjekt i markeringen skapas två separata nedrullningsbara segment: ett nedrullningsbart segment innehåller dimensionsobjekt och det andra innehåller mått.

  ![Panelfönstret med segmentfältet Mobilkunder tillgängligt för att släppa ett statiskt nedrullningsbart segment. ](assets/create-dropdown.png)

Om du högerklickar på ett nedrullningsbart segment finns följande alternativ:

* **[!UICONTROL Delete drop-down]**: Tar bort det nedrullningsbara segmentet från panelen.
* **[!UICONTROL Delete label]**: Ta bort texten ovanför ett nedrullningsbart segment. Om du vill ändra etiketten väljer du pennikonen .
* **[!UICONTROL Add label]**: När du lägger till ett nedrullningsbart segment i ett projekt ställs en etikett automatiskt in på komponentnamnet. Om du tar bort etiketten kan du lägga till den igen med det här alternativet.
* **[!UICONTROL Require selection]**: Kräver att ett segment är inställt på panelen.

[Se videon](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html) om du vill veta mer om hur du lägger till nedrullningsbara filter i ett projekt.

#### Använda statiska rullgardinssegment

Använd den nedrullningsbara segmentmenyn på något av följande sätt för att filtrera panelen:

* Använd ett segment på panelen genom att välja segmentet på den nedrullningsbara menyn.

* Använd flera segment på panelen genom att markera flera segment i listrutan. Panelen filtreras så att den innehåller något av de markerade segmenten.

  Om du vill ta bort ett segment från listan markerar du det igen i listrutan.

  ![Markera flera segment](assets/dropdown-filter-multiselect.png)

### Dynamiska rullgardinsmenyer

Med dynamiska listrutesegment kan du fastställa tillgängliga värden baserat på data i panelens rapporteringsintervall och värden i andra nedrullningsbara segment. Du kan till exempel skapa två dynamiska listrutor med [Länder](/help/components/dimensions/countries.md) dimension och [Städer](/help/components/dimensions/cities.md) dimension. När du väljer ett land i dialogrutan [!UICONTROL Countries] nedrullningsbar lista [!UICONTROL Cities] listrutan justeras dynamiskt till att endast visa städer i det landet.

Samma koncept gäller för alla dimensioner. Endast dimensionsobjekt som visas inom panelens datumintervall och markerade segment visas. Dimension som är markerad i statiska rullgardinssegment påverkar tillgängliga värden i dynamiska rullgardinssegment. Inverteringen är emellertid inte true. De Dimensioner som markeras i dynamiska rullgardinssegment påverkar inte tillgängliga värden i statiska rullgardinssegment.

Manuellt urval av dimensionsobjekt är tillgängligt om du förväntar dig att en viss dimensionsobjekt ska samlas in i framtiden. Du kan även rensa ett dynamiskt nedrullningsbart segment så att det inte innehåller något värde, vilket innebär att andra dynamiska nedrullningsbara segment kan innehålla fler värden. Välj **[!UICONTROL Reset all]** om du vill ta bort markeringen från alla nedrullningsbara segment för den panelen.

Så här skapar du ett dynamiskt nedrullningsbart segment:

* Dra och släpp en dimension till panelens dropzone **samtidigt som du håller`[Shift]`**.
* Dynamiska rullgardinsmenyer är inte tillgängliga för mått, segment eller datumintervall.
* Högerklicka på ett nedrullningsbart segment och välj **[!UICONTROL Delete dropdown]** för att ta bort den.

Om du högerklickar på ett dynamiskt nedrullningsbart filter finns samma alternativ som för statiska nedrullningsbara filter.

## Högerklicka på menyn {#right-click}

Ytterligare funktioner för en panel är tillgängliga genom att högerklicka på panelhuvudet.

![Högerklicka på menyn](assets/right-click-menu.png)

Följande inställningar är tillgängliga:

| Inställning | Beskrivning |
| --- | --- |
| Infoga kopierad panel/visualisering | Gör att du kan klistra in (&quot;infoga&quot;) en kopierad panel eller visualisering på en annan plats i projektet, eller i ett annat projekt. |
| Kopiera panel | Högerklicka och kopiera en panel så att du kan infoga den på en annan plats i projektet eller i ett annat projekt. |
| Tillämpa Report Suite på alla paneler | Gör att du kan använda den aktiva panelrapportsviten på alla paneler i projektet. |
| Duplicera panel | Skapar en exakt kopia av den aktuella panelen, som du sedan kan ändra. |
| Komprimera/expandera alla paneler | Komprimerar och utökar alla projektpaneler. |
| Komprimera/utöka alla visualiseringar i panelen | Komprimerar och utökar alla visualiseringar i den aktuella panelen. |
| Redigera beskrivning | Lägg till (eller redigera) en textbeskrivning för panelen. |
| Hämta panellänk | Du kan dirigera någon till en viss panel i ett projekt. När användaren klickar på länken måste mottagaren logga in innan han eller hon dirigeras till just den panel som är länkad till. |
