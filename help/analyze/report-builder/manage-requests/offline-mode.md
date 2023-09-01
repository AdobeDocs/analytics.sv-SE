---
description: Lär dig hur du använder offline-läge för att returnera platshållardata.
title: Aktivera offlineläge
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 4%

---

# Offlineläge för att skapa och redigera förfrågningar

Offlineläget returnerar platshållardata för att snabba upp processen att skapa och redigera begäranden.

När du skapar eller redigerar en ny begäran görs API-anrop för rapport för att hämta svaret. Ibland gör dessa anrop processen att skapa en begäran långsammare eftersom du måste vänta på att data ska returneras innan du går vidare till nästa steg. Offlineläget returnerar endast platshållardata och API:n görs inte.

Aktivera offlineläge

1. Klicka **[!UICONTROL Options]** på Report Builder-menyn.

   ![Skärmbild av skärmen Alternativ med offlineläge markerat.](assets/offline_mode.png)

1. Markera kryssrutan intill **[!UICONTROL Turn on offline mode for creating and editing requests]**.
1. I **[!UICONTROL Display Metric Data as]** anger du de platshållardata som du vill returnera i din begäran. Ange t.ex. &quot;1&quot;.
1. Klicka på **[!UICONTROL OK]**.
1. Skapa och kör din begäran i offlineläge med hjälp av begärandeguiden. I följande skärmbild visas ett exempel på en begäran med &quot;1&quot; som platshållardata.

   ![Skärmbild som visar offlineläget med 1 som platshållare.](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >Se till att du inaktiverar offlineläget innan du kör dina begäranden med riktiga data.
