---
title: Bearbetningsordning för data i Adobe Analytics
description: Lär dig ordningen på komponenter och tjänster som bearbetar data i Adobe Analytics.
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
feature: Data Configuration and Collection
source-git-commit: 6c947812d4fd8bc2ee951a5933c6e3b6d8ca1a6b
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 0%

---

# Bearbetningsordning för data i Adobe Analytics

Adobe erbjuder många sätt att ändra eller ändra data innan de visas i rapporter. På den här sidan visas i vilken ordning olika Adobe Analytics-funktioner bearbetar data. Du kan använda den här listan för att felsöka inkonsekvenser i data eller för att fastställa den bästa funktionen som ska användas när datajusteringar är nödvändiga.

![Bearbetar beställningsbild](assets/processing-order.png)

## Data innan de skickas till Adobe

Innan data skickas till Adobe kompileras de vanligtvis på klientsidan på något av följande sätt:

* **AppMeasurement**: En JavaScript-fil som finns på din webbplats och som refereras till på varje sida. Data skickas direkt till Adobe Analytics.
* **Adobe Experience Platform Web SDK**: En JavaScript-fil som lagras på din webbplats och som refereras till på varje sida. Data skickas till Adobe Experience Platform Edge Network.
* **Taggar i Adobe Experience Platform Data Collection**: En JavaScript-fil som refereras till på varje sida och som innehåller regler som skapats i användargränssnittet för datainsamling. Adobe Analytics-tillägget är ett enklare sätt att implementera AppMeasurement. Web SDK är ett enklare sätt att implementera Web SDK.
* **API**: Både AppMeasurement och Edge Network erbjuder programmatiska metoder för att skicka data till Adobe. AppMeasurement erbjuder API:t [Datainfogning](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) och API:t [Massdatainfogning](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/). Edge Network erbjuder API:t för [datainsamling](https://developer.adobe.com/data-collection-apis/docs/).

Om du skickar data till Edge Network kan du konfigurera det så att data vidarebefordras till Adobe Analytics (och till många andra Adobe Experience Cloud-lösningar). Oavsett implementeringsmetod kommer de insamlade träffdata till slut till Adobe Analytics bearbetningsservrar i ett format som de kan analysera.

## Förbearbetning i Adobe Analytics-samling

När data kommer till Adobe Analytics går de in i en förbearbetningsfas:

1. [**Dynamiska variabler**](/help/implement/vars/page-vars/dynamic-variables.md): Om en dynamisk variabel visas i någon del av en bildbegäran kopieras värdet över och behandlas som ett oberoende värde som flyttas framåt.
1. [**IP-förfalskning (senaste oktett)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): Om rapportsviten är konfigurerad att dölja endast den sista oktetten, gäller detta. Observera att IP-förfalskning (ta bort IP) inträffar senare i bearbetningsflödet.
1. **Uppslagstabeller**: Dimensioner som använder Adobe-interna uppslagstabeller (till exempel dimensionen [Webbläsare](/help/components/dimensions/browser.md)) matchas mot motsvarande värde.
1. [**IP-undantag**](/help/admin/tools/exclude-ip.md): Alla IP-adresser som du uttryckligen utelämnar från rapporter flaggas under det här steget.
1. [**Punktregler**](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md): Använd standard- eller anpassad robotfiltrering för att exkludera data från rapportering.
1. **Geoplatsdata**: Dimensioner som förlitar sig på IP-adresssökning (till exempel dimensionen [Länder](/help/components/dimensions/countries.md)) fylls i.
1. [**Bearbetar regler**](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md): Anpassade regler som din organisation har tillämpat på dina data. Inkluderar mappningen av [kontextdatavariabler](/help/implement/vars/page-vars/contextdata.md) till deras respektive Analytics-variabler.
1. [**VISTA-regler**](vista.md): Anpassade flexibla regler som tillämpas på dina data av en Adobe-konsult. VISTA-regler kan köras före eller efter att regler bearbetas, beroende på organisationens behov. De flesta VISTA-regler körs vanligtvis efter bearbetningsregler, men varje organisation har konfigurerats på olika sätt. Kontakta Adobe Account Team för mer information om befintliga VISTA-regler.
1. **Valutakonvertering**: Om träffen innehåller en annan [`currencyCode`](/help/implement/vars/config-vars/currencycode.md) än rapportsvitens valuta konverteras alla tillämpliga valutavariabler med den aktuella dagens växelkurs.
1. [**Postnummer**](/help/components/dimensions/zip-code.md): Dimensionen Postnummer fylls i baserat på inställningarna för rapportsviten.

## Mellanvärdesstadium i datainsamlingsflödet

När förbearbetningen är klar använder flera funktioner den här delvis bearbetade dataformen, som kallas&quot;mellanvärden&quot;. Innan dessa data skickas någonstans tillämpas viss mellanvärdesspecifik bearbetning:

1. [**Bearbetningsregler för marknadsföringskanaler på toppnivå**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md): Dessa bearbetningsregler körs specifikt för Analytics Source Connector. Eftersom det ännu inte finns något besöks- eller besöksnivåsammanhang förutsätter dessa regler att en träff inte är den första besöksträffen. Resultatet av att bearbeta regler för en träff är tillgängligt i `channel.typeAtSource` och `channel._id`.
1. [**IP-förfalskning (ta bort IP)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): Om rapportsviten är konfigurerad för att fullständigt dölja en IP-adress, gäller detta (endast för mellanvärden).

Nu skickas data med medelvärde till respektive funktion:

* [**API:t för direktuppspelning**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/): Anslut ett program till Adobe tjänst för direktuppspelning om du vill ha ett dataflöde när det samlas in.
* [**Analyserar Source Connector**](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics): Importera Adobe Analytics-rapportsvitsdata i en Adobe Experience Platform-datauppsättning.
* [**Realtidsrapportering**](/help/components/c-real-time-reporting/realtime.md): Tillhandahåller upp till tre konfigurerbara realtidsrapporter i Analysis Workspace.

## Bearbetning på besöks- och besöksnivå

Fram tills nu har en viss träff ingen kunskap om eller kontext för träffar som samlats före eller efter den. Detta steg i bearbetningen fyller i besöks- och besöksnivåfält.

1. [**Besök + besöksdefinition**](/help/implement/id/overview.md): träffen identifieras baserat på de ingående besökarvariablerna.
1. [**Besöksnummer**](/help/components/dimensions/visit-number.md): Besöken beräknas baserat på andra besök för den identifierade besökaren.
1. **Händelseavduplicering**: Om träffen innehåller en dubblett [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) eller [ händelseserialisering](/help/implement/vars/page-vars/events/event-serialization.md) kontrolleras dessa ID:n och flaggas.
1. [**Bearbetningsregler för marknadsföringskanaler på besöksnivå**](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md): Varje träff körs genom regler för bearbetning av marknadsföringskanaler, och dess kanal + kanaldetalj bestäms om träffen matchar någon regel. Dessa regler fyller i dimensionerna [Marknadskanal](/help/components/dimensions/marketing-channel.md) och [Marknadskanalsinformation](/help/components/dimensions/marketing-detail.md) som är tillgängliga i Analysis Workspace.
1. **Variabel beständighet**: För dimensioner som har beständighet (till exempel [eVars](/help/components/dimensions/evar.md)) bestäms värdet i det här steget. I allmänhet anges de flesta `post`-värden här.
1. **Transaktions-ID**: Om träffen innehåller ett nytt [`transactionID`](/help/implement/vars/page-vars/transactionid.md)-värde sparas en ögonblicksbild av alla värden som stöds. När en överföring från en datakälla innehåller ett matchande transaktions-ID inkluderas alla värden som stöds från den här ögonblicksbilden i datakällraden.
1. [**IP-förfalskning (ta bort IP)**](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md): Om rapportsviten är konfigurerad för att fullständigt dölja en IP-adress, gäller detta när alla andra bearbetningar har slutförts.

I det här skedet registreras den enskilda träffen i rapportsvitens datatabeller. Efter standardintervallet [latens](latency.md) är det tillgängligt i rapporter.

## Ändra data efter att de har bearbetats

Data i Adobe Analytics är i huvudsak permanenta, men det finns vissa funktioner som kan möjliggöra selektiv datainjustering eller -borttagning:

* [**API för datareparation**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/): Redigera vissa kolumner eller ta bort önskade datarader.
* [**Datastyrning**](/help/technotes/privacy/privacy-overview.md): Acceptera sekretessförfrågningar för permanent borttagning av data.
* [**Klassificeringar**](/help/components/classifications/classifications-overview.md): Skapa dimensioner baserat på regler eller överförda data som gör att du kan ordna data på ett annat sätt. Den underliggande rapportsvitens data ändras inte, så du kan fritt redigera eller skriva över klassificeringsdata.
* [**Virtuella rapportsviter**](/help/components/vrs/vrs-about.md): Skapa en alternativ rapportsvy som kan ändra tidsgränsen för besök.
