---
description: Offlineläget returnerar platshållardata för att snabba upp processen att skapa och redigera begäranden.
title: Offlineläge för att skapa och redigera förfrågningar
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 9%

---

# Offlineläge för att skapa och redigera förfrågningar

Offlineläget returnerar platshållardata för att snabba upp processen att skapa och redigera begäranden.

När du skapar eller redigerar en ny begäran görs API-anrop för rapport för att hämta svaret. Detta gör processen att skapa en begäran långsammare eftersom du måste vänta tills data har skickats tillbaka innan du går vidare till nästa steg. Offlineläget returnerar endast platshållardata, så inga API-anrop behöver göras.

Så här aktiverar du offlineläge:

1. Klicka på **[!UICONTROL Options]** på Report Builder-menyn.

   ![](assets/offline_mode.png)

1. Markera kryssrutan bredvid **[!UICONTROL Turn on offline mode for creating and editing requests]**.
1. I fältet **[!UICONTROL Display Metric Data as]** anger du platshållardata som du vill returnera i din begäran. Ange t.ex. &quot;1&quot;.
1. Klicka på **[!UICONTROL OK]**.
1. Skapa och kör din begäran (i offlineläge) med hjälp av Request Wizard.
1. Din begäran med &quot;1&quot; som platshållardata ser ut ungefär så här:

   ![](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >Se till att du inaktiverar offlineläget innan du kör dina begäranden med riktiga data. Gå tillbaka till **[!UICONTROL Options]** och ta bort bockmarkeringen.
