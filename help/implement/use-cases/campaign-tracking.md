---
title: Arbetsflöde för kampanjspårning
description: Använd Adobe Analytics för att spåra era marknadsföringssatsningar.
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
source-git-commit: c118d42667c4a1af55929834b87d148a5973bed9
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Arbetsflöde för kampanjspårning

Om din organisation vill följa upp resultatet och klickfrekvens för marknadsföringssatsningar kan du använda följande process. Vart och ett av dessa steg har dedikerade avsnitt nedan som innehåller mer information.

1. [Upprätta en process för att generera spårningskod](#establish-a-tracking-code-generation-process)
1. [Lägg till önskad spårningskod i e-postmeddelandet](#add-the-desired-tracking-code-to-the-email)
1. [Konfigurera eller justera implementeringen av Adobe Analytics så att den inkluderar spårningskod](#include-campaign-variables-in-your-implementation)
1. [Visa rapporter i Analysis Workspace](#view-the-reports-in-analysis-workspace)

[Adobe Campaign](https://business.adobe.com/products/campaign/adobe-campaign.html) kan hjälpa er att förenkla vart och ett av dessa steg för att få ut så mycket som möjligt av er marknadsföring. Kontakta din säljare på Adobe för mer information.

## Upprätta en process för att generera spårningskod

Alla organisationer har olika behov av att spåra koder. Vissa organisationer kan ha minimala behov där manuellt skapade spårningskoder är mer än tillräckliga. Andra organisationer kanske vill ha större kontroll över spårning och har flera system för att skapa önskade spårningskoder. Om din organisation använder Google Analytics tillsammans med Adobe Analytics kan din organisation redan ha en `utm` spårningskodmodellen har upprättats.

Oberoende av hur du väljer att skapa eller generera spårningskoder kan organisationen lättare gruppera spårningskoder när du vill rapportera på ett enhetligt sätt. Med konsekventa strukturerade spårningskoder kan du skapa [Klassificeringsregler](/help/components/classifications/crb/classification-rule-builder.md) så att ni kan få insikt i kategoriernas prestanda.

## Lägg till önskad spårningskod i en URL

När du har fått det önskade värdet för spårningskod kan du lägga till det i alla länkar som du publicerar online, till exempel annonser, sociala medier eller e-post. Dessa spårningskoder läggs vanligtvis till i en länks frågesträng. Vilken frågesträngsparameter du använder beror på organisationens spårningskrav; en vanlig frågesträngsparameter är `cid` (kort för kampanj-ID). Vissa organisationer som också använder Google Analytics kanske redan har flera frågesträngsparametrar som `utm_source`, `utm_medium`och andra.

Om du lägger till frågesträngar i en länk i ett e-postmeddelande ser det ut ungefär så här:

```text
https://example.com?cid=EM989027
```

## Inkludera kampanjvariabler i implementeringen

Adobe Analytics har en dedikerad [Spårningskod](/help/components/dimensions/tracking-code.md) som ni kan använda för att mäta olika marknadsföringssatsningar i hela organisationen. Olika organisationer kan dock ha olika spårningskrav. Det är viktigt att hänvisa till din organisations [Lösningsdesigndokument](../prepare/solution-design.md) för att konsekvent spåra rätt värden i rätt variabler.

Om organisationen ännu inte har ställt in kampanjspårning kan du justera implementeringen för att ställa in [`campaign`](/help/implement/vars/page-vars/campaign.md) variabel. Se [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) om du vill lära dig hur du kan samla in parametervärden för frågesträngar som är specifika för implementeringen i din organisation.

Om organisationen samlar in `utm` frågesträngar kan du välja mellan:

* Skicka alla `utm` frågesträngar i spårningskoddimensionen som sammanfogade värden. Du kan sedan använda [Klassificeringsregler](/help/components/classifications/crb/classification-rule-builder.md) för att skapa ytterligare dimensioner som fokuserar på varje `utm` parameter. Den här metoden har en mer komplex inlärningskurva, men använder inga extra eVars-variabler.
* Skicka varje `utm` frågesträng i en separat [eVar](/help/components/dimensions/evar.md). Den här metoden är enklare att implementera generellt, men kräver att extra eVars används.

## Visa rapporter i Analysis Workspace

När du har konfigurerat implementeringen för att samla in spårningskoddata kan du visa rapporter i Analysis Workspace.

1. Logga in på [Adobe Experience Cloud](https://experience.adobe.com) och markera [!UICONTROL Adobe Analytics].
1. Skapa en [Arbetsyteprojekt](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).
1. Dra i komponentlistan till vänster [Spårningskod](/help/components/dimensions/tracking-code.md) till arbetsytans arbetsyta.
1. Dra mätvärdena, till exempel [Besök](/help/components/metrics/visits.md) eller [Beställningar](/help/components/metrics/orders.md) till höger om arbetsytan.

![Kampanjspårningsrapport](../assets/campaign-tracking-report.png)
