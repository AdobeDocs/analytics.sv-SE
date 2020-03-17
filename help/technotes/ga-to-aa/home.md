---
title: Övergång från en analysplattform från tredje part till Adobe Analytics
description: Lär dig viktiga koncept för att få rapporter som riktar sig till användare som är bekanta med andra plattformar, som Google Analytics.
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Övergång från en analysplattform från tredje part till Adobe Analytics

I den här guiden presenteras vanliga rapporttyper som hjälper dig att lära dig viktiga koncept och arbetsflöden i Adobe Analytics, med fokus på viktiga likheter och skillnader mellan Adobe och andra populära verktyg. Den här guiden är utformad för analytiker som är bekanta med grundläggande digitala analyskoncept, men som är nya i Adobe Analytics. Det förutsätter att organisationen har en fungerande implementering som skickar data till Adobes datainsamlingsservrar. Om organisationen ännu inte har konfigurerat en Adobe Analytics-implementering börjar du med [Adobe Analytics First Admin Guide](/help/admin/admin-console/first-admin-guide.md).

Både Google Analytics och Adobe Analytics är kraftfulla plattformar som ger värdefulla insikter om webbplatsens resultat. De har en egen bearbetningsarkitektur och ett eget användargränssnitt, vilket ger varje plattform unika fördelar. Den här guiden är utformad för att hjälpa en användare som har erfarenhet av Google Analytics att kommunicera med Adobe Analytics.

I Adobe Analytics finns det två sätt att hämta grundläggande rapporter efter inloggning på Adobe Experience Cloud:

* **Rapporter och analyser** är den historiska metoden för att få fram grundläggande rapporter. Den vänstra menyn innehåller en lista med prefabricerade rapporter, och gör att användaren kan navigera till en rapport som han/hon vill ha och hämta data. Segment och mätvärden kan ge ytterligare anpassningar. Användare som har erfarenhet av Google Analytics-rapporter kanske tycker att den här layouten är bekant.
* **Analysis Workspace** är den metod som för närvarande rekommenderas för att hämta de flesta rapporter. Med den vänstra menyn kan användaren dra och släppa komponenter för att skapa en egen rapport. Det ger mycket större frihet att uppfylla de exakta rapporteringsbehoven. Användare som har erfarenhet av att skapa kontrollpaneler för Google Analytics och anpassade rapporter kanske tycker att den här layouten är bekant.

De flesta rapporter kan skapas i både rapport- och analysarbetsytan. Vissa rapporter kan dock bara hämtas på den ena plattformen eller den andra. I de flesta fall rekommenderar Adobe att du använder Analysis Workspace, såvida inte en viss funktion bara finns i Rapporter och analyser.

## Rekommenderad utbildningsväg

Adobe rekommenderar att du börjar med grunderna i att hämta rapportdata:

* [Skapa en grundläggande rapport i Analysis Workspace för GA-användare](reports/create-report.md)

När du känner till komponenter i Analysis Workspace kan du lära dig att återskapa de flesta rapporter med rätt komponenter.

* [Skapa realtidsrapporter i Adobe Analytics](reports/realtime-reports.md)
* [Skapa målgruppsrapporter i Adobe Analytics](reports/audience-reports.md)
* [Skapa förvärvsrapporter i Adobe Analytics](reports/acquisition-reports.md)
* [Skapa beteenderapporter i Adobe Analytics](reports/behavior-reports.md)
* [Skapa konverteringsrapporter i Adobe Analytics](reports/conversions-reports.md)

Efter att ha lärt sig dra nytta av rapporter kan förståelse för skillnader [i](processing-differences.md) bearbetning och arkitektur hjälpa till att stämma av antalet olika plattformar. Det finns även [vanliga frågor](faq.md) .
