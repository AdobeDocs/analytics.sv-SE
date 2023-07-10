---
title: Versionsinformation om den senaste analysen
description: Se versionsinformationen för Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: b0c97e4f9d3243e233999cf80f1d742a676f4023
workflow-type: tm+mt
source-wordcount: '1532'
ht-degree: 3%

---

# Aktuell versionsinformation för Adobe Analytics (juni 2023)

**Senaste uppdatering**: 10 juli 2023

Adobe Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Frigör högdagrar {#highlights}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Konfigurera lagringsplatser för molnkonton för inhämtning av klassificeringsdata** | Nu kan du hantera lagringsplatser för molnkonton som används för automatisering av klassificeringsuppsättningar.<p>[Läs mer](/help/components/locations/configure-import-accounts.md)</p> |  | 10 juli 2023 |
| **Förbättrat datareparationsfilter** | Tre filtreringsförbättringar har lagts till i Datareparation:<ul><li>Filtrera efter en variabel för att ändra en andra variabel. Om `eVar2` innehåller&quot;@&quot; och sedan ta bort `eVar3`.</li><li>Filter för numeriska eller icke-numeriska värden</li><li>Använd flera filter med AND. Där `eVar2="a"` OCH `eVar3="b"`</li></ul>[Läs mer](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) | 21 juni 2023 | 12 juli 2023 |
| **Länkdelning för projekt (ingen inloggning krävs)** | Nu kan du dela skrivskyddade länkar till Analysis Workspace-projekt med personer som inte har tillgång till Adobe Analytics. Detta inkluderar delning med personer utanför er organisation, eller personer inom er organisation som inte är anställda för Adobe Analytics. [Läs mer](../analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)<p>Den här funktionen är aktiverad som standard och kan inaktiveras av systemadministratören. [Läs mer](../analyze/analysis-workspace/user-preferences.md#company-preferences)</p> | 3 maj 2023 | 7 juni 2023 |
| **Nya funktioner för klassificeringsuppsättningar** | [Klassificeringsuppsättningar](/help/components/classifications/sets/overview.md) har uppdaterats med flera nya funktioner:<ul><li>**Konsolideringar**: Kombinera klassificeringsuppsättningar i en enda konsoliderad klassificeringsuppsättning. Den konsoliderade klassificeringsuppsättningen kan användas som andra klassificeringsuppsättningar eller som en uppslagsuppsättning i kundens Jourey Analytics. [Läs mer](../components/classifications/sets/consolidations/manage.md)</li><li>**Regler**: Klassificera värden automatiskt baserat på reglerna i klassificeringsuppsättningen. [Läs mer](../components/classifications/sets/manage/rules.md)</li><li>**Automatiserad import**: Importera klassificeringsdata automatiskt från molnlagringsmål. [Läs mer](../components/classifications/sets/manage/schema.md)</li></ul> | | 7 juni 2023 |
| **Variabeln Nytt AppMeasurement** | Variabeln `doubleEncodeLinkParameters` används för kantfall där implementeringar kodar flerbytetecken i länkspårningsvariabler. De flesta implementeringar behöver inte definiera den här variabeln. [Läs mer](../implement/vars/config-vars/doubleencodelinkparameters.md) |  | 7 juni 2023 |
| **Säkra destinationer för datafeed-export** | Datamatningar kan nu skickas till följande molnlagringsmål:<ul><li>Amazon S3</li><li>Azure RBAC</li><li>Azure SAS</li><li>Google Cloud Platform</li></ul>Destinationer som tidigare var tillgängliga (FTP, SFTP, S3 och Azure Blob) rekommenderas inte längre. [Läs mer](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html) | 12 juni 2023 | 15 juli 2023 |
| **Punktrapportering på arbetsytan** | Bot-rapportering finns nu i Analysis Workspace. Den här funktionen innehåller flera tillägg:<ul><li>En ny dimension: [Punktnamn](/help/components/dimensions/bot-name.md)</li><li>Två nya mätvärden: [Bot page views](/help/components/metrics/bot-page-views.md) och [Punkter](/help/components/metrics/bot-occurrences.md).</li><li>En ny mall för beräknade mått: [Vyförhållande för startsida](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>En ny rapport om arbetsytan: Bot-rapportering</li></ul>Den nya dimensionen och mätvärdena innehåller data som är förifyllda från och med mars 2023. |  | Juni 7,2023 |

{style="table-layout:auto"}

## Andra nya eller uppdaterade funktioner {#other}

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Ta bort rader som innehåller dynamiska dimensioner från en frihandstabell** | I en friformstabell i Analysis Workspace kan du nu snabbt ta bort specifika rader som innehåller dynamiska dimensioner med hjälp av x-ikonen. När du gör det används automatiskt en filterregel för att alltid utesluta objekt.<p>Tidigare var det enda sättet att ta bort rader som innehöll dynamiska dimensioner att manuellt skapa en regel i filterdialogrutan. [Läs mer](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | Ej tillämpligt | 17 maj 2023 |
| **Ny knapp för att lägga till en visualisering i en panel** | En ny knapp finns nu längst ned på varje panel i Analysis Workspace, så att du snabbt kan lägga till en visualisering. <p>Tidigare var de enda sätten att lägga till en visualisering på en panel att dra en visualisering från den vänstra listen, duplicera eller kopiera en befintlig visualisering eller skapa en tom panel. [Läs mer](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | Ej tillämpligt | 17 maj 2023 |
| **Djuplänkning (mobilapp)** | Tillåter användare att skicka länkar till styrkort som leder dem direkt till styrkortsprojektet i appen. Detta gör det ännu enklare att dela projekt och öka engagemanget från en mindre teknisk målgrupp. [Läs mer](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#share-scorecards-using-a-shareable-link) | Ej tillämpligt | 17 maj 2023 |
| **Dynamiska nedrullningsbara filter** | Vi introducerar en ny typ av nedrullningsbart filter som fastställer tillgängliga värden baserat på data i panelens rapporteringsintervall och värden i andra nedrullningsbara filter. Du kan använda dynamiska nedrullningsbara filter genom att dra en dimension till panelens dropzone medan du håller ned [!UICONTROL Shift]. Statiska nedrullningsbara filter ändras inte om du drar en grupp med dimensionsobjekt till panelens dropzon samtidigt som du håller ned [!UICONTROL Shift]. [Läs mer](/help/analyze/analysis-workspace/c-panels/panels.md) |  | 14 juni 2023 |
| **Uppdaterad Analytics Learning-sida** | Fliken Utbildning på Adobe Analytics landningssida innehåller nu följande förbättringar:<ul><li>Förbättrad design som visar mer utbildningsmaterial på en enda sida med förbättrad navigering</li><li>Möjlighet att personalisera utbildningsmaterial efter erfarenhetsnivå (nybörjare, mellanhand och avancerat)</li></ul>[Läs mer](/help/analyze/landing.md) | 27 juni 2023 | Juni 30,2023 |
| **Sortera komponenter i Analysis Workspace** | Ett nytt sorteringsalternativ är nu tillgängligt när du visar komponenter i den vänstra listen eller i datamappningslistan i Analysis Workspace. Du kan sortera komponenter efter Rekommenderat (de som används oftast), Alfabetiskt eller Kategoriserat (text).<p>Tidigare kunde du bara söka efter eller filtrera komponenter. [Läs mer](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)</p> | Ej tillämpligt | Juni 7,2023 |

{style="table-layout:auto"}

## Korrigeringar i Adobe Analytics

AN-311878; AN-313968; AN-314130; AN-315701; AN-315761; AN-316613; AN-317563; AN-318829; AN-319009; AN-319043; AN-319066; AN-319166; AN-319245; AN-319271; AN-319381; AN-319391; AN-319482; AN-319621; AN-319637; AN-319676; AN-320176; AN-320221; AN-320225; AN-320286; AN-320312; AN-320316; AN-320449; AN-320477; AN-320492; AN-320538; AN-320556; AN-320569; AN-320679; AN-320684; AN-320786; AN-320802; AN-320811; AN-320812; AN-320815; AN-321032; AN-321033; AN-321070; AN-321096; AN-321105; AN-321122; AN-321337;

## Viktiga meddelanden för Adobe Analytics-administratörer {#admin}

| Meddelande | Datum tillagt eller uppdaterat | Beskrivning |
| ----------- | ---------- | ---------- |
| **37-månaders förfallodatum för inköps-ID och händelse-ID (händelseserialisering)** | Maj 25,2023 | En kommande version av motorn för bearbetning av träff i Analytics, avsedd för lansering i **slutet av juni 2023 eller början av juli 2023**, kommer att börja genomdriva en 37-månaders förfallotid för inköps-ID och händelse-ID (händelseserialisering). För närvarande går köp-ID och händelse-ID aldrig ut i Adobe Analytics. När ett inköps-ID eller händelse-ID visas/används kommer eventuella framtida träffar, oavsett när, att markeras som dubbletter. Med den nya versionen av bearbetningsmotorn:<ul><li>Inköps-ID och händelse-ID:n går alltid ut efter 37 månader.</li><li>Om det har gått 37 månader sedan inköps-ID:t eller händelse-ID:t sågs, betraktas det inte längre som ett dubblettköp eller -händelse.</li><li> Om du återanvänder inköps-ID:n eller händelse-ID:n för mer än 37 månader sedan betraktas de inte längre som dubbletter.</li></ul> |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter genom att **1 januari 2025**. Mer information och tidslinjer finns i meddelandet om att produkten upphör att gälla i tabellen nedan. |
| **Nya IP-adresser som används av Adobe Analytics Data Feeds och Data warehouse i London Data Center** | 27 april 2023 | Detta gäller kunder i London Data Center som har förfrågningar om dataflöden och/eller Data warehouse-rapporter som levereras till en FTP/SFTP-tjänst. Följande IP-adressintervall bör läggas till i brandväggskonfigurationen för att tillåta åtkomst: <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |

{style="table-layout:auto"}

## EOL-meddelanden (End-of-life) {#eol}

| EOL-produkt eller -funktion | Datum tillagt eller uppdaterat | Beskrivning |
| --- | --- | --- |
| **Migrering till autentiseringsuppgifter för Adobe I/O OAuth Server-till-Server** | 11 maj 2023 | Adobe Analytics API- och LiveStream-kunder som använder Adobe I/O JWT-autentiseringsuppgifter måste migrera till Adobe I/O OAuth Server-till-Server-autentiseringsuppgifter genom att **1 januari 2025**. Adobe I/O tillåter inte att nya JWT-autentiseringsuppgifter skapas från och med 1 maj 2024. Kunder som använder JWT måste skapa en ny OAuth Server-till-Server-autentiseringsuppgift eller migrera sina befintliga JWT-autentiseringsuppgifter till en OAuth Server-till-Server-autentiseringsuppgift. Kunderna måste även uppdatera sina klientprogram för att kunna använda de nya autentiseringsuppgifterna för OAuth Server-till-Server. <ul><li>[Migrerar från JWT-autentiseringsuppgifter (Service Account)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Använda de nya autentiseringsuppgifterna för OAuth Server-till-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Vanliga frågor](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **EOL för[!DNL Reports & Analytics]** | 7 mars 2023 | Effektivt **31 december 2023** kommer Adobe att upphöra med sin verksamhet [!DNL Reports & Analytics] och tillhörande rapporter och funktioner. Rapporterna, visualiseringarna och den underliggande tekniken som ligger till grund för [!DNL Reports & Analytics] inte längre uppfyller Adobe teknikstandarder. Mest [!DNL Reports & Analytics] funktioner finns i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). Sedan Analysis Workspace släpptes 2015 har [!DNL Reports & Analytics] funktionaliteten och funktionerna har flyttats till Analysis Workspace och ett tröskelvärde för arbetsflödets paritet har uppnåtts. [Detta meddelande](https://spark.adobe.com/page/6WnF8JK6IRDhf/) förklarar processen för att avsluta livscykeln.<p>Den 31 december 2023 kommer vi att avsluta många av de tillhörande funktionerna i Rapporter och analyser, bland annat, men inte begränsat till: Schemalagda rapporter, dataextrakt och DL-rapporter. Efter den 31 december 2023 skickas inga schemalagda rapporter längre. I **April 2023**, kommer alla rapporter som skulle ha gått ut efter den 31 december 2023 automatiskt att uppdateras och återställas till att upphöra den 31 december 2023. Dessutom kan du inte längre schemalägga framtida rapporter efter 31 december 2023. |
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
