---
title: dc
description: En indragen variabel som gör att du kan avgöra vilket datacenter som ska användas.
translation-type: tm+mt
source-git-commit: dfe2b09b2ee287219d18099c51b6fbd7c86bab21
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 2%

---


# dc

>[!IMPORTANT]
>
>Den här variabeln har tagits bort. Använd [`trackingServer`](trackingserver.md) istället.

I tidigare versioner av Adobe Analytics behövde Adobe ange vilket datacenter du ville skicka data till. Om du skickar träffar till fel datacenter går data förlorade.

Adobe har förbättrat den här upplevelsen genom att tillåta implementeringar att skicka träffar `sc.adobedc.net`. Du behöver inte längre ange datacenter.
