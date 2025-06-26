---
description: Med Data Dictionary i Analysis Workspace kan användare katalogisera och hålla reda på de olika komponenterna i Analysis Workspace, inklusive deras avsedda användning, som är godkänd, som är dubbletter osv.
title: Redigera poster i Data Dictionary
feature: Components
role: Admin
exl-id: 4f15cad2-596e-41c3-89aa-4456d8e94fa0
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '1102'
ht-degree: 0%

---

# Redigera komponentposter i Data Dictionary

Analysadministratörer kan redigera komponentposter i Data Dictionary för en given Report Suite. Alla ändringar som görs är synliga för alla användare av Report Suite.

Så här redigerar du en komponent i Data Dictionary:

1. Gå till det Analysis Workspace-projekt som innehåller komponenten som du vill redigera.

1. Markera ikonen **Dataordlista** i den vänstra listen i Analysis Workspace. (Alternativa sätt att komma åt dataordlistan beskrivs i [Åtkomst till dataordlistan](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md#access-the-data-dictionary).)

   Fönstret Data Dictionary visas.

   ![Administrationsvy för datamordlista](assets/data-dictionary-admin.png)

1. Kontrollera att rätt Report Suite är markerat i listrutan. Som standard visas den rapportsvit som du redan ingår i.

1. (Valfritt) I sökfältet börjar du skriva namnet på komponenten som du vill redigera.

   Komponenttypen kan identifieras med både färg och ikon. **Dimensioner** ![Dimension-ikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) är orange, **Segment** ![Segmentikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) är blå, **Datumintervall** ![Datumintervallikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) är lila och **Mätvärden** ![Mätningsikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) är gröna. Adobe-ikonen indikerar antingen en beräknad mätmall eller en segmentmall, och räkningsikonen ![Beräkningsikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indikerar ett beräknat mätresultat som har skapats av en Analysadministratör i din organisation.

1. (Valfritt) Markera ikonen **Filter** ![Datamordlistefilter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) och välj sedan något av följande filteralternativ för att filtrera komponentlistan:

   | Alternativ | Funktion |
   |---------|----------|
   | **[!UICONTROL Approved]** | Endast komponenter som har markerats som Godkända av en administratör. |
   | **[!UICONTROL Favorites]** | Endast komponenter som finns i din favoritlista. Mer information om hur du lägger till komponenter i din favoritlista finns i [Komponentöversikt](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | **[!UICONTROL Dimensions]** | Endast komponenter som är dimensioner. (Det här alternativet är också tillgängligt på fliken **[!UICONTROL Quick filters]** när du först öppnar datamappningslistan.) |
   | **[!UICONTROL Metrics]** | Endast komponenter som är mätvärden. (Det här alternativet är också tillgängligt på fliken **[!UICONTROL Quick filters]** när du först öppnar datamappningslistan.) |
   | **[!UICONTROL Segments]** | Endast komponenter som är segment. (Det här alternativet är också tillgängligt på fliken **[!UICONTROL Quick filters]** när du först öppnar datamappningslistan.) |
   | **[!UICONTROL Date ranges]** | Endast komponenter som är datumintervall. (Det här alternativet är också tillgängligt på fliken **[!UICONTROL Quick filters]** när du först öppnar datamappningslistan.) |
   | **[!UICONTROL Show all]** | Alla komponenter. Det här alternativet är endast tillgängligt för administratörer. |
   | **[!UICONTROL Unapproved]** | Endast komponenter som ännu inte har markerats som godkända av en administratör. Som administratör är detta användbart när du identifierar komponenter som kräver granskning och godkännande. Det här alternativet är endast tillgängligt för administratörer. |
   | **[!UICONTROL Missing Description]** | Endast komponenter som ännu inte har någon beskrivning i fältet Beskrivning. Det här alternativet är endast tillgängligt för administratörer. |
   | **[!UICONTROL Show duplicates]** | <p>Endast komponenter som har antingen samma namn eller samma definition som en annan komponent i den valda rapportsviten. Namn eller definitioner måste vara exakta matchningar för att kunna visas som dubbletter.</p><p>Det här alternativet är endast tillgängligt för administratörer.</p><p>**OBS!** För definitioner omfattar detta både komponenter som du skapar och de som tillhandahålls av Adobe. För namn innehåller detta för närvarande bara komponenter som du skapar och inte de som tillhandahålls av Adobe. Dubblettnamn för komponenter som tillhandahålls av Adobe kommer att läggas till i en framtida version.</p> |
   | **[!UICONTROL No recent data]** | Endast komponenter som inte har samlat in några data de senaste 90 dagarna. Det här alternativet är endast tillgängligt för administratörer. |
   | **[!UICONTROL Created by Adobe]** <!-- I don't see this option--> | Visa endast komponenter som har skapats av Adobe.  Exempel: Adobe Target. Komponenter som har skapats av en administratör eller en annan användare i organisationen visas inte. |

   {style="table-layout:auto"}

1. (Valfritt) Välj ikonen **Sortera** ![Sortera komponenter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) och välj sedan något av följande filteralternativ för att sortera komponentlistan:

   | Alternativ | Funktion |
   |---------|----------|
   | [!UICONTROL **Rekommenderas**] | Sorterar komponenter med de som rekommenderas högst upp i listan. Komponenter som du eller andra i organisationen använder oftast och senast visas högst upp i listan. |
   | [!UICONTROL **Alfabetiskt**] | Sorterar komponenterna i bokstavsordning. |
   | [!UICONTROL **Kategorisisk**] | Sorterar komponenter efter komponenttyp (dimension, mått, segment, datumintervall). |

   {style="table-layout:auto"}

1. Markera den komponent som du vill redigera i listan med komponenter.

1. Välj ikonen **Redigera** ![Redigera datamordlista](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) bredvid komponentnamnet.

1. Redigera någon av följande information om komponenten:

   | Alternativ | Funktion |
   |---------|----------|
   | **[!UICONTROL Approved]** | <p>Anger att komponenten har granskats och godkänts av administratören.</p><p>När en komponent har godkänts kan administratörer ta bort godkännandet genom att klicka på knappen **Godkänd** .</p> |
   | **[!UICONTROL Approval needed]** | <p>Anger att komponenten ännu inte har granskats och godkänts av administratören.</p><p>Administratörer ser ett alternativ för **[!UICONTROL Approve]**. Om du väljer det här alternativet markeras komponenten som&quot;Godkänd&quot; för användare.</p> |
   | **[!UICONTROL Description]** | Beskriver komponentens avsedda funktion. (Den här informationen läggs till av Analytics-administratören, enligt beskrivningen i [Lägg till komponentbeskrivningar](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
   | **[!UICONTROL Frequently used with]** | <p>Visar komponenter som används oftast med den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknat mätvärde, Dimension, Segment och Datumintervall.</p><p>Listan baseras på data från de senaste 90 dagarna. Endast de komponenter som du har åtkomst till visas.</p><p>Administratörer kan strukturera de komponenter som användarna ser i det här avsnittet genom att välja önskade komponenter i listrutorna **[!UICONTROL Always Include]** och **[!UICONTROL Always Exclude]**. Innan du strukturerar de komponenter som användarna ser ska du först tillämpa filtret **Visa alla** för att vara säker på att du ser komponenter som inte delas med dig.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
   | **[!UICONTROL Similar to]** | <p>Visar komponenter med liknande namn som den komponent som du visar.</p><p>Upp till 5 komponenter visas för de 5 primära komponenttyperna: Mått, Beräknat mätvärde, Dimension, Segment och Datumintervall.</p><p>Endast de komponenter som du har åtkomst till visas.</p><p>Alla dubblettkomponenter i rapportsviten visas också här. Analysadministratörer bör identifiera och ta bort alla dubblettkomponenter, vilket beskrivs i [Övervaka dataordlistehälsa](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Administratörer kan strukturera de komponenter som användarna ser i det här avsnittet genom att välja önskade komponenter i listrutorna **[!UICONTROL Always Include]** och **[!UICONTROL Always Exclude]**. Innan du strukturerar de komponenter som användarna ser ska du först tillämpa filtret **Visa alla** för att vara säker på att du ser komponenter som inte delas med dig.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**OBS!** För närvarande innehåller avsnittet **Liknande** bara komponenter som du skapar och inte komponenter från Adobe. Komponenter som tillhandahålls av Adobe kommer att läggas till i en framtida version.</p> |
   | **[!UICONTROL Tags]** | Visar alla taggar som har tillämpats på komponenten. Användare med administratörsbehörighet kan lägga till taggar när komponenten redigeras. |
   | **[!UICONTROL Component type]** | Visar vilken typ av komponent det är, oavsett om det är en Dimension, ett mått, ett segment eller ett datumintervall. |
   | **[!UICONTROL Created by]** | Visar namnet på den användare som skapade komponenten. |
   | **[!UICONTROL Preview]** | Visar en förhandsgranskning av hur komponenten ser ut i Analysis Workspace. |
   | **[!UICONTROL Date last modified]** | Visar den dag som komponenten senast ändrades. Det här avsnittet visas när du visar segment, beräknade värden och datumintervall. |

   {style="table-layout:auto"}

1. Klicka på ikonen **Spara** ![Spara i datamordlista](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) för att spara ändringarna.
