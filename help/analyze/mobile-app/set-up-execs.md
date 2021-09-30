---
description: Skapa ett styrkort för kontrollpaneler i Analytics
title: Skapa ett styrkort
feature: Analytics Dashboards
role: User, Admin
source-git-commit: 012bbfa54d97ffcaf4cd0de380c196df06a03bfe
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 0%

---


# Konfigurera företagsledare med appen

I vissa fall kan företagsledare behöva lite extra hjälp för att komma åt och använda appen. I det här avsnittet finns information som du kan använda för att få hjälp.

## Systemkrav för verkställande användare

För att se till att chefsanvändare har tillgång till dina styrkort i appen ska du se till att:

* De lägsta kraven för mobiloperativsystem på enheterna är iOS version 10 eller senare, eller Android version 4.4 (KitKat) eller senare
* De har en giltig inloggning på Adobe Analytics
* Du har skapat mobila styrkort för dem och delat dessa styrkort med dem
* De har tillgång till Analysis Workspace och rapportsviten som styrkortet bygger på
* De har tillgång till de komponenter som styrkortet innehåller. Observera att du kan välja ett alternativ när du delar styrkort till **[!UICONTROL Share embedded components]**.

## Hjälp chefer att hämta och installera program

**För företagsledare på iOS:**

Klicka på följande länk (den är även tillgänglig i Analytics under **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (Mobile App)]**) och följ anvisningarna för att hämta, installera och öppna appen:

`[iOS link](https://apple.co/2zXq0aN)`

**För chefsanvändare på Android:**

Klicka på följande länk (den är även tillgänglig i Analytics under **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (Mobile App)]**) och följ anvisningarna för att hämta, installera och öppna appen:

`[Android link](https://bit.ly/2LM38Oo)`

När de har hämtats och installerats kan företagsanvändare logga in i appen med sina befintliga Adobe Analytics-inloggningsuppgifter. har stöd för både Adobe och Enterprise/Federated ID.

![App - välkomstskärm](assets/welcome.png)

## Hjälp chefer att komma åt styrkortet

1. Låt chefsanvändare logga in i appen.

   Skärmen **[!UICONTROL Choose a company]** visas. På den här skärmen visas de inloggningsföretag som den verkställande användaren tillhör.

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

Om du vill ändra inställningarna trycker du på **[!UICONTROL Preferences]**-alternativet som visas ovan. I inställningarna kan du aktivera biometrisk inloggning eller ställa in programmet för mörkt läge enligt nedan:

![Mörkt läge](assets/darkmode.png)

## Felsökning

Om den verkställande användaren loggar in och ser ett meddelande om att inget har delats:

![Inget delat](assets/nothing.png)

* Den verkställande användaren kan ha valt fel Analytics-instans, eller
* Styrkortet kanske inte har delats med den verkställande användaren.

Kontrollera att chefsanvändaren kan logga in på rätt Adobe Analytics-instans och att styrkortet har delats.

### Rapportera ett fel

Tryck på alternativet och välj en underkategori för felet. I formuläret för att rapportera ett fel anger du din e-postadress i det övre fältet och en beskrivning av felet i fältet nedanför. En skärmbild av din kontoinformation bifogas automatiskt till meddelandet, men du kan ta bort den om du vill genom att trycka på **X** i den bifogade bilden. Du kan också göra en skärminspelning, lägga till fler skärmbilder eller bifoga filer. Om du vill skicka rapporten trycker du på pappersplansikonen i formulärets övre högra hörn.

![Rapportera fel](assets/newbug.png)

### Lämna feedback

1. Tryck på inställningsikonen i appskärmens övre högra hörn.
1. Tryck på alternativet **[!UICONTROL Feedback]** på skärmen **[!UICONTROL Settings]**.
1. Tryck för att visa alternativen för att lämna feedback.

   ![Inställningsskärm](assets/settings.png)

### Föreslå en förbättring

Tryck på alternativet och välj en underkategori för förslaget. I förslagsformuläret anger du din e-postadress i det övre fältet och din beskrivning av felet i fältet nedanför. En skärmbild av din kontoinformation bifogas automatiskt till meddelandet, men du kan ta bort den om du vill genom att trycka på **X** i den bifogade bilden. Du kan också göra en skärminspelning, lägga till fler skärmbilder eller bifoga filer. Om du vill skicka förslaget trycker du på pappersplansikonen i formulärets övre högra hörn.

### Ställ en fråga

Tryck på alternativet och ange din e-postadress i det övre fältet och din fråga i fältet nedanför. En skärmdump bifogas automatiskt till meddelandet, men du kan ta bort den om du vill genom att trycka på **X** i den bifogade bilden. Du kan också göra en skärminspelning, lägga till fler skärmbilder eller bifoga filer. Om du vill skicka frågan trycker du på pappersplansikonen i formulärets övre högra hörn.

>[!IMPORTANT]
>
>Från och med oktober 2020 kommer Adobe gradvis att lansera en rad förbättringar för att optimera prestandan för appen&quot;Adobe Analytics dashboards&quot;. Dessa förbättringar handlar om att cachelagra historiska analysdata som används för att fylla i styrkort med datum (exklusive den aktuella dagen). Dessa data cachas i upp till 24 timmar i ett säkert Microsoft Azure-molnlagringskonto. Kontakta din CSM om du vill avanmäla dig från dessa prestandaförbättringsfunktioner.
