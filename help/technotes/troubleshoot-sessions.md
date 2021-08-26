---
title: Felsöka sessioner i Adobe Analytics
description: Lär dig hur du löser problem med utloggning från Adobe Analytics.
exl-id: 191250ef-8313-47be-9717-046cce870998
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Felsöka sessioner i Adobe Analytics

Den här sidan handlar om felsökningssessioner, vilket innebär att du kan logga in utan att behöva logga in. Om du har problem med att logga in på Adobe Analytics kan du läsa [Felsöka inloggning på Adobe Analytics](troubleshoot-login.md).

Nästan alla sessionsbaserade problem kommer från en organisations anpassade företagsnätverk. Om du kan logga in på Adobe Analytics men inte kan vara inloggad kan du använda den här artikeln för att fastställa orsaken.

## Kontrollera om problemet beror på din organisations nätverk

Många organisationer använder ytterligare nätverksfunktioner för att förbättra säkerheten, som proxyservrar eller brandväggar. Dessa anpassningar kan ibland påverka möjligheten att behålla en aktiv session i Adobe Analytics.

Använd inloggningsuppgifterna för Experience Cloud på en enhet utanför företagsnätverket för att avgöra om det företagsnätverk du är ansluten till orsakar problem med att använda Adobe Analytics. Exempel på enheter kan vara via ditt hemnätverk eller en mobilenhets dataplan. Om du kan gå från sida till sida utan att vara utloggad är det troligtvis din organisations nätverk som är orsaken till varför du loggar ut från Adobe Analytics.

## Problem på grund av proxy

Adobe använder en auktoriseringshuvud när begäranden görs till Adobe. Vissa proxies, till exempel Edge Secure Web Gateway (tidigare Bluecoat), tar bort viktig auktoriseringsrubrikinformation som används av Adobe Analytics. När Adobe inte ser auktoriseringshuvudet förfaller sessionen.

För att lösa detta rekommenderar Adobe att man samarbetar med IT-avdelningen i er organisation för att tillåta behörighetshuvudet via er organisations proxy.

>[!NOTE]
>
>Även om medlemmar i Analytics-communityn tycker att följande länkar är till hjälp, ägs de inte av Adobe. Tänk på detta när du visar innehållet.

Information om proxies och autentiseringshuvuden finns här:

* [Konfigurera autentisering av överordnad proxy i en proxykedja på en ProxySG- eller ASG-enhet](https://knowledge.broadcom.com/external/article/169255/configure-upstream-proxy-authentication.html)
* [Så här vidarebefordrar du inloggningsuppgifter till en server bakom ProxySG-enheten](https://knowledge.broadcom.com/external/article/165859/how-to-forward-user-credentials-to-a-ser.html)
