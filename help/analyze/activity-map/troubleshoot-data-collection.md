---
title: Felsöka datainsamling i Activity Map
description: Bestäm varför du inte kan se Activity Map data i bildbegäranden
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Felsöka datainsamling i Activity Map

Om du inte ser data för Activity Map-dimensioner kan du använda den här sidan för att avgöra varför.

## Bekräfta datainsamling med hjälp av felsökaren

Kontrollera först att AppMeasurement samlar in Activity Map-data på rätt sätt.

1. Hämta och installera [Adobe Experience Cloud Debugger Chrome Extension](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html).
2. Navigera till webbsidan och klicka sedan på en länk.
3. Öppna felsökaren när den följande sidan läses in. Validera att du ser datavariabler för kontext i Activity Map mellan `activitymap.` och `.activitymap`:

![Felsökningsdata](assets/debugger.png)

## Möjliga orsaker till varför det inte finns några data från Activity Map

Kontrollera följande för att se till att komponenterna i Activity Map finns:

* **AppMeasurement-version**: Activity Map stöds i v1.6 och senare. Många edge-problem åtgärdas när du uppgraderar till den senaste stabila versionen av AppMeasurement.
* **Modulen Activity Map**: Kontrollera om `AppMeasurement_Module_Activity_Map` finns i din `AppMeasurement.js` -fil. Om implementeringen använder Adobe Experience Platform för att samla in data, se till att **[!UICONTROL Enable ClickMap]** är markerat när Analytics-tillägget konfigureras under **[!UICONTROL Link tracking]**.
* **The `s_sq` cookie**: Activity Map är beroende av `s_sq` cookie för datainsamling.
   * Se till att `cookieDomainPeriods` variabeln har angetts korrekt, särskilt för regionala domäner som `*.co.uk` eller `*.co.jp`.
   * Se till att `linkInternalFilters` variabeln anges till önskade värden. Om en klickad länk inte matchar interna filter ser Activity Map den som en avslutslänk och samlar inte in data.
* **Activity Map-övertäckning körs**: AppMeasurement spårar inte klickdata för webbsidan när Activity Map-övertäckningen är aktiverad.
