---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 3bfa7e7eeac52370b32060c264c408de32a56fc1
workflow-type: tm+mt
source-wordcount: '1528'
ht-degree: 2%

---

# Aktuell versionsinformation för Adobe Analytics (mars 2023)

**Senaste uppdatering**: 5 april 2023

Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner i Adobe Analytics {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Delvis stöd för Activity Map med Web SDK** | Från och med Web SDK version 2.15.0 började vi fylla i data från Activity Map när länkspårning är aktiverat. Detta gör att Web SDK-användare kan få Activity Map-rapportering om de har länkspårning aktiverat med Web SDK och Activity Map som konfigurerats i Analytics.<p>Om du aktiverar länkspårning med Web SDK skickas länkhändelser när en kund navigerar från en sida till nästa. Detta skiljer sig från hur AppMeasurement fungerar och kan eventuellt resultera i extra fakturerbara träffar som skickas till Adobe. Läs mer [här](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html) och [här](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) | Ej tillämpligt | 31 mars 2023 |
| **Dataordlista i Analysis Workspace** | Med Data Dictionary kan både användare och administratörer hålla reda på, hantera och bättre förstå komponenterna (dimensioner, mätvärden) i sin Analytics-miljö. [Läs mer](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 15 mars 2023 | **Tillfälligt otillgänglig** |
| **Dataartiklar på mobilkontrollpaneler** | Med hjälp av databerättelser kan du lägga till flera anpassningsbara detaljvyer till paneler i projekt i Mobile Scorecard. Använd databerättelser för att fördjupa dig i viktiga drivrutiner, relaterade mätvärden och olika steg längs kundresan. Du kan enkelt svepa igenom de här vyerna för att förstå hela artikeln bakom nyckelmätningarna. [Läs mer](/help/analyze/mobile-app/create-scorecard.md#create-data-story) | Ej tillämpligt | 8 mars 2023 |
| **Utgångsdatum för schemalagt projekt** | Du kan ange maximalt förfallodatum för schemalagda projekt till upp till ett år, oavsett schemafrekvens. | Ej tillämpligt | 8 mars 2023 |
| **Länkdelning för projekt (ingen inloggning krävs)** - Endast privat betaversion | <p>Nu kan du dela skrivskyddade länkar till Analysis Workspace-projekt med personer som inte har tillgång till Adobe Analytics. Du kan dela projektlänkar med personer utanför organisationen eller personer inom organisationen som inte är tilldelade Adobe Analytics. [Läs mer](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>Om du vill gå med i den privata betaversionen kontaktar du Adobe Account Team.</p> | 26 april 2023 | Juni 2023 |
| **Uppdateringar för paneldatumintervall** | I Workspace har vi lagt till följande förbättringar:<ul><li>Från och med februari-versionen baseras dimensionsobjekt och förhandsgranskningar av data på panelens datumintervall och inte på de senaste 90 dagarna. </li><li>Alla dimensionsobjekt i listan baseras på data inom panelens datumintervall. Om ett dimensionsobjekt har data utanför datumintervallet kan du visa ytterligare data efter datumintervallet längst ned i listan.</li><li>Dimensioner som inte har data kan visas i den vänstra listen. Klicka på Visa fler alternativ för att visa dimensionsobjekt med data utanför panelens datumintervall.</li><li>Förhandsgranskningar av data i segmentet och beräknade mätvärden baseras på panelens datumintervall såvida de inte öppnas av komponenthanterarna, som inte har någon associerad panel och fortfarande baseras på de senaste 90 dagarna.</li><li>Förhandsgranskning av data visar data eller komponenter baserat på panelens datumintervall.</li></ul> | Ej tillämpligt | 8 februari 2023 |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

AN-308177; AN-308727; AN-308846; AN-309591; AN-310614; AN-311544; AN-311570; AN-311665; AN-311948; AN-312108; AN-312114; AN-312142; AN-312143; AN-312389; AN-312391; AN-312431; AN-312453; AN-312454; AN-312458; AN-312503; AN-312533; AN-312682; AN-312698; AN-312714; AN-312738; AN-312807; AN-312829; AN-312849; AN-312875; AN-312980; AN-312997; AN-313059; AN-313077; AN-313110; AN-313195; AN-313196; AN-313258; AN-313554; AN-313580; AN-313702; AN-313820; AN-313844; AN-313859; AN-313879; AN-314273

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Processer för enhetssökning använder nu en tredje part för alla enhetssökningar** | 3 mars 2023 | Den 2 mars 2023 uppdaterade vi våra enhetssökningsprocesser som en del av supportlanseringen för klienttips så att vi kan använda en tredje part för alla enhetssökningar. Tidigare hade vi bara använt den tredje parten för sökning på mobila enheter. Som en del av den utrullningen hade vissa operativsystem på stationära datorer en felaktig etikett med texten&quot;mobile&quot; (t.ex. &quot;Mobile OS X 10.15.7&quot; i stället för &quot;OS X 10.15.7&quot;).<p>Under Adobe aprilversionen kommer vi att rätta till de här namnen. Analys- och CJA-rapporter uppdateras retroaktivt eftersom deras rapportering söker efter operativsystemets namn baserat på ett ID som registreras som en del av händelsedata. När sökvärdet som motsvarar ett ID uppdateras korrigeras alla rapporter, inklusive historiska data. För [!UICONTROL Data Feeds] är ändringen retroaktiv om du använder en liknande sökprocess vid tidpunkten för rapporteringen. Om du lagrar operativsystemsvärdet i dina händelsedata uppdateras dock bara rapporten i framtiden. Se [Operativsystem](/help/components/dimensions/operating-systems.md) för mer information. |
| **Uppdatera till enhetssökningar på grund av Google klienttips** | 27 februari 2023 | Användningen av klienttips, som planerades till den 16 februari 2023, sköts upp för att bättre säkerställa kvaliteten på enhetssökningar med hjälp av tips. Vi gick vidare med den första fasen av releasen för stöd för kundtips den 27 februari 2023. Den andra och sista fasen av releasen slutfördes torsdagen den 2 mars 2023. [Läs mer](/help/technotes/client-hints.md) |
| **Tillgänglighet för Analytics Source Connector** | 15 februari 2023 | Den 28 februari 2023 blev Analytics Source Connector tillgänglig i det nya datacentret för Adobe Experience Platform i Kanada. |
| **Automatisk migrering till arkitekturen för klassificeringsuppsättning** | 8 februari 2023 | Under de kommande månaderna planerar Adobe att migrera alla klassificeringar i alla organisationer till den senaste klassificeringsarkitekturen. De sista kunderna som migrerar beräknas inträffa i maj 2023. Ingen kundåtgärd krävs, och ingen driftstopp förväntas. Den nya arkitekturen har många fördelar, bland annat:<ul><li>Betydande minskning av bearbetningstiden (72 timmar → 24 timmar)</li><li>Möjligheten att använda [Klassificeringsuppsättningar](/help/components/classifications/sets/overview.md) UI</li><li>Alternativet att använda klassificeringsdata i Adobe Experience Platform i framtiden via [Adobe Analytics källanslutning för klassificeringsdata](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>Observera följande ändringar som kan påverka organisationens arbetsflöde:<ul><li>Vid användning av webbläsare eller FTP-import, &#39;[!UICONTROL Overwrite on conflict]&#39; är alltid aktiverat.</li><li>När du använder en webbläsare eller FTP-import stöds inte längre alternativet att exportera direkt efter importen.</li><li>API:t för Analytics 2.0 `GetDimensions` slutpunkten returnerar nu strängidentifierare för klassificeringar i stället för numeriska identifierare. Numeriska identifierare kan fortfarande användas, men Adobe rekommenderar att du använder de nya strängidentifierarna där det är möjligt. Numeriska identifierare kan hämtas med `?expansion=hidden` frågesträngsparameter.</li></ul>Kontakta Adobe kundtjänst om du vill ha ett mer specifikt migreringsschema för din organisation, eller har frågor om migreringen. [Läs mer](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **EOL för telefonspårningstjänsten för japanska funktioner** | 21 mars 2023 | Endast för våra japanska kunder: I slutet av maj 2023 upphör telefonspårningstjänsten för japanska funktioner (mod_ktrack). Vi ber om ursäkt för besväret, men vi ber dig avinstallera eller inaktivera de moduler som är installerade på Apache-servern. Se sidorna 27 och 28 i [det här dokumentet](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf) för referens. |
| **EOL för[!DNL Reports & Analytics]** | 7 mars 2023 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln.<p>Den 31 december 2023 kommer vi att avsluta många av de tillhörande funktionerna i Rapporter och analyser, bland annat, men inte begränsat till: Schemalagda rapporter, dataextrakt och DL-rapporter. Efter den 31 december 2023 skickas inga schemalagda rapporter längre. I **April 2023**, kommer alla rapporter som skulle ha gått ut efter den 31 december 2023 automatiskt att uppdateras och återställas till att upphöra den 31 december 2023. Dessutom kan du inte längre schemalägga framtida rapporter efter 31 december 2023. |
| **EOL för [!UICONTROL People] mått** | 9 mars 2023 | Med borttagningen av [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html), är Device Co-op-relaterat personmått inte längre relevant. Den 8 maj 2023 ska vi ta bort [!UICONTROL People] mätvärden. Då kommer vi att omdirigera data till [!UICONTROL Unique Visitor] mätvärden för att förhindra att projekt, segment och beräknade värden bryts.<p>**Anteckning**: The [[!UICONTROL People] mätvärden kopplade till enhetsövergripande analys](/help/components/metrics/people.md) påverkas inte av detta meddelande. |
| **EOL för [!UICONTROL Publishing Lists] funktion** | 29 september 2022 | Som en del av ledningscentralen för rapporter och analyser [!UICONTROL Publishing Lists] kommer att nå slutet av livscykeln i **December 2023**. Du kommer inte att kunna skapa nya eller komma åt befintliga [!UICONTROL Publishing Lists] att skicka eller schemalägga [!UICONTROL Analysis Workspace] projekt. |
| **EOL för Data Workbench** | 14 september 2022 | Adobe har för avsikt att göra Datan Workbench gällande **31 december 2023**. Se [Datans Workbench meddelande om att livscykeln upphör](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) för mer information. Kontakta din organisations kontoansvarige på Adobe om du har frågor. |
| **EOL för[!DNL Reports & Analytics]** | 4 januari 2022 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://www.adobe.com/go/analytics_rnaeol_en) förklarar processen för att avsluta livscykeln. |

{style="table-layout:auto"}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement-versioner (version 2.23.0) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
