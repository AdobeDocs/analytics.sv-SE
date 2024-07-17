---
title: Operativsystem
description: Operativsystemet för besökaren.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 9c3e65392d6e5929ce1ecefbc460c1fd5576aed8
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---

# Operativsystem

Operativsystemet [dimension](overview.md) visar det operativsystem och den version som besökaren använde. Om du har funktioner som är operativsystemsspecifika på din webbegenskap, hjälper den här dimensionen dig att förstå vilka operativsystem som är vanligaste.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på HTTP-huvudet `User-Agent` i bildbegäranden. Adobe samarbetar med [DeviceAtlas](https://deviceatlas.com/) för att upprätthålla sökningar mellan användaragenten och operativsystemet.

* För implementeringar av AppMeasurement fungerar den här dimensionen som standard.
* Aktivera [!UICONTROL Device Lookup] när [konfigurerar ett datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html) för Web SDK-implementeringar.

## Dimensioner

Dimensionen innehåller operativsystem som besökarna använder. Exempel är `"Windows 10"`, `"OS X 10.15.7"` och `"Android 9"`.

## Spåra korrekta OS-versioner

När branschen går mot kundtips finns det risk för att vissa operativsystemsversioner blir förvirrade. Till exempel kan både&quot;Windows 10&quot; och&quot;Windows 11&quot; grupperas under&quot;Windows 10&quot; om du inte samlar in klienttips med hög entropi. Mer information finns i [Klienttips](/help/technotes/client-hints.md) i TechNotes-guiden.
