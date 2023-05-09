---
description: Med Data Dictionary i Analysis Workspace kan användare katalogisera och hålla reda på de olika komponenterna i Analysis Workspace, inklusive deras avsedda användning, som är godkända, som är dubbletter osv.
title: Visa dataordlistan
feature: Components
role: User, Admin
exl-id: 68f68ea4-f0a6-4937-bf8f-aecfa28572bb
source-git-commit: 02b3dca057731dc56f3ee72e3ce33e30b2cb2a28
workflow-type: tm+mt
source-wordcount: '302'
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

   Komponenttypen kan identifieras med både färg och ikon. **Dimensioner** ![Dimension, ikon](assets/dimension-icon.png) är orange, **Segment** ![Segmentikon](assets/segment-icon.png) är blå, **Datumintervall** ![Ikon för datumintervall](assets/date-range-icon.png) är lila, och **Mått** ![Mätningsikon](assets/default-metric-icon.png) är gröna. Ikonen Adobe ![Adobe, ikon](assets/default-calc-metric-icon.png) anger antingen en mall för beräknade mätvärden eller en segmentmall och räknikonen ![Beräkningsikon](assets/calculated-metric-icon-created.png) har angett ett beräknat mått som har skapats av en Analytics-administratör i organisationen.

{{dd-filter-criteria}}

1. (Valfritt) Välj **Sortera** icon ![Ikon för att sortera komponenter](assets/component-sort-icon.png)väljer du sedan något av följande filteralternativ för att sortera komponentlistan:

   {{components-sort-options}}

1. Välj den komponent du vill visa i listan med komponenter.

   Följande information om komponenten visas:

   {{dd-component-information}}

1. (Valfritt) Dra en komponent från Data Dictionary till Analysis Workspace.
