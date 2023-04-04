---
title: Slutet av livscykeln för fullständig bearbetning av datakällor
description: Läs mer om slutdatumet för meddelande om fullständig bearbetning av datakällor.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Slutet av livscykeln för fullständig bearbetning av datakällor

Med hjälp av fullständiga databehandlingskällor har företag och organisationer historiskt sett kunnat skicka data på hög nivå till Adobe Analytics. Dessa data bearbetades på samma sätt som data som samlats in via traditionella datainsamlingsmetoder, som AppMeasurement. 2020 släppte Adobe [API för massdatainfogning](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/), som utför samma funktioner som fullbearbetning av datakällor, men med ytterligare funktioner. Den här sidan innehåller information om ytterligare funktioner som tillhandahålls av API:t för infogning av gruppdata och visar skillnader i filformat.

Den 25 mars 2021 hindrade Adobe från att skapa anslutningar för nya, fullständiga datakällor. Den 31 januari 2022 inaktiverades alla datatjänster med fullständig bearbetning.

## Viktiga skillnader mellan den fullständiga bearbetningen av datakällor och API:t för infogning av gruppdata

* Genom att infoga flera data samtidigt kan du skicka flera filer för parallell bearbetning. Besöksgrupper säkerställer besökarnas kontinuitet och eVar.
* Dataverifiering och felhantering vid infogning i grupp innebär att en del av det administrativa arbetet med att skicka träffdata tas bort.
* Datainfogning i grupp stöder flera identifieringsmetoder för besökar-ID.
* Det finns ytterligare obligatoriska fält för infogning av gruppdata: En kolumn för besöksidentifiering, `pageName` (eller motsvarande länk), `reportSuiteID`, `timestamp`och `userAgent`.
* För att säkerställa besökarnas kontinuitet och attribuering kräver infogning av gruppdata att rader i filer sorteras i kronologisk ordning. Se [Besöksgrupper](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/) om du vill veta mer om ordningen för besöksaktiviteter mellan filer.
* För infogning av gruppdata krävs att filerna är .csv-komprimerade i .gzip-format.
* BDIA använder `timestamp` i stället för `date`.

## Variabel jämförelse mellan BDIA och datakällor med full bearbetning

Följande variabler introducerades för infogning av gruppdata, som tidigare inte fanns i datakällor med fullständig bearbetning:

* **`aamlh`**: Platstips för Adobe Audience Manager.
* **`contextData.key`**: [Sammanhangsdatavariabler](/help/implement/vars/page-vars/contextdata.md).
* **`customerID`**: Experience Cloud ID-tjänstvariabler. Inkluderar `id`, `authState` och `isMCSeed`.
* **`hints`**: [Klienttips](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html) variabler. Inkluderar `bitness`, `brands`, `mobile`, `model`, `platform`, `platformversion`och `wow64`.
* **`ipaddress`**: Besökarens IP-adress.
* **`language`**: The [Språk](/help/components/dimensions/language.md) dimension.
* **`list1`** - **`list3`**: [Listvariabler](/help/implement/vars/page-vars/list.md).
* **`marketingCloudVisitorID`**: Besökarens Experience Cloud-ID.
* **`tnta`**: Måldatanyttolast används i [Analyser för Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html) integreringar.
* **`trackingServer`**: The [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) variabel.
* **`transactionID`**: The [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variabel.
* **`userAgent`**: Enhetens användaragentsträng.

Följande variabler stöds inte genom infogning av gruppdata:

* **`charSet`**: The [`charSet`](/help/implement/vars/config-vars/charset.md) variabel. Infoga gruppdata har bara stöd för UTF-8.
* **`timezone`**: Besökarens tidszon har förskjutits från GMT i timmar.
* **`clickAction`**, **`clickActionType`**, **`clickContext`**, **`clickContextType`**, **`clickSourceID`**, **`clickTag`**: Variabler som används i datainsamlingen i Activity Map.
