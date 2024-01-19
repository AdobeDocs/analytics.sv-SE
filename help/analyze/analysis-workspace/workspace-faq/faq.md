---
description: Vanliga frågor om arbetsytan
title: Vanliga frågor och felsökningsarbetsyta
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 25%

---

# Frågor och svar

+++Vilka är förutsättningarna för att använda Analysis Workspace?
[Skicka data till Adobe Analytics med Adobe Analytics-tillägget](/help/implement/launch/validate-publish-prod.md): Analysis Workspace kräver en fungerande implementering. Se till att din organisation skickar data till Adobe innan du använder verktyget. Andra implementeringar, som till exempel äldre manuella implementeringar, kan också fungera.
+++

+++Vilka är kraven för administration och åtkomst för Analysis Workspace?
Se [Administrationskrav](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++Kommer Analysis Workspace att påverka datainsamlingen?
Eftersom Analysis Workspace är ett rapportverktyg påverkar det inte datainsamlingen. Du kan dra komponenter till ett projekt för att se vad som fungerar utan att oroa dig för följderna. Dra olika kombinationer av mått och mätvärden till arbetsyteprojektet för att se vad som är tillgängligt för dig. Om du av misstag drar en ogiltig komponent till Workspace-projektet eller vill gå bakåt ett steg trycker du på Ctrl+Z (Windows) eller Kommando+Z (Mac) för att ångra den senaste åtgärden. Du kan också börja från början genom att klicka på **[!UICONTROL Project]** > **[!UICONTROL New]** i den övre vänstra menyn.
+++

+++Hur många rapportsviter kan visas i ett Analysis Workspace-projekt?
Nu kan du skapa projekt i Analysis Workspace med data från fler [flera rapportsviter](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html).
+++

+++Hur implementerar man Analysis Workspace?
Ingen särskild implementering krävs. Analysis Workspace är tillgängligt för alla företag med Analytics Standard eller Premium. Standardbehörigheter för innehåll (till exempel rapportsviter och projektkomponenter) gäller, och för att strukturera och dela projekt. Se [Krav för administration och åtkomst](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++Ändrar Analysis Workspace förkonfigurerade rapporter i Adobe Analytics?
Nej. Eftersom det här är en separat miljö finns det inga ändringar i dina befintliga eller förkonfigurerade rapporter i Adobe Analytics. Du kan fortfarande använda Report Builder-standardrapporter med Analysis Workspace.
+++

+++Kan jag använda Analysis Workspace som Data Warehouse?
Analysis Workspace rekommenderas inte för bulkdataexport. Det är en visualiseringsarbetsyta som skapar kontrollpanelsliknande analysprojekt.
+++

+++Hur kan jag optimera prestandan för Analysis Workspace?
Se [Optimera prestanda](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md).
+++

+++Hur kommer data in i ditt Analysis Workspace-projekt?
Se den här videon:

>[!VIDEO](https://video.tv.adobe.com/v/31072/?quality=12)

+++

+++ Hur spårar jag arbetsytans användning?

Se den här videon om loggspårning av användningsloggar för Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/29768/?quality=12)

+++

+++När jag drar ett mätresultat över står det&quot;Ogiltiga data&quot;. Hur löser jag det här problemet?
Ogiltiga data innebär att Adobe inte kan returnera data med den kombination av mått och mätvärden som används i rapporten. Två mätvärden som staplas ovanpå varandra kan till exempel inte returneras som data, eftersom det inte finns något sätt att visa två mätvärden på det sättet. Istället placerar du mätvärdena sida vid sida.
+++

+++När jag drar ett mätresultat över ser jag inga verkliga data - bara nollor. Hur felsöker jag det här problemet?
Om du har skapat en rapport om arbetsytan men det inte finns några data kan du kontrollera några saker:

* Kontrollera att rapportsviten är ifylld med data.
* Om du tillämpade ett segment i rapporten kanske segmentvillkoren inte matchar några data. Prova med att ta bort segmentet eller justera segmentdefinitionen.
* Kontrollera datumintervallet i det övre högra hörnet och se till att det har ett förväntat värde.
* Navigera till webbplatsen och använd [Felsökning](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) för att validera att data samlas in.
+++
