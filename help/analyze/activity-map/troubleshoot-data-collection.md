---
title: Felsöka datainsamling i Activity Map
description: Bestäm varför du inte kan se Activity Map data i bildbegäranden
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 0%

---


# Felsöka datainsamling i Activity Map

Om du inte ser data för Activity Map-dimensioner kan du använda den här sidan för att avgöra varför.

## Bekräfta datainsamling med hjälp av felsökaren

Kontrollera först att AppMeasurement samlar in Activity Map-data på rätt sätt.

1. Hämta och installera [Adobe Experience Cloud Debugger Chrome Extension](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html).
2. Navigera till webbsidan och klicka sedan på en länk.
3. Öppna felsökaren när den följande sidan läses in. Verifiera att du ser datavariabler för kontext i Activity Map som är sammanflätade mellan `activitymap.` och `.activitymap`:

![Felsökningsdata](assets/debugger.png)

## Möjliga orsaker till varför det inte finns några data från Activity Map

Kontrollera följande för att se till att komponenterna i Activity Map finns:

* **AppMeasurement-version**: Activity Map stöds i v1.6 och senare. Många edge-problem åtgärdas när du uppgraderar till den senaste stabila versionen av AppMeasurement.
* **Activity Map-modul**: Kontrollera om modulen finns `AppMeasurement_Module_Activity_Map` i `AppMeasurement.js` filen. Om implementeringen använder Adobe Experience Platform Launch ska du kontrollera att **[!UICONTROL Enable ClickMap]** detta är markerat när du konfigurerar Analytics-tillägget under **[!UICONTROL Link tracking]**.
* **The`s_sq`cookie**: Activity Map är beroende av `s_sq` cookien för datainsamling.
   * Se till att variabeln är rätt inställd, särskilt för regionala domäner som `cookieDomainPeriods` eller `*.co.uk` `*.co.jp`.
   * Se till att variabeln är inställd på önskade värden `linkInternalFilters` . Om en klickad länk inte matchar interna filter ser Activity Map den som en avslutslänk och samlar inte in data.
* **Activity Map-övertäckning körs**: AppMeasurement spårar inte klickdata för webbsidan när Activity Map-övertäckningen är aktiverad.
