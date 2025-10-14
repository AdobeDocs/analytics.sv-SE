---
description: Länknamnet som klickades på.
title: Activity Map Link
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 0%

---

# Activity Map Link

Activity Map Link [dimension](overview.md) visar de mest populära länkarna som du klickade på. Du kan använda den här dimensionen för att jämföra vilka länkar på webbplatsen som används mest, oavsett var länkarna klickades.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [kontextdatavariabeln &#x200B;](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`. Om implementeringen använder [Activity Map](/help/analyze/activity-map/overview.md) samlar den här kontextdatavariabeln automatiskt in data när någon klickar på länkar.

För en viss länk som du klickade på söker Activity Map efter följande (i ordning):

1. Variabeln `s_objectID`
1. Länkens inre text
1. Attributet `alt` för bilder
1. Attributet `title`
1. Attributet `src` för bilder
1. Attributet `action` för formulär

Om det klickade elementet inte innehåller något av ovanstående villkor, samlar Activity Map inte in data för det klicket.

## Dimensioner

Dimensionen innehåller länktexten eller andra länkattribut som besökarna klickar på. Organisationens webbplatsstruktur och implementering avgör de exakta värden som samlas in.
