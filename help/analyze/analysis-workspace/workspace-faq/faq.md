---
description: Vanliga frågor om Workspace
title: Vanliga frågor och felsökning av Workspace
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
source-git-commit: b53ef727adc563e05403c50d80bbd0c48bb8a054
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 24%

---

# Frågor och svar

+++Vilka är förutsättningarna för att använda Analysis Workspace?
[Skicka data till Adobe Analytics med Adobe Analytics-tillägget](/help/implement/launch/validate-publish-prod.md): En fungerande implementering krävs för att använda Analysis Workspace. Kontrollera att din organisation skickar data till Adobe innan du använder verktyget. Andra implementeringar, som till exempel äldre manuella implementeringar, kan också fungera.
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

+++Kan jag använda Analysis Workspace för Data Warehouse?
Analysis Workspace rekommenderas inte för bulkdataexport. Det är en visualiseringsarbetsyta som skapar kontrollpanelsliknande analysprojekt.
+++

+++Hur kan jag optimera prestandan för Analysis Workspace?

Se [Optimera prestanda](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md).

+++

+++Hur kommer data in i ditt Analysis Workspace-projekt?

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data till Analysis Workspace](https://video.tv.adobe.com/v/31072?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

+++

+++Hur kan jag spåra användning i Workspace?

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Loggspårning](https://video.tv.adobe.com/v/29768?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

+++

+++När jag drar ett mätresultat över står det&quot;Ogiltiga data&quot;. Hur löser jag det här problemet?

Ogiltiga data innebär att Adobe inte kan returnera data med den kombination av mått och mätvärden som används i rapporten. Två mätvärden som staplas ovanpå varandra kan till exempel inte returneras som data, eftersom det inte finns något sätt att visa två mätvärden på det sättet. Istället placerar du mätvärdena sida vid sida.

+++

+++När jag drar ett mätresultat över ser jag inga verkliga data - bara nollor. Hur felsöker jag det här problemet?

Om du har skapat en rapport om arbetsytan men det inte finns några data kan du kontrollera några saker:

* Kontrollera att rapportsviten är ifylld med data.
* Om du tillämpade ett segment i rapporten kanske segmentvillkoren inte matchar några data. Prova med att ta bort segmentet eller justera segmentdefinitionen.
* Kontrollera datumintervallet i det övre högra hörnet och se till att det har ett förväntat värde.
* Navigera till webbplatsen och använd [Felsökning](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) för att verifiera att data samlas in.


+++

+++Vilka åtgärder kan jag utföra i Analysis Workspace som skrivskyddad användare?
När ett projekt delas som skrivskyddat är alla redigeringsfunktioner och -funktioner helt inaktiverade och mottagarna kan bara ändra listrutan för att använda ett filter på panelen på ett fördefinierat sätt.
+++
