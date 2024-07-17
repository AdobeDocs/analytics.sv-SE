---
description: Beskriver hur landningssidan sammanför både Analysis Workspace och Rapporter och analyser i ett enda gränssnitt och en enda åtkomstpunkt under Workspace paraply.
title: Adobe Analytics landningssida
role: User, Admin
feature: Analytics Basics
exl-id: 0a2fb778-491a-4dc3-aae4-afadb3ab1a1e
source-git-commit: 416725e01f469e3fafc1d52971535ab63e998f5f
workflow-type: tm+mt
source-wordcount: '1760'
ht-degree: 0%

---

# Adobe Analytics landningssida

Landningssidan för Adobe Analytics sammanför både [!DNL Analysis Workspace] och [!DNL Reports & Analytics] (slutet av livscykeln) i ett enda gränssnitt och en åtkomstpunkt under paraplyet [!DNL Workspace]. Här finns en startsida för projektledare, en uppdaterad rapportmeny, uppdaterade rapporter och en utbildningssektion som hjälper dig att komma igång på ett effektivare sätt. Här är en videoöversikt:

>[!VIDEO](https://video.tv.adobe.com/v/334278/?quality=12)

Adobe Analytics landningssida består av följande underflikar: Projekt, rapporter och Utbildning.

**[!UICONTROL Projects]** är anpassade designer som kombinerar datakomponenter, tabeller och visualiseringar som du har skapat eller som någon annan har skapat och delat med dig. [!UICONTROL Projects] refererar också till tomma projekt och tomma mobilstyrkort.

**[!UICONTROL Reports]** refererar till allt som är färdigbyggt av Adobe, till exempel mallar i Workspace.

Fliken **[!UICONTROL Learning]** innehåller praktiska videoutgångar, självstudiekurser och länkar till dokumentation.

## Navigera på fliken [!UICONTROL Projects] {#navigate-projects}

Fliken [!UICONTROL Projects] fungerar som startsida för [!UICONTROL Workspace]. Den visar företagsmappen, eventuella personliga mappar som du har skapat, dina projekt och Mobile Scorecards. Använd den här sidan om du vill visa, skapa och ändra mappar, projekt och mobila styrkort. Mer information finns i [Om mappar i Analytics](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

![Landing all](assets/landing-all2.png)

>[!NOTE]
>
>Flera av följande inställningar finns kvar under sessionen och mellan sessionerna. Till exempel den flik du har markerat, de markerade filtren, de markerade kolumnerna och kolumnsorteringsriktningen. Sökresultaten är inte beständiga.

### Anpassa tabellkolumner

Om du vill anpassa kolumnbredder drar du det lodräta strecket som skiljer varje kolumn åt.

Om du vill lägga till eller ta bort kolumner från listan med projekt klickar du på kolumnikonen (![Landing all](/help/analyze/assets/select-column.png) ) i det övre högra hörnet och markerar eller avmarkerar sedan kolumnrubriker.

De tillgängliga kolumnerna är:

| Kolumnnamn | Beskrivning |
|---------|----------|
| [!UICONTROL **Namn**] | Identifierar namnet på projektet. |
| [!UICONTROL **Typ**] | Anger om den här typen är ett Workspace-projekt, ett Mobile-styrkort eller en mapp. |
| [!UICONTROL **Taggar**] | Taggar projekt för att ordna dem i grupper. |
| [!UICONTROL **Schemalagd**] | Ange [!UICONTROL On] när ett projekt är schemalagt eller [!UICONTROL Off] när det inte är det. Om du klickar på länken [!UICONTROL On] kan du visa information om det schemalagda projektet. Du kan också [redigera projektschemat](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md) om du är projektägare. |
| [!UICONTROL **Projektroll**] | Identifierar projektrollerna: om du är projektägare och om du har behörighet att redigera eller duplicera projektet. |
| [!UICONTROL **Rapportsviten**] | Identifierar de rapportsviter som är kopplade till projektet.<br>Tabeller och visualiseringar i en panel hämtar data från rapportsviten som har valts i panelens övre högra hörn. Rapportsviten avgör också vilka komponenter som är tillgängliga i den vänstra listen. Inom ett projekt kan du använda en eller flera rapportsviter beroende på dina analysexempel. Listan med rapportsviter sorteras efter relevans. Adobe definierar relevansen baserat på hur nyligen och ofta sviten har använts av den aktuella användaren och hur ofta sviten används i organisationen. |
| [!UICONTROL **Ägare**] | Identifierar den person som skapade projektet. |
| [!UICONTROL **Delas med**] | Visar vem projektet delas med. |
| [!UICONTROL **Senast ändrad**] | Datum och tid då projektet senast ändrades. |
| [!UICONTROL **Senast öppnad**] | Identifierar det datum då ett projekt senast öppnades av den användare som för närvarande visar projektsidan. |
| [!UICONTROL **Senast använd**] | Hjälper till att avgöra om ett projekt är värdefullt för användare i organisationen genom att visa datum och tid när projektet senast öppnades av någon användare i organisationen.<p>Tänk på följande när du visar den här kolumnen:</p><ul><li>Användningsinformation finns tillgänglig från och med september 2023.</li><li>Den här kolumnen är bara tillgänglig för systemadministratörer.</li></ul> |
| [!UICONTROL **Projekt-ID**] | Kan användas för felsökning. |
| [!UICONTROL **Högsta datumintervall**] | Längre datumintervall ökar projektets komplexitet och kan öka bearbetnings- och inläsningstiderna. |
| [!UICONTROL **Antal frågor**] | Det totala antalet begäranden som gjorts till Analytics när projektet läses in. Ett högre antal projektfrågor ökar projektets komplexitet och kan öka bearbetnings- och inläsningstiden. Dessa data är bara tillgängliga när ett projekt har lästs in eller när ett schemalagt projekt har skickats. |
| [!UICONTROL **Plats**] | Visar mappen där projektet finns. |

### Andra gränssnittselement på sidan Projekt

| UI-element | Definition |
| --- | --- |
| Redigera inställningar | Gör att du kan [!UICONTROL View Tutorials] och [redigera användarinställningar](/help/analyze/analysis-workspace/user-preferences.md). |
| [!UICONTROL Create new] | Öppnar det modala projektet där du kan skapa ett Workspace-projekt eller ett Mobile-styrkort eller öppna en företagsmall. |
| [!UICONTROL Show less<br> Visa mer] | Växlar mellan att inte visa och visa banderollen: ![Övre banderoll](assets/top-banner.png) |
| [!UICONTROL Workspace project] | Skapar ett tomt [Workspace-projekt](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) som du kan utforma och skapa. |
| [!UICONTROL Mobile scorecard] | Skapar ett tomt [mobilstyrkort](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html) som du kan utforma och skapa. |
| [!UICONTROL Open Training Tutorial] | Öppnar Workspace självstudiekurs som vägleder dig genom processen att skapa ett nytt startprojekt i en stegvis självstudiekurs. |
| [!UICONTROL Open release notes] | Öppnar Adobe Analytics-delen av den senaste versionsinformationen för Adobe Experience Cloud. |
| Filterikon | Filter efter taggar, rapportsviter, ägare, typer och andra filter (Min, Delad med mig, Favoriter och Godkänd) |
| Sökfältet | Söker igenom alla kolumner i tabellen. |
| Markeringsruta | Väljer ett eller flera projekt för att visa de projekthanteringsåtgärder som du kan utföra: **Ta bort**, **Dela**, **Byt namn**, **Kopiera**, **Ta bort**, **Flytta uppåt**, **Flytta nedåt**, **Tagg** 6}Godkänn **,** Exportera CSV **och** Flytta till **.** Du kanske inte har behörighet att utföra alla listade åtgärder. |
| [!UICONTROL Favorites] | Lägger till en stjärna bredvid ett favoritprojekt eller en mapp som kan användas som filter. |
| [!UICONTROL Name] | Identifierar namnet på projektet. |
| Fäst ikon | Fäster objekt så att de alltid visas högst upp i listan, men du kan ändra ordningen genom att flytta dem uppåt eller nedåt i den ordning som de visas. Använd ellipsalternativmenyn och välj **Flytta upp** eller **Flytta ned** i listan. |
| Info (i), ikon | Visar följande information om ett projekt: Typ, Projektroll, Ägare, Beskrivning och vem det delas med. Det anger också vem som kan [redigera eller duplicera](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html) det här projektet. |
| Ellips (...) | Visar de projekthanteringsåtgärder du kan utföra: **Ta bort**, **Dela**, **Byt namn**, **Kopiera**, **Ta bort**, **Flytta upp**, **Flytta ned**, **Tagg**, **Godkänn**, **Exportera CSV** och **Flytta till**. Du kanske inte har behörighet att utföra alla listade åtgärder. |
| VISA: Mappar och projekt eller alla projekt | Ändrar visningsinställningen för tabellen så att mappar och projekt visas enligt mapporganisationen **eller**, vilket visar alla dina projekt i en oordnad lista. |
| &lt; (Bakåt-knappen) | Returnerar dig till den senaste konfigurationen av landningssidan i ett Workspace-projekt eller en rapport. Sidkonfigurationen som du hade när du lämnade landningssidan kommer att finnas kvar när du kommer tillbaka. |

## Navigera på fliken [!UICONTROL Reports] {#navigate-reports}

Fliken [!UICONTROL Reports] konsoliderar följande uppsättningar rapporter:

* De fördefinierade [!UICONTROL Workspace]-mallarna som tidigare fanns under [!UICONTROL Workspace] > [!UICONTROL Project] > [!UICONTROL New]. Adobe använder inte längre ordet&quot;mall&quot; i det här sammanhanget.
* De flesta av de färdiga rapporterna på den tidigare översta menyn i Adobe Analytics [!UICONTROL Reports]. Rapporterna visas nu i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html).

>[!NOTE]
>
>Tänk på följande när du använder rapporter:
>* Under Rapporter visas en Favoriter-mapp bara om du har markerat en ny rapport som favorit. Inga tidigare favoriter för Rapporter och analyser överförs.
>* Endast de mest använda rapporterna som tidigare grupperats i Rapporter och analyser är tillgängliga. En handfull sällan använda eller inte längre relevanta rapporter finns inte längre tillgängliga. Mer information finns i [Vanliga frågor och svar](#landing-page-faq) nedan.

![Fliken Rapporter](assets/reports-tab2.png)

Mer information om fliken Rapporter i Analysis Workspace, inklusive visning och sparande av rapporter, finns i [Använda färdigbyggda rapporter](/help/analyze/analysis-workspace/reports/use-reports.md).

Mer information om hur du skapar och hanterar anpassade företagsrapporter finns i [Skapa och hantera företagsrapporter](/help/analyze/analysis-workspace/reports/create-company-reports.md).

## Använda fliken Utbildning {#navigate-learning}

Utbildningssidan innehåller praktiska videoutgångar, självstudiekurser och länkar till dokumentation.

På sidan Lär dig mer om nybörjare, mellanfunktioner och avancerade funktioner i Adobe Analytics.

### Gå till sidan Utbildning

1. I Adobe Analytics väljer du [!UICONTROL **Workspace**] > [!UICONTROL **Om**].

### Funktioner för utbildningssidor

* **Filtrera innehåll:** Med Filterikonen i den vänstra listen kan du filtrera utbildningsinnehåll efter erfarenhetsnivå (Nybörjare, Mellan eller Avancerat) och efter innehållstyp (dokument, video eller Tours och självstudiekurser).
* **Spåra förlopp:** När du har markerat en del av innehållet visas en **[!UICONTROL Viewed]** -tagg. Den här taggen hjälper dig att spåra dina framsteg med utbildningsinnehållet. Du kan markera taggen **[!UICONTROL Viewed]** om du vill ta bort den från innehållet.
* **Visa ytterligare innehåll:** När du visar en videofilm kan du visa relaterat dokumentationsinnehåll på Experience League genom att klicka på knappen **[!UICONTROL Learn more]** . Du kan också välja något av följande alternativ på sidan Lär dig mer om du vill visa ytterligare innehåll:
   * **[!UICONTROL Visit YouTube]:** Visa hela spelningslistan för Analysis Workspace YouTube.
   * [!UICONTROL **Besök Experience League**]: Se hela uppsättningen Adobe Analytics-dokumentation på Experience League.
* **Grundläggande om nya användare:** Demonstrationen [!UICONTROL Workspace Fundamentals] rekommenderas för nya användare. Demonstrationen tar dig direkt till Workspace och leder dig igenom de vanligaste åtgärderna. Demonstrationen kan också öppnas igen när som helst i Workspace via verktygstipset i panelhuvudet.

## Ange landningssida {#set-landing}

Användare kan ange sin favoritlandningssida.

1. Gå till Analytics > [!UICONTROL Components] > [!UICONTROL Preferences] > [!UICONTROL General].
1. Kontrollera vilken landningssida du vill använda:

   ![Ange landningssida](assets/landing-pref.png)

## Dölj fliken Rapport {#hide-reports}

Administratörer kan dölja fliken Rapporter för alla användare i organisationen.

1. Gå till [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Preferences] > [!UICONTROL Company].
1. Kontrollera **[!UICONTROL Hide Reports Tab]**.

## Vanliga frågor om landningssidan {#landing-faq}

| Fråga | Svar |
| --- | --- |
| Var är mallarna som jag är van vid att se i [!UICONTROL Workspace]? | Mallarna grupperas under fliken [!UICONTROL Reports]. |
| Överför mitt arbete i betaprogrammets användargränssnitt till produktionen [!UICONTROL Workspace]? | Ja, allt arbete som görs i betaversionen överförs till den gamla/aktuella [!UICONTROL Workspace]-upplevelsen. |
| Överförs mina tidigare favoriter i Rapporter och analyser? | Nej, de förs INTE vidare. Alla [!UICONTROL Workspace]-projektfavoriter överförs dock. |
| Finns det ett maximalt antal projekt jag kan fästa? | Nej, det finns ingen gräns för hur många projekt du kan fästa. |
| Kan administratörer ange den här landningssidan för sina användare? | Nej, administratörer kan inte ange landningssidan för användarnas räkning. Enskilda användare måste aktivera växeln själva. |
| Är alla rapporter som fanns i [!DNL Reports & Analytics] fortfarande tillgängliga? | Nej, följande rapporter har fasats ut baserat på övergripande användningsdata: <ul><li>Anpassade eVars/props/events/classifications<li>Mina rekommenderade rapporter</li><li>unika besökare varje timme/dag/vecka/månad/kvartal/år</li><li>unika kunder varje vecka/månad/kvartal/år</li><li>Åtgärdsnamn - djup</li><li>Sammanfattning av åtgärdsnamn</li><li>Lägg till instrumentpanel</li><li>Ålder</li><li>Stöd för ljud</li><li>Faktureringsinformation</li><li>Klicka på sidan</li><li>Färgdjup</li><li>Cookie-stöd</li><li>Cookies</li><li>Anslutningstyper</li><li>Kreativa element</li><li>Kreditkortstyp</li><li>Korsförsäljning</li><li>Anpassade händelsegrupper</li><li>Egna länkar</li><li>Kund-ID</li><li>Veckodag</li><li>Åtgärdsnamn för registrering</li><li>Avsluta åtgärdsnamn</li><li>Avsluta länkar</li><li>Utfall</li><li>Filnedladdningar</li><li>Sök i butik</li><li>Fullständiga banor</li><li>Kön</li><li>Träfftypens VISTA-regel</li><li>Bildstöd</li><li>Java</li><li>JavaScript</li><li>JavaScript</li><li>Hantera bokmärken</li><li>Hantera instrumentpaneler</li><li>Skärmfärgdjup</li><li>Övervaka upplösningar</li><li>Nyhetsbrev - registreringar</li><li>Nästa åtgärdsnamn</li><li>Nästa åtgärdsnamnflöde</li><li>Inga sökningar</li><li>Operativsystem</li><li>Ordergranskning</li><li>Dagens sida</li><li>Sidorna hittades inte</li><li>Banhanteraren</li><li>Banlängd</li><li>Namn på föregående åtgärd</li><li>Namnflöde för föregående åtgärd</li><li>Produktaktivitet</li><li>Produktkostnad</li><li>Produktavdelning</li><li>Produktlagerkategori</li><li>Produktnamn</li><li>Produktrecensioner</li><li>Produktsäsong</li><li>Produktdelningar</li><li>Produktzoomningar</li><li>Läs in igen</li><li>Sökningar</li><li>Servrar</li><li>Besök enstaka sidor</li><li>Leveransinformation</li><li>Platshierarki</li><li>Sociala omnämnanden</li><li>Tid på dagen</li><li>Tid som använts för åtgärdsnamn</li><li>Stöd för video</li><li>Besökarläge</li></ul> |
