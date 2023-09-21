---
title: Anledning till avanmälan av spårning
description: Förhandsgranskar vilka data som skulle uteslutas om du aktiverade sekretessinställningar.
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# Anledning till avanmälan av spårning

*Den här sidan refererar till [dimension](overview.md) som gör att du kan se möjliga dataeffekter av att aktivera vissa inställningar för Report Suite. Det är inte relaterat till [Adobe Experience Cloud ID-anmälningstjänst](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html).*

Dimensionen Anledning till avanmälan av spårning fungerar som en förhandsgranskning av data som skulle uteslutas om du aktiverade sekretessinställningar. Den här dimensionen används främst för att avgöra om implementeringen skulle påverkas negativt om du aktiverade den [Sekretessinställningar](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) under Report Suite-inställningar.

Vanliga implementeringar ser 1 % eller mindre av den totala trafiken för rapportsviten i den här dimensionen om sekretessinställningarna ännu inte har aktiverats. Procent högre än 1 % av all trafik tyder på ett potentiellt implementeringsproblem som hindrar AppMeasurementet från att ställa in cookies från första part.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar som ännu inte har aktiverats [Sekretessinställningar](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). Om din organisation redan har aktiverat **[!UICONTROL Remove users who have blocked all cookies]** den här dimensionen innehåller inga data för webbläsare både för datorer och mobila enheter.

## Dimensioner

Dimensionerna innehåller `"Cookies disabled by Desktop Browser"` och `"Cookies disabled by Mobile Browser"`.

* **Cookies inaktiverade av datorwebbläsaren**: besökaren blockerade cookies med en webbläsare på datorn, och **[!UICONTROL Remove users who have blocked all cookies on desktop browsers]** är inaktiverat.
* **Cookies inaktiverade av mobilwebbläsaren**: besökaren blockerade cookies med en mobilwebbläsare, och **[!UICONTROL Remove users who have blocked all cookies on mobile browsers]** är inaktiverat.
