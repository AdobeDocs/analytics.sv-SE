---
title: Vad är nya Adobe Report Builder?
description: Beskriver de nya funktionerna i Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: 04d663559aa82f93eb59c787f6110bdfd3448099
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 1%

---

# Om nya Adobe Report Builder

Det nya tillägget Javascript Report Builder som ursprungligen endast fanns i Customer Journey Analytics introduceras nu också i Adobe Analytics. Den nya versionen har flera fördelar:

- Hitta insikter i Excel snabbare och enklare med förbättrade arbetsflöden för att skapa och hantera datablock, inklusive större flexibilitet i datablocken
- Plattformsoberoende: ingen mer loggning in på din virtuella dator för att använda Report Builder när vi nu stöder PC, Mac och Excel Online
- Tack vare uppgraderingen av API 2.0 slipper du vänta på att datablocken ska returneras
- Högre hastighet

>[!NOTE]
>
>Arbetsboksplanering för den här versionen av Report Builder på Adobe Analytics har ännu inte släppts, men kommer att vara tillgänglig i början av 2025. Nu kan du komma igång med arbetsböcker som inte kräver schemaläggning.

Användare av verktyget Äldre Report Builder kan [konvertera äldre arbetsböcker](/help/analyze/report-builder/convert-workbooks.md) till nya Report Builder.

Med Report Builder kan du enkelt skapa, redigera och uppdatera anpassade rapporter med Adobe Analytics-data. Med Report Builder enkla och flexibla dra-och-släpp-gränssnitt kan du skapa komplexa datafrågor och anpassade rapporter från Adobe Analytics-data, allt inifrån Excel.

Med Report Builder kan man

- Referera befintliga kalkylbladsceller för att få perfekt radordning, datumintervall eller filter
- Skapa anpassade datum med kalender, cellreferenser eller matematik för datum
- Designa tabeller och visualiseringar med välbekanta formateringsverktyg från Excel

## Använda äldre Report Builder och nya Report Builder sida vid sida

Du kan fortfarande använda båda versionerna av Report Builder med följande caveats:

- Använd inte båda Report Builder-versionerna på samma fil samtidigt. De utesluter varandra.
- Du kan fortfarande använda äldre Report Builder på äldre arbetsböcker och nya Report Builder på nya arbetsböcker.
- Dessutom kan du automatiskt [konvertera äldre arbetsböcker](/help/analyze/report-builder/convert-workbooks.md) till det nya Report Builder-formatet. Duplicera och byt namn på filen innan du gör det.

## Äldre Report Builder-funktioner som inte stöds i nya Report Builder

När funktionen för äldre Report Builder jämförs med det nya tillägget Report Builder är vissa funktioner inte längre tillgängliga:

- Förfrågningar i realtid

- Sökväg-/bortfallsrapportering

- FTP-alternativ för schemalagda rapporter

- Besökarstatistik. Följande mått konverteras till&quot;unika besökare&quot;, även om rapportresultatet kanske inte är en exakt matchning: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` och `visitorsyearly`. Detta gäller även `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` och `mobilevisitorsyearly`.

## Vanliga användningsfall

- **Dataextrahering**: Med Adobe Report Builder kan du extrahera data från Adobe Analytics till Excel. Du kan skapa anpassade rapporter och frågor för att hämta specifika datapunkter som är relevanta för din analys.

- **Anpassad rapportering**: Du kan utforma och formatera anpassade rapporter i Excel efter dina specifika rapporteringsbehov. Detta är särskilt användbart för att skräddarsy rapporter för olika intressenter.

- **Ad-hoc-analys**: Användare kan snabbt generera ad-hoc-rapporter för att besvara specifika frågor eller utforska datatrender utan att behöva gå igenom en lång process för att skapa rapporter.

- **Kontrollpaneler**: Data som extraheras från CJA kan användas för att skapa Excel-baserade instrumentpaneler och visualiseringar för en översikt på hög nivå över nyckelutförandeindikatorer (KPI).

- **Dela insikter**: Du kan dela Excel-rapporter och insikter med teammedlemmar eller intressenter som kanske inte har direkt åtkomst till CJA.

## Översiktsvideo

>[!IMPORTANT]
>
>I den här översiktsvideon visas användargränssnittet Report Builder i Customer Journey Analytics. En del användargränssnitt och terminologi skiljer sig åt. I annat fall är användarupplevelsen densamma.

>[!VIDEO](https://video.tv.adobe.com/v/337569/?quality=12&learn=on)

Du kan hämta Report Builder från [Microsoft Store](https://www.microsoft.com/en-us/store/apps/windows).
