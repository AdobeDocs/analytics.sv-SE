---
title: Alternativ för att minska effekten av webbläsar-cookie-begränsningar
description: Lär dig hur du minskar effekten av webbläsar-cookie-begränsningar för att förbättra datainsamlingen för Adobe Analytics.
feature: Data Configuration and Collection
exl-id: 81cf3f0c-4871-435d-bcc9-bcff5c682f05
role: Admin
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 0%

---

# Alternativ för att minska effekten av webbläsar-cookie-begränsningar

I det här dokumentet diskuteras olika alternativ för att bevara beständig besöksidentifiering i olika egenskaper och lösningar, eftersom de flesta webbläsare implementerar spårningsförebyggande åtgärder för cookies.

Adobe Analytics förlitar sig på cookies från första part för att registrera en besökares aktivitet på plats. Analyserna bygger också på cookies från tredje part för att förstå en besökares aktivitet utanför webbplatsen, till exempel aktivitet på andra domäner du äger. Cookies från tredje part blockeras i många webbläsare och är i stort sett inte tillgängliga i och med att Chrome kommer att ta bort stödet (vilket nu planeras till slutet av 2024). cookies från första part tillåts i alla webbläsare men har en begränsad giltighetstid för Safari och andra webbläsare under Apple [Spårning av ITP](https://webkit.org/tracking-prevention) åtgärder. Mer information om aktuella begränsningar för webbläsarcookies finns i [Adobe Analytics och webbläsarcookies](cookies.md).

Dessa begränsningar i webbläsaren innebär en bredare övergång från anonym tredje parts spårning till explicit informationsutbyte mellan användare och varumärken som de litar på. För att stödja detta har Adobe möjlighet för kunder att komplettera traditionella cookies genom att inkludera varaktiga identifierare som samlats in via sina egna relationer.

## Customer Journey Analytics och Cross Device Analytics

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) och [Enhetsövergripande analys](/help/components/cda/overview.md) gör det möjligt för användare att inkludera varaktiga identifierare, t.ex. hash-inloggningar, utöver cookies. På så sätt kan ni förstå kundresan över olika enheter och, när det gäller Customer Journey Analytics, över online- och offlinekanaler:

* **Customer Journey Analytics** bygger på Adobe Experience Platform och ger flexibilitet att kombinera online- och offlinedata i Analysis Workspace, baserat på vilket gemensamt kund-ID som helst. Du kan ange vilket ID du vill använda för en given analys och utforska data i Analysis Workspace. Kunder med Analytics Select, Prime och Ultimate har rätt att köpa detta som en tilläggsprodukt.

* **Enhetsövergripande analys** är en förbättring av traditionella Adobe Analytics som gör det möjligt för kunderna att använda alternativa identifierare för besökare. Med den här funktionen kan du gå från en enhetscentrerad vy till en personcentrerad vy. Enhetsövergripande analys är tillgängligt för kunder med Analytics Ultimate.

## Datainsamling på serversidan

Samling på serversidan ger flexibilitet att tillhandahålla en egen identifierare i stället för att förlita sig på webbläsarmekanismer för att ställa in cookies.

Du kan skicka data till Analytics-servern via [API för datainfogning](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) eller [API för massdatainmatning](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). API för datainfogning i grupp rekommenderas för nya implementeringar på serversidan. En jämförelse av de två API:erna finns i[Vilket Adobe Analytics-verktyg ska jag använda](/help/analyze/get-started/which-analytics-tool.md).&quot;

## FPID (First Party Device ID) med Web SDK

Med Adobe Experience Platform Web SDK kan du välja att ställa in och hantera egna enhetsidentifierare i stället för Adobe-genererade Experience Cloud-ID:n (ECID). Dessa kallas för FPID (First-party device ID). Läs mer [här](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html).

## Mer information

Mer information om hur du kan gå över från cookies från tredje part finns i [Förvärva och hålla kunderna i en cookiefri värld med Adobe](https://business.adobe.com/solutions/cookieless.html) och detaljinfo [Tänk bortom cookie-filen från tredje part: En komplett guide till en värld utan cookies från tredje part](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).&quot;

>[!MORELIKETHIS]
>
>[Adobe Analytics och webbläsarcookies](cookies.md)
