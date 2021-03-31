---
description: Offlineläget returnerar platshållardata för att snabba upp processen att skapa och redigera begäranden.
title: Offlineläge för att skapa och redigera förfrågningar
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '184'
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

