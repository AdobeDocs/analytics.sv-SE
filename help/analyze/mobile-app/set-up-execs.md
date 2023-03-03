---
description: Chefsanvändare kan behöva lite extra hjälp för att komma åt och använda appen. I det här avsnittet finns information som du kan använda för att få hjälp.
title: Konfigurera företagsledare med appen
feature: Analytics Dashboards
role: User, Admin
exl-id: 0e858407-2852-4a5f-a0df-3ba290fcca8f
source-git-commit: 02d0baee99ad2ea5966788f036644d3e3780016e
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Konfigurera företagsledare med appen

I vissa fall kan företagsledare behöva lite extra hjälp för att komma åt och använda appen. I det här avsnittet finns information som du kan använda för att få hjälp.

## Se till att appanvändare har tillgång till Adobe Analytics

1. Konfigurera nya användare i [Experience Cloud Admin Console](/help/admin/admin-console/permissions/product-profile.md).

1. För att kunna dela styrkort måste du ge appanvändare behörighet att komma åt styrkortskomponenter som Analysis Workspace, de rapportsviter som styrkort baseras på samt segment, mått och mått.

## Systemkrav för appanvändare

För att se till att företagsinterna användare har tillgång till dina styrkort i appen ska du se till att:

* De lägsta kraven för mobiloperativsystem på enheterna är iOS version 10 eller senare, eller Android version 4.4 (KitKat) eller senare
* De har en giltig inloggning på Adobe Analytics.
* Du har skapat mobila styrkort för dem och delat dem med dem.
* De har tillgång till de komponenter som styrkortet innehåller. Observera att du kan välja ett alternativ när du delar styrkort till **[!UICONTROL Share embedded components]**.

## Hjälp chefer att hämta och installera program

**För chefsanvändare på iOS:**

Klicka på följande länk (den är också tillgänglig i Analytics under **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (Mobile App)]**) och följ anvisningarna för att hämta, installera och öppna programmet:

`[iOS link](https://apple.co/2zXq0aN)`

**För chefsanvändare på Android:**

Klicka på följande länk (den är också tillgänglig i Analytics under **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (Mobile App)]**) och följ anvisningarna för att hämta, installera och öppna programmet:

`[Android link](https://bit.ly/2LM38Oo)`

När de har hämtats och installerats kan företagsanvändare logga in i appen med sina befintliga Adobe Analytics-inloggningsuppgifter. har stöd för både Adobe och Enterprise/Federated ID.

![App - välkomstskärm](assets/welcome.png)

## Hjälp cheferna att komma åt styrkortet

1. Låt chefsanvändare logga in i appen.

   The **[!UICONTROL Choose a company]** visas. På den här skärmen visas de inloggningsföretag som den verkställande användaren tillhör.

1. Låt dem trycka på namnet på inloggningsföretaget eller Experience Cloud-organisationen som gäller för styrkortet som du delade.

   Styrkortslistan visar sedan alla styrkort som har delats med den verkställande direktören under det inloggningsföretaget.

1. Låt dem sortera listan efter **[!UICONTROL Most recently modified]**, om tillämpligt.

1. Låt dem trycka på namnet på styrkortet för att visa det.

   ![Välj ett företag](assets/accesscard.png)


### Förklara styrkortets användargränssnitt

Förklara för den verkställande användaren hur rutor visas i de styrkort som du delar.

![Förklaringar](assets/newexplain.png)

![Exempelstyrkort](assets/intro_scorecard.png)

Ytterligare information om plattor:

* Miniatyrdiagrammens granularitet beror på datumintervallets längd:
* En dag visar en timtrend
   * Mer än en dag och mindre än ett år visar en daglig trend
   * Ett år eller mer visar en vecktrend
   * Formeln för ändring av procentvärde är metrisk summa (aktuellt datumintervall) - metrisk summa (jämförelsedatumintervall) / metrisk summa (jämförelsedatumintervall).
   * Du kan dra ned skärmen för att uppdatera styrkortet.


1. Tryck på en platta för att visa hur en detaljerad uppdelning för plattan fungerar.

   ![Uppdelningsvy](assets/sparkline.png)

   * Tryck på en punkt i ett miniatyrdiagram för att se data som hör till den punkten på raden.

   * En tabell inkluderas för att visa data med dimensioner som lagts till i rutan. Tryck på nedpilen för att välja mått. Om ingen dimension har lagts till i rutan visas diagramdata i tabellen.

1. Om du vill ändra datumintervall för styrkortet trycker du på datumhuvudet och väljer den primära kombination och den kombination av datumintervall som du vill visa.

   ![Ändra datum](assets/changedate.png)

## Ändra appinställningar

Om du vill ändra inställningarna trycker du på **[!UICONTROL Preferences]** som visas ovan. I inställningarna kan du aktivera biometrisk inloggning eller ställa in programmet för mörkt läge enligt nedan:

![Mörkt läge](assets/darkmode.png)

## Felsökning

Om den verkställande användaren loggar in och ser ett meddelande om att inget har delats:

![Inget delat](assets/nothing.png)

* Den verkställande användaren kan ha valt fel Analytics-instans, eller
* Styrkortet kanske inte har delats med den verkställande användaren.

Kontrollera att chefsanvändaren kan logga in på rätt Adobe Analytics-instans och att styrkortet har delats.

>[!IMPORTANT]
>
>Från och med oktober 2020 kommer Adobe gradvis att lansera en serie förbättringar för att optimera prestandan för appen&quot;Adobe Analytics dashboards&quot;. Dessa förbättringar handlar om att cachelagra historiska analysdata som används för att fylla i styrkort med datum (exklusive den aktuella dagen). Dessa data cachas i upp till 24 timmar i ett säkert Microsoft Azure-molnlagringskonto. Kontakta kontoteamet på Adobe om du vill avanmäla dig från dessa prestandaförbättringar.
