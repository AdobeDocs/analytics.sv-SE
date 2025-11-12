---
description: Hantera Analytics-användare och deras resurser i Adobe Admin Console.
title: Hantera Analytics-användare och -resurser
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 0%

---

# Hantera äldre användarkonton, resurser och förfallodatum

Du kan hantera äldre användarkonton, deras migreringsstatus, förfallodata, överföring av resurser till andra användare och mycket mer med **[!UICONTROL Admin]> [!UICONTROL All Admin] >[!UICONTROL Analytics users & admin]**.

På skärmen Användare visas en lista över aktuella Adobe Analytics-användare, med följande kolumner:

| Kolumn | Beskrivning |
|---|---|
| [!UICONTROL User ID] | Det användar-ID som användaren använder för att logga in på Adobe Analytics. |
| [!UICONTROL Name] | Användarens namn. |
| [!UICONTROL Migration status] | Status för migreringen från ett äldre användarkonto till en Enterprise ID eller Adobe ID.  Status kan inte initieras, ställas i kö eller migreras. |
| [!UICONTROL Email] | Användarens e-postadress. |
| [!UICONTROL Legacy login] | Status för äldre inloggning, som kan aktiveras eller inaktiveras. |
| [!UICONTROL Date created] | Tidsstämpel när användarkontot skapades i Adobe Analytics. |
| [!UICONTROL Last Analytics access] | Tidsstämpel för senaste åtkomst av användarkontot till Adobe Analytics, |
| [!UICONTROL Expiration] | Utgångsdatum för användarkontot eller Ingen om användarkontot inte har förfallit. |

![Användare](assets/users.png)

- Om du vill söka efter en viss användare använder du fältet ![Sök](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) *Sök efter titel* .
- Om du vill filtrera listan över migreringsstatus väljer du ![Sparron](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Migration status]**.
- Om du vill filtrera listan över äldre inloggningsstatus väljer du ![Sparron](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Legacy login]**.
- Om du vill ändra visningen av kolumner väljer du ![Kolumninställningar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) och markerar kolumnerna i popup-fönstret.

Du kan använda olika åtgärder när du väljer en eller flera användare i listan:

| Åtgärd | Beskrivning |
|---|---|
| ![Migrera](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Briefcase_18_N.svg) **[!UICONTROL Migrate]** | Du kan migrera en eller flera användare till Enterprise ID eller Adobe ID. |
| ![Kalendern låst](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CalendarLocked_18_N.svg) **[!UICONTROL Set expiration]** | Du kan ange ett förfallodatum för användning av äldre Adobe Analytics-inloggning för de valda användarna.  Välj det datum som ska användas i en kalender-popup för att ange datumet. Välj **[!UICONTROL Done]** för att bekräfta förfallotiden. |
| ![Överför resurser](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Switch_18_N.svg) **[!UICONTROL Transfer assets]** | Den här åtgärden är bara tillgänglig när du väljer en användare. Om användaren har resurser som kan överföras kan du markera kontoobjekten (som bokmärken, instrumentpaneler med mera). Välj **[!UICONTROL Transfer]** för att slutföra överföringen.<br/>![Överför resurser](assets/transfer-assets.png) |
| ![Ta bort konton](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Delete accounts]** | En dialogruta visas där du kan bekräfta borttagningen av de markerade kontona. Välj **[!UICONTROL OK]** om du vill ta bort kontona. Välj **[!UICONTROL Cancel]** om du vill avbryta. |
| ![Exportera till CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL Export to CSV]** | Den här åtgärden hämtar omedelbart en fil som innehåller en kommaavgränsad värdelista med information om de valda användarna (namn, migreringsstatus, e-post med mera). |

