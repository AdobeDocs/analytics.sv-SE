---
title: Sida för Activity Map
description: Sidnamnet när någon klickar på en länk.
feature: Dimensions
role: User, Admin
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 3%

---

# Sida för Activity Map

Sidan Activity Map [dimension](overview.md) visar den sida som en besökare var på när användaren klickade på en länk. Du kan använda den här dimensionen för att avgöra vilka sidor som innehåller länkar som klickas mest. Den här dimensionen används även av Activity Map-övertäckningen för att avgöra vilka länkar som ska visas.

## Fyll den här dimensionen med data

Den här dimensionen hämtar data från [kontextdatavariabeln &#x200B;](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`. Om implementeringen använder [Activity Map](/help/analyze/activity-map/overview.md) samlar den här kontextdatavariabeln automatiskt in data när någon klickar på länkar.

För en viss länk som du klickade på samlar den här kontextdatavariabeln in värdet i dimensionen [Sida](page.md). Om siddimensionen inte innehåller något värde används dimensionen [Sida-URL](page-url.md) i stället (på samma sätt som siddimensionens reservvärde). Activity Map data skickas vanligtvis vid nästa träff efter att en länk klickats. Med den här dimensionen kan du bestämma sidvärdet när någon klickar på länken, i stället för sidvärdet när data skickades.

## Dimensioner

Dimensioner innehåller alla värden som finns i dimensionen [Sida](page.md).
