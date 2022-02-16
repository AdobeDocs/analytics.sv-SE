---
description: Alla rapporter med bokmärken och kontrollpanelsrapporter listas nu som dimensioner i begärandeguiden steg 1 och kan importeras som rapportbyggarbegäranden.
title: Importera bokmärkta rapporter och minirapporter från kontrollpaneler
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 3%

---

# Importera bokmärkta rapporter och minirapporter från kontrollpaneler

Alla rapporter med bokmärken och kontrollpanelsrapporter listas nu som dimensioner i begärandeguiden steg 1 och kan importeras som rapportbyggarbegäranden.

När du väljer en rapport med bokmärken fylls alla dimensioner och mått som definierar den här rapporten i. Datumintervallet, granulariteten och det valda segmentet uppdateras också baserat på det valda bokmärket.

Så här visar begärandeguiden steg 1 en kontrollpanel och dess rapportplatser:

![](assets/import_dashboard_reportlet.png)

När du klickar **[!UICONTROL Retrieve your Dashboards]** eller **[!UICONTROL Retrieve your Bookmarks]** hämtar och klistrar dina befintliga data från kontrollpanelen och/eller bokmärket in i kalkylbladet.

>[!NOTE]
>
>I Report Builder är listan med tillgängliga kontrollpaneler och bokmärken begränsad till användaren, men även till de som gäller för den rapportserie du valde i steg 1 i guiden. I marknadsföringsrapporter och -analyser får ni däremot tillgång till alla bokmärken och instrumentpaneler som är tillgängliga för er, oavsett vilka rapportsviter dessa instrumentpaneler och bokmärken använder.

>[!NOTE]
>
>Endast data importeras, så om bokmärket innehåller ett diagram, eller om kontrollpanelens rapportlåt bara består av ett diagram, importeras endast de data som används för att fylla diagrammet.

När du har skapat en begäran genom att importera en kontrollpanelsrapport (eller ett bokmärke) kopplas begäran sedan till rapportletens (eller bokmärkets) primära dimension. Om du redigerar begäran kommer trädvyn därför inte längre att välja trädvisningsnoden (eller bokmärkesnoden) för kontrollpanelsrapporten: i stället väljs dess primära dimension.

Det importerade bokmärkesschemat ställer in rapportsviten, det valda segmentet, dimensionen och valda mätvärden på samma parametrar som visas i bokmärket Rapporter och analyser.

>[!IMPORTANT]
>
>Datumintervallet ställs in på samma datumintervall, men som ett statiskt datumintervall - även om det här datumintervallet var ett rullande datumintervall i bokmärket Rapporter och analyser.
