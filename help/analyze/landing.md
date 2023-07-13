---
description: Beskriver hur landningssidan sammanför både Analysis Workspace och Rapporter och analyser i ett enda gränssnitt och en enda åtkomstpunkt under arbetsytans paraply.
title: Adobe Analytics landningssida
role: User, Admin
feature: Analytics Basics
exl-id: 0a2fb778-491a-4dc3-aae4-afadb3ab1a1e
source-git-commit: f7bd5eaffd4502510451e3afb5929682ad967ecb
workflow-type: tm+mt
source-wordcount: '3933'
ht-degree: 0%

---

# Adobe Analytics landningssida

Adobe Analytics landningssida sammanför båda [!DNL Analysis Workspace] och [!DNL Reports & Analytics] i ett enda gränssnitt och en enda åtkomstpunkt under [!DNL Workspace] paraply. Här finns en startsida för projektledare, en uppdaterad rapportmeny, uppdaterade rapporter och en utbildningssektion som hjälper dig att komma igång på ett effektivare sätt. Här är en videoöversikt:

>[!VIDEO](https://video.tv.adobe.com/v/334278/?quality=12)

## Nya funktioner på landningssidan {#new-features}

| Funktion | Beskrivning | Skärmbild |
| --- | --- | --- |
| Expandera [!UICONTROL Projects] tabell till helskärm | Om du vill expandera tabellen klickar du bara på menyikonen för hamburgaren. Den här åtgärden komprimerar flikarna till vänster. | ![Expandera tabell](assets/landing-collapse2.png) |
| Anpassa kolumnbredd | Tidigare var kolumnbredden fast. Nu kan du justera den genom att dra kolumnavgränsaren. | ![Kolumnbredd](assets/column-width.png) |
| Ändra ordning på fästa objekt | Om du vill flytta fasta objekt uppåt och nedåt klickar du på ellipsen bredvid det fästa objektet och väljer **[!UICONTROL Move up]** eller **[!UICONTROL Move down]**. | ![Flytta fästa objekt](assets/move-up-down.png) |
| Nya tabellkolumner | Klicka på [!UICONTROL Customize table] ikonen längst upp till höger i tabellen. Nya tabellkolumner innehåller: <ul><li>**[!UICONTROL Scheduled]**: Ange till [!UICONTROL On] när ett projekt är schemalagt eller [!UICONTROL Off] när det inte är det. Klicka på [!UICONTROL On] -länken kan du visa information om det schemalagda projektet. Du kan också [redigera projektschemat](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md) om du är projektägare.</li><li>**[!UICONTROL Project ID]**: Projekt-ID kan användas för felsökningsprojekt.</li><li>**[!UICONTROL Longest Date Range]**: Längre datumintervall ökar projektets komplexitet och kan öka bearbetnings- och inläsningstiderna. </li><li>**[!UICONTROL Number of Queries]**: Det totala antalet begäranden som gjorts till Analytics när projektet läses in. Ett högre antal projektfrågor ökar projektets komplexitet och kan öka bearbetnings- och inläsningstiden. Dessa data är bara tillgängliga när ett projekt har lästs in eller när ett schemalagt projekt har skickats. </li></ul> | ![Nya kolumner](assets/new-columns.png) |
| Klicka en gång för att öppna en rapport | Tidigare var du tvungen att dubbelklicka. |  |
| Nya länkar till **[!UICONTROL Reports & Analytics]** rapporter | <ul><li>**[!UICONTROL Reports]** > **[!UICONTROL Audience]** > **[!UICONTROL Bots]**</li><li>**[!UICONTROL Reports]** > **[!UICONTROL Audience]** > **[!UICONTROL Bot Pages]**<li>**[!UICONTROL Reports]** > **[!UICONTROL Engagement]** > **[!UICONTROL Real-Time]**</li></ul> | ![Nya länkar](assets/report-links.png) |
| Nya färdiga rapporter | <ul><li>**[!UICONTROL Reports]** > **[!UICONTROL Most popular]** > **[!UICONTROL Next page]**</li><li>**[!UICONTROL Reports]** > **[!UICONTROL Most popular]** > **[!UICONTROL Previous page]**</li><li>**[!UICONTROL Reports]** > **[!UICONTROL Engagement]** > **[!UICONTROL Page analysis]** > **[!UICONTROL Page summary]**</li></ul>Observera att dessa rapporter finns i [!UICONTROL Workspace] -format och kräver konfiguration och bygge. Resultatet består av en panel med högnivåstatistik, trenddata, [!UICONTROL Flow] visualisering med mera. Du kan ändra de här rapporterna och ändra dimensioner, dimensionsobjekt osv. Dessa rapporter finns också som paneler under arbetsytepaneler. | ![Nästa sida](assets/next-page.png) |
| **[!UICONTROL Create Project]** modal är tillbaka | När du klickar **[!UICONTROL Create Project]** i arbetsytan får du ännu en gång möjlighet att välja mellan [!UICONTROL Blank project] och [!UICONTROL Blank mobile scorecard]. Du kan också välja bland de mallar som företaget har skapat. | ![Skapa nytt](assets/create-new.png) |
| Finns även i Customer Journey Analytics | Denna landningssida, i ändrad form, finns också tillgänglig i Customer Jourey Analytics. |  |

{style="table-layout:auto"}

## Övre menystruktur {#top-menu}

![Övre menyn](assets/top-menus.png)

* Top Analytics-menyn: De flesta rapporter finns nu i [!UICONTROL Reports] menyn i den vänstra listen.
* Den vänstra listen har tre flikar: [!UICONTROL Projects], [!UICONTROL Reports]och [!UICONTROL Learning].

### Terminologi

* **[!UICONTROL Projects]** är anpassade designer som kombinerar datakomponenter, tabeller och visualiseringar som du har skapat eller som någon annan har skapat och delat med dig. [!UICONTROL Projects] hänvisar också till tomma projekt och tomma mobilstyrkort.
* **[!UICONTROL Reports]** hänvisar till allt som är färdigbyggt av Adobe, till exempel rapporter i rapporter och analyser och mallar i Workspace.
* **[!UICONTROL Templates]** används inte längre som en term för Adobe färdigbyggda Workspace-projekt. De är nu under [!UICONTROL Reports]. Termen [!UICONTROL Templates] används fortfarande för mallar som ditt företag har skapat.

## Navigera i [!UICONTROL Projects] tab {#navigate-projects}

[!UICONTROL Projects] fungerar som [!UICONTROL Workspace] hemsida. Fliken Projekt visar företagsmappen, eventuella personliga mappar som du har skapat, dina projekt och Mobile Scorecards. Använd den här sidan om du vill visa, skapa och ändra mappar, projekt och mobila styrkort. Mer information finns i [Om mappar i Analytics](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

![Alla landningar](assets/landing-all2.png)

>[!NOTE]
>
>Flera av följande inställningar finns kvar under sessionen och mellan sessionerna. Till exempel den flik du har markerat, de markerade filtren, de markerade kolumnerna och kolumnsorteringsriktningen. Sökresultaten är inte beständiga.

| UI-element | Definition |
| --- | --- |
| Redigera inställningar | Gör att du kan [!UICONTROL View Tutorials]och [Redigera användarinställningar](/help/analyze/analysis-workspace/user-preferences.md). |
| [!UICONTROL Create new] | Öppnar det modala projektet där du kan skapa ett Workspace-projekt eller ett Mobile-styrkort eller öppna en företagsmall. |
| [!UICONTROL Show less<br> Visa mer] | Växlar mellan att inte visa och visa banderollen: ![Övre banderoll](assets/top-banner.png) |
| [!UICONTROL Workspace project] | Skapar en tom [Arbetsyteprojekt](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) så att du kan designa och bygga. |
| [!UICONTROL Mobile scorecard] | Skapar en tom [mobilstyrkort](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html) så att du kan designa och bygga. |
| [!UICONTROL Open Training Tutorial] | Öppnar självstudiekursen om arbetsytan som guidar dig genom processen att skapa ett nytt startprojekt i en stegvis självstudiekurs. |
| [!UICONTROL Open release notes] | Öppnar Adobe Analytics-delen av den senaste versionsinformationen för Adobe Experience Cloud. |
| Filterikon | Filter efter taggar, rapportsviter, ägare, typer och andra filter (Min, Delad med mig, Favoriter och Godkänd) |
| Sökfältet | Söker igenom alla kolumner i tabellen. |
| Markeringsruta | Väljer ett eller flera projekt för att visa de projekthanteringsåtgärder du kan utföra: **Ta bort**, **Dela**, **Byt namn**, **Kopiera**, **Ta bort**, **Flytta uppåt**, **Flytta nedåt**, **Tagg**, **Godkänn**, **Exportera CSV** och **Flytta till**. Du kanske inte har behörighet att utföra alla listade åtgärder. |
| [!UICONTROL Favorites] | Lägger till en stjärna bredvid ett favoritprojekt eller en mapp som kan användas som filter. |
| [!UICONTROL Name] | Identifierar namnet på projektet. |
| Fäst ikon | Fäster objekt så att de alltid visas högst upp i listan, men du kan ändra ordningen genom att flytta dem uppåt eller nedåt i den ordning som de visas. Använd ellipsalternativmenyn och välj **Flytta uppåt** eller **Flytta nedåt** i listan. |
| Info (i), ikon | Visar följande information om ett projekt: Typ, Projektroll, Ägare, Beskrivning och vem det delas med. Det anger också vem som kan [redigera eller duplicera](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html) det här projektet. |
| Ellips (..) | Visar de projekthanteringsåtgärder du kan utföra: **Ta bort**, **Dela**, **Byt namn**, **Kopiera**, **Ta bort**, **Flytta uppåt**, **Flytta nedåt**, **Tagg**, **Godkänn**, **Exportera CSV** och **Flytta till**. Du kanske inte har behörighet att utföra alla listade åtgärder. |
| [!UICONTROL Type] | Anger om den här typen är ett Workspace-projekt, ett Mobile-styrkort eller en mapp. |
| [!UICONTROL Tags] | Taggar projekt för att ordna dem i grupper. |
| [!UICONTROL Project Role] | Identifierar projektrollerna: om du är projektägare och om du har behörighet att redigera eller duplicera projektet. |
| [!UICONTROL Report Suite] | Identifierar de rapportsviter som är kopplade till projektet.<br>Tabeller och visualiseringar i en panel hämtar data från rapportsviten som valts i panelens övre högra hörn. Rapportsviten avgör också vilka komponenter som är tillgängliga i den vänstra listen. Inom ett projekt kan du använda en eller flera rapportsviter beroende på dina analysexempel. Listan med rapportsviter sorteras efter relevans. Adobe definierar relevansen baserat på hur nyligen och ofta sviten har använts av den aktuella användaren och hur ofta sviten används i organisationen. |
| [!UICONTROL Owner] | Identifierar den person som skapade projektet. |
| [!UICONTROL Last opened] | Identifierar det datum du senast öppnade projektet. |
| Anpassa tabellikon | Väljer vilka kolumner som ska visas i tabellen. Om du vill lägga till eller ta bort kolumner från listan med projekt klickar du på kolumnikonen (![Alla landningar](/help/analyze/assets/select-column.png) ) i det övre högra hörnet och markera eller avmarkera sedan kolumnrubriker. |
| VISA: Mappar och projekt eller alla projekt | Ändrar visningsinställningen för tabellen så att mappar och projekt visas enligt mappordningen **eller** visa alla dina projekt i en oordnad lista. |
| &lt; (Bakåt-knappen) | Returnerar dig till den senaste konfigurationen av landningssidan i ett Workspace-projekt eller en rapport. Sidkonfigurationen som du hade när du lämnade landningssidan kommer att finnas kvar när du kommer tillbaka. |

### Borttagning av Project Manager-sidan {#deprecate-pm-page}

I och med lanseringen av den nya landningssidan har vi ersatt Project Manager som listats under Components Manager. Den nya landningssidan hanterar alla funktioner på den gamla Project Manager-sidan med mera.

Ett vanligt användningsexempel för Project Manager-sidan var att visa alla dina projekt.

Om du vill visa alla dina projekt på den nya landningssidan med filterspåret väljer du **ANDRA FILTER** och sedan markera **Visa alla**.

![Visa alla projekt](assets/show-all-fIlter.png)

Om du arbetar i vyn &quot;Mappar och projekt&quot; visas ett modalt popup-fönster där du får frågan om du vill växla till vyn &quot;Alla projekt&quot;, vilket gör det enklare att visa alla dina projekt utanför de mappar där de är organiserade.   Välj **Växla till vyn&quot;Alla projekt&quot;** för att bättre visa alla projekt du har tillgång till.

![Växla till alla projekt](assets/switch-all-projects-view.png)

Ett annat användningssätt för administratörer är att hantera företagsrapporter för att ta bort, byta namn på, tagga eller godkänna rapporter. Information om hur du hanterar rapporter finns i [Hantera företagsrapporter](#manage-company-reports).

## Navigera i [!UICONTROL Reports] tab {#navigate-reports}

The [!UICONTROL Reports] konsoliderar följande uppsättningar rapporter:

* Den färdiga [!UICONTROL Workspace] mallar som tidigare fanns under [!UICONTROL Workspace] > [!UICONTROL Project] > [!UICONTROL New]. Adobe använder inte längre ordet&quot;mall&quot; i det här sammanhanget.
* De flesta färdigbyggda rapporterna från tidigare Adobe Analytics [!UICONTROL Reports] översta menyn. Dessa rapporter visas nu i [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html).

>[!NOTE]
>
>Tänk på följande när du använder rapporter:
>* Under Rapporter visas en Favoriter-mapp bara om du har markerat en ny rapport som favorit. Inga tidigare favoriter för Rapporter och analyser överförs.
>* Endast de mest använda rapporterna som tidigare grupperats i Rapporter och analyser är tillgängliga. En handfull sällan använda eller inte längre relevanta rapporter finns inte längre tillgängliga. Se [Vanliga frågor om landningssidan](#landing-page-faq) nedan om du vill ha mer information.

![Fliken Rapporter](assets/reports-tab2.png)


### Visa rapporter {#menus}

1. Gå till [!UICONTROL **Rapporter**] -fliken.
1. Använd sökfältet för att söka efter en viss rapport.

   eller

   Navigera till rapporten som du vill visa.

   Följande rapporter är tillgängliga:

   | Menyalternativ | Rapporter under det här menyobjektet |
   | --- | --- |
   | **[!UICONTROL Most Popular]** | <ul><li>Självstudiekurs (befintlig mall för arbetsyta)</li><li>Sidor (Vad är mina översta sidor?)</li><li>Sidvyer (hur många sidvyer skapar jag?)</li><li>Besök (hur många besök får jag?)</li><li>Besökare (hur många besökare får jag?)</li><li>Viktiga mätvärden (Hur fungerar mina viktigaste mätvärden?)</li><li>Webbplatsavsnitt (Vilka avsnitt på min webbplats genererade de flesta sidvyerna?</li><li>Nästa sida (Vilka är de nästa sidor som besökarna går till?)</li><li>Föregående sida (Vilka är de föregående sidorna som mina besökare gick till?)</li><li>Kampanjer (Vilka kampanjer driver på min nyckelstatistik?)</li><li>Produkter (Vilka produkter driver på min nyckelstatistik?)</li><li>Senaste beröringskanal (Vilken senaste beröringskanal fungerar bäst?)</li><li>Senaste beröringskanaldetalj (Vilken specifik sista beröringskanal presterar bättre än andra?)</li><li>Intäkter (hur fungerar mina intäkter?)</li><li>Beställningar (Hur fungerar mina order?)</li><li>Enheter (hur många enheter säljer jag?)</li></ul> |
   | **[!UICONTROL Engagement]** | <ul><li>Viktiga mätvärden (Hur fungerar mina viktigaste mätvärden?)</li><li>Sidvyer (hur många sidvyer skapar jag?)</li><li>Sidor (Vad är mina översta sidor?)</li><li>Besök (hur många besök får jag?)</li><li>Besökare (hur många besökare får jag?)</li><li>Tid per besök (hur mycket tid tillbringar mina användare per besök?)</li><li>Tid före händelse (Hur mycket tid tillbringar mina användare före en lyckad händelse?)</li><li>Webbplatsavsnitt (Vilka avsnitt på min webbplats genererade de flesta sidvyerna?</li><li>Konsumtion av webbinnehåll (Vilket innehåll konsumeras mest och engagerar användarna)?</li><li>Förbrukning av mediematerial (vilket innehåll konsumeras mest och engagerar användarna)?</li><li>Nästa och föregående sidflöde (Vilka är/var nästa/föregående sökvägar som mina besökare tar/tog?)</li><li>Utfall (Var ser jag utfall från mina digitala resurser?)</li><li>Enhetsövergripande analys (Använda enhetsövergripande analys i Analysis Workspace)</li><li>Webbbevarande (Vilka är mina lojala användare och vad gör de?)</li><li>Medieljudförbrukning (Vad är trender och de viktigaste mätvärdena för ljudförbrukning?)</li><li>Media Recency, frequency, loyalty (Vilka är mina lojala läsare?)</li><li>Sidanalys > Läs in igen (vilka sidor genererar de mest laddade)?</li><li>Sidanalys > Tidsåtgång för sidan (hur mycket tid lägger mina användare på mina sidor?)</li><li>Poster och utträde > Startsidor (Vad är mina övre startsidor?)</li><li>Poster och utträden > Ursprungliga startsidor (Vilken sida angav min besökare ursprungligen från?)</li><li>Poster och avslutningar > Enkelsidiga besök (Vilka sidor genererade de mest enkelsidiga besöken?)</li><li>Poster och avslutningar > Avsluta sidor (Vad är mina översta avslutssidor?)</li></ul> |
   | **[!UICONTROL Conversion]** | <ul><li>Produkter > Produkter (Vilka produkter påverkar min nyckelstatistik?)</li><li>Produkter > Produktprestanda (Vilka produkter fungerar bäst?)</li><li>Produkter > Kategorier (Vilka är mina mest framgångsrika produktkategorier?</li><li>Kundvagn > Korgar (hur många användare har lagt till en produkt i kundvagnen?</li><li>Kundvagn > Vyer av kundvagn (hur många gånger såg mina besökare sina kundvagnar?)</li><li>Kundvagn > Tillägg av kundvagn (Hur ofta lägger användare till en produkt i kundvagnen?)</li><li>Kundvagn > Ta bort kundvagn (Hur ofta tar användarna bort en produkt från kundvagnen?)</li><li>Inköp > Inkomster (hur fungerar mina intäkter?)</li><li>Inköp > Beställningar (hur fungerar mina order?)</li><li>Inköp > Enheter (hur många enheter säljer jag?)</li><li>[Magento: marknadsföring och handel](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#commerce)</li></ul> |
   | **[!UICONTROL Audience]** | <ul><li>Personmätvärden (hur många interagerar med mitt varumärke?)</li><li>Besökarprofil > Platsöversikt (vilka platser som används mest av användarna)</li><li>Besökarprofil > Geosegmentering > Geo Counties, Geo US States, Geo Regions, Geo Cities, Geo US DMA (Vilka platser besöker mina användare?)</li><li>Besökarprofil > Språk (vilket språk föredrar mina användare?)</li><li>Besökarprofil > Tidszoner (vilka tidszoner besöker mina användare?)</li><li>Besökarprofil > Domäner (Vilka internetleverantörer använder mina besökare för att komma åt min webbplats?)</li><li>Besökarprofil > Domäner på översta nivån (Vilka domäner kör trafik till min webbplats?)</li><li>Besöksprofil > Teknik > Teknik - översikt (Vilka tekniker använder människor för att komma åt min webbplats?)</li><li>Besökarprofil > Teknik > Webbläsare, webbläsartyp, webbläsarbredd, webbläsarhöjd (vilket företags webbläsare, webbläsarversion och dess bredd och höjd använder någon för att komma åt min webbplats?)</li><li>Besökarprofil > Teknik > Operativsystem, operativsystemtyper (vilket operativsystem och vilken version använder mina besökare?)</li><li>Besöksprofil > Teknik > Mobiloperatör (Vilka mobiloperatörer använder mina besökare för att besöka min webbplats?)</li><li>Bevarande av besökare > Returfrekvens (hur lång tid går det mellan min användares aktuella besök och tidigare besök?)</li><li>Bevarande av besökare > Returbesök (hur många av mina besök returnerar användare?)</li><li>Bevarande av besökare > Besök nummer (som besöks av sifferhaken styr de flesta av mina nyckeltal)</li><li>Besökarlojalitet > Försäljningscykel > Kundlojalitet (vilket lojalitetssegment tillhör mina användare?)</li><li>Bevarande av besökare > Försäljningscykel > Dagar före första köp (hur många dagar gick det mellan mitt användares första besök och deras första inköp?)</li><li>Bevarande av besökare > Försäljningscykel > Dagar sedan senaste köp (hur många dagar har gått mellan mitt användarbesök och det senaste köpet? )</li><li>Bevarande av besökare > Mobil > Enheter och enhetstyper (vilka enheter och enhetstyper använder mina besökare?)</li><li>Bevarande av besökare > Mobil > Tillverkare (Vilken mobilenhetstillverkare använder mina besökare?)</li><li>Bevarande av besökare > Mobil > Skärmstorlek, Skärmhöjd, Skärmbredd (Vilken mobilskärmstorlek/-höjd/bredd har mina besökare?)</li><li>Behåll besökarna > Mobil > [Användning av mobilappar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Behåll besökarna > Mobil > [Mobilappsresor](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Behåll besökarna > Mobil > [Mätvärden för mobilappar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Behåll besökarna > Mobil > [Mobilappsmeddelanden](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Behåll besökarna > Mobil > [Mobilappsprestanda](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Behåll besökarna > Mobil > [Underhåll av mobilappar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li></ul> |
   | **[!UICONTROL Acquisition]** | <ul><li>Marknadskanaler > Första beröringskanalen, Första beröringskanalen (Vilken första beröringskanal och vilken specifik första beröringskanal fungerar bäst?)</li><li>Marknadsföringskanaler > Första sista kanalen, Första sista kanalinformationen (Vilken sista beröringskanal och vilken specifik sista beröringskanal fungerar bäst?)</li><li>Campaigns > Campaigns (Vilka kampanjer driver min nyckelstatistik?)</li><li>Kampanjer > Kampanjresultat (Vilka kampanjer genererar störst intäkter?)</li><li>Kampanjer > Spårningskod (Vilka kampanjspårningskoder fungerar bäst?)</li><li>[Webbförvärv](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#web)</li><li>[Mobilförvärv](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>[Advertising Analytics: betalsökningar](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#advertising)</li><li>Söknyckelord - alla, betalda, naturliga (vilka söknyckelord och betalda/naturliga söknyckelord ger bäst nyckeltal?)</li><li>Sökmotorer - alla, betalda, naturliga (vilka sökmotorer och betalsökmotorer/naturliga sökmotorer ger mina nyckeltal bäst resultat?)</li><li>All rankning av söksidor (Vilken söksida besöker mina användare?)</li><li>Referensdomäner (Vilka domäner driver trafik till min plats?)</li><li>Ursprungliga refererande domäner (Vad var de första domänanvändarna var på innan de besökte min webbplats?)</li><li>Referenter (Vilka URL:er var mina användare på innan de klickade igenom till min webbplats?)</li><li>Refererartyper (vilken kategori tillhör mina refererande URL:er?)</li></ul> |

### Visa och spara en rapport {#use-reports}

Om du lämnar en rapport efter att ha gjort ändringar uppmanas du att spara eller ignorera ändringarna. Om du sparar ändringar i en rapport sparas rapporten som ett nytt projekt.

1. Gå till [!UICONTROL **Rapporter**] -fliken.
1. Markera den rapport som du vill visa. Till exempel, under [!UICONTROL **Mest populära**] väljer du [!UICONTROL **Sidor**] rapport.

   ![Sidrapport](assets/pages-report.png)

1. Sidrapporten, som den visas i Analysis Workspace, visar två [visualiseringar](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Stapeldiagram](/help/analyze/analysis-workspace/visualizations/bar.md) och [Sammanfattningsnummer](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)) och [Frihandsregister](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md). Det mätvärde som används är förekomster.
1. Gör något av följande:

   * Visa rapporten.
   * Dra ett eller flera segment till segmentsläppzonen längst upp. Dra till exempel segmentet [!UICONTROL **Mobilkunder**] och visa resultaten.
   * Ändra datumintervallet genom att gå till kalendern längst upp till höger.
   * Lägg till dimensionsanalyser, dra in andra mätvärden och anpassa rapporten generellt efter behov.

1. (Valfritt) Spara rapporten som ett projekt genom att välja [!UICONTROL **Projekt**] > [!UICONTROL **Spara**].

   Detta sparar rapporten som ett nytt projekt. den ändrar inte den befintliga rapporten. Mer information om hur du sparar en rapport som ett projekt finns i&quot;Skapa ett projekt från ett tomt projekt eller en rapport&quot; i [Skapa projekt](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md).

### Skapa en anpassad företagsrapport {#company-report}

Anpassade rapporter som skapats och sparats så att andra i ditt inloggningsföretag kan använda dem kallas företagsrapporter. Tidigare skapade företagsrapporter och nyskapade företagsrapporter finns listade i modal Create Project enligt nedan.

Så här skapar du en ny företagsrapport:

1. Bygg ett projekt i Analysis Workspace till önskat tillstånd.
1. Välj [!UICONTROL **Projekt**] > **[!UICONTROL Save as company report…]**.

   ![Företagsrapport](assets/company-report.png)

1. Uppdatera rapportens namn, lägg till en beskrivning och lägg till eventuella taggar och välj sedan [!UICONTROL **Spara som företagsrapport**].

   Rapporten läggs till i listan Företagsrapporter i modal Create Project och är tillgänglig för användare i ditt inloggningsföretag.

   Mer information om hur användare kan skapa ett projekt baserat på en företagsrapport finns i&quot;Skapa ett projekt från ett tomt projekt eller en rapport&quot; i [Skapa projekt](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md).

Fler utbildningsalternativ:

* Observera att du har tillgång till en 20-minuters videoöversikt över Analysis Workspace längst upp till vänster i alla rapporter du öppnar.
* För nya användare rekommenderar vi [Utbildning - självstudiekurs](https://www.youtube.com/watch?v=lCH1Kl1q9Wk) video som leder dig genom att bygga ett nytt projekt.
* Här är en länk till [fullständig Analysis Workspace-dokumentation](/help/analyze/analysis-workspace/home.md).
* Här är det fullständiga [YouTube spellista för Analysis Workspace](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS).

### Hantera företagsrapporter {#manage-company-reports}

Administratörer kan filtrera projektlistan för att visa och hantera företagsrapporter. Fastnålade objekt förblir fästa följt av listan med företagsrapporter som identifieras av ![rapportikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileTemplate_18_N.svg) rapportikon . I den här vyn kan du ta bort, byta namn på, tagga eller godkänna en eller flera rapporter.

Visa och hantera företagsrapporter

1. Välj **ANDRA FILTER** och sedan markera **Företagsrapporter**.
En lista över företagsrapporter visas. Alla vanliga projekt visas inte, såvida de inte är fästa.

   ![Visa företagsrapportfilter](assets/company-reports-filter.png)

   När företagsrapporter visas kan administratörer ta bort, byta namn på, lägga till en tagg eller godkänna rapporten.

1. Välj en rapport eller flera rapporter i rapportlistan.

1. Klicka på **...** elikonen bredvid en rapport om du vill visa de tillgängliga alternativen (Ta bort, Byt namn, Tagga och Godkänn).

   ![Åtgärder för företagsrapport](assets/company-reports-actions.png)

1. Välj ett alternativ (Ta bort, Byt namn, Tagga och Godkänn).

1. Om du vill återgå till den vanliga vyn när du är klar avmarkerar du alternativet Företagsrapporter igen i filterfältet.

### Ta bort en företagsrapport

Administratörer kan ta bort en rapport med alternativet Företagsrapportlista (beskrivs ovan) eller ta bort en rapport från alternativet Skapa projekt.

![Andra filter](assets/delete-fr-create-project-modal.png)

### Plats för mallar (kallas nu rapporter) {#templates}

| Namn på rapport (mall) | Rapportplats |
| --- | --- |
| Utbildning - självstudiekurs | Populäraste > Utbildning |
| Webbinnehållskonsumtion | Engagemang > Webbinnehållsförbrukning |
| Förbrukning av mediainnehåll | Engagement > Media Content Consumer |
| Enhetsövergripande analys | Engagement > Cross-Device Analysis |
| Webblagring | Engagemang > Web Retention |
| Medieljudförbrukning | Engagemang > Medieljudförbrukning |
| Medieåtergivning, frekvens, lojalitet | Engagement > Media Recency, Frequency, Loyalty |
| ITP-effekt | Engagemang > ITP Impact |
| Produktprestanda | Conversion > Products > Product Performance |
| Magento: Marknadsföring och handel | Konvertering > Magento: Marknadsföring och handel |
| Personmått | Audience > People Metric |
| Platsöversikt | Målgrupp > Besöksprofil > Platsöversikt |
| Tekniköversikt | Målgrupp > Besöksprofil > Teknik > Tekniköversikt |
| Användning av mobilappar | Målgrupp > Mobil > Användning av mobilappar |
| Mobila appresor | Målgrupp > Mobil > Mobila appresor |
| Mobilappsmått | Audience > Mobile > Mobile App Messaging |
| Mobilappsprestanda | Målgrupp > Mobiler > Mobilappsprestanda |
| Behåll mobilappar | Målgrupp > Mobil > Behåll mobilappar |
| Kampanjprestanda | Anskaffning > Kampanjer > Kampanjresultat |
| Mobilförvärv | Förvärv > Mobilvärvning |
| Webbförvärv | Anskaffning > Webbförvärv |
| Advertising Analytics: Betalsökning | Anskaffning > Advertising Analytics: Betalsökning |


## Använda fliken Utbildning {#navigate-learning}

Utbildningssidan innehåller praktiska videoutgångar, självstudiekurser och länkar till dokumentation.

På sidan Lär dig mer om nybörjare, mellanfunktioner och avancerade funktioner i Adobe Analytics.

### Gå till sidan Utbildning

1. I Adobe Analytics väljer du [!UICONTROL **Arbetsyta**] > [!UICONTROL **Utbildning**].

### Funktioner för utbildningssidor

* **Filterinnehåll:** Med ikonen Filter i den vänstra listen kan du filtrera utbildningsinnehåll efter erfarenhetsnivå (Nybörjare, Mellan eller Avancerat) och efter innehållstyp (Dokument, Video eller Tours och självstudiekurser).
* **Spåra förlopp:** När du har markerat en del av innehållet **[!UICONTROL Viewed]** -taggen visas. Den här taggen hjälper dig att spåra dina framsteg med utbildningsinnehållet. Du kan välja **[!UICONTROL Viewed]** för att ta bort den från ett visst innehåll.
* **Visa ytterligare innehåll:** När du visar en video väljer du **[!UICONTROL Learn more]** för att visa relaterat dokumentationsinnehåll på Experience League. Du kan också välja något av följande alternativ på sidan Lär dig mer om du vill visa ytterligare innehåll:
   * **[!UICONTROL Visit YouTube]:** Se hela spellistan för Analysis Workspace YouTube.
   * [!UICONTROL **Besök Experience League**]: Se hela uppsättningen Adobe Analytics-dokumentation för Experience League.
* **Grundläggande för nya användare:** The [!UICONTROL Workspace Fundamentals] vi rekommenderar för nya användare. Den här demon tar dig direkt till Workspace och leder dig igenom de vanligaste åtgärderna. Den här demon kan också öppnas igen när som helst i Workspace via verktygstipset i panelhuvudet.

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
| Var är mallarna som jag är van vid att se i [!UICONTROL Workspace]? | Mallarna är grupperade under [!UICONTROL Reports] -fliken. |
| Överför mitt arbete i betaprogrammets användargränssnitt till produktionen [!UICONTROL Workspace] upplevelse? | Ja, allt arbete som görs i betan överförs till den gamla/aktuella [!UICONTROL Workspace] upplevelse. |
| Är min nuvarande [!DNL Reports & Analytics] favoriter? | Nej, de förs INTE vidare. Men om [!UICONTROL Workspace] projektfavoriter överförs. |
| Finns det ett maximalt antal projekt jag kan fästa? | Nej, det finns ingen gräns för hur många projekt du kan fästa. |
| Kan administratörer ange den här landningssidan för sina användare? | Nej, administratörer kan inte ange landningssidan för användarnas räkning. Enskilda användare måste aktivera växeln själva. |
| Finns alla rapporter i [!DNL Reports & Analytics] fortfarande tillgängliga? | Nej, följande rapporter har fasats ut baserat på övergripande användningsdata: <ul><li>Anpassade eVars/props/events/classifications<li>Mina rekommenderade rapporter</li><li>unika besökare varje timme/dag/vecka/månad/kvartal/år</li><li>unika kunder varje vecka/månad/kvartal/år</li><li>Åtgärdsnamn - djup</li><li>Sammanfattning av åtgärdsnamn</li><li>Lägg till instrumentpanel</li><li>Ålder</li><li>Stöd för ljud</li><li>Faktureringsinformation</li><li>Klicka på sidan</li><li>Färgdjup</li><li>Cookie-stöd</li><li>Cookies</li><li>Anslutningstyper</li><li>Kreativa element</li><li>Kreditkortstyp</li><li>Korsförsäljning</li><li>Anpassade händelsegrupper</li><li>Egna länkar</li><li>Kund-ID</li><li>Veckodag</li><li>Åtgärdsnamn för registrering</li><li>Avsluta åtgärdsnamn</li><li>Avsluta länkar</li><li>Utfall</li><li>Filnedladdningar</li><li>Sök i butik</li><li>Fullständiga banor</li><li>Kön</li><li>Träffype-VISTA-regel</li><li>Bildstöd</li><li>Java</li><li>JavaScript</li><li>JavaScript-version</li><li>Hantera bokmärken</li><li>Hantera instrumentpaneler</li><li>Skärmfärgdjup</li><li>Övervaka upplösningar</li><li>Nyhetsbrev - registreringar</li><li>Nästa åtgärdsnamn</li><li>Nästa åtgärdsnamnflöde</li><li>Null-sökningar</li><li>Operativsystem</li><li>Ordergranskning</li><li>Dagens sida</li><li>Sidorna hittades inte</li><li>Banhanteraren</li><li>Banlängd</li><li>Föregående åtgärdsnamn</li><li>Namnflöde för föregående åtgärd</li><li>Produktaktivitet</li><li>Produktkostnad</li><li>Produktavdelning</li><li>Produktlagerkategori</li><li>Produktnamn</li><li>Produktrecensioner</li><li>Produktsäsong</li><li>Produktdelningar</li><li>Produktzoomningar</li><li>Läs in igen</li><li>Sökningar</li><li>Servrar</li><li>Besök enstaka sidor</li><li>Leveransinformation</li><li>Platshierarki</li><li>Sociala omnämnanden</li><li>Tid på dagen</li><li>Tid som använts för åtgärdsnamn</li><li>Stöd för video</li><li>Besökarläge</li></ul> |
