---
description: 'null'
title: Översikt över Advertising Analytics
uuid: 00e461ff-3e17-4071-818b-93fd1e4b36f1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Översikt över Advertising Analytics

Med Advertising Analytics kan ni se alla era Google- och Bing Paid Search-data sida vid sida, inifrån Adobe Analytics. Tidigare måste alla Google AdWords/DFA- eller Microsoft Bing Ads-data visas i Adobe Advertising Cloud (AMO) eller i Google/Bing. Du får nu följande data i Adobe Analytics: Impressions, Clicks, Costs, Quality Score och Average Position direkt från sökmotorerna samt en AMO ID-instans (Click Instances).

>[!NOTE] Yahoo Gemini absorberades av Microsoft Bing den 31 mars 2019. Detta innebär att annonskontoalternativet Yahoo Gemini inte längre är tillgängligt.

Genom att samla data från dessa sökmotorer i Adobe Analytics kan ni analysera dessa data med hjälp av Analysis Workspace. Den här analysen underlättas av en ny mall för [betalningsprestanda](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) i arbetsytan.

![](assets/aa_aw.png)

Denna integrering riktar sig till följande målgrupper:

* Den **analytiker** som behöver samla in resultatrapporter för den betalande sökmarknadsföraren.
* Den **betalande sökmarknadsföraren** som söker svar på följande frågor: Hur mycket trafik skickar jag till vår webbplats och konverterar kunderna? Vilka är mina kostnadseffektiva annonskampanjer?

## Förutsättningar {#section_C25E0CA3474C4EDEAEAA9A5B8AAC9299}

* Advertising Analytics finns endast för SKU:erna Adobe Analytics [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html)och [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) .

* Den här funktionaliteten är tillgänglig för kunder som inte använder Advertising Cloud eller AMO.
* Du måste vara Adobe Analytics-administratör för att få tillgång till Advertising Analytics. Därefter kan du [ge icke-administratörer åtkomstbehörigheter](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) .
* Alla analysrapportsviter där du vill visa Google-/Bing-sökdata måste [mappas till din Experience Cloud-organisation](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).
* För alla rapportsviter där du vill visa Google-/Bing-sökdata måste du [aktivera dessa rapportsviter för Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Admin]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**).

* Du behöver inloggningsuppgifter för en användare med redigeringsbehörighet för det/de sökkonto/sökkonton som du vill integrera med Adobe Analytics, till exempel ett Google-konto-ID och ett lösenord.
* När det gäller Bing Ads behöver du också Bing Customer ID.
* Om du använder Internet Explorer 11 (eller tidigare) kommer du inte att kunna [konfigurera ett annonskonto](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) för någon av de tre sökmotorerna. Använd andra webbläsare i stället.

## Tillstånd för annonsanalys {#section_FCC58EB635954A32990D4E67B52B4369}

Analyserna har två behörigheter som automatiskt tilldelas Analytics-administratörer. Administratörer kan sedan välja att ge dessa behörigheter till icke-administratörer.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Behörighet </th> 
   <th colname="col2" class="entry"> Definition </th> 
   <th colname="col3" class="entry"> Bevilja tillstånd i Adobe Analytics </th> 
   <th colname="col4" class="entry"> Bevilja behörighet om du är inloggad på Adobe Experience Cloud </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Hantering av annonsanalys </p> </td> 
   <td colname="col2"> <p>Tillåter användare att konfigurera/redigera/visa annonssökkonton. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> Användarhantering</span> &gt; <span class="uicontrol"> Grupper</span> &gt; Redigera all rapportåtkomst <span class="uicontrol"> &gt;</span> Anpassa analysverktyg <span class="uicontrol"> &gt;</span> <span class="uicontrol"> Hantering av annonsanalys</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Logga in på adminconsole.adobe.com</span> &gt; <span class="uicontrol"> Products</span> &gt; <span class="uicontrol"> Product Profile</span> &gt; <span class="uicontrol"> Permissions tab</span> &gt; <span class="uicontrol"> Analytics Tools</span> &gt; <span class="uicontrol"> Advertising Analytics Management</span></span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Konfiguration av annonsanalys </p> </td> 
   <td colname="col2"> <p>Tillåter användare att konfigurera rapportsviter som ska etableras för Advertising Analytics. </p> </td> 
   <td colname="col3"><span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> User Management</span> &gt; <span class="uicontrol"> Groups</span> &gt; <span class="uicontrol"> Edit All Report Access</span> &gt; <span class="uicontrol"> Customize Report Suite Tools</span> &gt; <span class="uicontrol"> Advertising Analytics Configuration</span></span> </td> 
   <td colname="col4"><span class="ignoretag"><span class="uicontrol"> Logga in på adminconsole.adobe.com</span> &gt; <span class="uicontrol"> Products</span> &gt; <span class="uicontrol"> Product Profile</span> &gt; <span class="uicontrol"> Permissions tab</span> &gt; <span class="uicontrol"> Report Suite Tools</span> &gt; <span class="uicontrol"> Advertising Analytics Configuration</span></span> </td> 
  </tr> 
 </tbody> 
</table>

## Reklamanalys, dimensioner och mätvärden {#section_C0DF4A08EA9E46ADABE9E465AFC11E32}

Advertising Analytics lägger till följande mått och mätvärden i Analysis Workspace, Reports &amp; Analytics, Report Builder och Analytics Reporting API.

**Dimensioner**

>[!IMPORTANT]
>
>Den här integreringen skapar en ny uppsättning dimensioner genom klassificeringar av variabeln AMO ID. Dessa nya dimensioner påverkar inte eller ändrar inte era befintliga marknadsföringskanaler eller variabeldimensioner för kampanjspårning. AMO-ID:t är kopplat till en besökares profil när en besökare landar på webbplatsen från en betald sökannons. AMO-dimensionerna kan därför användas för att bryta ned både de AMO-mått som den här integreringen ger och alla data som besökaren tar in längre fram i kedjan (besök, besökare, sidvisningar, avhoppsfrekvens, order, intäkter, anpassade händelser etc.). De kan också delas upp efter andra dimensioner vid rapportering av andra mätvärden på plats.
>
>Klassificeringarna för dessa mått uppdateras dagligen. Om du ändrar metadata i en sökmotor kanske du inte ser dessa ändringar förrän följande dag när klassificeringarna uppdateras.

| Klassificeringsnamn (dimension) | Definition |
|--- |--- |
| Matchningstyp för nyckelord (AMO ID) | Nyckelordsmatchningstypen. Värdena är vanligtvis breda, fras, exakta eller inga värden om annonstypen inte har någon matchningstyp. |
| Ad Platform (AMO ID) | Sökmotorns namn. Värdena kan vara Google AdWords eller Microsoft Bing Ads. |
| Konto (AMO-ID) | Namnet på sökmotorkontot som spåras. |
| Kampanj (AMO-ID) | Namnet på kampanjen i sökmotorkontot. |
| Annonsgrupp (AMO-ID) | Namnet på annonsgruppen i dina sökmotorkampanjer. |
| Annons (AMO-ID) | Ad Title + Ad Description som används i annonsen. |
| Nyckelord (AMO-ID) | Nyckelordsvärdet från ditt sökmotorkonto |
| Matcha typ (AMO-ID) | Nyckelordsmatchningstypen som tilldelats nyckelordet. Värdena är vanligtvis breda, fras, exakta eller inga värden om annonstypen inte har någon matchningstyp. |
| Annonstyp (AMO-ID) | Den typ av annons som hanteras, som vanligtvis är&quot;Text Ad&quot;. |
| Annonsrubrik (AMO-ID) | Titelobjektet som används i din annons. |
| Annonsbeskrivning (AMO-ID) | Objektet Annonsbeskrivning som används i din annons. |
| Webbadress för annonsvisning (AMO-ID) | Det URL-objekt för annonsvisning som används i annonsen. |
| Måladress för annons (AMO-ID) | Landningssidans URL eller den slutliga URL som är tilldelad din annons. |
| Nätverk (AMO-ID) | Det nätverk där annonsen serveras. För Advertising Analytics är det här värdet alltid&quot;Search&quot;. |
| Placement (AMO-ID) | Den hanterade placeringswebbplatsen (för innehållsnätverk). Endast hanterade placeringar använder den här dimensionen. |
| Produktmål (AMO-ID) | Namnet på produktmålet som används på PLA-annonser (inte den faktiska produkt som köpts). |
| Optimering (AMO-ID) | Detta används inte av Advertising Analytics. Det används endast av Advertising Cloud-kunder. |
| Enhet (AMO-ID) | Används inte idag. Platshållare för potentiell framtida produktförbättring av angiven målenhetstyp (t.ex. mobil, dator) för annons (inte besökarens faktiska enhet). |

**Mått**

>[!IMPORTANT]
>
>De mätvärden som tillhandahålls av Advertising Analytics (listas nedan) är data på sammanfattningsnivå från sökmotorerna. De är inte anslutna till besökarprofilerna i Analytics. De är bara kopplade till variabeln AMO ID och dess tillhörande klassificeringsdimensioner. Därför bör de inte rapporteras för andra dimensioner/segment än de som baseras på AMO ID-dimensionerna. Om du gör det visas nollor för data i Analytics. Du kan inkludera dem i beräknade värden med andra mått, men dessa beräknade värden ska även delas upp endast efter AMO ID-dimensionerna.
>
>Dessa mätvärden är data som hämtas dagligen så att de inte har data för den aktuella dagen. De ska inte heller rapporteras på granularitet som är lägre än dagligen.
>
>Det finns ett mått för AMO ID-instanser som ställs in när AMO-ID:t ställs in på en landningssida (dvs. en klickfrekvens). Detta mätresultat hämtas i realtid med landningssidans träff och är tillgängligt för delningar med andra dimensioner som också anges på landningssidan.

| Måttnamn | Definition |
|--- |--- |
| AMO Impressions | Antalet annonsvisningar som rapporterats av sökmotorn. |
| AMO Clicks | Antalet klick på annonser som rapporterats av sökmotorn. |
| AMO-kostnad | Kostnaden för varje nyckelord/annons som rapporteras av sökmotorn. |
| Medel. Pos | Ett beräknat mätvärde som återspeglar den genomsnittliga positionen för annonserna enligt vad sökmotorn rapporterade. |
| Medel. Kvalitetspoäng | Ett beräknat mått som återspeglar det genomsnittliga kvalitetsmomentet som rapporterats av sökmotorn. |
