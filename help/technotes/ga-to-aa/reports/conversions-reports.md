---
title: Konverteringsrapporter i Adobe Analytics
description: Lär dig hur du använder konverteringsrapporter i Adobe Analytics.
feature: Third-party Integration
exl-id: 315b7dc0-1cd9-4beb-8203-88e205375f84
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 0%

---

# Konverteringsrapporter

En &#39;konvertering&#39; är en åtgärd som en besökare utför på er webbplats som direkt översätts till organisationens nyckelindikatorer. Konverteringsrapporter visar detaljer om hur besökare konverterar.

Den här sidan förutsätter att användaren har grundläggande kunskaper i Analysis Workspace. Se [Skapa en grundläggande rapport i Analysis Workspace för användare av Google Analytics](create-report.md) om du ännu inte känner till verktyget i Adobe Analytics.

## Målrapporter

Med mål kan användare av Google Analytics definiera konverteringen av en webbplats. De är standardmetoden för att skapa kanaler, omvänt beteendeflöde, flerkanalskanaler och attribuering. Mål i Google Analytics är inte retroaktiva och kan bara ställas in på adminsidan. Dessutom baseras de endast på en sida, en händelse, en använd tid eller ett genomsnittligt antal sidor.

I Adobe Analytics behövs inte begreppet mål eftersom mätvärden kan användas i alla sammanhang. Så länge implementeringen klarar de händelser du vill spåra kan du justera alla konverteringsrapporter och omedelbart få resultat för historiska data.

### Trattvisualisering

Med trattvisualiseringsrapporten kan analytiker fokusera på en viss serie steg som krävs för konvertering. Innan en besökare gör ett inköp måste han eller hon till exempel gå till kundvagnen, fakturerings- och leveranssidan, betalningssidan och ordergranskningssidan.

I Analysis Workspace kan dessa data visas med hjälp av bortfallsvisualiseringen.

1. Klicka på visualiseringsikonen till vänster och dra en utfallsvisualisering till arbetsytan ovanför frihandstabellen
2. Klicka på komponentikonen till vänster och leta upp **Sidor** dimension.
3. Klicka på pilikonen bredvid siddimensionen för att visa sidvärden. Dimensionen är gul.
4. Leta reda på sidan som du vill ska fungera som första kontaktyta och dra den till utrymmet med etiketten Lägg till pekpunkt i visualiseringen.
5. Fortsätt lägga till önskade kontaktytor genom att dra sidvärden till visualiseringen.

Utfallsvisualiseringen är inte begränsad till bara siddimensionen. Alla dimensioner, mätvärden och segment kan användas för att skräddarsy utfallsrapporten efter organisationens behov.

![Utfallsvisualisering](/help/technotes/ga-to-aa/assets/fallout.png)

## E-handelsrapporter

E-handelsrapporter används vanligtvis av webbplatser som säljer produkter eller tjänster för att mäta beställningar och intäkter på inköpta artiklar. Den här funktionen är tillgänglig i Adobe Analytics och kallas för produktrapporter.

Både e-handelsrapporter i Google Analytics och produktrapporter i Adobe Analytics kräver anpassade implementeringsändringar. Se [Produkter](/help/components/dimensions/product.md) dimension i användarhandboken för komponenter om du vill ha mer information.

## Flerkanalstrattrapporter

Flerkanaliga trattrapporter ger ytterligare marknadsföringskanaldata utöver vad förvärvsrapporter erbjuder. Dessa rapporter fokuserar på hur besökarna konverterar, i stället för hur besökarna kommer till er webbplats.

>[!NOTE]
>
> Användningen av flerkanalsrapporter i Adobe Analytics kräver både installation av marknadsföringskanaler och en anpassad implementering för att passa produktvariabeln och inköpshändelsen. Adobe rekommenderar att du arbetar med en implementeringskonsult om dessa funktioner ännu inte har konfigurerats för rapportsviten.

### Flerkanals - assisterade konverteringar

Med hjälp av konverteringar visas hur många gånger varje kanal hanteras med en konvertering. I Analysis Workspace **Orderassistenter** kan användas.

1. På menyn Komponenter letar du reda på **Marknadsföringskanal** och dra den till det stora frihandsritbordet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra **Orderassistenter** mätvärden ovanpå de automatiskt skapade **Förekomster** metrisk rubrik som ersätter den. Ytterligare mätvärden kan dras till arbetsytan om det behövs.

### Flerkanals - övre konverteringsbanor

I rapporten med de översta konverteringssökvägarna visas de översta kanalsökvägarna som en användare tar innan konverteringen. Analysis Workspace använder en flödesrapport för att visualisera toppkonverteringsbanor.

1. Klicka på panelikonen till vänster och dra en attributpanel ovanför frihandstabellen.
2. Klicka på ikonen Komponenter till vänster och leta upp **Marknadsföringskanal** och dra den till rutan Lägg till Dimension.
3. Leta upp konverteringshändelsen under Metrisk (t.ex. Beställningar) och dra den till rutan med etiketten &quot;Lägg till mått&quot;. Observera att beräknade värden inte stöds för attributpanelen.
4. Klicka på Skapa.
5. Leta reda på visualiseringen för kanalflöde i den resulterande rapporten. Det här flödet visar de viktigaste sökvägarna en besökare rörde före ett köp.

Denna flödesvisualisering är interaktiv. Klicka på varje kanal för att utöka flödet i båda riktningarna.

![Flödesvisualisering](/help/technotes/ga-to-aa/assets/flow.png)

### Flerkanals - tidsfördröjning

I tidsfördröjningsrapporten visas hur lång tid det tog för en besökare att konvertera på webbplatsen. I Analysis Workspace är dessa data tillgängliga via **Dagar före första köpet** dimension. Den är bara tillgänglig i samband med en korrekt implementerad köphändelse.

1. På menyn Komponenter letar du reda på **Dagar före första köpet** och dra den till det stora frihandsritbordet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra önskade mätvärden till arbetsytan bredvid de automatiskt skapade **Förekomster** mätvärden. Se [Guide för översättning av mått](common-metrics.md) om du vill ha mer information om hur du får fram respektive mätvärden.

Adobe rekommenderar att du använder **Beställningar**, **Enheter**, eller **Intäkter** mätvärden med den här dimensionen.

För andra typer av konverteringar, inklusive anpassade händelser, finns **Tid före händelse** dimension är tillgänglig. Den visar hur lång tid det tog för en besökare att utlösa händelsen inom besöket i minuter.

1. På menyn Komponenter letar du reda på **Tid före händelse** och dra den till det stora frihandsritbordet med etiketten &#39;Släpp en Dimension här&#39;.
2. Dra önskade mätvärden till arbetsytan bredvid de automatiskt skapade **Förekomster** mätvärden. Se [Guide för översättning av mått](common-metrics.md) om du vill ha mer information om hur du får fram respektive mätvärden.

Adobe rekommenderar att du använder den här dimensionen tillsammans med anpassade händelser eller köphändelser.

### Flera kanaler - längd på bana

I rapporten om sökvägslängd visas antalet kanaler som berördes före en konverteringshändelse. I Analysis Workspace innehåller attributpanelen dessa data i en av dess visualiseringar.

1. Klicka på ikonen Paneler till vänster och dra en attributpanel ovanför frihandstabellen
2. Klicka på ikonen Komponenter till vänster och leta upp **Marknadsföringskanal** och dra den till rutan Lägg till Dimension.
3. Leta upp konverteringshändelsen under Metrisk (t.ex. Beställningar) och dra den till rutan med etiketten &quot;Lägg till mått&quot;. Observera att beräknade värden inte stöds för attributpanelen.
4. Klicka på Skapa.
5. Leta reda på visualiseringen &#39;Touchpoints per Journey&#39; i den resulterande rapporten. Det här histogrammet visar antalet kanaler som en besökare rörde före ett köp.
