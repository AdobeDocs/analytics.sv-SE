---
description: Så här kommer du igång med Adobe Analytics.
keywords: Analysis Workspace
title: Guiden Komma igång
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '1329'
ht-degree: 98%

---


# Analysis Workspace

Analysis Workspace är ett av Adobes paradverktyg och används för att fatta databaserade beslut i organisationen. Med den vanligaste visualiseringen, friformstabellen, kan du enkelt skapa anpassade rapporter med mått, mätvärden, segment och datumintervall.

## Förutsättningar

[Skicka data till Adobe Analytics med Adobe Experience Platform Launch](/help/implement/launch/validate-publish-prod.md): Analysis Workspace kräver en fungerande implementering. Kontrollera att er organisation skickar data till Adobe innan du använder verktyget. Andra implementeringar, som DTM eller äldre manuella implementeringar, kan också fungera.

## Hämta en grundläggande rankad rapport i Workspace

Hämta en grundläggande rankad rapport med Analysis Workspace. En rankad rapport visar en sammanställd totalvy för varje dimensionsobjekt, med de största värdena först. Den här typen av rapporter är användbara för att se vilka komponenter på webbplatsen som är mest effektiva, till exempel vilka sidor som får mest trafik eller vilka produkter som säljer mest.

1. Logga in på [experiencecloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
2. Klicka på ikonen med nio kvadrater i det övre högra hörnet och klicka sedan på den färgade Analytics-logotypen.
3. Klicka på Workspace i det övre navigeringsfältet.
4. Klicka på knappen Skapa nytt projekt.
5. Kontrollera att Tomt projekt är markerat i det modala popup-fönstret och klicka sedan på Skapa.
6. Till vänster visas en lista med mått, mätvärden, segment och datumintervall. Leta upp måttet Sidor (med orange färg) och dra den till arbetsytan där det står Släpp ett mått här.
7. Tänk på att om rapportsviten innehåller data visas en rapport med de bästa sidorna för den här månaden. Analysis Workspace fyller i rapporten automatiskt med måttet [Förekomster](/help/components/metrics/occurrences.md).
8. Leta reda på måttet Besök (med grön färg) och dra det antingen **över** eller **bredvid** rubriken för måttet Förekomster (undvik att placera det ovanför måttet). Om du drar och släpper måttet Besök över Förekomster ersätts måttet i rapporten. Om du drar och släpper måttet Besök bredvid Förekomster visas båda måtten sida vid sida.
9. Om du vill spara projektet klickar du på *[!UICONTROL Project] > [!UICONTROL Save]* i den övre vänstra menyn.

## Hämta en grundläggande trendrapport i Workspace

Hämta en grundläggande trendrapport med Analysis Workspace. En trendrapport visar en vy med mätvärden över tid för det valda datumintervallet. Den här typen av rapporter är användbara för att identifiera trender över tid och kan användas för att avgöra om de affärsbeslut som fattats är lyckade eller inte. Du kan till exempel titta på en rapport över sidvisningar över tid för att se om en ny webbplatsdesign bidrog till att öka eller minska trafiken.

1. Logga in på [experiencecloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
2. Klicka på ikonen med nio kvadrater i det övre högra hörnet och klicka sedan på den färgade Analytics-logotypen.
3. Klicka på Workspace i det övre navigeringsfältet.
4. Klicka på knappen Skapa nytt projekt.
5. Kontrollera att Tomt projekt är markerat i det modala popup-fönstret och klicka sedan på Skapa.
6. Till vänster visas en lista med mått, mätvärden, segment och datumintervall. Leta upp måttet Sidvisningar och dra det till det lilla utrymmet på arbetsytan där det står Släpp ett mätvärde här. Släpp det inte i det utrymme som är reserverat för mått (åtminstone inte i den här övningen).
7. Tänk på att om rapportsviten innehåller data bör det visas en grundläggande rapport om sidvisningar för den aktuella månaden. Analysis Workspace hämtade automatiskt datumintervallet för dag så att du kan se trenden för sidvisningar för den aktuella månaden.
8. Leta upp datumintervallet för vecka (med lila färg) i listan med datumintervallkomponenter till vänster. Klicka på datumintervallets rubrik för att expandera det och visa alla datumintervallkomponenter eller använd sökfältet.
9. Ersätt datumintervallet genom att dra datumintervallet för vecka över rubriken för datumintervallet för dag på arbetsytan.
10. Tänk på att trendrapporten nu sammanställs per vecka i stället för per dag.
11. Om du vill spara projektet klickar du på *[!UICONTROL Project] > [!UICONTROL Save]* i den övre vänstra menyn.

## Experimentera med verktyget

Eftersom Analysis Workspace är ett rapportverktyg påverkar det inte datainsamlingen. Du kan dra komponenter till ett projekt för att se vad som fungerar utan att oroa dig för följderna. Dra olika kombinationer av mått och mätvärden till Workspace-projektet för att se vad som är tillgängligt för dig.

Om du av misstag drar en ogiltig komponent till Workspace-projektet eller vill gå bakåt ett steg trycker du på Ctrl+Z (Windows) eller Kommando+Z (Mac) för att ångra den senaste åtgärden. Du kan också börja från början genom att klicka på *[!UICONTROL Project] > [!UICONTROL New]* i den övre vänstra menyn.

## Felsökning

**När jag drar ett mätvärde står det ”Ogiltiga data”.**

Ogiltiga data innebär att Adobe inte kan returnera data med den kombination av mått och mätvärden som används i rapporten. Två mätvärden som staplas ovanpå varandra kan till exempel inte returneras som data, eftersom det inte finns något sätt att visa två mätvärden på det sättet. Placera i stället mätvärdena bredvid varandra.

**När jag drar ett mätvärde ser jag inga data, bara nollor.**

Om du har skapat en Workspace-rapport utan problem, men det inte finns några data, kan du kontrollera följande:

* Kontrollera att rapportsviten innehåller data.
* Om du använder ett segment i rapporten kanske segmentvillkoren inte matchar några data. Prova med att ta bort segmentet eller justera segmentdefinitionen.
* Kontrollera datumintervallet i det övre högra hörnet och se till att det har ett förväntat värde.
* Navigera till webbplatsen och använd felsökaren för att bekräfta att data faktiskt samlas in.

## Ytterligare material

* [Versionsinformation för Analysis Workspace](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md): Läs om de senaste funktionerna i verktyget.
* [Analysis Workspace på YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): Lär dig hur du använder de flesta funktionerna i Analysis Workspace via den här omfattande spellistan.
* Produkttips: Dagens tips, tillsammans med korta videoklipp, visas ibland i det nedre högra hörnet av Analysis Workspace. Om du stänger de här tipsen kan du visa dem igen via *[!UICONTROL Help] > [!UICONTROL Tips]* när du vill.
* [Analysis Workspace-community](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace): Diskutera Analysis Workspace med andra användare och rösta på funktioner som du vill se i verktyget.
* Blogginlägg:
   * [Empowering Organizations with Smarter Analysis](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [New Adobe Analytics Capabilities Make Powerful Insights More Accessible](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [5 Tips to Maximize Your Productivity with Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [Faster Insights with Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [Why You Should Be Using Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## Nästa steg

Du kan fördjupa dig i Analysis Workspace på många olika sätt. Här är några grunder som Adobe rekommenderar:

### För slutanvändare som vill lära sig mer om att använda Analysis Workspace

* [Information om gränssnittet i Workspace](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md): Nu när du har skapat en grundläggande rapport kan du bekanta dig mer med resten av gränssnittet.
* [Visualiseringar i Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md): Friformstabeller är bara en av många visualiseringar i Analysis Workspace. Läs mer om hur du använder andra visualiseringar, som linjediagram, stapeldiagram och geokartor.
* [Mått i Workspace](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): Läs mer om vad mått är och hur du använder dem i annat än rankade rapporter.
* [Mätvärden i Workspace](/help/analyze/analysis-workspace/components/apply-create-metrics.md): Läs mer om vad mätvärden är och hur du använder dem i andra delar av friformstabeller.
* [Introduktion till segmentering](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md): Läs mer om vad segment är och hämta en grundläggande rapport med ett segment.
* [Datumintervall i Workspace](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): Läs mer om relativa och rullande datum och använd dem i Workspace-projekt.
* Dela projekt i Workspace: Visa kollegorna det fantastiska Workspace-projektet du har skapat.
* [(Avancerat) Paneler i Workspace](/help/analyze/analysis-workspace/c-panels/panels.md): Använd avancerade funktioner i Workspace, till exempel funktioner för attribuering och segmentjämförelser.

### För analytiker och administratörer som vill förbättra kvaliteten på Workspace i organisationen

* [Behörigheter för Analysis Workspace](https://docs.adobe.com/content/help/sv-SE/core-services/interface/manage-users-and-products/admin-getting-started.html): Tilldela användarbehörigheter till Workspace via Adobe Admin Console.
* [Mallar i Workspace](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md): Skapa mallar så att kollegorna kan börja med ett projekt som passar deras behov.
* [Anpassa Workspace](/help/analyze/analysis-workspace/curate-share/curate.md): Skapa ett projekt som begränsar de tillgängliga komponenterna, så att Workspace blir lättare att använda för dem som inte är vana vid verktyget.
