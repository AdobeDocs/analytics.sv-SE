---
title: dc
description: En indragen variabel som gör att du kan avgöra vilket datacenter som ska användas.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 2%

---


# dc

>[!IMPORTANT]
>
>Den här variabeln har tagits bort. Använd [`trackingServer`](trackingserver.md) istället.

I tidigare versioner av Adobe Analytics behövde du ange vilket datacenter du vill skicka data till. Om du skickar träffar till fel datacenter går data förlorade.

Adobe har förbättrat denna upplevelse genom att tillåta alla implementeringar att skicka träffar `sc.omtrdc.net`. Du behöver inte längre ange datacenter.
