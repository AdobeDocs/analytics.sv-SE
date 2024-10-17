---
description: Alla rapporter med bokmärken och kontrollpanelsrapporter listas nu som dimensioner i begärandeguiden steg 1 och kan importeras som Report Builder-begäranden.
title: Importera bokmärkesrapporter och kontrollpanelrapporter
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# Importera bokmärkesrapporter och kontrollpanelrapporter

{{legacy-arb}}

Alla rapporter med bokmärken och kontrollpanelsrapporter listas nu som dimensioner i begärandeguiden steg 1 och kan importeras som Report Builder-begäranden.

När du väljer en rapport med bokmärken fylls alla dimensioner och mått som definierar den här rapporten i. Datumintervallet, granulariteten och det valda segmentet uppdateras också baserat på det valda bokmärket.

Så här visar begärandeguiden steg 1 en kontrollpanel och dess rapportplatser:

![Skärmbild som visar begärandeguiden Steg 1 av 2 som markerar Hämta dina instrumentpaneler och Hämta dina bokmärken.](assets/import_dashboard_reportlet.png)

När du klickar på **[!UICONTROL Retrieve your Dashboards]** eller **[!UICONTROL Retrieve your Bookmarks]** hämtas och klistras dina befintliga instrumentpanels- och/eller bokmärkesdata in i kalkylbladet.

>[!NOTE]
>
>Endast data importeras, så om bokmärket innehåller ett diagram, eller om kontrollpanelens rapportlåt bara består av ett diagram, importeras endast de data som används för att fylla diagrammet.

När du har skapat en begäran genom att importera en kontrollpanelsrapport (eller ett bokmärke) kopplas begäran sedan till rapportletens (eller bokmärkets) primära dimension. Om du redigerar begäran markeras därför inte längre trädvisningsnoden (eller bokmärkesnoden) för kontrollpanelsrapportletten, utan den primära dimensionen väljs i stället.

