---
title: Arbetsflöde för kampanjspårning
description: Använd Adobe Analytics för att spåra era marknadsföringssatsningar.
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '574'
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

Alla organisationer har olika behov av att spåra koder. Vissa organisationer kan ha minimala behov där manuellt skapade spårningskoder är mer än tillräckliga. Andra organisationer kanske vill ha större kontroll över spårning och har flera system för att skapa önskade spårningskoder. Om din organisation använder Google Analytics tillsammans med Adobe Analytics kan det hända att din organisation redan har en `utm`-spårningskodmodell upprättad.

Oberoende av hur du väljer att skapa eller generera spårningskoder kan organisationen lättare gruppera spårningskoder när du vill rapportera på ett enhetligt sätt. Med konsekventa strukturerade spårningskoder kan du skapa [klassificeringsregler](/help/components/classifications/crb/classification-rule-builder.md) så att du får insikt i kategoriseringen av prestanda.

## Lägg till önskad spårningskod i en URL

När du har fått det önskade värdet för spårningskod kan du lägga till det i alla länkar som du publicerar online, till exempel annonser, sociala medier eller e-post. Dessa spårningskoder läggs vanligtvis till i en länks frågesträng. Vilken frågesträngsparameter du använder beror på organisationens spårningskrav. En vanlig frågesträngsparameter är `cid` (kort för kampanj-ID). Vissa organisationer som även använder Google Analytics kan redan ha flera frågesträngsparametrar som `utm_source`, `utm_medium` och andra.

Om du lägger till frågesträngar i en länk i ett e-postmeddelande ser det ut ungefär så här:

```text
https://example.com?cid=EM989027
```

## Inkludera kampanjvariabler i implementeringen

Adobe Analytics har en dedikerad [spårningskod](/help/components/dimensions/tracking-code.md) som du kan använda för att mäta olika marknadsföringsaktiviteter i organisationen. Olika organisationer kan dock ha olika spårningskrav. Det är viktigt att referera till din organisations [lösningsdesigndokument](../prepare/solution-design.md) för att konsekvent spåra rätt värden i rätt variabler.

Om din organisation ännu inte har ställt in kampanjspårning kan du justera implementeringen för att ställa in variabeln [`campaign`](/help/implement/vars/page-vars/campaign.md). Läs metoden [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) om du vill veta mer om hur du kan samla in parametervärden för frågesträngar som är specifika för din organisations implementering.

Om din organisation samlar in `utm` frågesträngar kan du antingen:

* Skicka alla `utm` frågesträngar till spårningskoddimensionen som sammanfogade värden. Du kan sedan använda [klassificeringsregler](/help/components/classifications/crb/classification-rule-builder.md) för att skapa ytterligare dimensioner som fokuserar på varje `utm` -parameter. Den här metoden har en mer komplex inlärningskurva, men använder inga extra eVars-variabler.
* Skicka varje `utm`-frågesträng till en separat [eVar](/help/components/dimensions/evar.md). Den här metoden är enklare att implementera generellt, men kräver att extra eVars används.

## Visa rapporter i Analysis Workspace

När du har konfigurerat implementeringen för att samla in spårningskoddata kan du visa rapporter i Analysis Workspace.

1. Logga in på [Adobe Experience Cloud](https://experience.adobe.com) och välj [!UICONTROL Adobe Analytics].
1. Skapa ett [Workspace-projekt](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).
1. Dra dimensionen [Spårningskod](/help/components/dimensions/tracking-code.md) i listan med komponenter till vänster till arbetsytan.
1. Dra de önskade måtten, till exempel [Besök](/help/components/metrics/visits.md) eller [Beställningar](/help/components/metrics/orders.md), till höger på arbetsytan.

![Kampanjspårningsrapport](../assets/campaign-tracking-report.png)
