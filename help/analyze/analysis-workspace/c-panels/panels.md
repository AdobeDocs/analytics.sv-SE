---
description: En panel är en samling tabeller och visualiseringar
title: Översikt över paneler
feature: Panels
role: User, Admin
exl-id: dd1a3c40-8b5b-47dd-86d9-da766575ee46
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '1404'
ht-degree: 1%

---

# Översikt över paneler

A [!UICONTROL panel] är en samling tabeller och visualiseringar. Du kommer åt panelerna från den övre vänstra ikonen i Workspace eller en [tom panel](blank-panel.md). Paneler är användbara när du vill ordna dina projekt efter tidsperioder, rapportsviter eller användningsfall för analyser.

## Paneltyper

Följande paneltyper är tillgängliga i Analysis Workspace:

| Panelnamn | Beskrivning |
| --- | --- |
| [Tom panel](blank-panel.md) | Välj bland tillgängliga paneler och visualiseringar för att starta analysen. |
| [Panelen Snabbinsikter](quickinsight.md) | Bygg snabbt ett frihandsbord och en medföljande visualisering för att analysera och hitta insikter snabbare. |
| [Analyser för målpanelen](a4t-panel.md) | Analysera Target-aktiviteter och -upplevelser i Analysis Workspace. |
| [Panelen Attribution](attribution.md) | Jämför och visualisera snabbt valfritt antal attribueringsmodeller med alla mått och konverteringsvärden. |
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

Med panelens listzon kan du tillämpa segment- och listrutefilter på alla tabeller och visualiseringar i en panel. Du kan använda ett eller flera filter på en panel. Titeln ovanför varje filter kan ändras genom att du klickar på redigeringspennan eller så kan du högerklicka för att ta bort den helt.

### Segmentfilter

Dra och släpp ett segment från den vänstra listen i panelens släppzon för att börja filtrera panelen.

![Filter](/help/admin/admin/assets/filter.png)

### Ad hoc-segmentfilter

Komponenter som inte är segmentkomponenter kan också dras direkt till släppzonen för att skapa ad hoc-segment, vilket sparar tid och arbete med att gå till segmentbyggaren. Segment som skapas på det här sättet definieras automatiskt som träffnivåsegment. Du kan ändra den här definitionen genom att klicka på informationsikonen (i) bredvid segmentet, sedan den pennformade redigeringsikonen och redigera den i segmentbyggaren.

Ad hoc-segment är en typ av snabbsegment och är lokala för projektet. De visas inte i den vänstra listen om du inte gör dem offentliga.

Mer information finns i [Snabbsegment](/help/analyze/analysis-workspace/components/segments/quick-segments.md).

### Statiska nedrullningsbara filter

Med nedrullningsbara filter kan du interagera med data på ett kontrollerat sätt. Du kan t.ex. lägga till ett nedrullningsbart filter för mobila enhetstyper så att du kan segmentera panelen via Surfplatta, Mobiltelefon eller Skrivbord.

Nedrullningsbara filter kan även användas för att konsolidera flera projekt till ett. Om du till exempel har många versioner av samma projekt med olika landssegment tillämpade, kan du konsolidera alla versioner till ett enda projekt och lägga till ett nedrullningsbart landsfilter.

![](assets/dropdown-filter-intro.png)

Så här skapar du ett statiskt nedrullningsbart filter:

* För nedrullningsbara filter som använder dimensionsobjekt klickar du på högerpilsikonen bredvid önskad dimension i den vänstra listen. Den här åtgärden visar alla tillgängliga dimensionsobjekt. Välj flera dimensionsobjekt från den här listan med `[Shift + Click]` eller `[Ctrl + Click]`och sedan släppa dem i panelens dropzone **samtidigt som du håller`[Shift]`**.
* För nedrullningsbara filter som använder andra komponenter som mått, segment eller datumintervall väljer du flera komponenter med `[Shift + Click]` eller `[Ctrl + Click]`. Släpp markeringen i panelens dropzone **samtidigt som du håller`[Shift]`**. Alla komponenttyper behandlas som segment i det här sammanhanget.
* Ett enda nedrullningsbart filter kan bara innehålla en enda komponenttyp. Om du inkluderar flera komponenttyper i markeringen skapas ett separat nedrullningsbart filter per komponenttyp. Om du till exempel inkluderar både mått och dimensionsobjekt i markeringen skapas två separata nedrullningsbara filter. Ett nedrullningsbart filter innehåller dimensionsobjekt och det andra innehåller mått.

Välj ett av alternativen i listrutan om du vill ändra data på panelen. Du kan också välja att inte filtrera paneldata genom att markera **[!UICONTROL No filter]**.

![](assets/create-dropdown.png)

Om du högerklickar på ett nedrullningsbart filter finns följande alternativ:

* **[!UICONTROL Add label]**: När du lägger till ett nedrullningsbart filter i ett projekt ställs en etikett automatiskt in på komponentnamnet. Om du tar bort etiketten kan du lägga till den igen med det här alternativet.
* **[!UICONTROL Delete label]**: Ta bort texten ovanför ett nedrullningsbart filter.
* **[!UICONTROL Delete drop-down filter]**: Tar bort det nedrullningsbara filtret från panelen.

[Se videon](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html) om du vill veta mer om hur du lägger till nedrullningsbara filter i ett projekt.

### Dynamiska nedrullningsbara filter

Med dynamiska nedrullningsbara filter kan du bestämma tillgängliga värden baserat på data i panelens rapporteringsintervall och värden i andra nedrullningsbara filter. Du kan till exempel skapa två dynamiska listrutor med [Länder](/help/components/dimensions/countries.md) dimension och [Städer](/help/components/dimensions/cities.md) dimension. När du väljer ett land i dialogrutan [!UICONTROL Countries] nedrullningsbar lista [!UICONTROL Cities] listrutan justeras dynamiskt till att endast visa städer i det landet.

Samma koncept gäller för alla dimensioner. Endast dimensionsobjekt som visas inom panelens datumintervall och markerade filter visas. De Dimensioner som markeras i statiska nedrullningsbara filter påverkar tillgängliga värden i dynamiska nedrullningsbara filter. Inverteringen är emellertid inte true. De Dimensioner som markeras i dynamiska listrutefilter påverkar inte tillgängliga värden i statiska listrutefilter.

Manuellt urval av dimensionsobjekt är tillgängligt om du förväntar dig att en viss dimensionsobjekt ska samlas in i framtiden. Du kan även rensa ett dynamiskt nedrullningsbart filter så att det inte innehåller något värde, vilket innebär att andra dynamiska nedrullningsbara filter kan innehålla fler värden. Välj **[!UICONTROL Reset all]** för att ta bort markeringen från alla nedrullningsbara filter för den panelen.

Så här skapar du ett dynamiskt nedrullningsbart filter:

* Dra och släpp en dimension till panelens dropzone **samtidigt som du håller`[Shift]`**.
* Dynamiska nedrullningsbara filter är inte tillgängliga för mått, segment eller datumintervall.
* Högerklicka på ett nedrullningsbart filter och välj **[!UICONTROL Delete filter]** för att ta bort den.

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
