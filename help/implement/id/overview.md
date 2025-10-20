---
title: Besökaridentifiering i Adobe Analytics
description: Lär dig identifiera besökare i Adobe Analytics med hjälp av de senaste metodtips.
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# Besökaridentifiering i Adobe Analytics

Identifiering av besökare är en viktig del av det värde som Adobe Analytics ger för att förstå onlineanvändarbeteenden. Det handlar om att länka träffar till samma person över tiden med hjälp av en gemensam identifierare. Korrekt identifiering av besökare ger tillförlitliga mätvärden och stöder en sund implementeringsstrategi. Adobe rekommenderar att organisationer prioriterar moderna identitetstjänster för enhetlighet och dataintegritet på olika plattformar.

Besökaridentifieringen i Adobe Analytics består av följande komponenter:

* Identifierare på klientsidan: Lagras vanligtvis i en cookie från en annan leverantör. Implementeringar som är beroende av cookies från tredje part är mindre konsekventa med besökaridentifiering på grund av moderna webbläsarsekretessstandarder.
* Server-side identifier: Each Analytics visitor ID is bound to a profile on Adobe servers. Dessa besökarprofiler tillåter beständighet på variabler som [eVars](/help/components/dimensions/evar.md). Profiler tas bort efter minst 13 månaders inaktivitet, oavsett om en cookie-fil för besöks-ID har gått ut eller inte.

## Adobe Analytics identifieringsordning för operationer

När Adobe får en träff utförs följande kontroller i rätt ordning. Om det finns en viss egenskap använder Adobe den identifieraren för träffen. Om det finns flera identifierare i en träff används bara den första metoden.

| Order som används | Frågeparameter | Visas när |
|---|---|---|
| **1<sup>st</sup>** | `vid` | Variabeln [`visitorID`](/help/implement/vars/config-vars/visitorid.md) har angetts. |
| **2<sup>nd</sup>** | `aid` | Besökaren har en befintlig [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics)-cookie. Ange implementeringar utan eller innan du implementerar Visitor ID-tjänsten. |
| **3<sup>rd</sup>** | `mid` | Besökaren har en befintlig [`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics)-cookie. Ange implementeringar med hjälp av [Adobe Experience Cloud Identity-tjänsten](https://experienceleague.adobe.com/docs/id-service/using/home.html). Adobe rekommenderar att du använder ID-tjänsten för alla implementeringar där det är möjligt. |
| **4<sup>th</sup>** | `fid` | Besökaren har en befintlig [`s_fid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics)-cookie, eller om `aid` och `mid` inte kunde anges av någon anledning. |
| **5<sup>th</sup>** | IP-adress, användaragent, gateway-IP-adress | Används som en sista utväg för att identifiera en unik besökare om besökarens webbläsare inte accepterar cookies. |

## Beteende som påverkar antalet unika besökare

Unika besöksidentifierare lagras vanligtvis i en webbläsarcookie. En ny unik besökare räknas om en besökare utför någon av följande åtgärder:

* Rensar sina cookies när som helst. En unik besökare räknas för en träff varje gång deras cache rensas.
* Besökar-ID-cookies går ut på grund av webbläsarens sekretessinställningar. Vissa webbläsare innehåller metoder för att förhindra spårning som begränsar cookies livstid.
* Öppnar en annan webbläsare på samma dator. En unik besökare räknas per webbläsare.
* Öppnar en privat surfsession (till exempel fliken Chrome Incognito). En unik besökare räknas per surfsession när alla flikar har stängts.
* Besöker webbplatsen på olika enheter. En unik besökare räknas per enhet.
* Besök webbplatsen efter mer än 13 månaders inaktivitet.

Använd [Stitching](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview) i Customer Journey Analytics för att identifiera samma person i flera webbläsare eller på flera enheter.

## Beteende som inte påverkar antalet unika besökare

En ny unik besökare *räknas inte*, så länge besökaridentifieraren bevaras:

* Stänger webbläsaren (under mindre än 13 månader)
* Uppgraderar webbläsaren till den senaste versionen
* Startar om datorn
