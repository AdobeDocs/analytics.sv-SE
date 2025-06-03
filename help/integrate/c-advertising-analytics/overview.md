---
description: Upptäck allt du kan göra med Advertising Analytics, inklusive behörigheter som krävs och tillgängliga mått och mätvärden.
title: Advertising Analytics
feature: Advertising Analytics
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
source-git-commit: 6bedfb9b1333a442bf17cf71dad1e0883b97fd45
workflow-type: tm+mt
source-wordcount: '1007'
ht-degree: 78%

---

# Advertising Analytics

Med Advertising Analytics kan du se alla dina Google Ads- och Microsoft Advertising-betalda sökdata sida vid sida i Adobe Analytics. Tidigare måste alla Google Ads- och Microsoft Advertising-data visas i Adobe Advertising Cloud (AMO) eller i varje annonsgränssnitt. Du kan nu få indata för exponering, klick och kostnader direkt från sökmotorer och AMO ID-instanser (klicka på instanser).

Genom att samla data från sökmotorerna i Adobe Analytics kan du analysera dessa data med hjälp av Analysis Workspace. Den här analysen underlättas av en ny mall för [Paid Search Performance](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) i Workspace.

![](assets/aa_aw.png)

Denna integrering riktar sig till följande målgrupper:

* Den **analytiker** som behöver samla in resultatrapporter för Paid Search Marketer.
* Den **Paid Search Marketer** som söker svar på följande frågor: Hur mycket trafik skickar jag till vår webbplats och konverterar kunderna? Vilka är mina kostnadseffektiva annonskampanjer?


## Förutsättningar {#prerequisites}

* Advertising Analytics finns endast för SKU:erna Adobe Analytics [Select](https://www.adobe.com/se/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/se/data-analytics-cloud/analytics/prime.html) och [Ultimate](https://www.adobe.com/se/data-analytics-cloud/analytics/ultimate.html).
* Den här funktionen är tillgänglig för kunder som inte använder Advertising Cloud eller AMO.
* Du måste vara Adobe Analytics-administratör för att få tillgång till Advertising Analytics eller tillhöra en produktprofil som [har beviljats åtkomst](/help/integrate/c-advertising-analytics/overview.md#permissions) till Advertising Analytics.
* För alla rapportsviter där du vill visa sökdata för Google Ads eller Microsoft Advertising måste du [aktivera dessa rapportsviter för Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Admin]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Advertising Analytics Configuration]**).
* Du behöver inloggningsuppgifter för en användare med redigeringsbehörighet för sökkonton som du vill integrera med Adobe Analytics, till exempel ett Google-konto-ID och ett lösenord.
* När det gäller Microsoft Advertising behöver du även [[!UICONTROL Account ID] och [!UICONTROL Manager Account ID]](c-adanalytics-workflow/aa-locate-account-id.md).

## Advertising Analytics-behörigheter {#permissions}

Analytics har två behörigheter som automatiskt beviljas Analytics-administratörer. Administratörer kan sedan välja att ge dessa behörigheter till icke-administratörer.

| Behörighet | Definition | Bevilja behörighet om du är inloggad på Adobe Experience Cloud |
| --- | --- | --- |
| Hantering av Advertising Analytics | Tillåter användare att konfigurera/redigera/visa annonssökkonton. | Logga in på [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Products] > [!UICONTROL Adobe Analytics] > [!UICONTROL Product Profile] > fliken [!UICONTROL Permissions] > [!UICONTROL Analytics Tools] > [!UICONTROL Advertising Analytics Management] |
| Konfiguration av Advertising Analytics | Användaren kan konfigurera rapportsviter som ska etableras för Advertising Analytics. | Logga in på [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Products] > [!UICONTROL Adobe Analytics] > [!UICONTROL Product Profile] > fliken [!UICONTROL Permissions] > [!UICONTROL Analytics Tools] > [!UICONTROL Advertising Analytics Configuration] |

## Advertising Analytics mått och mätvärden {#dimensions-metrics}

Advertising Analytics lägger till följande mått och mätvärden i Analysis Workspace, Report Builder och API:t för analysrapporter.

### Mått

>[!IMPORTANT]
>
>Den här integreringen skapar en ny uppsättning dimensioner genom klassificeringar av variabeln AMO ID. Dessa nya dimensioner påverkar inte och ändrar inte era befintliga marknadsföringskanaler eller variabeldimensioner för kampanjspårning. AMO-ID:t är kopplat till en besökares profil när en besökare landar på webbplatsen från en Paid Search-annons. AMO-dimensionerna kan därför användas för att bryta ned både de AMO-mätvärden som den här integreringen ger men även alla data som besökaren tar in längre fram i kedjan (besök, besökare, sidvisningar, avhoppsfrekvens, order, intäkter, anpassade händelser etc.). De kan också delas upp efter andra dimensioner vid rapportering av andra mätvärden på plats.
>
>Klassificeringarna för dessa mätvärden uppdateras dagligen. Om du ändrar metadata i en sökmotor kanske du inte ser dessa ändringar förrän följande dag när klassificeringarna uppdateras.

| Klassificeringsnamn (dimension) | Definition |
| --- | --- |
| **[!UICONTROL Keyword MatchType (AMO ID)]** | Nyckelordsmatchningstypen. Värdena är vanligtvis breda, fras, exakta eller inga värden om annonstypen inte har någon matchningstyp. |
| **[!UICONTROL Ad Platform (AMO ID)]** | Sökmotorns namn. Värdena kan vara &quot;Google AdWords&quot; eller &quot;Microsoft Bing Ads&quot;. |
| **[!UICONTROL Account (AMO ID)]** | Namnet på sökmotorkontot som spåras. |
| **[!UICONTROL Campaign (AMO ID)]** | Namnet på kampanjen i sökmotorkontot. |
| **[!UICONTROL Ad Group (AMO ID)]** | Namnet på annonsgruppen i dina sökmotorkampanjer. |
| **[!UICONTROL Ad (AMO ID)]** | Annonsrubrik + Annonsbeskrivning som används i annonsen. |
| **[!UICONTROL Keyword (AMO ID)]** | Nyckelordsvärdet från ditt sökmotorkonto. |
| **[!UICONTROL Match Type (AMO ID)]** | Nyckelordsmatchningstypen som tilldelats nyckelordet. Värdena är vanligtvis breda, fras, exakta eller inga värden om annonstypen inte har någon matchningstyp. |
| **[!UICONTROL Ad Type (AMO ID)]** | Den typ av annons som hanteras, och som vanligtvis är &quot;Textannons&quot;. |
| **[!UICONTROL Ad Title (AMO ID)]** | Rubrikobjektet som används i din annons. |
| **[!UICONTROL Ad Description (AMO ID)]** | Objektet Annonsbeskrivning som används i din annons. |
| **[!UICONTROL Ad Display URL (AMO ID)]** | Det webbplatsobjekt för annonsvisning som används i annonsen. |
| **[!UICONTROL Ad Destination URL (AMO ID)]** | Landningssidans webbadress eller den slutliga webbadressen som tilldelats din annons. |
| **[!UICONTROL Network (AMO ID)]** | Det nätverk där annonsen hanteras. För Advertising Analytics är det här värdet alltid &quot;Search&quot;. |
| **[!UICONTROL Placement (AMO ID)]** | Den hanterade placeringswebbplatsen (för innehållsnätverk). Endast hanterade placeringar använder den här dimensionen. |
| **[!UICONTROL Product Target (AMO ID)]** | Namnet på produktmålet som används på PLA-annonser (inte den faktiska produkt som köpts). |
| **[!UICONTROL Optimization (AMO ID)]** | Detta används inte av Advertising Analytics. Det används endast av Advertising Cloud-kunder. |
| **[!UICONTROL Device (AMO ID)]** | Används inte i dag. Platshållare för potentiell framtida produktförbättring av angiven målenhetstyp (t.ex. mobil, dator) för annons (inte besökarens faktiska enhet). |

### Mätvärden

>[!IMPORTANT]
>
>De mätvärden som tillhandahålls av Advertising Analytics (listas nedan) är data på sammanfattningsnivå från sökmotorerna. De är inte kopplade till besökarprofilerna i Analytics. De är bara kopplade till variabeln AMO ID och dess tillhörande klassificeringsdimensioner. Därför bör de inte rapporteras för andra dimensioner/segment än dem som baseras på AMO ID-dimensionerna. I annat fall visas nollor för data i Analytics. Du kan inkludera dem i beräknade värden med andra mätvärden, men dessa beräknade värden får även bara delas upp efter AMO ID-dimensionerna.
>
>Dessa mätvärden är data som hämtas dagligen och de har inte data för den aktuella dagen. De ska inte heller rapporteras detaljrikare än dagligen.
>
>Det finns ett mått för AMO ID-instanser som ställs in när AMO-ID:t ställs in på en landningssida (dvs. en klickfrekvens). Detta mätresultat hämtas i realtid med landningssidans träff och är tillgängligt för delningar med andra dimensioner som också anges på landningssidan.

| Måttnamn | Definition |
| --- | --- |
| **[!UICONTROL AMO Impressions]** | Antalet annonsvisningar som rapporteras av sökmotorn. |
| **[!UICONTROL AMO Clicks]** | Antalet klick på annonser som rapporterats av sökmotorn. |
| **[!UICONTROL AMO Cost]** | Kostnaden för varje nyckelord/annons som rapporteras av sökmotorn. |
