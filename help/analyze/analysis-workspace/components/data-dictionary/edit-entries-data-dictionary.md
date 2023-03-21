---
description: Med Data Dictionary i Analysis Workspace kan användare katalogisera och hålla reda på de olika komponenterna i Analysis Workspace, inklusive deras avsedda användning, som är godkända, som är dubbletter osv.
title: Redigera poster i Data Dictionary
feature: Components
role: Admin
source-git-commit: 7e105b4cd22187411dedd663080703e6daec91f5
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Redigera komponentposter i Data Dictionary

{{release-limited-testing}}

Analysadministratörer kan redigera komponentposter i Data Dictionary för en given Report Suite. Alla ändringar som görs är synliga för alla användare av Report Suite.

Så här redigerar du en komponent i Data Dictionary:

1. Gå till det Analysis Workspace-projekt som innehåller komponenten som du vill redigera.

1. Välj **Dataordlista** ikonen till vänster i Analysis Workspace. (Alternativa sätt att komma åt dataordlistan beskrivs i&quot;Åtkomst till dataordlistan&quot; i [Översikt över dataordlistan](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   Fönstret Data Dictionary visas.

   ![Administratörsvy för datamordlista](assets/data-dictionary-admin.png)

1. Kontrollera att rätt Report Suite är markerat i listrutan. Som standard visas den rapportsvit som du redan ingår i.

1. (Valfritt) I sökfältet börjar du skriva namnet på komponenten som du vill redigera.

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

1. Markera den komponent som du vill redigera i listan med komponenter.

1. Välj **Redigera** icon ![Ikon för redigering av dataordlista](assets/data-dictionary-edit-icon.png) bredvid komponentnamnet.

1. Redigera någon av följande information om komponenten:

   {{dd-component-information}}

1. Klicka på **Spara** icon ![Ikonen Spara i datamordlista](assets/data-dictionary-save-icon.png) för att spara ändringarna.
