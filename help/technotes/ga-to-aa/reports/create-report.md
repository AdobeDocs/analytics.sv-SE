---
title: Skapa en grundläggande rapport i Analysis Workspace
description: Lär dig hur du skapar en grundläggande rapport i Analysis Workspace i ett format som är avsett för användare som är bekanta med tredjepartsverktyg som Google Analytics.
translation-type: tm+mt
source-git-commit: 099662d021c1919f0760e79154536cfd0e23e959

---


# Skapa en grundläggande rapport i Analysis Workspace för Google Analytics-användare

Analysis Workspace (en av huvudfunktionerna i Adobe Analytics) är ett robust område där användaren kan få insikt i insamlade data. Rapporterna skiljer sig mycket åt mellan Google Analytics och Adobe Analytics:

* Med rapporteringsstrukturen i Google Analytics kan ni välja en viss typ av data, till exempel geopositionering eller hänvisningstrafik. Plattformen använder en prefabricerad rapportvy baserad på det bästa sättet att se dessa data.
* Rapportstrukturen i Analysis Workspace ger en tom arbetsyta, vilket ger större flexibilitet när det gäller att uppfylla de exakta rapporteringsbehoven.

Eftersom Analysis Workspace fungerar mer som en arbetsyta än prefabricerade rapporter, är det bara att återskapa rapporter från Google Analytics som handlar om att använda rätt visualiseringar och komponenter.

## Nyckeltermer som används i arbetsytan

* **Paneler** är de övergripande byggstenarna för arbetsytan. I nästan alla scenarier används en friformspanel.
* **Visualiseringar** består av alla frihandspaneler. Syftet med dem är att representera data i olika format. För det mesta är formatet en tabell, men för det andra kan det vara t.ex. en munk eller ett linjediagram. Många rapporter i Google Analytics består av två visualiseringar: ett linjediagram och frihandstabell.
* **Komponenterna** placeras i en visualisering för att returnera data. Komponenter kan blandas på många olika sätt för att uppfylla rapporteringsbehoven.
   * **Dimensioner** är variabelvärden och innehåller vanligtvis text. Exempel är sidnamn, referent eller land. De listas oftast som rader i en tabell.
   * **Mätvärden** betecknar vanligtvis en händelse eller konvertering av någon typ. Exempel är vanliga händelser som en sidvy eller något mer viktigt som ett köp eller en registrering. De ses oftast som kolumner i tabeller för att visa hur många gånger händelsen inträffade per dimension.
   * **Segment** är en delmängd av era data och fungerar på ungefär samma sätt som segment i Google Analytics. Med dem kan du skapa anpassade filter, så att du kan fokusera på en viss del av dina data.
   * **Med datumintervall** kan du ordna data efter när en händelse inträffar. De utgör ryggraden i att visa trender över tid och kombineras vanligtvis med ett mätvärde.

## Skapa en grundläggande rapport i arbetsytan

Skapa en Alla sidor-rapport (liknande den i Google Analytics) genom att dra de högra komponenterna till en arbetsyta.

1. Logga in på [experienceCloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
1. Klicka på ikonen med nio kvadrater i det övre högra hörnet och klicka sedan på den färgade Analytics-logotypen.
1. Klicka på Arbetsyta i det övre navigeringsfältet.
1. Klicka på knappen Skapa nytt projekt.
1. Kontrollera att Tomt projekt är markerat i det modala popup-fönstret och klicka sedan på Skapa.
1. Till vänster visas en lista med mått, mått, segment och datumintervall. Leta reda på siddimensionen (färgad orange) och dra den till arbetsytan med etiketten &#39;Släpp en dimension här&#39;.
1. En rapport över de översta sidorna för den här månaden visas. Analysis Workspace fyller automatiskt i rapporten med [förekomstmåttet](/help/components/c-variables/c-metrics/metrics-occurrences.md) .
1. En tabell i Google Analytics innehåller vanligtvis 7-8-mätvärden. Leta upp mätvärdet för studsfrekvens (grönt) och dra det intill rubriken för förekomstmått. Om du drar studs-/hastighetsmåtten bredvid Förekomster visas båda måtten sida vid sida.
1. Många mätvärden kan placeras sida vid sida genom att dra mätvärden bredvid befintliga mätrubriker. Mer information om hur du hämtar mätvärden som vanligtvis används i Google Analytics finns i [ofta använda mätvärden](common-metrics.md) .

   ![Nytt mått](/help/technotes/ga-to-aa/assets/new_metric.png)

## Börja med en färdig rapportmall i Workspace

Skapa mallen Innehållsförbrukning (liknar rapporten Alla sidor i Google Analytics) genom att gå till en projektmall.

1. Klicka på knappen Skapa nytt projekt.
1. Leta upp och dubbelklicka på ikonen &quot;Innehållsförbrukning (webb)&quot; som finns under Alla mallar.
1. Bläddra bland de visualiseringar som har färdigbyggts: Sidflöde på ingångssidan, tabell över översta sidor, sidflöde för att avsluta, avsnittsflöde för startplats och tabell över övre webbplatsavsnitt.

   ![Mallval](/help/technotes/ga-to-aa/assets/content_consumption_template.png)

## Experimentera med verktyget

Eftersom Analysis Workspace är ett rapportverktyg har det ingen effekt på datainsamlingen. Det får inga följder om man utan åtskillnad drar komponenter till ett projekt för att se vad som fungerar. Dra olika kombinationer av mått och mätvärden till arbetsyteprojektet för att se vad som är tillgängligt för dig.

Om du av misstag drar en ogiltig komponent till arbetsyteprojektet eller vill gå tillbaka ett steg, trycker du på Ctrl+Z (Windows) eller Cmd+Z (Mac) för att ångra den senaste åtgärden. Du kan också börja med en ren skiva genom att klicka *[!UICONTROL Project]>[!UICONTROL New]*i den övre vänstra menyn.

Adobe har placerat en mängd funktioner i Analysis Workspace på snabbmenyn för högerklickning. De flesta visualiseringar och komponenter kan högerklickas för mer detaljerad analys och interaktion. Överväg att högerklicka på komponenter på arbetsytan för att se vilka alternativ som är tillgängliga.

## Förstå vilka dimensioner och mätvärden som ska användas

Om du känner dig bekväm med Analysis Workspace och vill återskapa en specifik rapport som vanligtvis visas i Google Analytics kan du hitta rapporten på deras respektive sida:

* [Realtidsrapporter](realtime-reports.md)
* [Målgruppsrapporter](audience-reports.md)
* [Anskaffningsrapporter](acquisition-reports.md)
* [Beteenderapporter](behavior-reports.md)
* [Konverteringsrapporter](conversions-reports.md)
