---
title: Operativsystem
description: Operativsystemet för besökaren.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 0%

---

# Operativsystem

Operativsystemet [dimension](overview.md) visar det operativsystem och den version som besökaren använde. Om du har funktioner som är operativsystemsspecifika på din webbegenskap, hjälper den här dimensionen dig att förstå vilka operativsystem som är vanligaste.

## Fyll den här dimensionen med data

Den här dimensionen refererar till en uppslagstabell som är intern för Adobe. Uppslagsvärdet baseras på `User-Agent` HTTP-huvud i bildbegäranden. Om du använder ett AppMeasurementen bibliotek (till exempel via taggar i Adobe Experience Platform) fungerar den här dimensionen automatiskt.

## Dimensioner

Dimensionen innehåller operativsystem som besökarna använder. Exempel: `"Windows 10"`, `"OS X 10.15"`och `"Android 9"`.

## Förändringar i märkning och definition

Nedan finns en lista över specifika problem med hur operativsystemet har beskrivits i användaragenten och i Adobe Analytics-rapporter.

### Ändra till granularitet för operativsystem

Den 2 mars 2023 uppdaterade vi vår rapportering för att inkludera mer information i operativsystemet. Efter detta datum inkluderar vi operativsystemets korrigeringsversion. En användare med OS X 10.15.7 skulle till exempel ha visat sig vara &quot;OS X 10.15&quot; före 2 mars. Efter den 2 mars visas de som&quot;OS X 10.15.7&quot;.

### Byt till namnkonvention för Apple operativsystem:

Från och med version 11 använder vi MacOS i stället för OS X för att hänvisa till Apple operativsystem.

Exempel:

* &quot;OS X 10.15&quot; (se anmärkning nedan om version 10.15.7 över representation i UA-strängar).
* &quot;MacOS 11.0.0

### Mac OS-versionen är felaktig i användaragenten efter version 10.15.7 

Användaragenten på Apple-datorer visar OS-versionen som 10.15.7 även för nyare versioner. Det här gjordes eftersom version 11 i användargränssnittet uppenbarligen orsakade problem med vissa webbplatser. Detta gäller *alla webbläsare* och är inte relaterat till Google frysning av användaragenten i Chromium-webbläsare.

Observera att klienttipsen innehåller rätt version i plattformsversionstipset (&quot;Sec-CH-UA-Platform-Version&quot;). Det här är ett högt entropi-tips, så det samlas inte in automatiskt av Adobe. Se [Vanliga frågor om Adobe Analytics tips](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) om du vill ha mer information om hur du samlar in entropytips.

### Windows-versionen är felaktig i användaragenten som börjar med Windows 11

Från och med januari 2023 representerar användaragenten i alla webbläsare Windows 11 som Windows 10.

Observera att klienttipsen innehåller rätt version i plattformsversionstipset (&quot;Sec-CH-UA-Platform-Version&quot;). Det här är ett högt entropi-tips, så det samlas inte in automatiskt av Adobe. Se [Vanliga frågor om Adobe Analytics tips](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) om du vill ha mer information om hur du samlar in entropytips.
