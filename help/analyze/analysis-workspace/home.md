---
description: Så här kommer du igång med Adobe Analytics.
keywords: Analysis Workspace
title: Guiden Komma igång
topic: Reports and analytics
uuid: 851feadb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Analysis Workspace

Analysis Workspace är ett av Adobes flaggskeppsverktyg för att fatta databaserade beslut som kan användas i organisationen. Den vanligaste visualiseringen, frihandstabellen, gör att du enkelt kan skapa anpassade rapporter med mått, mätvärden, segment och datumintervall.

## Förutsättningar

[Skicka data till Adobe Analytics med Adobe Experience Platform Launch](/help/implement/launch/validate-publish-prod.md): Användningen av Analysis Workspace kräver en fungerande implementering. Kontrollera att din organisation skickar data till Adobe innan du använder verktyget. Andra implementeringar, som DTM eller äldre manuella implementeringar, fungerar också.

## Hämta en grundläggande rankad rapport i Workspace

Hämta en grundläggande rankad rapport med Analysis Workspace. En rankad rapport visar en sammanställd totalvy över varje dimensionsvärde, med de största värdena först. Den här typen av rapporter är användbara för att se vilka komponenter på din webbplats som är mest effektiva, till exempel vilka sidor som får mest trafik eller vilka produkter som säljer mest.

1. Logga in på [experienceCloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
2. Klicka på ikonen med nio kvadrater i det övre högra hörnet och klicka sedan på den färgade Analytics-logotypen.
3. Klicka på Arbetsyta i det övre navigeringsfältet.
4. Klicka på knappen Skapa nytt projekt.
5. Kontrollera att Tomt projekt är markerat i det modala popup-fönstret och klicka sedan på Skapa.
6. Till vänster finns en lista med mått, mått, segment och datumintervall. Leta reda på siddimensionen (färgad orange) och dra den till arbetsytan där det står &#39;Släpp en dimension här&#39;.
7. Observera att om rapportsviten innehåller data kan du se en rapport som visar de översta sidorna för den här månaden. Analysis Workspace fyllde automatiskt i rapporten med [förekomstmåttet](/help/components/c-variables/c-metrics/metrics-occurrences.md) .
8. Leta reda på Visits-måttet (grönt i färg) och dra det antingen **över** eller **bredvid** måtthuvudet Förekomster (undvik att placera det ovanför måttet). Om du drar Visits-måttet över förekomster ersätts måtten i rapporten. Om du drar Visits-måttet bredvid Förekomster visas båda måtten sida vid sida.
9. Om du vill spara projektet klickar du på *[!UICONTROL Project]>[!UICONTROL Save]*i den övre vänstra menyn.

## Hämta en grundläggande trendrapport i Workspace

Hämta en grundläggande trendrapport med Analysis Workspace. En trendrapport visar en övertidsvy med mätvärden som använder det valda datumintervallet. Den här typen av rapporter är användbara för att identifiera trender över tid och kan användas för att mäta om affärsbeslut som fattas är lyckade eller inte. Du kan till exempel titta på en rapport över sidvisningar som trendas över tid för att se om en ny webbplatsdesign bidrog till att öka eller minska trafiken.

1. Logga in på [experienceCloud.adobe.com](https://experiencecloud.adobe.com) med inloggningsuppgifterna för ditt Adobe ID.
2. Klicka på ikonen med nio kvadrater i det övre högra hörnet och klicka sedan på den färgade Analytics-logotypen.
3. Klicka på Arbetsyta i det övre navigeringsfältet.
4. Klicka på knappen Skapa nytt projekt.
5. Kontrollera att Tomt projekt är markerat i det modala popup-fönstret och klicka sedan på Skapa.
6. Till vänster finns en lista med mått, mått, segment och datumintervall. Leta reda på dimensionen Sidvisning och dra den till det lilla utrymmet på arbetsytan med etiketten &#39;Släpp ett mätvärde här&#39;. Undvik att släppa det i det utrymme som är reserverat för dimensioner (åtminstone för den här övningen).
7. Observera att om rapportsviten innehåller data bör du se en grundläggande rapport om sidvisningar som trendas över den aktuella månaden. Analysis Workspace infogade automatiskt datumintervallet &quot;Dag&quot; så att du kan se trenden för sidvisningar för den aktuella månaden.
8. Leta reda på datumintervallet för vecka (lila) i listan med datumintervallkomponenter till vänster. Klicka på datumintervallets rubrik för att expandera och visa alla datumintervallkomponenter, eller använd sökfältet.
9. Ersätt datumintervallet genom att dra datumintervallet Vecka över datumintervallhuvudet på arbetsytan.
10. Observera att din trendrapport nu är sammanställd per vecka istället för dag.
11. Om du vill spara projektet klickar du på *[!UICONTROL Project]>[!UICONTROL Save]*i den övre vänstra menyn.

## Experimentera med verktyget

Eftersom Analysis Workspace är ett rapportverktyg har det ingen effekt på datainsamlingen. Det får inga följder om man utan åtskillnad drar komponenter till ett projekt för att se vad som fungerar. Dra olika kombinationer av mått och mätvärden till arbetsyteprojektet för att se vad som är tillgängligt för dig.

Om du av misstag drar en ogiltig komponent till arbetsyteprojektet eller vill gå tillbaka ett steg, trycker du på Ctrl+Z (Windows) eller Cmd+Z (Mac) för att ångra den senaste åtgärden. Du kan också börja med en ren skiva genom att klicka *[!UICONTROL Project]>[!UICONTROL New]*i den övre vänstra menyn.

## Felsökning

**När jag drar ett mätresultat över står det&quot;Ogiltiga data&quot;.**

Ogiltiga data innebär att Adobe inte kan returnera data med den kombination av dimensioner och mått som används i rapporten. Två mätvärden som staplas ovanpå varandra kan till exempel inte returneras som data, eftersom det inte finns något sätt att visa två mätvärden på det sättet. Placera i stället måtten sida vid sida.

**När jag drar ett mätresultat över ser jag inga verkliga data - bara nollor.**

Om du har skapat en rapport för arbetsytan men det inte finns några data kan du kontrollera några saker:

* Kontrollera att rapportsviten är ifylld med data.
* Om du använder ett segment i rapporten kanske segmentvillkoren inte matchar några data. Försök att ta bort segmentet eller justera segmentdefinitionen.
* Kontrollera datumintervallet i det övre högra hörnet och se till att det har ett förväntat värde.
* Navigera till webbplatsen och använd Felsökning för att validera att data samlas in.

## Ytterligare resurser

* [Versionsinformation](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md)för Analysis Workspace: Läs om de senaste funktionerna som ingår i verktyget.
* [Analysis Workspace på YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): Lär dig hur du använder de flesta funktionerna i Analysis Workspace via den här omfattande spellistan.
* Produkttips: Dagens tips, tillsammans med korta videoklipp, visas ibland i det nedre högra hörnet av Analysis Workspace. Om de här tipsen avvisas kan du när som helst nå dem fram till *[!UICONTROL Help]>[!UICONTROL Tips]*.
* [Analysis Workspace-community](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace): Diskutera Analysis Workspace med andra användare och rösta på funktioner som du vill se i verktyget.
* Blogginlägg:
   * [Möjliggör för organisationer med smartare analys](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [Nya funktioner i Adobe Analytics gör kraftfulla insikter mer tillgängliga](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [5 tips för att maximera produktiviteten med Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [Snabbare insikter med Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [Varför ska du använda Analysis Workspace?](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## Nästa steg

Det finns många inriktningar på att fördjupa din förståelse av Analysis Workspace. Här är några grunder som Adobe rekommenderar:

### För slutanvändare som vill utöka kunskapen om hur man använder Analysis Workspace

* [Information om gränssnittet](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)för arbetsytan: Nu när du har skapat en grundläggande rapport blir du mer bekant med resten av gränssnittet.
* [Visualiseringar i arbetsytan](visualizations/freeform-analysis-visualizations.md): Frihandsregister är bara en typ av visualisering i Analysis Workspace. Lär dig hur du använder andra visualiseringar, till exempel linjediagram, stolpdiagram och geokartor.
* [Dimensioner i arbetsytan](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): Lär dig mer om vilka dimensioner som är och hur du använder dem i mer än bara rankade rapporter.
* [Mätvärden i arbetsytan](/help/analyze/analysis-workspace/components/apply-create-metrics.md): Läs mer om vad mätvärden är och hur du använder dem i andra delar av frihandstabeller.
* [Introduktion till segmentering](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md): Lär dig mer om vilka segment som är och hämta en grundläggande rapport med ett segment.
* [Datumintervall i arbetsytan](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): Lär dig mer om relativa och rullande datum och använd dem i arbetsyteprojekt.
* Dela projekt i Workspace: Visa dina kollegor det fantastiska Workspace-projekt du skapat.
* [(Avancerade) Paneler i arbetsytan](c-panels/panels.md): Använd avancerade funktioner i Workspace, till exempel Attribution och Segment Comparison.

### För analytiker och administratörer som vill förbättra kvaliteten på arbetsytan i sin organisation

* [Behörigheter](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)för Analysis Workspace: Tilldela användarbehörigheter till arbetsytan via Adobe Admin Console.
* [Skapa ett designdokument](/help/implement/prepare/solution-design.md): Börja planera hur organisationen samlar in ytterligare dimensioner eller mätvärden som är specifika för er webbplats.
* [Mallar i arbetsytan](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md): Skapa mallar så att dina kollegor kan börja med ett projektutrymme som är anpassat efter deras behov.
* [Arbetsyteurval](curate-share/curate.md): Skapa ett projekt som begränsar antalet tillgängliga komponenter så att arbetsytan blir mer tillgänglig för dem som inte är vana vid verktyget
