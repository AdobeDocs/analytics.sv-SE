---
title: Alternativ för att minska effekten av webbläsar-cookie-begränsningar
description: Lär dig hur du minskar effekten av webbläsar-cookie-begränsningar för att förbättra datainsamlingen för Adobe Analytics.
translation-type: tm+mt
source-git-commit: 07c76cea1f6fd64957fd4fd20bc5187976f3c14c
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 2%

---


# Alternativ för att minska effekten av webbläsar-cookie-begränsningar

I det här dokumentet beskrivs hur du bevarar beständig besöksidentifiering i olika egenskaper och lösningar när de flesta webbläsare implementerar spårningsförebyggande åtgärder för cookies.

Adobe Analytics förlitar sig på cookies från första part för att registrera en besökares aktivitet på plats. Analyserna bygger också på cookies från tredje part för att förstå en besökares aktivitet utanför webbplatsen, till exempel aktivitet på andra domäner du äger. Cookies från tredje part blockeras i många webbläsare och är i stort sett inte tillgängliga i och med att Chrome kommer att ta bort stödet (som planeras till 2022). Cookies från första part tillåts i alla webbläsare men har en begränsad förfallotid för Safari och andra webbläsare under Apples [ITP tracking prevent](https://webkit.org/tracking-prevention)-åtgärder. Mer information om aktuella begränsningar för webbläsarcookies finns i &quot;[Adobe Analytics och webbläsarcookies](cookies.md).

Dessa begränsningar i webbläsaren innebär en bredare övergång från anonym tredje parts spårning till explicit informationsutbyte mellan användare och varumärken som de litar på. För att stödja detta har Adobe möjlighet att komplettera traditionella cookies genom att inkludera varaktiga identifierare som samlats in via sina egna relationer.

## Customer Journey Analytics och Cross Device Analytics

[Med Adobe Customer Journey ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) Analytics och  [Cross-Device ](/help/components/cda/overview.md) Analytics kan användare inkludera varaktiga identifierare, till exempel hashade inloggningar, utöver cookies:

* **Customer Journey** Analytics möjliggör flerkanalsanalys i Analysis Workspace genom integrering med Adobe Experience Platform. Den konsoliderar kunddata online och offline som är tillgängliga för dig i Experience Platform vid frågetiden, med valfritt ID.

* **Enhetsövergripande** analys identifierar hur digitala enheter mappas till människor och sammanfogar användarresan över alla ID:n med Adobe Experience Platform identitetstjänst. Det använder antingen Adobe Experience Cloud Device Co-op-diagrammet, ett privat enhetsdiagram eller fältbaserad sammanfogning.

## Datainsamling på serversidan

Samling på serversidan ger flexibilitet att tillhandahålla en egen identifierare i stället för att förlita sig på webbläsarmekanismer för att ställa in cookies.

Du kan importera data på serversidan till Analytics med antingen [API:t för datainmatning](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) eller API:t [för datainmatning i grupp](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). En jämförelse av de två API:erna finns i &quot;[Vilket Adobe Analytics-verktyg ska jag använda](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html).&quot;

## Mer information

Mer information om hur du kan gå över från cookies från tredje part finns i &quot;[Köpa och hålla kvar kunder i en cookiefri värld med Adobe](https://business.adobe.com/solutions/cookieless.html)&quot; och i &quot;[Fundera bortom cookie-filen från tredje part: Din fullständiga guide till en värld utan cookies från tredje part](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).&quot;

>[!MORELIKETHIS]
>
>[Adobe Analytics och webbläsarcookies](cookies.md)
