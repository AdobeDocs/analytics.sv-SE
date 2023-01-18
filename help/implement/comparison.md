---
title: Jämför implementeringsmetoder
description: Se fördelarna med de olika sätten att skicka data till Adobe Analytics.
source-git-commit: 96a5daaf9d8358e4a5222a20f64c381cb8340ab1
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---

# Jämför implementeringsmetoder

Jämför de olika metoderna för att implementera Adobe Analytics med varandra. Du kan använda den här tabellen för att hjälpa din organisation att fastställa det mest idealiska sättet att skicka data till Adobe.

|  | AppMeasurement | Adobe Analytics-tillägg | Web SDK | Web SDK-tillägg |
| --- | --- | --- | --- | --- |
| Implementeringskrav | Referens `AppMeasurement.js` på varje sida, definiera variabler, skicka data med `s.t()` | Inläsare av referenstaggar på varje sida använder användargränssnittet för datainsamling för att definiera variabler och skicka data till Adobe | Referens `Alloy.js` på varje sida använder `alloy("sendEvent",{})` för att skicka ett JSON-objekt som innehåller önskade data | Inläsare av referenstaggar på varje sida använder användargränssnittet för datainsamling för att etablera JSON-objektet för att skicka data |
| Datamål | Skickat direkt till Adobe Analytics | Skickat direkt till Adobe Analytics | Skickat till Adobe Experience Platform Edge som vidarebefordrar data till Adobe Analytics | Skickat till Adobe Experience Platform Edge som vidarebefordrar data till Adobe Analytics |
| Svårighet att göra implementeringsjusteringar | Kräver åtkomst till webbplatskod för varje implementeringsändring | Webbplatskoden behöver bara ändras en gång för att installera Loader-taggen. alla ytterligare implementeringsuppdateringar kan göras i användargränssnittet för datainsamling | Kräver åtkomst till webbplatskod för varje implementeringsändring | Webbplatskoden behöver bara ändras en gång för att installera Loader-taggen. alla ytterligare implementeringsuppdateringar kan göras i användargränssnittet för datainsamling |
| Så här hanteras A4T | A4T-anrop ingår i träffar som skickas till Adobe | A4T-anrop ingår i träffar som skickas till Adobe | A4T-anrop skickas som separata träffar | A4T-anrop skickas som separata träffar |
| Hur referenten hanteras |