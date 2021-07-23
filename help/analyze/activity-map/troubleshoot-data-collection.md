---
title: Felsöka datainsamling i Activity Map
description: Bestäm varför du inte kan se Activity Map data i bildbegäranden
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---

# Felsöka datainsamling i Activity Map

Om du inte ser data för Activity Map-dimensioner kan du använda den här sidan för att avgöra varför.

## Bekräfta datainsamling med hjälp av felsökaren

Kontrollera först att AppMeasurement samlar in Activity Map-data på rätt sätt.

1. Hämta och installera [Adobe Experience Cloud Debugger Chrome Extension](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html).
2. Navigera till webbsidan och klicka sedan på en länk.
3. Öppna felsökaren när den följande sidan läses in. Verifiera att du ser datavariabler för kontext i Activity Map mellan `activitymap.` och `.activitymap`:

![Felsökningsdata](assets/debugger.png)

## Möjliga orsaker till varför det inte finns några data från Activity Map

Kontrollera följande för att se till att komponenterna i Activity Map finns:

* **AppMeasurement-version**: Activity Map stöds i v1.6 och senare. Många edge-problem åtgärdas när du uppgraderar till den senaste stabila versionen av AppMeasurement.
* **Activity Map-modul**: Kontrollera om  `AppMeasurement_Module_Activity_Map` modulen finns i  `AppMeasurement.js` filen. Om implementeringen använder Adobe Experience Platform Data Collection (Launch) kontrollerar du att **[!UICONTROL Enable ClickMap]** är markerat när du konfigurerar Analytics-tillägget under **[!UICONTROL Link tracking]**.
* **The  `s_sq` cookie**: Activity Map är beroende av  `s_sq` cookien för datainsamling.
   * Kontrollera att variabeln `cookieDomainPeriods` är korrekt inställd, särskilt för regionala domäner som `*.co.uk` eller `*.co.jp`.
   * Kontrollera att variabeln `linkInternalFilters` är inställd på önskade värden. Om en klickad länk inte matchar interna filter ser Activity Map den som en avslutslänk och samlar inte in data.
* **Activity Map-övertäckning körs**: AppMeasurement spårar inte klickdata för webbsidan när Activity Map-övertäckningen är aktiverad.
