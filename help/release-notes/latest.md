---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7d90ef81082fcb98b87547b591be7aa1040609cb
workflow-type: tm+mt
source-wordcount: '1342'
ht-degree: 2%

---

# Aktuell versionsinformation för Adobe Analytics (maj 2023)

**Senaste uppdatering**: 17 maj 2023

Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner i Adobe Analytics {#features}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Bakgrundsfyllning för icke-produktionssandlådor** | När du skapar ett dataflöde för Analytics Source Connector i en icke-produktionssandlåda, begränsas bakgrundsfyllningen i icke-produktionssandlådor till tre månader. Den kommer att finnas kvar på 13 månader för produktionssandlådor. | Ej tillämpligt | 26 april 2023 |
| **Länkdelning för projekt (ingen inloggning krävs)** | Nu kan du dela skrivskyddade länkar till Analysis Workspace-projekt med personer som inte har tillgång till Adobe Analytics. Detta inkluderar delning med personer utanför er organisation, eller personer inom er organisation som inte är anställda för Adobe Analytics. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link)<p>Den här funktionen är aktiverad som standard och kan inaktiveras av systemadministratören. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 3 maj 2023 | Juni 2023 |
| **Uppdaterad startskärm för kontrollpanelsappen Analytics (mobilapp)** | På den nya uppdaterade startskärmen kan du visa alla dina styrkort i en konsoliderad styrkortslista.  Om du har tillgång till mer än en organisation under en inloggning är alla styrkort från din organisation tillgängliga i en enda lista. | Ej tillämpligt | 10 maj 2023 |
| **Sortera komponenter i Analysis Workspace** | Ett nytt sorteringsalternativ är nu tillgängligt när du visar komponenter i den vänstra listen eller i datamappningslistan i Analysis Workspace. Du kan sortera komponenter efter Rekommenderat (de som används oftast), Alfabetiskt eller Kategoriserat (text).<p>Tidigare kunde du bara söka efter eller filtrera komponenter. [Läs mer](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)</p> | Ej tillämpligt | 17 maj 2023 |
| **Ta bort rader som innehåller dynamiska dimensioner från en frihandstabell** | I en friformstabell i Analysis Workspace kan du nu snabbt ta bort specifika rader som innehåller dynamiska dimensioner med hjälp av x-ikonen. När du gör det används automatiskt en filterregel för att alltid utesluta objekt.<p>Tidigare var det enda sättet att ta bort rader som innehöll dynamiska dimensioner att manuellt skapa en regel i filterdialogrutan. [Läs mer](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | Ej tillämpligt | 17 maj 2023 |
| **Ny knapp för att lägga till en visualisering i en panel** | En ny knapp finns nu längst ned på varje panel i Analysis Workspace, så att du snabbt kan lägga till en visualisering. <p>Tidigare var de enda sätten att lägga till en visualisering på en panel att dra en visualisering från den vänstra listen, duplicera eller kopiera en befintlig visualisering eller skapa en tom panel. [Läs mer](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | Ej tillämpligt | 17 maj 2023 |
| **Djuplänkning (mobilapp)** | Tillåter användare att skicka länkar till styrkort som leder dem direkt till styrkortsprojektet i appen. Detta gör det ännu enklare att dela projekt och öka engagemanget från en mindre teknisk målgrupp. | Ej tillämpligt | 17 maj 2023 |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

AN-312098; AN-318309; AN-316675; AN-318173; AN-310359; AN-317613; AN-318836; AN-315744; AN-311772; AN-318719; AN-314074; AN-316651<!--"Verified" status-->; AN-318602; AN-315961; AN-317534; AN-318607; AN-316498; AN-316648; AN-318244; AN-317747; AN-318432; AN-318231; AN-317590; AN-318415; AN-318154; AN-316647; N-314417; AN-317614; AN-317725; AN-318114; AN-317876; AN-318052; AN-317966; AN-316477; AN-318036; AN-317931; AN-318045; AN-316246; AN-317281; AN-317879; AN-308077; AN-317708; AN-316115; AN-315963

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **Migrering till autentiseringsuppgifter för AdobeIO OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder inloggningsuppgifter för AdobeIO JWT måste migrera till inloggningsuppgifter för AdobeIO OAuth Server-till-Server med **1 januari 2025**. Mer information och tidslinjer finns i meddelandet om att produkten upphör att gälla i tabellen nedan. |
| **Obs! Nya IP-adresser som används av Adobe Analytics Data Feeds och Data warehouse i London Data Center** | 27 april 2023 | För kunder i London Data Center som har dataflödesbegäranden och/eller Data warehouse-rapporter som levereras till en FTP/SFTP-tjänst bör följande IP-adressintervall läggas till i brandväggskonfigurationen för att tillåta åtkomst: <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |
| **Processer för enhetssökning använder nu en tredje part för alla enhetssökningar** | 3 mars 2023 | Den 2 mars 2023 uppdaterade vi våra enhetssökningsprocesser som en del av supportlanseringen för klienttips så att vi kan använda en tredje part för alla enhetssökningar. Tidigare hade vi bara använt den tredje parten för sökning på mobila enheter. Som en del av den utrullningen hade vissa operativsystem på stationära datorer en felaktig etikett med texten&quot;mobile&quot; (t.ex. &quot;Mobile OS X 10.15.7&quot; i stället för &quot;OS X 10.15.7&quot;).<p>Under Adobe aprilversionen kommer vi att rätta till de här namnen. Analys- och CJA-rapporter uppdateras retroaktivt eftersom deras rapportering söker efter operativsystemets namn baserat på ett ID som registreras som en del av händelsedata. När sökvärdet som motsvarar ett ID uppdateras korrigeras alla rapporter, inklusive historiska data. För [!UICONTROL Data Feeds] är ändringarna retroaktiva om du använder en liknande sökprocess vid tidpunkten för rapporteringen. Om du lagrar operativsystemsvärdet i dina händelsedata uppdateras dock bara rapporten i framtiden. Se [Operativsystem](/help/components/dimensions/operating-systems.md) för mer information. |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Migrering till autentiseringsuppgifter för AdobeIO OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder inloggningsuppgifter för AdobeIO JWT måste migrera till inloggningsuppgifter för AdobeIO OAuth Server-till-Server med **1 januari 2025**. AdobeIO tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter (Service Account)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Använda de nya autentiseringsuppgifterna för OAuth Server-till-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul>![](assets/jwt.png) |
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
