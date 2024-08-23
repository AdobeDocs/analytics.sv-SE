---
source-git-commit: cc0b8703d6b6488adf9a2ea41a51001538d1cbee
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 0%

---
# Fragment

## Rapporter och analyser - meddelande om att produkten har upphört att gälla {#ra-eol}

>[!IMPORTANT]
>
>Från och med den **17 januari 2024** har Adobe avbrutit rapporter och analyser och tillhörande rapporter och funktioner. Vid den tidpunkten slutade rapporter och analyser och alla rapporter och tidsplaner att fungera. Rapporterna, visualiseringarna och den underliggande tekniken som används i Rapporter och analyser uppfyller inte längre Adobe teknikstandarder. De flesta funktionerna Rapporter och Analytics är tillgängliga i Analysis Workspace. Mer information om hur du använder rapporter i Analysis Workspace finns i [Använda färdigbyggda rapporter](/help/analyze/analysis-workspace/reports/use-reports.md).
> 
>Sedan Analysis Workspace lanserades 2015 har funktionerna och funktionerna i Rapporter och analyser flyttats till Analysis Workspace och en tröskel på arbetsflödets paritet har uppnåtts. Det här meddelandet förklarar processen vid slutet av livscykeln.
>
>Läs mer om rapporterna och analysen [Slutet av livscykelmeddelandet](https://www.adobe.com/go/analytics_rnaeol_en).

## Filtervillkor för dataordlista {#dd-filter-criteria}

1. (Valfritt) Markera ikonen **Filter** ![Datamordlistefilter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) och välj sedan något av följande filteralternativ för att filtrera komponentlistan:

| Alternativ | Funktion |
|---------|----------|
| [!UICONTROL **Godkänd**] | Visa endast komponenter som har markerats som Godkänd av en administratör. |
| [!UICONTROL **Favoriter**] | Visa endast komponenter som finns i din favoritlista. Mer information om hur du lägger till komponenter i din favoritlista finns i [Komponentöversikt](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
| [!UICONTROL **Dimensioner**] | Visa endast komponenter som är Dimensioner. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbfilter**] när du först öppnar datamappningslistan.) |
| [!UICONTROL **Mätvärden**] | Visa endast komponenter som är mätvärden. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbfilter**] när du först öppnar datamappningslistan.) |
| [!UICONTROL **Segment**] | Visa endast komponenter som är segment. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbfilter**] när du först öppnar datamappningslistan.) <!--this is Filters in Customer Journey Analytics--> |
| [!UICONTROL **Datumintervall**] | Visa endast komponenter som är datumintervall. (Det här alternativet är också tillgängligt på fliken [!UICONTROL **Snabbfilter**] när du först öppnar datamappningslistan.) |
| [!UICONTROL **Visa alla**] | Visa alla komponenter. Det här alternativet är endast tillgängligt för administratörer. |
| [!UICONTROL **Ej godkänt**] | Visa endast komponenter som ännu inte har markerats som Godkända av en administratör. Som administratör är detta användbart när du identifierar komponenter som kräver granskning och godkännande. Det här alternativet är endast tillgängligt för administratörer. |
| [!UICONTROL **Beskrivning saknas**] | Visa endast komponenter som ännu inte har någon beskrivning i fältet Beskrivning. Det här alternativet är endast tillgängligt för administratörer. |
| [!UICONTROL **Visa dubbletter**] | <p>Visa bara komponenter som har samma namn eller definition som en annan komponent i den valda rapportsviten. Namn eller definitioner måste vara exakta matchningar för att kunna visas som dubbletter.</p><p>Det här alternativet är endast tillgängligt för administratörer.</p><p>**Obs!** För definitioner omfattar detta både komponenter som du skapar och de som tillhandahålls av Adobe. För namn innehåller detta för närvarande bara komponenter som du skapar och inte de som tillhandahålls av Adobe. Dubblettnamn för komponenter som tillhandahålls av Adobe läggs till i en framtida version.</p> |
| [!UICONTROL **Inga senaste data**] | Visa endast komponenter som inte har samlat in några data under de senaste 90 dagarna. Det här alternativet är endast tillgängligt för administratörer. |
| [!UICONTROL **Skapad av Adobe**] <!-- I don't see this option--> | Visa endast komponenter som har skapats av Adobe. Komponenter som har skapats av en administratör eller en annan användare i organisationen visas inte. |

{style="table-layout:auto"}

## Komponentinformation för dataordlista {#dd-component-information}

| Alternativ | Funktion |
|---------|----------|
| [!UICONTROL **Godkänd**] | <p>Anger att komponenten har granskats och godkänts av administratören.</p><p>När en komponent har godkänts kan administratörer ta bort godkännandet genom att klicka på knappen **Godkänd** .</p> |
| [!UICONTROL **Godkännande krävs**] | <p>Anger att komponenten ännu inte har granskats och godkänts av administratören.</p><p>Administratörer ser ett alternativ för att [!UICONTROL **godkänna**]. Om du väljer det här alternativet markeras komponenten som&quot;Godkänd&quot; för användare.</p> |
| [!UICONTROL **Beskrivning**] | Beskriver komponentens avsedda funktion. (Den här informationen läggs till av Analytics-administratören, enligt beskrivningen i [Lägg till komponentbeskrivningar](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
| [!UICONTROL **Används ofta med**] | <p>Visar komponenter som används oftast med den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknat mätvärde, Dimension, Segment och Datumintervall.</p><p>Listan baseras på data från de senaste 90 dagarna. Endast de komponenter som du har åtkomst till visas.</p><p>Administratörer kan strukturera de komponenter som användarna ser i det här avsnittet genom att välja önskade komponenter i listrutorna [!UICONTROL **Inkludera alltid**] och [!UICONTROL **Uteslut alltid**]. Innan du strukturerar de komponenter som användarna ser ska du först tillämpa filtret **Visa alla** för att vara säker på att du ser komponenter som inte delas med dig.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Liknar**] | <p>Visar komponenter med liknande namn som den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknat mätvärde, Dimension, Segment och Datumintervall.</p><p>Endast de komponenter som du har åtkomst till visas.</p><p>Alla dubblettkomponenter i rapportsviten visas också här. Analysadministratörer bör identifiera och ta bort alla dubblettkomponenter, vilket beskrivs i [Övervaka dataordlistehälsa](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Administratörer kan strukturera de komponenter som användarna ser i det här avsnittet genom att välja önskade komponenter i listrutorna [!UICONTROL **Inkludera alltid**] och [!UICONTROL **Uteslut alltid**]. Innan du strukturerar de komponenter som användarna ser ska du först tillämpa filtret **Visa alla** för att vara säker på att du ser komponenter som inte delas med dig.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**OBS!** För närvarande innehåller avsnittet **Liknande** bara komponenter som du skapar och inte de som tillhandahålls av Adobe. Komponenter som tillhandahålls av Adobe kommer att läggas till i en framtida version.</p> |
| [!UICONTROL **Taggar**] | Visar alla taggar som har tillämpats på komponenten. Användare med administratörsbehörighet kan lägga till taggar när komponenten redigeras. |
| [!UICONTROL **Komponenttyp**] | Visar vilken typ av komponent det är, oavsett om det är en Dimension, ett mått, ett segment eller ett datumintervall. |
| [!UICONTROL **Skapad av**] | Visar namnet på den användare som skapade komponenten. |
| [!UICONTROL **Förhandsgranska**] | Visar en förhandsgranskning av hur komponenten ser ut i Analysis Workspace. |
| [!UICONTROL **Senast ändrad**] | Visar den dag som komponenten senast ändrades. Det här avsnittet visas när du visar segment, beräknade värden och datumintervall. |

{style="table-layout:auto"}

## Alternativ för komponentsortering {#components-sort-options}

| Alternativ | Funktion |
|---------|----------|
| [!UICONTROL **Rekommenderas**] | Sorterar komponenter med de som rekommenderas högst upp i listan. Komponenter som du eller andra i organisationen använder oftast och senast visas högst upp i listan. |
| [!UICONTROL **Alfabetiskt**] | Sorterar komponenterna i bokstavsordning. |
| [!UICONTROL **Kategorisisk**] | Sorterar komponenter efter komponenttyp (dimension, mått, segment, datumintervall). |

{style="table-layout:auto"}

## Begränsad testning av versionsfas {#release-limited-testing}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i den här artikeln är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Analytics-releaser finns i [Adobe Analytics-funktionsreleaser](/help/release-notes/releases.md).

## Frisläppningsfas, begränsad testsektion {#release-limited-testing-section}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i det här avsnittet är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Analytics-releaser finns i [Adobe Analytics-funktionsreleaser](/help/release-notes/releases.md).


## Ansvarsfriskrivning för plugin-program {#plug-in}

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du din organisations Adobe Account Team. De kan ordna ett möte med en konsult för att få hjälp.


## Endast tillgängligt för befintliga kunder {#available-existing-customers}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i det här avsnittet är bara tillgängliga för befintliga kunder som redan har en licens för funktionen. Funktionen erbjuds inte längre som ett tillägg till befintliga eller nya kunder.
>
