---
description: Med Data Dictionary i Analysis Workspace kan användare katalogisera och hålla reda på de olika komponenterna i Analysis Workspace, inklusive deras avsedda användning, som är godkända, som är dubbletter osv.
title: Visa dataordlistan
feature: Components
role: User, Admin
exl-id: 68f68ea4-f0a6-4937-bf8f-aecfa28572bb
source-git-commit: a6805f0944570bee265d5db9a159ae24e0694837
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Visa komponentinformation i Data Dictionary

Med Data Dictionary kan du visa information om en komponent, inklusive komponentbeskrivningen, liknande komponenter, andra komponenter som en komponent ofta används med, med mera.

Så här visar du information om en komponent i Data Dictionary:

1. Gå till det Analysis Workspace-projekt som innehåller komponenten som du vill visa.

1. Välj [!UICONTROL **Dataordlista**] ikonen till vänster i Analysis Workspace. (Alternativa sätt att komma åt dataordlistan beskrivs i&quot;Åtkomst till dataordlistan&quot; i [Översikt över dataordlistan](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   Fönstret Data Dictionary visas.

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Kontrollera att den rapportsvit som innehåller den komponent som du vill visa är markerad i listrutan. Som standard visas den rapportsvit som du redan ingår i.

1. (Valfritt) I sökfältet börjar du med att skriva namnet på komponenten som du vill visa.

   Komponenttypen kan identifieras med både färg och ikon. **Dimensioner** ![Dimension, ikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) är orange, **Segment** ![Segmentikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) är blå, **Datumintervall** ![Ikon för datumintervall](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) är lila, och **Mått** ![Mätningsikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) är gröna. Ikonen Adobe anger antingen en mall för beräknade mätvärden eller en segmentmall och räknesymbolen ![Beräkningsikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) har angett ett beräknat mått som har skapats av en Analytics-administratör i organisationen.

{{dd-filter-criteria}}

1. (Valfritt) Välj **Sortera** icon ![Ikon för att sortera komponenter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)väljer du sedan något av följande filteralternativ för att sortera komponentlistan:

   {{components-sort-options}}

1. Välj den komponent du vill visa i listan med komponenter.

   Följande information om komponenten visas:

   {{dd-component-information}}

1. (Valfritt) Dra en komponent från Data Dictionary till Analysis Workspace.
