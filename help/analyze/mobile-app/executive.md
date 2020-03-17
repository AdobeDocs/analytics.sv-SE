---
description: Instruktioner för hur du ställer in styrkort för mobilappar.
title: Adobe Analytics Mobile App Curator Guide
translation-type: tm+mt
source-git-commit: 9149e9ad5a74ef1de0ece5fb0056ee6fee5d50e9

---


# Mobilappen Analytics: Snabbstartsguide för användare

## Introduktion

Mobilappen Adobe Analytics ger dig alltid insikter från Adobe Analytics.  Appen ger användarna mobil åtkomst till intuitiva styrkort. Styrkort är en samling viktiga mätvärden och andra komponenter som presenteras i en sida vid sida-layout som du kan trycka på för mer detaljerade uppdelningar och trendrapporter. Mobilappen stöds på både iOS- och Android-operativsystem.

## Om den här guiden

Den här guiden är avsedd att hjälpa chefsanvändare att läsa och tolka styrkort i Analytics-mobilappen. Med appen kan chefsanvändare snabbt och enkelt visa en bred återgivning av viktiga sammanfattningsdata på sina egna mobila enheter.

## Ordlista

| Villkor | Definition |
|--- |--- |
| Konsument | Chefspersonalen som tittar på viktiga mätvärden och insikter från Analytics på en mobil enhet |
| Kurator | Datalitterera persona som hittar och distribuerar insikter från Analytics och konfigurerar styrkorten så att de kan ses av konsumenterna |
| Kuration | Att skapa eller redigera ett mobilstyrkort med relevanta mått, dimensioner och andra komponenter för konsumenten |
| Styrkort | En mobilappsvy som innehåller en eller flera paneler |
| Platta | En återgivning för ett mätresultat i en styrkortsvy |
| Uppdelning | En sekundär vy som du kommer åt genom att trycka på en platta i styrkortet. Den här vyn utökas med det mått som visas på rutan och kan även innehålla rapporter om ytterligare uppdelningsdimensioner. |
| Datumintervall | Det primära datumintervallet för mobilappsrapportering |
| Jämförelsedatumintervall | Datumintervallet som jämförs med det primära datumintervallet |

## Konfigurera appen på din enhet

Om du vill använda appen effektivt måste du ha styrkortets kurator till hands. I det här avsnittet finns information som hjälper dig att komma igång med hjälp av kuratorn.

### Få åtkomst

Om du vill få åtkomst till styrkort för appen måste du se till att:

* Du har en giltig inloggning på Adobe Analytics
* Markören har skapat mobila styrkort korrekt och delat dem med dig

### Hämta och installera programmet

Följ stegen i operativsystemet på enheten för att hämta och installera programmet.

**För iOS-enheter:**

1. Klicka på följande offentliga länk (den finns även i Analytics under **Tools** > **Mobile App**):

   [iOS-länk](https://testflight.apple.com/join/WtXMQxlI): `https://testflight.apple.com/join/WtXMQxlI`

   När du har klickat på länken visas följande testflight-skärm:

   ![Testflightskärm](assets/testflight1.png)

2. Tryck på länken **Visa i App Store** på skärmen för att hämta testflight-appen.

3. När du har installerat Testflight-appen letar du reda på och installerar Adobe Analytics-mobilappen inifrån Testflight enligt nedan:

   ![Testflightskärm](assets/testflight2.png)

**För Android-enheter:**

1. Tryck på följande Play Store-länk på användarens enhet (den är även tillgänglig i Analytics under **Tools** > **Mobile App**):


   [Android](https://play.google.com/apps/testing/com.adobe.analyticsmobileapp): `https://play.google.com/apps/testing/com.adobe.analyticsmobileapp`

   När du har tryckt på länken trycker du på länken Bli en testare på följande skärm:

   ![Spela upp Store-skärm](assets/play.png)

2. Tryck på **nedladdningslänken på Google Play** -länken på följande skärm:

   ![Hämta länk](assets/playnext.png)

## Använd appen

Så här använder du appen:

1. Logga in i appen. Inloggningsskärmen visas när appen startas. Följ instruktionerna med dina befintliga Adobe Analytics-inloggningsuppgifter. Vi stöder både Adobe och Enterprise/Federated ID.

   ![Logga in sekvens](assets/signseq.png)

2. Välj ett företag. När du har loggat in i appen visas skärmen **Välj ett företag** . På den här skärmen visas de inloggningsföretag som du tillhör. Tryck på det företagsnamn som är associerat med det styrkort som delas med dig.

3. I styrkortslistan visas sedan alla styrkort som har delats med dig. Tryck på det styrkort som du vill visa.

   ![Välj ett företag](assets/accesscard.png)

   *Obs! Om du loggar in och ser ett meddelande som säger att inget har delats kontrollerar du följande med markören:*

   * *Du kan logga in på rätt Analytics-instans*
   * *Styrkortet har delats med dig*

      ![Inget delat](assets/nothing.png)

4. Undersök hur rutorna visas i styrkortet.

   ![Förklarade plattor](assets/newexplain.png)

   Ytterligare information om plattor:

   * Miniatyrdiagrammens granularitet beror på datumintervallets längd:
   * En dag visar en timtrend
   * Fler än en dag och mindre än ett år visar en daglig trend
   * Ett år eller mer visar en vecktrend
   * Formeln för ändring av procentvärde är metrisk summa (aktuellt datumintervall) - metrisk summa (jämförelsedatumintervall) / metrisk summa (jämförelsedatumintervall).
   * Du kan dra ned skärmen för att uppdatera styrkortet.

5. Tryck på en platta för att visa hur en detaljerad uppdelning för plattan fungerar.

   ![Brytpunktsvy](assets/sparkline.png)


6. Så här ändrar du datumintervall för styrkortet:

   ![Ändra datum](assets/changedate.png)

   *Obs! Du kan också ändra datumintervallen i den detaljerade vyn som visas ovan på samma sätt.*

   Beroende på vilket intervall du knackar på (**Dag**, **Vecka**, **Månad** eller **År**) visas två alternativ för datumintervall, antingen det aktuella tidsintervallet eller det som ligger omedelbart före det. Tryck på något av dessa två alternativ för att markera det första intervallet. Under listan **JÄMFÖR MED** , tryck på ett av alternativen som visas för att jämföra data för den här tidsperioden med det första datumintervallet som du valde. Tryck på **Klar** i skärmens övre högra hörn. Fälten **Datumintervall** och Styrkortsinställningarna uppdateras med nya jämförelsedata från de nya intervall som du har valt.

7. Hämta styrkortsuppdateringar. Om ett styrkort inte innehåller alla mätvärden eller uppdelningar som du kan vara intresserad av kontaktar du analysteamet så att styrkortet uppdateras. När kortet har uppdaterats kan du dra ned det på skärmen för att uppdatera det och läsa in nyligen tillagda data.



8. Lämna feedback. Lämna feedback:

   1. Tryck på användarikonen i appskärmens övre högra hörn.
   2. Tryck på alternativet **Feedback** på skärmen **Mitt konto** .
   3. Tryck för att visa alternativen för att lämna feedback.
   ![Lämna feedback](assets/feedback.png)
   ![Alternativ för feedback](assets/feedback_option.png)


**Så här rapporterar du ett fel**:

Tryck på alternativet och välj en underkategori för felet. I formuläret för att rapportera ett fel anger du din e-postadress i det övre fältet och en beskrivning av felet i fältet nedanför. En skärmbild av din kontoinformation bifogas automatiskt till meddelandet, men du kan ta bort den om du vill genom att trycka på **X** i den bifogade bilden. Du kan också göra en skärminspelning, lägga till fler skärmbilder eller bifoga filer. Om du vill skicka rapporten trycker du på pappersplansikonen i formulärets övre högra hörn.


![Rapportera fel](assets/newbug.png)

**Så här föreslår du en förbättring**:

Tryck på alternativet och välj en underkategori för förslaget. I förslagsformuläret anger du din e-postadress i det övre fältet och din beskrivning av felet i fältet nedanför. En skärmbild av din kontoinformation bifogas automatiskt till meddelandet, men du kan ta bort den om du vill genom att trycka på **X** i den bifogade bilden. Du kan också göra en skärminspelning, lägga till fler skärmbilder eller bifoga filer. Om du vill skicka förslaget trycker du på pappersplansikonen i formulärets övre högra hörn.

**Så här ställer du en fråga**:

Tryck på alternativet och ange din e-postadress i det övre fältet och din fråga i fältet nedanför. En skärmdump bifogas automatiskt till meddelandet, men du kan ta bort den om du vill genom att trycka på **X** i den bifogade bilden. Du kan också göra en skärminspelning, lägga till fler skärmbilder eller bifoga filer. Om du vill skicka frågan trycker du på pappersplansikonen i formulärets övre högra hörn.
