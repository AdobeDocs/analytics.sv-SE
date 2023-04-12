---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 6d9b568a0ce9d0e8b25d04e934052d2f8012da8c
workflow-type: tm+mt
source-wordcount: '1520'
ht-degree: 2%

---

# Aktuell versionsinformation för Adobe Analytics (april 2023)

**Senaste uppdatering**: 12 april 2023

Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner i Adobe Analytics {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Rad-/kolumnfiltrering för Analytics Source Connector-direktuppspelning** | Med Analytics Source Connector i Adobe Experience Platform går det nu att filtrera analysdata som används för att fylla i profiler i [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en). Filtrering på radnivå minskar antalet händelser som är associerade med profiler. Filtrering på kolumnnivå bidrar till att minska detaljrikedomen i själva händelserna och gör att du kan optimera användningen av profilberättiganden. Denna filtrering gäller endast data som skickas till kundprofilen i realtid och [Identitetstjänst](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en). **Filtreringen påverkar inte data som skickas till Data Lake för användning i program som Customer Journey Analytics**. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | Ej tillämpligt | 29 mars 2023 |
| **Delvis stöd för Activity Map med Web SDK** | Från och med Web SDK version 2.15.0 började vi fylla i data från Activity Map när länkspårning är aktiverat. Detta gör att Web SDK-användare kan få Activity Map-rapportering om de har länkspårning aktiverat med Web SDK och Activity Map som konfigurerats i Analytics.<p>Om du aktiverar länkspårning med Web SDK skickas länkhändelser när en kund navigerar från en sida till nästa. Detta skiljer sig från hur AppMeasurement fungerar och kan eventuellt resultera i extra fakturerbara träffar som skickas till Adobe. Läs mer [här](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html) och [här](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) | Ej tillämpligt | 31 mars 2023 |
| **IP-infusation för Experience Edge** | Experience Edge har stöd för IP-tvång för data som skickas direkt till Adobe Experience Platform. Detta gynnar kunder som skickar data direkt till Platform för användning i CJA eller andra plattformslösningar. IP-förfalskning kommer att konfigureras på dataströmsnivå. Det har stöd för att ta bort den sista oktetten eller hela IP-adressen.<p>**Anteckning**: Invändning gäller INTE data som skickas till Adobe Analytics. Analyserna fortsätter att få hela IP-adressen. IP-bearbetning fortsätter att utföras separat i Analytics. I framtiden planerar vi att tillåta att analysdata döljs vid Edge. | Ej tillämpligt | AEP-version 26 april 2023 |
| **Dataordlista i Analysis Workspace** | Med Data Dictionary kan både användare och administratörer hålla reda på, hantera och bättre förstå komponenterna (dimensioner, mätvärden) i sin Analytics-miljö. [Läs mer](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 15 mars 2023 | 29 mars 2023 |
| **Länkdelning för projekt (ingen inloggning krävs)** - Endast privat betaversion | <p>Nu kan du dela skrivskyddade länkar till Analysis Workspace-projekt med personer som inte har tillgång till Adobe Analytics. Du kan dela projektlänkar med personer utanför organisationen eller personer inom organisationen som inte är tilldelade Adobe Analytics. [Läs mer](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>Om du vill gå med i den privata betaversionen kontaktar du Adobe Account Team.</p> | 26 april 2023 | Juni 2023 |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

* Ett problem med sökfiler för Operating System.tsv i dataflödet har korrigerats.
* Korrigerade ett problem med att mätvärden skiljer sig mellan rapporter och analyser och arbetsytan (AN-315965).
* Ett problem har korrigerats med att det inte gick att importera partiella klassificeringar. (AN-315854)
* Ett problem med Analytics API 1.4 har korrigerats. (AN-316475)
* Korrigerade ett problem som hindrade vissa kunder från att få klassificeringar för siddimensionen via Report Builder och rapport och analys. (AN-314445)
* Korrigerade ett problem med att det inte gick att överföra aviseringar. (AN-306457)

### Andra korrigeringar

AN-288373; AN-305144; AN-309023; AN-310466; AN-311686; AN-311705; AN-312018; AN-312105; AN-312116; AN-312191; AN-312502; AN-312737; AN-312854; AN-312991; AN-313253; AN-313275; AN-313278; AN-313282; AN-313365; AN-313390; AN-313547; AN-313549; AN-313818; AN-313986; AN-314080; AN-314248; AN-314251; AN-314262; AN-314300; AN-314309; AN-314448; AN-314643; AN-314564; AN-314645; AN-314705; AN-314761; AN-314831; AN-314919; AN-314948; AN-315032; AN-315115; AN-315154; AN-315158; AN-315321; AN-315375; AN-315379; AN-315392; AN-315407; AN-315427; AN-315582; AN-315591; AN-315699; AN-315700; AN-315704; AN-315705; AN-315777; AN-315923; AN-316237; AN-316243; AN-316324; AN-316415; AN-316474; AN-316493; AN-316596; AN-316864;

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Processer för enhetssökning använder nu en tredje part för alla enhetssökningar** | 3 mars 2023 | Den 2 mars 2023 uppdaterade vi våra enhetssökningsprocesser som en del av supportlanseringen för klienttips så att vi kan använda en tredje part för alla enhetssökningar. Tidigare hade vi bara använt den tredje parten för sökning på mobila enheter. Som en del av den utrullningen hade vissa operativsystem på stationära datorer en felaktig etikett med texten&quot;mobile&quot; (t.ex. &quot;Mobile OS X 10.15.7&quot; i stället för &quot;OS X 10.15.7&quot;).<p>Under Adobe aprilversionen kommer vi att rätta till de här namnen. Analys- och CJA-rapporter uppdateras retroaktivt eftersom deras rapportering söker efter operativsystemets namn baserat på ett ID som registreras som en del av händelsedata. När sökvärdet som motsvarar ett ID uppdateras korrigeras alla rapporter, inklusive historiska data. För [!UICONTROL Data Feeds] är ändringen retroaktiv om du använder en liknande sökprocess vid tidpunkten för rapporteringen. Om du lagrar operativsystemsvärdet i dina händelsedata uppdateras dock bara rapporten i framtiden. Se [Operativsystem](/help/components/dimensions/operating-systems.md) för mer information. |
| **Uppdatera till enhetssökningar på grund av Google klienttips** | 27 februari 2023 | Användningen av klienttips, som planerades till den 16 februari 2023, sköts upp för att bättre säkerställa kvaliteten på enhetssökningar med hjälp av tips. Vi gick vidare med den första fasen av releasen för stöd för kundtips den 27 februari 2023. Den andra och sista fasen av releasen slutfördes torsdagen den 2 mars 2023. [Läs mer](/help/technotes/client-hints.md) |
| **Automatisk migrering till arkitekturen för klassificeringsuppsättning** | 8 februari 2023 | Under de kommande månaderna planerar Adobe att migrera alla klassificeringar i alla organisationer till den senaste klassificeringsarkitekturen. De sista kunderna som migrerar beräknas inträffa i maj 2023. Ingen kundåtgärd krävs, och ingen driftstopp förväntas. Den nya arkitekturen har många fördelar, bland annat:<ul><li>Betydande minskning av bearbetningstiden (72 timmar → 24 timmar)</li><li>Möjligheten att använda [Klassificeringsuppsättningar](/help/components/classifications/sets/overview.md) UI</li><li>Alternativet att använda klassificeringsdata i Adobe Experience Platform i framtiden via [Adobe Analytics källanslutning för klassificeringsdata](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>Observera följande ändringar som kan påverka organisationens arbetsflöde:<ul><li>Vid användning av webbläsare eller FTP-import, &#39;[!UICONTROL Overwrite on conflict]&#39; är alltid aktiverat.</li><li>När du använder en webbläsare eller FTP-import stöds inte längre alternativet att exportera direkt efter importen.</li><li>API:t för Analytics 2.0 `GetDimensions` slutpunkten returnerar nu strängidentifierare för klassificeringar i stället för numeriska identifierare. Numeriska identifierare kan fortfarande användas, men Adobe rekommenderar att du använder de nya strängidentifierarna där det är möjligt. Numeriska identifierare kan hämtas med `?expansion=hidden` frågesträngsparameter.</li></ul>Kontakta Adobe kundtjänst om du vill ha ett mer specifikt migreringsschema för din organisation, eller har frågor om migreringen. [Läs mer](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **EOL för telefonspårningstjänsten för japanska funktioner** | 21 mars 2023 | Endast för våra japanska kunder: På **slutet av maj 2023**, kommer telefonspårningstjänsten för japanska funktioner (mod_ktrack) att avbrytas. Vi ber om ursäkt för besväret, men vi ber dig avinstallera eller inaktivera de moduler som är installerade på Apache-servern. Se sidorna 27 och 28 i [det här dokumentet](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf) för referens. |
| **EOL för[!DNL Reports & Analytics]** | 7 mars 2023 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln.<p>Den 31 december 2023 kommer vi att avsluta många av de tillhörande funktionerna i Rapporter och analyser, bland annat, men inte begränsat till: Schemalagda rapporter, dataextrakt och DL-rapporter. Efter den 31 december 2023 skickas inga schemalagda rapporter längre. I **April 2023**, kommer alla rapporter som skulle ha gått ut efter den 31 december 2023 automatiskt att uppdateras och återställas till att upphöra den 31 december 2023. Dessutom kan du inte längre schemalägga framtida rapporter efter 31 december 2023. |
| **EOL för [!UICONTROL People] mått** | 9 mars 2023 | Med borttagningen av [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html), är Device Co-op-relaterat personmått inte längre relevant. Den 8 maj 2023 ska vi ta bort [!UICONTROL People] mätvärden. Då kommer vi att omdirigera data till [!UICONTROL Unique Visitor] mätvärden för att förhindra att projekt, segment och beräknade värden bryts.<p>**Anteckning**: The [[!UICONTROL People] mätvärden kopplade till enhetsövergripande analys](/help/components/metrics/people.md) påverkas inte av detta meddelande. |
| **EOL för [!UICONTROL Publishing Lists] funktion** | 29 september 2022 | Som en del av ledningscentralen för rapporter och analyser [!UICONTROL Publishing Lists] kommer att nå slutet av livscykeln i **December 2023**. Du kommer inte att kunna skapa nya eller komma åt befintliga [!UICONTROL Publishing Lists] att skicka eller schemalägga [!UICONTROL Analysis Workspace] projekt. |
| **EOL för Data Workbench** | 14 september 2022 | Adobe har för avsikt att göra Datan Workbench gällande **31 december 2023**. Se [Datans Workbench meddelande om att livscykeln upphör](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html) för mer information. Kontakta din organisations kontoansvarige på Adobe om du har frågor. |

{style="table-layout:auto"}

## AppMeasurement

De senaste uppdateringarna av AppMeasurement-versioner (version 2.23.0) finns i [Versionsinformation om AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html).


## Relaterade resurser

* [Information om föregående version för 2022](/help/release-notes/2022.md)
* [Versionsinformation för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* Den senaste releaseuppdateringen för [Adobe Experience Cloud-produkter](https://business.adobe.com/products/adobe-experience-cloud-products.html)
