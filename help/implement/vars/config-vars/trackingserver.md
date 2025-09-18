---
title: trackingServer
description: Domänen som används för att skicka data till Adobe via HTTP.
feature: Appmeasurement Implementation
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 35675c2e65456a175d1516dd421b80d2af809286
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 0%

---

# trackingServer

>[!IMPORTANT]
>
>Den här variabeln är inaktuell. Använd [`trackingServerSecure`](trackingserversecure.md) i stället med förekomsten av HTTPS.

Variabeln `trackingServer` avgör vilken domän AppMeasurement använder för att skicka data till Adobe via HTTP. Om den här variabeln inte är korrekt definierad kan din implementering uppleva dataförlust.

Före [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/sv/docs/id-service/using/home) fastställde variabeln också var cookies från tredje part angavs. Adobe rekommenderar starkt att du använder ID-tjänsten i alla implementeringar där det är möjligt.

AppMeasurement använder `trackingServer` som reserv om [`trackingServerSecure`](trackingserversecure.md) inte har angetts. Många äldre implementeringar anger inte `trackingServerSecure`, vilket använder `trackingServer` som reserv på säkra sidor. Med en prevalens av HTTPS rekommenderar Adobe att du använder `trackingServerSecure` där det är möjligt.
