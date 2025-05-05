---
title: Report Builder - översikt
description: Beskriver Report Builder funktioner
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: b6f2b1f5-8790-4342-85c8-524fdf346073
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 1%

---

# Report Builder - översikt

Det nya Javascript Report Builder-tillägget som ursprungligen endast fanns i Customer Journey Analytics introduceras nu också i Adobe Analytics. Den här nya versionen har flera fördelar:

- Hitta insikter i Excel snabbare och enklare med förbättrade arbetsflöden för att skapa och hantera datablock, inklusive större flexibilitet för datablock
- Plattformsoberoende: du behöver inte längre logga in på den virtuella datorn för att använda Report Builder eftersom vi nu har stöd för PC, Mac och Excel Online
- Mindre tid att vänta på att datablock ska återvända tack vare API 2.0-uppgradering
- Högre hastighet

Användare av verktyget Legacy Report Builder kan [konvertera äldre arbetsböcker](/help/analyze/report-builder/convert-workbooks.md) till den nya Report Builder.

Med Report Builder kan du enkelt skapa, redigera och uppdatera anpassade rapporter med hjälp av Adobe Analytics-data. Med Report Builders enkla och flexibla dra-och-släpp-gränssnitt kan ni skapa komplexa datafrågor och anpassade rapporter från Adobe Analytics-data, allt i Excel.

Med Report Builder kan man

- Referera befintliga kalkylbladsceller för att få perfekt radordning, datumintervall eller filter
- Skapa anpassade datum med kalender, cellreferenser eller matematik för datum
- Designa tabeller och visualiseringar med välbekanta formateringsverktyg från Excel

## Använda äldre Report Builder och nya Report Builder sida vid sida

Du kan fortfarande använda båda versionerna av Report Builder, med följande förbehåll:

- Använd inte båda Report Builder-versionerna i samma fil samtidigt. De utesluter varandra.
- Du kan fortfarande använda äldre Report Builder i äldre arbetsböcker och den nya Report Builder i nya arbetsböcker.
- Dessutom kan du automatiskt [konvertera äldre arbetsböcker](/help/analyze/report-builder/convert-workbooks.md) till det nya Report Builder-formatet. Innan du gör det, duplicera och byt namn på filen.

## Äldre Report Builder-funktioner som inte stöds i nya Report Builder

När funktionen för äldre Report Builder jämförs med det nya Report Builder-tillägget är vissa funktioner inte längre tillgängliga:

- Förfrågningar i realtid

- Sökväg-/bortfallsrapportering

- FTP-alternativ för schemalagda rapporter

- Mätvärden för besökare. Följande mätvärden konverteras till &quot;unika besökare&quot;, även om rapportresultatet kanske inte är en exakt matchning: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly` `visitorsquarterly`, och `visitorsyearly`. Detta gäller även för `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly`och `mobilevisitorsyearly`.

## Vanliga användningsfall

- **Dataextrahering**: Med Adobe Report Builder kan du extrahera data från Adobe Analytics till Excel. Du kan skapa anpassade rapporter och frågor för att hämta specifika datapunkter som är relevanta för din analys.

- **Anpassad rapportering**: Du kan designa och formatera anpassade rapporter i Excel för att passa dina specifika rapporteringsbehov. Detta är särskilt användbart för att skräddarsy rapporter till olika intressenter.

- **Ad-hoc-analys**: Användare kan snabbt generera ad-hoc-rapporter för att besvara specifika frågor eller utforska datatrender utan att behöva gå igenom en lång process för att skapa rapporter.

- **Instrumentpanelsarbete**: Data som extraheras från CJA kan användas för att skapa Excel-baserade instrumentpaneler och visualiseringar för en översikt över nyckeltal (KPI) på hög nivå.

- **Dela insikter**: Du kan dela Excel-rapporter och insikter med teammedlemmar eller intressenter som kanske inte har direktåtkomst till CJA.

## Översiktsvideo

>[!IMPORTANT]
>
>I den här översiktsvideon visas Report Builder användargränssnitt i Customer Journey Analytics. En del av användargränssnittet och terminologin skiljer sig åt. Annars är användarupplevelsen identisk.


>[!BEGINSHADEBOX]

En demovideo finns [i Översikt över](https://video.tv.adobe.com/v/337569?quality=12&learn=on){target="_blank"} VideoCheckedOut![&#128279;](/help/assets/icons/VideoCheckedOut.svg) Report Builder.

>[!ENDSHADEBOX]

Du kan ladda ned Report Builder från [Microsoft Store](https://appsource.microsoft.com/en-us/product/office/WA200003101?tab=Overview).
