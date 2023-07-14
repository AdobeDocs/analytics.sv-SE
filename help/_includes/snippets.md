---
source-git-commit: 57b439dac433c4d99d4f2029760f324f8404a920
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 1%

---
# Fragment

## Rapporter och analyser - meddelande om att produkten har upphört att gälla {#ra-eol}

>[!IMPORTANT]
>
>Läs mer om rapporter och analyser [Meddelande om att produkten är slut](https://www.adobe.com/go/analytics_rnaeol_en).

## Filtervillkor för dataordlista {#dd-filter-criteria}

1. (Valfritt) Välj **Filter** icon ![Ikon för dataordlistefilter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)väljer du sedan något av följande filteralternativ för att filtrera komponentlistan:

   | Alternativ |  -funktion |
   |---------|----------|
   | [!UICONTROL **Godkänd**] | Visa endast komponenter som har markerats som Godkänd av en administratör. |
   | [!UICONTROL **Favoriter**] | Visa endast komponenter som finns i din favoritlista. Mer information om hur du lägger till komponenter i din favoritlista finns i [Komponenter - översikt](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensioner**] | Visa endast komponenter som är Dimensioner. (Det här alternativet är också tillgängligt i [!UICONTROL **Snabbfilter**] -fliken när du först kommer åt datamordlistan.) |
   | [!UICONTROL **Mätvärden**] | Visa endast komponenter som är mätvärden. (Det här alternativet är också tillgängligt i [!UICONTROL **Snabbfilter**] -fliken när du först kommer åt datamordlistan.) |
   | [!UICONTROL **Segment**] | Visa endast komponenter som är segment. (Det här alternativet är också tillgängligt i [!UICONTROL **Snabbfilter**] -fliken när du först kommer åt datamordlistan.) <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Datumintervall**] | Visa endast komponenter som är datumintervall. (Det här alternativet är också tillgängligt i [!UICONTROL **Snabbfilter**] -fliken när du först kommer åt datamordlistan.) |
   | [!UICONTROL **Visa alla**] | Visa alla komponenter. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Ej godkänt**] | Visa endast komponenter som ännu inte har markerats som Godkända av en administratör. Som administratör är detta användbart när du identifierar komponenter som kräver granskning och godkännande. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Beskrivning saknas**] | Visa endast komponenter som ännu inte har någon beskrivning i fältet Beskrivning. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Visa dubbletter**] | <p>Visa endast komponenter som har samma namn eller definition som en annan komponent i den valda rapportsviten. Namn eller definitioner måste vara exakta matchningar för att kunna visas som dubbletter.</p><p>Det här alternativet är endast tillgängligt för administratörer.</p><p>**OBS!** För definitioner omfattar detta både de komponenter du skapar och de som tillhandahålls av Adobe. För namn innehåller detta för närvarande bara komponenter som du skapar och inte de som tillhandahålls av Adobe. Dubblettnamn för komponenter som tillhandahålls av Adobe läggs till i en framtida version.</p> |
   | [!UICONTROL **Inga senaste data**] | Visa endast komponenter som inte har samlat in några data under de senaste 90 dagarna. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Skapad av Adobe**] <!-- I don't see this option--> | Visa endast komponenter som har skapats av Adobe. Komponenter som har skapats av en administratör eller en annan användare i organisationen visas inte. |

   {style="table-layout:auto"}

## Komponentinformation för dataordlista {#dd-component-information}

| Alternativ |  -funktion |
|---------|----------|
| [!UICONTROL **Godkänd**] | <p>Anger att komponenten har granskats och godkänts av administratören.</p><p>När en komponent har godkänts kan administratören ta bort godkännandet genom att välja **Godkänd** -knappen.</p> |
| [!UICONTROL **Godkännande krävs**] | <p>Anger att komponenten ännu inte har granskats och godkänts av administratören.</p><p>Administratörer ser ett alternativ för att [!UICONTROL **Godkänn**]. Om du väljer det här alternativet markeras komponenten som&quot;Godkänd&quot; för användare.</p> |
| [!UICONTROL **Beskrivning**] | Beskriver komponentens avsedda funktion. (Den här informationen läggs till av Analytics-administratören, enligt beskrivningen i [Lägga till komponentbeskrivningar](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
| [!UICONTROL **Används ofta tillsammans med**] | <p>Visar de komponenter som oftast används för den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknade mått, Dimension, Segment och Datumintervall.</p><p>Listan baseras på data från de senaste 90 dagarna. Endast de komponenter som du har åtkomst till visas.</p><p>Administratörer kan strukturera de komponenter som användarna ser i det här avsnittet genom att välja önskade komponenter i [!UICONTROL **Inkludera alltid**] och [!UICONTROL **Uteslut alltid**] nedrullningsbara fält. Innan du strukturerar de komponenter som användarna ser ska du först använda **Visa alla** filtrera så att du ser alla komponenter som inte delas med dig.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Liknar**] | <p>Visar komponenter med liknande namn som den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknade mått, Dimension, Segment och Datumintervall.</p><p>Endast de komponenter som du har åtkomst till visas.</p><p>Alla dubblettkomponenter i rapportsviten visas också här. Analysadministratörer bör identifiera och ta bort alla dubblettkomponenter enligt beskrivningen i [Övervaka dataordlistans hälsa](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Administratörer kan strukturera de komponenter som användarna ser i det här avsnittet genom att välja önskade komponenter i [!UICONTROL **Inkludera alltid**] och [!UICONTROL **Uteslut alltid**] nedrullningsbara fält. Innan du strukturerar de komponenter som användarna ser ska du först använda **Visa alla** filtrera så att du ser alla komponenter som inte delas med dig.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**OBS!** För närvarande är **Liknar** -avsnittet innehåller bara komponenter som du skapar och inte de som tillhandahålls av Adobe. Komponenter som tillhandahålls av Adobe kommer att läggas till i en framtida version.</p> |
| [!UICONTROL **Taggar**] | Visar alla taggar som har tillämpats på komponenten. Användare med administratörsbehörighet kan lägga till taggar när komponenten redigeras. |
| [!UICONTROL **Komponenttyp**] | Visar vilken typ av komponent det är, oavsett om det är en Dimension, ett mått, ett segment eller ett datumintervall. |
| [!UICONTROL **Skapad av**] | Visar namnet på den användare som skapade komponenten. |
| [!UICONTROL **Förhandsgranska**] | Visar en förhandsgranskning av hur komponenten ser ut i Analysis Workspace. |
| [!UICONTROL **Senast ändrad**] | Visar den dag som komponenten senast ändrades. Det här avsnittet visas när du visar segment, beräknade värden och datumintervall. |

{style="table-layout:auto"}

## Alternativ för komponentsortering {#components-sort-options}

| Alternativ |  -funktion |
|---------|----------|
| [!UICONTROL **Rekommenderas**] | Sorterar komponenter med de som rekommenderas högst upp i listan. Komponenter som du eller andra i organisationen använder oftast och senast visas högst upp i listan. |
| [!UICONTROL **Alfabetiskt**] | Sorterar komponenterna i bokstavsordning. |
| [!UICONTROL **Kategorisisk**] | Sorterar komponenter efter komponenttyp (dimension, mått, segment, datumintervall). |

{style="table-layout:auto"}

## Begränsad testning av versionsfas {#release-limited-testing}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i den här artikeln är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Analytics-processen finns i [Adobe Analytics funktionsreleaser](/help/release-notes/releases.md).

## Frisläppningsfas, begränsad testsektion {#release-limited-testing-section}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i det här avsnittet är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Analytics-processen finns i [Adobe Analytics funktionsreleaser](/help/release-notes/releases.md).


## Ansvarsfriskrivning för plugin-program {#plug-in}

>[!IMPORTANT]
>
>Denna plugin tillhandahålls av Adobe Consulting som en tjänst som hjälper dig att få ut mer av Adobe Analytics. Adobe kundtjänst ger inte support för denna plugin, inklusive installation och felsökning. Om du behöver hjälp med det här plugin-programmet kontaktar du din organisations Adobe Account Team. De kan ordna ett möte med en konsult för att få hjälp.

