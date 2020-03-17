---
title: Felsöka sessioner i Adobe Analytics
description: Lär dig hur du löser problem med utloggning från Adobe Analytics.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Felsöka sessioner i Adobe Analytics

Den här sidan handlar om felsökningssessioner, vilket innebär att du kan logga in utan att behöva logga in. Om du har problem med att logga in på Adobe Analytics, se [Felsöka inloggning på Adobe Analytics](troubleshoot-login.md).

Nästan alla sessionsbaserade problem kommer från en organisations anpassade företagsnätverk. Om du kan logga in på Adobe Analytics men har problem med att vara inloggad kan du använda den här artikeln för att fastställa orsaken.

## Kontrollera om problemet beror på din organisations nätverk

Många organisationer använder ytterligare nätverksfunktioner för att förbättra säkerheten, som proxyservrar eller brandväggar. Dessa anpassningar kan ibland påverka möjligheten att behålla en aktiv session i Adobe Analytics.

Om du vill avgöra om det företagsnätverk du är ansluten till orsakar problem med att använda Adobe Analytics kan du använda dina inloggningsuppgifter för Experience Cloud på en enhet utanför företagsnätverket. Exempel på enheter kan vara via ditt hemnätverk eller en mobilenhets dataplan. Om du kan gå från sida till sida utan att vara utloggad är det troligtvis din organisations nätverk som är orsaken till varför du loggar ut från Adobe Analytics.

## Problem på grund av proxy

Adobe använder en auktoriseringshuvud när förfrågningar görs till Adobe. Vissa proxies, till exempel Bluecoat (som nu ägs av Symantec), tar bort viktig auktoriseringsinformation som används av Adobe Analytics. När Adobe inte ser auktoriseringshuvudet förfaller sessionen.

För att lösa problemet rekommenderar Adobe att ni samarbetar med IT-avdelningen i er organisation för att tillåta behörighetshuvudet via er organisations proxy.

> [!NOTE] Även om medlemmar i Analytics-communityn tycker att följande länkar är användbara, ägs de inte av Adobe. Tänk på detta när du visar innehållet.

Information om Symantec-proxies och autentiseringshuvuden finns här:

* [Konfigurera autentisering av överordnad proxy i en proxykedja på en ProxySG- eller ASG-enhet](https://support.symantec.com/en_US/article.TECH246122.html)
* [Tillåt att ProxySG alltid vidarebefordrar serverauktorisering uppströms](https://support.symantec.com/en_US/article.TECH244708.html)
