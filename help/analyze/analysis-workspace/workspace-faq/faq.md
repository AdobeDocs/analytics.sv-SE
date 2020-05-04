---
description: Vanliga frågor om arbetsytan
title: Vanliga frågor och felsökningsarbetsyta
translation-type: tm+mt
source-git-commit: 7fbeac0488fbe9b3d10d7c1242f31250f1c7dc16

---


# Frågor och svar

| Fråga | Svar |
|--- |--- |
| Vilka är förutsättningarna för att använda Analysis Workspace? | [Skicka data till Adobe Analytics med Adobe Experience Platform Launch](/help/implement/launch/validate-publish-prod.md): Användningen av Analysis Workspace kräver en fungerande implementering. Kontrollera att din organisation skickar data till Adobe innan du använder verktyget. Andra implementeringar, som DTM eller äldre manuella implementeringar, fungerar också. |
| Vilka är administrations- och åtkomstkraven för Analysis Workspace? | Se [Administrationskrav](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| Påverkar användning av Analysis Workspace datainsamling? | Eftersom Analysis Workspace är ett rapportverktyg har det ingen effekt på datainsamlingen. Det får inga följder om man utan åtskillnad drar komponenter till ett projekt för att se vad som fungerar. Dra olika kombinationer av mått och mätvärden till arbetsyteprojektet för att se vad som är tillgängligt för dig. Om du av misstag drar en ogiltig komponent till arbetsyteprojektet eller vill gå tillbaka ett steg, trycker du på Ctrl+Z (Windows) eller Cmd+Z (Mac) för att ångra den senaste åtgärden. Du kan också börja med en ren skiva genom att klicka *[!UICONTROL Project]>[!UICONTROL New]*i den övre vänstra menyn. |
| Hur många rapportsviter kan visas i ett Analysis Workspace-projekt? | Nu kan du skapa projekt i Analysis Workspace med data från fler [rapportsviter](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html). |
| Hur implementerar man Analysis Workspace? | Ingen särskild implementering krävs. Analysis Workspace är tillgängligt för alla företag med Analytics Standard eller Premium. Standardbehörigheter för innehåll (till exempel rapportsviter och projektkomponenter) gäller, och för att strukturera och dela projekt. Se Krav för [administration och åtkomst](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| Ändrar Analysis Workspace förkonfigurerade rapporter i Adobe Analytics? | Nej. Eftersom detta är en separat miljö finns det inga ändringar i dina befintliga eller förkonfigurerade rapporter i Adobe Analytics. Du kan fortfarande använda standardrapporter för rapporter och analyser samt Report Builder-rapporter med Analysis Workspace. |
| Kan jag använda Analysis Workspace för datalager? | Analysis Workspace rekommenderas inte för massdataexport. Det är en visualiseringsarbetsyta som skapar kontrollpanelsliknande analysprojekt. |
| Hur kan jag optimera prestandan för Analysis Workspace? | Se [Optimera prestanda](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md). |
| Hur fungerar Analysis Workspace jämfört med Ad Hoc Analysis? | Se [Analysis Workspace jämfört med Ad Hoc Analysis](/help/analyze/analysis-workspace/workspace-faq/adhocanalysis-vs-analysisworkspace.md). |

## Felsökning

**När jag drar ett mätresultat över står det&quot;Ogiltiga data&quot;.**

Ogiltiga data innebär att Adobe inte kan returnera data med den kombination av dimensioner och mått som används i rapporten. Två mätvärden som staplas ovanpå varandra kan till exempel inte returneras som data, eftersom det inte finns något sätt att visa två mätvärden på det sättet. Istället placerar du mätvärdena sida vid sida.

**När jag drar ett mätresultat över ser jag inga verkliga data - bara nollor.**

Om du har skapat en rapport för arbetsytan men det inte finns några data kan du kontrollera några saker:

* Kontrollera att rapportsviten är ifylld med data.
* Om du tillämpade ett segment i rapporten kanske segmentvillkoren inte matchar några data. Försök att ta bort segmentet eller justera segmentdefinitionen.
* Kontrollera datumintervallet i det övre högra hörnet och se till att det har ett förväntat värde.
* Navigera till webbplatsen och använd [felsökaren](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html) för att validera att data samlas in.