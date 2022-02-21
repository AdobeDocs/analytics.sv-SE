---
title: Övergång från en analysplattform från tredje part till Adobe Analytics
description: Lär dig viktiga koncept för att få rapporter som riktar sig till användare som är bekanta med andra plattformar, som Google Analytics.
feature: Third-party Integration
exl-id: e71b12ad-11b7-48a0-8586-f8eb63975479
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 90%

---

# Övergång från en analysplattform från tredje part till Adobe Analytics

I den här guiden presenteras vanliga rapporttyper som lär dig viktiga koncept och arbetsflöden i Adobe Analytics, med fokus på viktiga likheter och skillnader mellan Adobe och andra populära verktyg. Den här guiden är utformad för analytiker som är bekanta med grundläggande digitala analyskoncept, men som är nya i Adobe Analytics. Den förutsätter att organisationen har en fungerande implementering som skickar data till Adobes datainsamlingsservrar. Om organisationen ännu inte har konfigurerat en Adobe Analytics-implementering börjar du med [Adobe Analytics First Admin Guide](/help/admin/admin-console/first-admin-guide.md).

Både Google Analytics och Adobe Analytics är kraftfulla plattformar som ger värdefulla insikter om webbplatsens resultat. De har en egen bearbetningsarkitektur och ett eget användargränssnitt, vilket ger varje plattform unika fördelar. Den här guiden är utformad för att hjälpa en användare som har erfarenhet av Google Analytics att kommunicera med Adobe Analytics.

I Adobe Analytics finns det två sätt att hämta grundläggande rapporter efter inloggning på Adobe Experience Cloud:

* **Reports &amp; Analytics** är den historiska metoden för att få fram grundläggande rapporter. Den vänstra menyn innehåller en lista med prefabricerade rapporter, och gör att användaren kan navigera till en rapport som han/hon vill ha och hämta data. Segment och mätvärden kan ge ytterligare anpassningar. Användare som har erfarenhet av Google Analytics-rapporter kanske tycker att den här layouten är bekant.
* **Analysis Workspace** är den metod som för närvarande rekommenderas för att hämta de flesta rapporter. Med den vänstra menyn kan användaren dra och släppa komponenter för att skapa en egen rapport. Det ger mycket större frihet att uppfylla de exakta rapporteringsbehoven. Användare som har erfarenhet av att skapa kontrollpaneler för Google Analytics och anpassade rapporter kanske tycker att den här layouten är bekant.

De flesta rapporter kan skapas i båda [!UICONTROL Reports & Analytics] och [!UICONTROL Analysis Workspace]. Vissa rapporter kan dock bara hämtas på en av plattformarna. I de flesta fall rekommenderar Adobe att du använder [!UICONTROL Analysis Workspace], om inte en viss funktion bara finns i [!UICONTROL Reports & Analytics].

## Rekommenderad utbildningsväg

Adobe rekommenderar att du börjar med grunderna i att hämta rapportdata:

* [Skapa en grundläggande rapport i Analysis Workspace för GA-användare](reports/create-report.md)

När du känner till komponenterna i [!UICONTROL Analysis Workspace]kan du lära dig att återskapa de flesta rapporter med rätt komponenter.

* [Skapa realtidsrapporter i Adobe Analytics](reports/realtime-reports.md)
* [Skapa målgruppsrapporter i Adobe Analytics](reports/audience-reports.md)
* [Skapa förvärvsrapporter i Adobe Analytics](reports/acquisition-reports.md)
* [Skapa beteenderapporter i Adobe Analytics](reports/behavior-reports.md)
* [Skapa konverteringsrapporter i Adobe Analytics](reports/conversions-reports.md)

När du har lärt dig att dra nytta av rapporter kan förståelse för [skillnader i bearbetning och arkitektur](processing-differences.md) öka förståelsen för de olika siffror som hämtas med olika plattformar. Det finns även [vanliga frågor](faq.md).
