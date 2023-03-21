---
description: Med Data Dictionary i Analysis Workspace kan användare katalogisera och hålla reda på de olika komponenterna i Analysis Workspace, inklusive deras avsedda användning, som är godkända, som är dubbletter osv.
title: Visa dataordlistan
feature: Components
role: User, Admin
source-git-commit: 5d83d2621ee5eee7dbbc2af3793a9e1d3de0f97b
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 0%

---

# Visa komponentinformation i Data Dictionary

{{release-limited-testing}}

Med Data Dictionary kan du visa information om en komponent, inklusive komponentbeskrivningen, liknande komponenter, andra komponenter som en komponent ofta används med, med mera.

Så här visar du information om en komponent i Data Dictionary:

1. Gå till det Analysis Workspace-projekt som innehåller komponenten som du vill visa.

1. Välj [!UICONTROL **Dataordlista**] ikonen till vänster i Analysis Workspace. (Alternativa sätt att komma åt dataordlistan beskrivs i&quot;Åtkomst till dataordlistan&quot; i [Översikt över dataordlistan](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   Fönstret Data Dictionary visas.

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Kontrollera att den rapportsvit som innehåller den komponent som du vill visa är markerad i listrutan. Som standard visas den rapportsvit som du redan ingår i.

1. (Valfritt) I sökfältet börjar du med att skriva namnet på komponenten som du vill visa.

   Ikoner visas bredvid komponentnamn för att ange komponenttyp:

   | Ikon | Betydelse |
   |---------|----------|
   | ![Dimension, ikon](assets/dimension-icon.png) | Anger en **dimension**. Dimensioner tillhandahålls av Adobe. Befintliga dimensioner kan inte ändras och nya dimensioner kan inte skapas. |
   | ![Mätningsikon](assets/default-metric-icon.png) | Anger en **standardmått** (inte beräknat). Standardvärden tillhandahålls av Adobe och kan inte ändras. |
   | ![Adobe, ikon](assets/default-calc-metric-icon.png) | Anger en **mall för beräknat mått** eller en **segmentmall**. Dessa komponenter tillhandahålls av Adobe och kan inte ändras. |
   | ![Beräkningsikon](assets/calculated-metric-icon-created.png) | Anger en **beräknat mått** som har skapats av en Analytics-administratör i din organisation. |
   | ![Segmentikon](assets/segment-icon.png) | Anger en **segment**. Dessa kan vara segment som tillhandahålls av Adobe eller skapas av en Analytics-administratör i din organisation. |
   | ![Ikon för datumintervall](assets/date-range-icon.png) | Anger en **datumintervall**. Det kan vara datumintervall som tillhandahålls av Adobe eller skapas av en Analytics-administratör i din organisation. |

{{dd-filter-criteria}}

1. Välj den komponent du vill visa i listan med komponenter.

   Följande information om komponenten visas:

   {{dd-component-information}}

1. (Valfritt) Dra en komponent från Data Dictionary till Analysis Workspace.