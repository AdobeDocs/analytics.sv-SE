---
description: Svar på frågor du kan ha när du implementerar Audience Analytics.
solution: Experience Cloud
title: Frågor och svar om Audience Analytics
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 0%

---

# Vanliga frågor

Svar på frågor du kan ha när du implementerar Audience Analytics.

## Frågor och svar {#legal}

+++ Hur vet jag om jag har PII (Personally Identiitable Information) i mina analysdata? Och om ja, vad gör jag åt det?

Om du har e-post/adresser/så vidare i ett utkast eller eVar bör du överväga att hash-koda data under insamlingen. Om ditt land anser att IP-adressen är en PII-adress, [aktiverar du IP-förfalskning](/help/admin/tools/exclude-ip.md). Tala med er Analytics Admin för att se vad ni samlar in. Tala med er juridiska avdelning för att se vad de anser vara PII.

+++

+++ Hur vet jag om mina rapportsviter gör personalisering på plats eller målgruppsanpassning på plats eller utanför webbplatsen?

Dessa gäller inte när du skickar Adobe Analytics-data till Adobe Audience Manager. Fråga dig själv:

* Kommer ni att dela ett analysdelat segment med en MCA-dimension tillbaka till Experience Cloud?

* Exporterar ni (t.ex. via dataflöden) till ett Business Intelligence (BI)-system som används för dessa ändamål?

+++

## Adobe Audience Manager-specifika frågor {#aam-specific}

+++ Hur skapar jag ett Analytics-mål i Audience Manager?

Se [Konfigurera ett analysmål i Adobe Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html?lang=sv-SE).

+++

+++ När du har skapat och sparat ett Analytics-mål, hur lång tid tar det tills data visas i de valda rapportsviterna?

Det kan ta flera timmar att fylla i rapportsviterna med nya data.

+++

+++ Jag har skapat ett nytt Analytics-mål, men det visas inte i avsnittet Destination Mappings i mina tillgängliga segment. Vart tog den vägen eller hur hittar jag den?

Ett Analytics-mål försvinner från ett segments målmappningsavsnitt när du väljer alternativet **[!UICONTROL Automatically map all current and future segments]** i **[!UICONTROL Segment Mappings]**. Om du vill förhindra detta väljer du **[!UICONTROL Manually map segments]** i stället för det automatiska alternativet.

+++

Får jag all information från Adobe Audience Manager i Analytics?

Nej, endast data som rör personer som kommer till er webbplats under eller efter det att Audience Manager-målgrupper aktiverats och under/efter det att segmentet kvalificerats.

+++

+++ Ger det mig en adresserbar målgrupp per segment?

Egentligen inte. Här visas antalet besökare i det segmentet som kom till webbplatsen under eller efter en segmentkvalificering.

+++

+++ På vilket sätt skiljer sig detta från det gamla cookie-målet till Analytics?

Segmenten kvalificeras för och returneras i realtid - med samma träff. Eget namn visas automatiskt.

+++

+++ Vad händer om vissa av mina rapporteringsprogram har personuppgifter och andra inte har det?&lt;

Tips: Skapa två destinationer - lägg till rapporteringssviterna för personuppgifter till ett mål och rapporteringssviterna för icke-personliga data till ett annat.

+++

## Analysspecifika frågor {#aa-specific}

+++ Kommer den här integreringen att bli en dimension eller ett segment i Analytics?

Som dimensioner: Publikens ID och Publikens namn.

+++

+++Var kan jag använda de här dimensionerna i Analytics?

Överallt behandlas de precis som alla andra dimensioner som samlas in i Analytics.

+++

+++ Varför ser jag inte data som kommer in i Analytics?

Du har troligtvis konflikter mellan Adobe Audience Manager sekretesskontroller mellan datakällor och mål.

+++

+++ Varför saknas några av mina segment i Analytics, trots att jag valde att skicka alla segment?&lt;

* Dina dataexportkontroller för Adobe Audience Manager på målet och i segmentets datakällor kan vara i konflikt, vilket förhindrar att vissa segment skickas.

* Om du använder dataegenskaper från tredje part i dina segment kan dessa segment inte delas med mål (en uppsättning rapportsviter) som innehåller personuppgifter.

+++

+++ Varför ser jag&quot;Målgruppsgräns nådd&quot; i min Analytics-rapport? (Obs! Detta kommer också att representeras som Audience ID = -1 och `::max_audiences_exceeded::` i Data Warehouse)

Som standard skickar Audience Analytics-integreringen för Adobe Audience Manager alla segment som en besökare kvalificerar sig för till Analytics, per besök. Om en besökare tillhör fler än 150 Adobe Audience Manager-segment i en enda träff skickas de **150 senast kvalificerade segmenten** till Analytics, medan den återstående listan trunkeras. En extra flagga skickas till Analytics som anger att segmentlistan trunkerades och visas som&quot;Målgruppsgräns nådd&quot; i dimensionen Målgruppsnamn och&quot;-1&quot; i dimensionen Målgrupps-ID.

Det är osannolikt att en besökare kvalificerar sig för mer än 150 segment för en viss träff, men det kan hända en liten del av tiden. Om du upplever&quot;Målgruppsgräns nådd&quot; i din rapportering har du två alternativ:

* Alternativ 1: Fortsätt att låta integreringen fungera i det färdiga läget och skicka de 150 senast kvalificerade segmenten för en viss besökare.

* Alternativ 2: I Adobe Audience Manager väljer du de 150 segment som är viktigast för ditt företag för integreringen. Adobe Audience Manager kontrollerar sedan besökarna mot endast dessa 150 segment. Nackdelen med detta är att ni bara får dessa 150 segment över alla besökare. Å andra sidan kan alternativ 1-metoden leverera ett obegränsat antal segment på grund av integreringens per-träfftyp.

+++

+++ Faktureras ytterligare serversamtal till Analytics för den här integreringen?

Nej. Adobe Audience Manager Audiences ingår i Analytics på serversidan. Detta medför inte ytterligare serveranrop till Analytics (primär eller sekundär).

+++

## Vanliga frågor och svar om vidarekoppling på serversidan (SSF) {#SSF}

+++ Om jag har implementerat en äldre SSF-fil, måste jag då också gå till Analytics Admin och aktivera rapportsviten SSF?

Ja. I Adobe Audience Manager-målinställningarna visas endast rapportsviter som har SSF aktiverat.

+++

+++ Varför kan jag inte aktivera vissa rapporteringsprogram för SWF i Analytics Admin?

Endast sviter som är mappade till din Experience Cloud Org kan aktiveras.

Mer information om vanliga frågor och svar om det här avsnittet finns i [Vanliga frågor om vidarebefordran på serversidan](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md).

+++

## Allmänna frågor och svar {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

+++ Varför skiljer sig segmentbesökarnas antal mellan Audience Manager och Analytics?

Se [Skillnader i antal besökare](/help/integrate/c-audience-analytics/visitor-count-reconciliation.md).

+++

+++ Vad är skillnaden mellan&quot;målgrupper&quot; i Adobe Audience Manager och&quot;segment&quot; i Analytics?

Se [Förstå segment i Analytics och Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md). Adobe Audience Manager målgrupper skickas vidare och delas som&quot;dimensionskomponenter&quot; som ska användas i Analytics. De visas inte som segment i segmentbyggaren, till exempel, utan som dimensioner som du kan skapa segment med.

+++

+++ Vad är skillnaden mellan kundattribut och kunddata som är integrerade från Adobe Audience Manager?

Kundattribut är inte tidsbaserade. De gäller retroaktivt och går framåt. Adobe Audience Manager-integrerade data är tidsbaserade och kan bara vidareutvecklas. Dessutom är kundattribut ett sökregister för besökar-ID:n från Experience Cloud, medan Adobe Audience Manager-integreringen är data som sammanfogas i varje träff för en besökare.

+++

+++ Hur är det med äldre metoder för detta problem, till exempel gamla beta- eller konsultplugin-program för cookie-mål?

Vi rekommenderar att du implementerar den nya integreringen och tar bort gamla destinationer.

+++
