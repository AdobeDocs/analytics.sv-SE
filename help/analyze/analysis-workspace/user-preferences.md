---
title: Användarinställningar
description: Lär dig hur du anger allmänna inställningar och projektinställningar för användare.
feature: Workspace Basics
role: User, Admin
exl-id: f32e3061-f396-4730-96e1-d251b00e32f0
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '3363'
ht-degree: 0%

---

# Användarinställningar

Du kan hantera inställningar för Analysis Workspace och dess relaterade komponenter för alla nya projekt eller paneler som du skapar. Befintliga projekt och paneler påverkas inte.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Hantera inställningar](https://video.tv.adobe.com/v/3429989/?quality=12&learn=on&captions=swe){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

## Uppdatera inställningar

Du kan uppdatera dina inställningar på följande sätt:

- Välj ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Edit preferences]** i Workspace huvudgränssnitt.
- Välj **[!UICONTROL Project]** > **[!UICONTROL User preferences]** på menyn när du arbetar i ett Workspace-projekt.
- Välj **[!UICONTROL Components]** > **[!UICONTROL Preferences]** på den övre menyraden i Customer Journey Analytics (endast tillgängligt för produktadministratörer).

## Konfigurera inställningar

Du kan konfigurera följande inställningar:


## Allmänna inställningar

Du kan anpassa allmänna inställningar för alla nya projekt som du skapar i Analysis Workspace. Mer information om hur du kommer åt de här inställningarna finns i [Uppdatera inställningar](#update-preferences).

| Inställningar | Alternativ |
| --- | --- |
| Landningssida | Välj vilken sida som ska visas som standardsida när du öppnar Adobe Analytics: <ul><li>Projektlista (standard)</li><li>Tomt projekt</li><li>Specifikt projekt valt från en lista</li></ul> |
| Visa tips | Visar tips i en blå ruta längst ned till höger i Analysis Workspace. <p>Det här alternativet är aktiverat som standard.</p> |
| Komponenter som visas i grupper med vänster skena | Välj hur många av varje komponent som ska visas på komponentmenyn i den vänstra listen. <p>Om du väljer 0 är komponenten inte längre tillgänglig från den vänstra listen på arbetsytorna.</p><p>Som standard visas fem komponenter för vart och ett av följande:</p> <ul><li>Mått</li><li>Mätvärden</li><li>Filter</li><li>Datumintervall</li></ul> <p>Mer information om komponenter i Analysis Workspace finns i [Komponentöversikt](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).</p> |

## Företagsinställningar {#company-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_shareonlyworkspace"
>title="Tillåt endast delning med Workspace-användare"
>abstract="När alternativet **[!UICONTROL Share with anyone]** är aktiverat är det inte längre tillgängligt för användare när de delar ett Analysis Workspace-projekt. Personer som tidigare fått åtkomst till ett projekt via det här delningsalternativet har inte längre åtkomst till projektet."

>[!CONTEXTUALHELP]
>id="workspace_prefs_requireexperiencecloudauth"
>title="Kräv Experience Cloud-autentisering"
>abstract="När det här alternativet är aktiverat måste personer som får åtkomst till ett projekt från alternativet **[!UICONTROL Share with anyone]** i Analysis Workspace autentisera med sina Experience Cloud-autentiseringsuppgifter."

>[!CONTEXTUALHELP]
>id="workspace_prefs_projectcommenting"
>title="Tillåt kommentarer i projekt"
>abstract="När det här alternativet är aktiverat finns det ett kommentarsområde till höger om varje projekt i Analysis Workspace."


Du kan uppdatera företagsinställningarna som gäller för alla användare och projekt i organisationen. Mer information om hur du kommer åt de här inställningarna finns i [Uppdatera inställningar](#update-preferences).

| Avsnitt | Inställningar | Alternativ |
| --- | --- | --- |
| **Fliken Mallar** | | |
|  | Dölj fliken Mallar | Döljer fliken Mallar för alla användare i organisationen. |
| **Projektdelning** | | |
| | Tillåt endast delning med Workspace-användare | När det här alternativet är aktiverat kan användare i organisationen inte se alternativet **[!UICONTROL Share with anyone]** på menyn **[!UICONTROL Share]**. Användare kan inte dela projekt med personer som inte har ett Analysis Workspace-konto i din organisation enligt beskrivningen i [Dela ett projekt med någon (ingen inloggning krävs)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link).<br/>Det här alternativet är inaktiverat som standard för alla organisationer, förutom för kunder som har licensierat vårdsköld. <p>Tänk på följande när du aktiverar eller inaktiverar det här alternativet:<ul><li>När du aktiverar det här alternativet kan personer som tidigare fått åtkomst till ett projekt via delningsalternativet **[!UICONTROL Share with anyone]** inte längre få åtkomst till projektet.</li><li>Om det här alternativet är aktiverat (för att endast tillåta delning med Workspace-användare) och sedan inaktiveras (för att tillåta delning med vem som helst), kommer personer som tidigare fått åtkomst till ett projekt via delningsalternativet **[!UICONTROL Share with anyone]** inte automatiskt att få tillgång till projektet. I det här fallet måste användaren som delade projektet aktivera alternativet [!UICONTROL **Link är aktivt**] som är tillgängligt när ett projekt delas med någon **([!UICONTROL Share]** > **[!UICONTROL Share with anyone]**), vilket beskrivs i [Dela ett projekt med vem som helst (ingen inloggning krävs)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link).</li><li>**För kunder som licensierar hälsovård:** Det här alternativet är aktiverat som standard och kan inte inaktiveras. Innan du kan inaktivera det här alternativet så att användare kan använda delningsalternativet **[!UICONTROL Share with anyone]** måste du först lägga till behörigheten [!UICONTROL Share project links with anyone] (som finns under [!UICONTROL Reporting Tools]) i Adobe Admin Console. När behörigheten har lagts till kan du inaktivera det här alternativet och sedan godkänna det juridiska meddelandet. Mer information om hur du lägger till en behörighet i Admin Console finns i [Hantera produktbehörigheter i Admin Console](https://helpx.adobe.com/se/enterprise/using/manage-permissions-and-roles.html).</li></ul> |
| | Kräv Experience Cloud-autentisering | När det här alternativet är aktiverat måste personer som får åtkomst till ett projekt från alternativet **[!UICONTROL Share with anyone]** i Analysis Workspace autentisera med sina Experience Cloud-autentiseringsuppgifter.<p>När det här alternativet är aktiverat aktiveras alternativet **[!UICONTROL Share with anyone]** i delningsdialogrutan när en användare delar ett projekt med delningsalternativet **[!UICONTROL Require Experience Cloud authentication]** och det kan inte inaktiveras av den användare som delar projektet. Mer information om hur användare kan dela projekt med vem som helst finns i [Dela ett projekt med vem som helst (ingen inloggning krävs)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link). <p> <p>Tänk på följande när du aktiverar det här alternativet: <ul><li>När du aktiverar det här alternativet inaktiveras alla projekt som tidigare delats med delningsalternativet **[!UICONTROL Share with anyone]** och som inte har alternativet [!UICONTROL Require Experience Cloud authentication] aktiverat.<p>Om det här alternativet är aktiverat (för att kräva Experience Cloud-autentisering) och sedan inaktiverat (för att tillåta alla med länken att komma åt projektet), kommer personer som tidigare fått åtkomst till ett projekt via delningsalternativet **[!UICONTROL Share with anyone]** inte automatiskt att återfå sin åtkomst till projektet. I det här fallet måste användaren som delade projektet aktivera alternativet [!UICONTROL Link is active] som är tillgängligt när ett projekt delas med någon **([!UICONTROL Share]** > **[!UICONTROL Share with anyone]** > **[!UICONTROL Link is active]**), vilket beskrivs i [Dela ett projekt med vem som helst (ingen inloggning krävs)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link).</li><li>Det här alternativet är bara tillgängligt om enkel inloggning har implementerats i din organisation. Mer information om hur systemadministratörer kan aktivera enkel inloggning för din organisation finns i [Konfigurera identitet och enkel inloggning](https://helpx.adobe.com/se/enterprise/using/set-up-identity.html).</p><p>Om enkel inloggning har konfigurerats för din organisation kontrollerar du om någon typ av autokontoskapande har implementerats i konsolen. Vanligtvis konfigurerar en systemadministratör detta enligt beskrivningen i [Aktivera automatiskt skapande av konto](https://helpx.adobe.com/se/enterprise/using/automatic-account-creation.html).</li><li>Om din organisation licensierar hälso- och sjukvårdssköld är det här alternativet aktiverat som standard och kan inte inaktiveras.</li></ul> |

{style="table-layout:auto"}

## Inställningar för projekt och analys {#project-analyses-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_categoricalpalette"
>title="Kategoriserad palett"
>abstract="Gäller många visualiseringar i Analysis Workspace och guidad analys. Varje färg representerar ett tydligt kategoriserat värde."

>[!CONTEXTUALHELP]
>id="workspace_prefs_divergingpalette"
>title="Förvrängningspalett"
>abstract="Används för kohorttabellen i Analysis Workspace och för guidad analys av användartillväxt. Den här paletten har en numerisk betydelse med två extremvärden och en baslinje i mitten."

>[!CONTEXTUALHELP]
>id="workspace_prefs_sequentialpalette"
>title="Sekventiell palett"
>abstract="Används för den guidade analysen av frekvenstrender (staplade fält). Den här paletten har en numerisk innebörd från ljust till mörkt."

Du kan anpassa projektinställningarna för alla nya projekt som du skapar i Analysis Workspace. Mer information om hur du kommer åt de här inställningarna finns i [Uppdatera inställningar](#update-preferences).

Vissa av dessa inställningar kan också anpassas för enskilda projekt, vilket beskrivs i [Projektöversikt](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).

Klicka på de länkade inställningsrubrikerna för mer information och kontext om varje inställning.

| Avsnitt | Inställningar | Alternativ |
| --- | --- | --- |
| **Visning** | | |
|  | [Visa densitet](/help/analyze/analysis-workspace/build-workspace-project/view-density.md) | Välj hur mycket innehåll som ska visas på skärmen genom att minska den lodräta utfyllnaden för den vänstra listen, frihandstabeller och kohorttabeller. <ul><li>Kompakt</li><li>Bekväm</li><li>Utökad (standard)</li></ul> |
| | [Färgpaletten](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md) | Välj de visualiseringsfärgpaletter som används i Analysis Workspace.<ul><li>**Kategorisisk palett**: Används för många visualiseringar i Analysis Workspace. Varje färg representerar ett tydligt kategoriserat värde. Välj mellan alternativ som tillhandahålls av Adobe eller ange en anpassad palett som definieras av kommaavgränsade hexvärden.</li><li>**Divergerande palett**: Används i kohorttabellen i Analysis Workspace. Den här paletten har en numerisk betydelse med två extremvärden och en baslinje i mitten.</li><li>**Sekventiell palett**: Används för den guidade analysen av frekvenstrender (staplade fält). Den här paletten har en numerisk innebörd från ljust till mörkt.</li></ul> |
| **Data** | | |
|  | [Rapportsviten](/help/analyze/analysis-workspace/c-panels/panels.md) | Välj var tabeller och visualiseringar ska hämta sina data. <ul><li>Senaste (standard)</li><li>Specifik rapportsvit som valts i en lista</li></ul> |
|  | [Kalender](/help/analyze/analysis-workspace/c-panels/panels.md) | Välj i en lista över: <ul><li>Intervall som tillhandahålls av Adobe (standard är denna månad)</li><li>Anpassade intervall</li></ul> |
|  | [Paneltyp](/help/analyze/analysis-workspace/c-panels/panels.md) | <ul><li>Frihandsfigur (standard)</li><li>Tom</li><li>Snabba insikter</li></ul> |
|  | Antal upprepande instanser | Anger om upprepade instanser räknas i rapporter. Den här inställningen (när den är aktiverad) hanterar flera på varandra följande sidvyer till samma sida som flera sidvyer. När det är inaktiverat räknas de som en enda sidvy. <p>**Obs!** Den här inställningen påverkar bara vissa mått (t.ex. enkelsidiga besök) och den gäller inte för visualiseringar av flöde och utfall.</p> |
|  | Nummerformat | <ul><li>1 000,00 (standard)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | CSV-avgränsningstecken | <ul><li>Komma (standard)</li><li>Semikolon</li><li>Colon</li><li>Pipe</li><li>Period</li><li>Blanksteg</li><li>Tabb</li></ul> |
|  | Visa anteckningar | Välj om anteckningar ska visas i dina projekt. Mer information om anteckningar finns i [Översikt över anteckningar](/help/analyze/analysis-workspace/components/annotations/overview.md). |

## Inställningar för frihandstabell {#freeform-table-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_showanomalies"
>title="Visa avvikelser"
>abstract="Om du väljer **[!UICONTROL Show anomalies]** körs avvikelseidentifiering automatiskt på den första metriska kolumnen som läggs till i en tidsserievisualisering av Freeform-tabell."

>[!CONTEXTUALHELP]
>id="workspace_prefs_showforecast"
>title="Visa prognos"
>abstract="Om du väljer **[!UICONTROL Show forecast]** förutspås automatiskt den första måttkolumnen som lagts till i en tidsserie visualisering av friformstabellen."


>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulttablemetric"
>title="Standardtabellmått"
>abstract="Välj standardmåttet som ska användas för frihandstabeller. Om den markerade datavyn inte innehåller det valda standardmåttet växlar tabellen automatiskt till ett annat primärt mått."


Du kan anpassa inställningarna för frihandstabeller för alla nya projekt som du skapar i Analysis Workspace. Mer information om hur du kommer åt de här inställningarna finns i [Uppdatera inställningar](#update-preferences).

Vissa av dessa inställningar kan även anpassas för enskilda tabeller.

Klicka på de länkade avsnittsrubrikerna för mer information och kontext om de tillgängliga inställningarna.

| Avsnitt | Inställningar | Alternativ |
| --- | --- | --- |
| **Tabell** | | |
| | Tabelltyp | <ul><li>Frihandsfigur</li><li>Table builder</li></ul> |
| | Standardtabellmått | <ul><li>Förekomster</li><li>Unika besökare</li><li>Besök</li></ul> |
| | Standardregisterdimension | Välj mellan Minute, Timme, Dag, Vecka, Månad, Kvartal eller År. |
| | Justera datum | Välj det här alternativet om du vill justera datum från varje kolumn så att alla börjar på samma rad. |
| **[Kolumn](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | Radbryt rubriktext | Radbryt rubriktexten i frihandstabeller så att rubrikerna blir lättare att läsa och tabellerna blir mer delbara. Figursättningen är användbar för PDF-återgivning och för mått med långa namn. Aktiverat som standard. |
| | Visa summor | Denna summa är vanligtvis lika med eller en delmängd av [!UICONTROL Grand total]. Alla tabellfilter som används i frihandstabellen, inklusive alternativet [!UICONTROL Include None], visas. |
| | Visa totalsummor | Den här summan representerar alla träffar som har samlats in, ibland kallade *totalt rapportpaket*. När ett segment används antingen på panelnivå eller i friformstabellen justeras det totala värdet så att alla träffar som matchar segmentvillkoren visas. Summan stöds inte för tabeller eller uppdelningar med [statiska rader](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| | Visa miniatyrdiagram | Visa eller dölj linjediagram längst ned i diagrammet. När teckenförklaringen är dold ändras den inte längre till att referera till raderna visuellt. |
| | Nummer | Avgör om en cell visar/döljer det numeriska värdet för måttet. Om måttet till exempel är sidvyer är det numeriska värdet antalet sidvyer för radobjektet. |
| | Procent | Avgör om en cell visar/döljer procentvärdet för måttet. Om måttet till exempel är sidvyer är procentvärdet antalet sidvyer för radobjektet delat med de totala sidvyerna för kolumnen.  Obs! För att vara mer exakt: procenttal som är större än 100 % visas ibland. Det övre gränsvärdet flyttas till 1 000 % för att säkerställa att kolumnerna kan växa i för stora bredder. |
| | Visa avvikelser | Avgör om avvikelseidentifiering körs på värdena i den här kolumnen. |
| | Tolka noll som inget värde | För celler med värdet 0 anger om en 0-cell eller en tom cell ska visas. Det här är användbart när du tittar på data för varje dag i en månad, och vissa dagar har inte inträffat än.  I stället för att visa 0 för framtida datum kan tomma celler visas i stället. Diagram följer även den här inställningen (det vill säga de visar inte en linje eller stapel med 0 värden när den här inställningen är markerad). |
| | Bakgrund | Anger om en cell visar/döljer all cellformatering, inklusive stapeldiagrammet och villkorsstyrd formatering <ul><li>Stolpdiagram</li> Ett vågrätt stolpdiagram som representerar cellens värde i förhållande till totalvärdet för kolumnen. <li>Villkorsstyrd formatering</li>Mer information om villkorlig formatering finns i Villkorsstyrd formatering i [Kolumninställningar](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)</ul> |
| | Cellförhandsgranskning | En förhandsvisning av hur varje cell visas med de valda formateringsalternativen. |
| **[Rad](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | Uppdelning efter position | Välj det här alternativet om du vill att detaljerna ska ligga kvar vid objektets position i stället för själva objektet. Mer information om uppdelningar finns i [Dela upp dimensioner](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md). |
| | Procentberäkning | <ul><li>Kolumn</li><li>Rad</li></ul> |
| | Kolumnsummor (endast statiska rader) | <ul><li>Visa summan av rader: Visar summan av enskilda radobjekt </li><li>Visa totalsumma: visar den borttagna dubblettsumman av rader.</li></ul> |

## Visualiseringsinställningar

Du kan uppdatera visualiseringsinställningarna för alla nya projekt som du skapar i Analysis Workspace. Mer information om hur du kommer åt de här inställningarna finns i [Uppdatera inställningar](#update-preferences).

Vissa av dessa inställningar kan också anpassas för individuella visualiseringar.

Klicka på de länkade avsnittsrubrikerna för mer information och kontext om de tillgängliga inställningarna.

| Avsnitt | Inställningar | Alternativ |
| --- | --- | --- |
| **Allmänna standardinställningar** | | |
| | Procenttal | Visar värden i procent för alla visualiseringar. |
| | Förklaring synlig | Gör att du kan dölja förklaringstexten för alla visualiseringar. |
| | Begränsa högsta antal objekt | Minskar antalet objekt på X-axeln för alla visualiseringar. Detta kan vara användbart om du har en stor datauppsättning. |
| | Visa dubbelaxel (om tillämpligt) | Gäller endast om du har två mätvärden - du kan ha en y-axel till vänster (för ett mätresultat) och till höger (för övriga mätvärden). Den här inställningen är användbar när plottade mätvärden har mycket olika förstoringsgrader. |
| | Normalisering (om tillämpligt) | Tvingar måtten att ha samma proportioner. Den här inställningen är användbar när plottade mätvärden har mycket olika förstoringsgrader. |
| | Fästpunkt Y-axel vid noll | Om alla värden som är ritade i diagrammet ligger betydligt över noll, gör diagrammets standardvärde att y-axelns undre del inte är noll. Om du markerar den här rutan tvingas y-axeln till noll (och diagrammet ritas om). |
| | Tillåt avvikelser att skala Y-axeln | Om du har flera mätvärden i ett diagram måste du hovra över varje avvikelse för att se konfidensintervallet för det måttet. För att göra visualiseringen mer läsbar skalas inte y-axeln automatiskt i konfidensintervallet för avvikelseidentifiering. Med det här alternativet kan konfidensintervallet skalförändra visualiseringen. <p>Mer information finns i [Visa avvikelser i Analysis Workspace](/help/analyze/analysis-workspace/c-anomaly-detection/view-anomalies.md).</p> |
| **[Linjediagram](/help/analyze/analysis-workspace/visualizations/line.md)** | | |
| | Procenttal | Visar värden i procent för linjevisualiseringar. |
| | Förklaring synlig | Dölj den detaljerade förklaringstexten för linjevisualiseringen. |
| | Begränsa högsta antal objekt | Minskar antalet objekt på X-axeln i linjevisualiseringen. Den här inställningen är användbar om du har en stor datauppsättning. |
| | Visa dubbelaxel (om tillämpligt) | Gäller endast om du har två mätvärden - du kan ha en y-axel till vänster (för ett mätresultat) och till höger (för övriga mätvärden). Den här inställningen är användbar när plottade mätvärden har mycket olika förstoringsgrader. |
| | Normalisering (om tillämpligt) | Tvingar måtten att ha samma proportioner. Den här inställningen är användbar när plottade mätvärden har mycket olika förstoringsgrader. |
| | Visa x-axel | Visar x-axeln i linjediagrammet. |
| | Visa y-axel | Visar y-axeln i linjediagrammet. |
| | Fästpunkt Y-axel | Om alla värden som är ritade i diagrammet ligger betydligt över noll, gör diagrammets standardvärde att y-axelns undre del inte är noll. Om du markerar den här rutan tvingas y-axeln till noll (och diagrammet ritas om). |
| | Visa min | Täck över en minimivärdetikett för att snabbt markera värdena i ett mätresultat. Obs! Minsta värden härleds från synliga datapunkter i visualiseringen, inte från hela uppsättningen värden inom en dimension. |
| | Visa max | lägg över en maxvärdetikett för att snabbt markera topparna i ett mätresultat. Obs! De högsta värdena härleds från de synliga datapunkterna i visualiseringen, inte från hela uppsättningen värden inom en dimension. |
| | Visa trendlinje | Visa en regression eller en glidande medeltrendlinje i linjeserien. Trendlinjer hjälper till att beskriva ett tydligare mönster i data. |
| **[Kohort](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | Kornighet | För trendvisualiseringar kan du ändra tidgranulariteten (dag, vecka, månad, kvartal eller år). Den här ändringen gäller även för datakälltabellen. |
| | Visa endast procent | Tar bort talvärdet och visar bara procentvärdet. |
| | Avrunda procent till närmaste heltal | Avrundar procentvärdet till närmaste heltal i stället för att visa decimalvärdet. |
| | Visa genomsnittlig procentrad | Infogar en ny rad högst upp i tabellen och lägger sedan till medelvärdet för värdena i varje kolumn. |
| | Förhandsgranska kohort | En förhandsvisning av hur färgpaletten visas i kohortvisualiseringen. |
| | Kohortpalett | Den färgpalett som används i kohortvisualiseringen. |
| **[Kombinationsdiagram](/help/analyze/analysis-workspace/visualizations/combo-charts.md)** | | |
| | Visa X-axel | Visar x-axeln i kombinationsdiagrammet. |
| | Visa Y-axel | Visar y-axeln i kombinationsdiagrammet. |
| | Visa streckade linjer | Visa streckade linjer i kombinationsdiagram. |
| **[Sammanfattning av nyckelmått](/help/analyze/analysis-workspace/visualizations/key-metric.md)** | | |
| | Visningstyp för sammanfattning | <ul><li>Betonar procentuell ändring</li><li>Betonar talvärde</li></ul> |
| | Visa miniatyrbilder | Visa eller dölj linjediagram längst ned i diagrammet. När teckenförklaringen är dold ändras den inte längre till att referera till raderna visuellt. |
| | Visa max och min för miniatyrbilder | Visa lägsta och högsta värden i primära och jämförande raddiagram. |
| | Visa jämförelse | Visa jämförelsedata. När det är dolt döljs både jämförelsetabellen och de sammanfattande ändringsobjekten. |
| | Alternativ för talvärde | I avsnittet [!UICONTROL **Sammanfattning av nyckelmått**] <ul><li>Visa procentuell ändring</li><li>Visa rådifferens</li>Rådifferens mellan det totala värdet för måttet i det primära datumintervallet och det sekundära datumintervallet</ul> |
| **[Utfall](/help/analyze/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | Behållare | Växla mellan Besök och Besök för att analysera besökarnas sökvägar. Standardvärdet är Visitor. Dessa inställningar hjälper er att förstå besökarnas engagemang på besökarnivå (mellan besök) eller begränsa analysen till ett enda besök. <p>Följande alternativ är tillgängliga:</p> <ul><li>Besök</li><li>Besökare</li></ul> |
| **[Flöde](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | Behållare | I avsnittet [!UICONTROL **Flöde**] <ul><li>Besök</li><li>Besökare</li></ul> |
| | Radbryt etiketter | Etiketterna på Flow-elementen trunkeras normalt för att spara skärmutrymme, men du kan göra hela etiketten synlig genom att markera den här rutan. Standard = avmarkerat. |
| | Inkludera upprepade förekomster | Flödesvisualiseringar baseras på instanser av en dimension. Den här inställningen ger dig möjlighet att inkludera eller exkludera upprepade instanser, till exempel Sidomladdning. Det går dock inte att ta bort upprepningar från Flow-visualiseringar som innehåller flervärdesdimensioner, som listVars, listProps, s.product, merchandising eVars osv. Standard = avmarkerat. |
| | Visa verktygstips | Avgör om verktygstips, som innehåller noddata, ska visas när du hovrar över enskilda noder i en flödesvisualisering. |
| | Antal kolumner | Anger hur många kolumner du vill ha i flödesdiagrammet. |
| | Objekt utökade per kolumn | Hur många objekt du vill ha i varje kolumn. |
| **Skiktade diagram** | | |
| | 100 % staplad | Den här inställningen för staplade ytor, staplade staplade staplar eller vågräta staplade visualiseringar gör att diagrammet blir en&quot;100 % staplade&quot; visualisering. <p>Mer information finns i [Stapel och stapel](/help/analyze/analysis-workspace/visualizations/bar.md).</p> |
| **[Histogram](/help/analyze/analysis-workspace/visualizations/histogram.md)** | | |
| | Antal fickor | Välj antalet dataintervall (bucket) i visualiseringen. Det högsta antalet bucklor är 50. <p>Mer information finns i [Histogram](/help/analyze/analysis-workspace/visualizations/histogram.md).</p> |
| | Inventeringsmetod | Välj bland följande alternativ: <ul><li>Träff</li><li>Besök</li><li>Besökare</li></ul> <p>Om du till exempel använder sidvyer kan du välja sidvyer per besökare, sidvyer per besök eller sidvyer per träff. För Träff används&quot;Förekomster&quot; som y-axelmått i en friformstabell.</p> |
| **[Mappa](/help/analyze/analysis-workspace/visualizations/map-visualization.md)** | | |
| | Ritningsdimension | <ul><li>Mobil latitud/longitud</li><li>Geografisk dimension</li></ul> |
| | Karttyp | <ul><li>Bubblor</li><li>Värmekarta</li></ul> |
| | Färgtema | Välj mellan Coral, Reds, Green, Blues, Heatmap och Positive/Negative. |
| | Kartstil | Välj mellan Basic, Streets, Bright, Light, Dark och Satellite. |
| **[Sammanfattningsändring](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Värde | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>Procentuell ändring</li><li>Rådifferens</li></ul> |
| | Procenttal | Visar värden i procent för visualiseringar av sammanfattningsändringar. |
| | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för visualiseringen av Sammanfattningsändring. |
| | Förkortningsvärde | När du väljer det här alternativet anger du antalet decimaler. |
| **[Sammanfattningsnummer](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Procenttal | Visar värden i procent för visualiseringar av sammanfattningsnummer. |
| | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för visualisering av sammanfattningsnummer. |
| | Sammanfattningsvärde per | Välj mellan Max, Min, Medel, Median och Summa. |
| | Förkortningsvärde | När du väljer det här alternativet anger du antalet decimaler. |
| **[Treemap-diagram](/help/analyze/analysis-workspace/visualizations/treemap.md)** | | |
| | Procenttal | Visar värden i procent för Treemap-visualiseringar. |
| | Begränsa högsta antal objekt | Minskar antalet objekt på X-axeln i Treemaps visualisering. Detta kan vara användbart om du har en stor datauppsättning. |
| **[Venn](/help/analyze/analysis-workspace/visualizations/venn.md)** | | |
| | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för Vennvisualiseringen. |
| **[Spridning](/help/analyze/analysis-workspace/visualizations/scatterplot.md)** | | |
| | Procenttal | Visar värden i procent för Spridningsvisualiseringar. |
| | Förklaring synlig | Gör att du kan dölja den detaljerade förklaringstexten för Spridningsvisualiseringen. |
| | Begränsa högsta antal objekt | Minskar antalet objekt på X-axeln i Spridningsvisualiseringen. Detta kan vara användbart om du har en stor datauppsättning. |
| | Fästpunkt y-axel vid noll | Om alla värden som är ritade i diagrammet ligger betydligt över noll, gör diagrammets standardvärde att y-axelns undre del inte är noll. Om du markerar den här rutan tvingas y-axeln till noll (och diagrammet ritas om). |

## Återställ standardinställningar

Du kan återställa alla dina användarinställningar till standardinställningarna. Det här alternativet påverkar inte administratörsinställningarna på fliken **[!UICONTROL Company]**. Det går inte att ångra den här åtgärden.

1. I Adobe Analytics väljer du [!UICONTROL **Komponenter**] **>** [!UICONTROL **Inställningar**] på den översta menyn. Eller välj **[!UICONTROL Project]** > **[!UICONTROL User settings]** på Workspace-menyn.

1. Välj **[!UICONTROL Restore defaults]** i det övre högra hörnet.

1. Välj **[!UICONTROL Restore defaults]** i **[!UICONTROL Restore system default settings]**.

## [!UICONTROL Dark theme]

Om du föredrar en mörk bakgrund för ditt Customer Journey Analytics-användargränssnitt kan du växla till [!UICONTROL Dark theme].

1. Välj Experience Cloud-ikonen längst upp till höger.

   ![mörkt-tema](assets/dark-theme.png)

1. Aktivera **[!UICONTROL Dark theme]**.

