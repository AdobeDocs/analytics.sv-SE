---
source-git-commit: df0d2c4687117fd00714ced56db6259e44698a20
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 1%

---
# Fragment

## Rapporter och analyser - meddelande om att produkten har upphört att gälla {#ra-eol}

>[!IMPORTANT]
>
>Läs mer om rapporter och analyser [Meddelande om att produkten är slut](https://express.adobe.com/page/6WnF8JK6IRDhf/).

## Filtervillkor för dataordlista {#dd-filter-criteria}

1. (Valfritt) Välj **Filter** icon ![Ikon för dataordlistefilter](/help/analyze/analysis-workspace/components/data-dictionary/assets/data-dictionary-filter-icon.png)väljer du sedan något av följande filteralternativ för att filtrera komponentlistan:

   | Alternativ |  -funktion |
   |---------|----------|
   | [!UICONTROL **Godkänd**] | Visa endast komponenter som har markerats som Godkänd av en administratör. |
   | [!UICONTROL **Favoriter**] | Visa endast komponenter som finns i din favoritlista. Mer information om hur du lägger till komponenter i din favoritlista finns i [Komponenter - översikt](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensioner**] | Visa endast komponenter som är Dimensioner. (Det här alternativet är också tillgängligt i [!UICONTROL **Snabbfilter**] -fliken när du först kommer åt datamordlistan.) |
   | [!UICONTROL **Mätvärden**] | Visa endast komponenter som är mätvärden. (Det här alternativet är också tillgängligt i [!UICONTROL **Snabbfilter**] -fliken när du först kommer åt datamordlistan.) |
   | [!UICONTROL **Segment**] | Visa endast komponenter som är segment. (Det här alternativet är också tillgängligt i [!UICONTROL **Snabbfilter**] -fliken när du först kommer åt datamordlistan.) <!--this is Filters in CJA--> |
   | [!UICONTROL **Datumintervall**] | Visa endast komponenter som är datumintervall. (Det här alternativet är också tillgängligt i [!UICONTROL **Snabbfilter**] -fliken när du först kommer åt datamordlistan.) |
   | [!UICONTROL **Visa alla**] | Visa alla komponenter. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Ej godkänt**] | Visa endast komponenter som ännu inte har markerats som Godkända av en administratör. Som administratör är detta användbart när du identifierar komponenter som kräver granskning och godkännande. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Beskrivning saknas**] | Visa endast komponenter som ännu inte har någon beskrivning i fältet Beskrivning. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Visa dubbletter**] | Visa endast komponenter som har samma etikett eller samma beskrivning som en annan komponent i den valda rapportsviten. Etiketter eller beskrivningar måste vara exakta matchningar för att kunna visas som dubbletter. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Inga senaste data**] | Visa endast komponenter som inte har samlat in några data under de senaste 90 dagarna. Det här alternativet är endast tillgängligt för administratörer. |
   | [!UICONTROL **Skapad av Adobe**] <!-- I don't see this option--> | Visa endast komponenter som har skapats av Adobe. Komponenter som har skapats av en administratör eller en annan användare i organisationen visas inte. |

   {style=&quot;table-layout:auto&quot;}

## Komponentinformation för dataordlista {#dd-component-information}

| Alternativ |  -funktion |
|---------|----------|
| [!UICONTROL **Godkänd**] | <p>Anger att komponenten har granskats och godkänts av administratören.</p><p>Administratörer ser ett alternativ för att [!UICONTROL **Ogodkänd**]. Om du väljer det här alternativet markeras komponenten som&quot;Inte godkänd&quot; för användarna.</p> |
| [!UICONTROL **Ej godkänt**] | <p>Anger att komponenten ännu inte har granskats och godkänts av administratören.</p><p>Administratörer ser ett alternativ för att [!UICONTROL **Godkänn**]. Om du väljer det här alternativet markeras komponenten som&quot;Godkänd&quot; för användare.</p> |
| [!UICONTROL **Beskrivning**] | Beskriver komponentens avsedda funktion. (Den här informationen läggs till av Analytics-administratören, enligt beskrivningen i [Lägga till komponentbeskrivningar](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
| [!UICONTROL **Används ofta tillsammans med**] | <p>Visar de komponenter som oftast används för den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknade mått, Dimension, Segment och Datumintervall.</p><p>Listan baseras på data från de senaste 90 dagarna. Endast de komponenter som du har åtkomst till visas. <!--Add info about how users with administrator access can control these after the feature is available. How?--></p> |
| [!UICONTROL **Liknar**] | <p>Visar komponenter med liknande etiketter som den komponent du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknade mått, Dimension, Segment och Datumintervall.</p><p>Endast de komponenter som du har åtkomst till visas.</p><p>Alla dubblettkomponenter i rapportsviten visas här. Analysadministratörer bör identifiera och ta bort alla dubblettkomponenter enligt beskrivningen i [Övervaka dataordlistans hälsa](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md). <!--Add info about how users with administrator access can control these after the feature is available. How?--></p> |
| [!UICONTROL **Taggar**] | Visar alla taggar som har tillämpats på komponenten. Användare med administratörsbehörighet kan lägga till taggar när komponenten redigeras. |
| [!UICONTROL **Komponenttyp**] | Visar vilken typ av komponent det är, oavsett om det är en Dimension, ett mått, ett segment eller ett datumintervall. |
| [!UICONTROL **Skapad av**] | Visar namnet på den användare som skapade komponenten. |
| [!UICONTROL **Förhandsgranska**] | Visar en förhandsgranskning av hur komponenten ser ut i Analysis Workspace. |
| [!UICONTROL **Senast ändrad**] | Visar den dag som komponenten senast ändrades. Det här avsnittet visas när du visar segment, beräknade värden och datumintervall. <!--for CJA, it is displayed for all components--> |

{style=&quot;table-layout:auto&quot;}

## Begränsad testning av versionsfas {#release-limited-testing}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i den här artikeln är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Analytics-processen finns i [Adobe Analytics funktionsreleaser](/help/release-notes/releases.md).

## Frisläppningsfas, begränsad testsektion {#release-limited-testing-section}

>[!AVAILABILITY]
>
>Funktionerna som beskrivs i det här avsnittet är i den begränsade testfasen av releasen och är kanske inte tillgängliga än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Analytics-processen finns i [Adobe Analytics funktionsreleaser](/help/release-notes/releases.md).

