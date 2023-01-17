---
title: Operativsystem
description: Operativsystemet för besökaren.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 26de81f090cebb45473a04a2edbe281f1c8591a4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Operativsystem

Dimensionen &#39;Operativsystem&#39; visar det operativsystem och den version som besökaren använde. Om du har funktioner som är operativsystemsspecifika på din webbegenskap, hjälper den här dimensionen dig att förstå vilka operativsystem som är vanligaste.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på `User-Agent` HTTP-huvud i bildbegäranden. Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen direkt.

## Dimensioner

Dimensionen innehåller operativsystem som besökarna använder. Exempel `"Windows 10"`, `"OS X 10.15"`och `"Android 9"`.

## Förändringar i märkning och definition

Nedan finns en lista över specifika problem med hur operativsystemet har beskrivits i användaragenten och i Adobe Analytics-rapporter.

### Byt till namnkonvention för Apple operativsystem:

Från och med version 11 använder vi OS X i stället för Mac OS för att hänvisa till Apple operativsystem.

Exempel:

* macOS version 10.15.7 (se anm. nedan om version 10.15.7 över representation i UA-strängar).
* OS X version 11.0.0

### Mac OS-versionen är felaktig i användaragenten efter version 10.15.7 

Från och med januari 2023 visar användaragenten i alla webbläsare Mac OS-versionen som 10.15.7, även för nyare versioner. Det här gjordes eftersom version 11 i användargränssnittet uppenbarligen orsakade problem med vissa webbplatser. Apple noterar också att om du inkluderar en felaktig OS-version i användargränssnittet får du vissa sekretessfördelar.

Observera att klienttipsen innehåller rätt version i plattformsversionstipset (&quot;Sec-CH-UA-Platform-Version&quot;). Detta är ett högt entropi-tips, så det samlas inte in automatiskt av Adobe. Se [Vanliga frågor om Adobe Analytics-tips](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) om du vill ha mer information om hur du samlar in entropytips.

### Windows-versionen är felaktig i användaragenten som börjar med Windows 11

Från och med januari 2023 representerar användaragenten i alla webbläsare Windows 11 som Windows 10.

Observera att klienttipsen innehåller rätt version i plattformsversionstipset (&quot;Sec-CH-UA-Platform-Version&quot;). Detta är ett högt entropi-tips, så det samlas inte in automatiskt av Adobe. Se [Vanliga frågor om Adobe Analytics-tips](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) om du vill ha mer information om hur du samlar in entropytips.
