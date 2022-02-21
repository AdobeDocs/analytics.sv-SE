---
title: Skapa en grundläggande rapport i Analysis Workspace
description: Lär dig hur du skapar en grundläggande rapport i Analysis Workspace i ett format som riktar sig till användare som är bekanta med verktyg från tredje part som Google Analytics.
feature: Third-party Integration
exl-id: 513da3f1-ad24-4d5b-bc35-dbcd3694cbdf
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 18%

---

# Skapa en grundläggande rapport i Analysis Workspace för användare av Google Analytics

Analysis Workspace (en av huvudfunktionerna i Adobe Analytics) är ett robust område där man kan få insikt i insamlade data. Rapporteringen är mycket annorlunda mellan Google Analytics och Adobe Analytics:

* Med rapportstrukturen i Google Analytics kan du välja en viss typ av data, till exempel geopositionering eller hänvisningstrafik. Plattformen använder en prefabricerad rapportvy baserad på det bästa sättet att se dessa data.
* Rapporteringsstrukturen i Analysis Workspace ger en tom arbetsyta, vilket ger större flexibilitet när det gäller att uppfylla de exakta rapporteringsbehoven.

Eftersom Analysis Workspace fungerar mer som en arbetsyta än prefabricerade rapporter är det bara att återskapa rapporter från Google Analytics som handlar om att använda rätt visualiseringar och komponenter.

## Nyckeltermer som används i arbetsytan

* **Paneler** är de övergripande byggstenarna i arbetsytan. I nästan alla scenarier används en friformspanel.
* **Visualiseringar** skapa alla frihandspaneler. Syftet med dem är att representera data i olika format. För det mesta är formatet en tabell, men för det andra kan det vara t.ex. en munk eller ett linjediagram. Många rapporter i Google Analytics är gjorda av två visualiseringar: ett linjediagram och frihandstabell.
* **Komponenter** placeras i en visualisering för att returnera data. Komponenter kan blandas på många olika sätt för att uppfylla rapporteringsbehoven.
   * **Dimensioner** är variabelvärden och innehåller vanligtvis text. Exempel är sidnamn, referent eller land. De listas oftast som rader i en tabell.
   * **Mått** innebär vanligtvis en händelse eller konvertering av någon typ. Exempel är vanliga händelser som en sidvy eller något mer viktigt som ett köp eller en registrering. De ses oftast som kolumner i tabeller för att visa hur många gånger händelsen inträffade per dimension.
   * **Segment** är en delmängd av era data och beter sig ungefär som segment i Google Analytics. Med dem kan du skapa anpassade filter, så att du kan fokusera på en viss del av dina data.
   * **Datumintervall** gör att du kan ordna data efter när en händelse inträffar. De utgör ryggraden i att visa trender över tid och kombineras vanligtvis med ett mätvärde.

## Skapa en grundläggande rapport i arbetsytan

Skapa en Alla sidor-rapport (liknande den i Google Analytics) genom att dra de högra komponenterna till en arbetsyta.

1. Logga in på [experiencecloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
1. Klicka på ikonen med nio kvadrater i det övre högra hörnet och klicka sedan på den färgade Analytics-logotypen.
1. Klicka på Workspace i det övre navigeringsfältet.
1. Klicka på knappen Skapa nytt projekt.
1. Kontrollera att Tomt projekt är markerat i det modala popup-fönstret och klicka sedan på Skapa.
1. Till vänster visas en lista med mått, mått, segment och datumintervall. Leta reda på siddimensionen (färgad orange) och dra den till arbetsytan med etiketten &#39;Släpp en Dimension här&#39;.
1. En rapport över de översta sidorna för den här månaden visas. Analysis Workspace fyller automatiskt i rapporten med [Förekomster](/help/components/metrics/occurrences.md) mätvärden.
1. En tabell i Google Analytics innehåller vanligtvis 7-8 mätvärden. Leta upp mätvärdet för studsfrekvens (grönt) och dra det intill rubriken för förekomstmått. Om du drar studs-/hastighetsmåtten bredvid Förekomster visas båda måtten sida vid sida.
1. Många mätvärden kan placeras sida vid sida genom att dra mätvärden bredvid befintliga mätrubriker. Se [vanliga mått](common-metrics.md) om du vill ha information om hur du får in mätvärden som används i Google Analytics.

   ![Nytt mått](/help/technotes/ga-to-aa/assets/new_metric.png)

## Börja med en färdig rapportmall i Workspace

Skapa mallen Innehållsförbrukning (liknar rapporten Alla sidor i Google Analytics) genom att öppna en projektmall.

1. Klicka på knappen Skapa nytt projekt.
1. Leta upp och dubbelklicka på ikonen &quot;Innehållsförbrukning (webb)&quot; som finns under Alla mallar.
1. Bläddra bland de visualiseringar som har färdigbyggts: Sidflöde på ingångssidan, tabell över översta sidor, sidflöde för att avsluta, avsnittsflöde för startplats och tabell över övre webbplatsavsnitt.

   ![Mallval](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## Experimentera med verktyget

Eftersom Analysis Workspace är ett rapportverktyg påverkar det inte datainsamlingen. Du kan dra komponenter till ett projekt för att se vad som fungerar utan att oroa dig för följderna. Dra olika kombinationer av mått och mätvärden till Workspace-projektet för att se vad som är tillgängligt för dig.

Om du av misstag drar en ogiltig komponent till Workspace-projektet eller vill gå bakåt ett steg trycker du på Ctrl+Z (Windows) eller Kommando+Z (Mac) för att ångra den senaste åtgärden. Du kan också börja från början genom att klicka på *[!UICONTROL Project] > [!UICONTROL New]* i den övre vänstra menyn.

Adobe har placerat en hel del funktionalitet i Analysis Workspace på snabbmenyn för högerklickning. De flesta visualiseringar och komponenter kan högerklickas för mer detaljerad analys och interaktion. Överväg att högerklicka på komponenter på arbetsytan för att se vilka alternativ som är tillgängliga.

## Förstå vilka dimensioner och mätvärden som ska användas

Om du känner dig bekväm med Analysis Workspace och vill återskapa en specifik rapport som vanligtvis visas i Google Analytics går du till rapporten på respektive sida:

* [Realtidsrapporter](realtime-reports.md)
* [Målgruppsrapporter](audience-reports.md)
* [Anskaffningsrapporter](acquisition-reports.md)
* [Beteenderapporter](behavior-reports.md)
* [Konverteringsrapporter](conversions-reports.md)
