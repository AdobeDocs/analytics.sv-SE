---
description: Mäter det inkomstbelopp som genereras genom alla dina produkter under en viss tidsperiod.
title: Intäkter
topic: Reports
uuid: e5b72798-f5c7-440d-a62d-376bfd115ac8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Intäkter

Mäter det inkomstbelopp som genereras genom alla dina produkter under en viss tidsperiod.

Använd Intäkter för att se hur framgångsrik och tendens sajten är generellt. Ni kan också använda den för att identifiera perioder där sajten var särskilt framgångsrik, för att hitta källan och använda den för framtida kampanjer.

## Allmänna egenskaper för rapporten {#section_97FC92DFB07D45A79F40B452F9AEE57B}

* Det finns krav som måste uppfyllas för att den här rapporten ska kunna samla in data. Följande måste finnas i samma bildbegäran:

   * En [!UICONTROL purchase] händelse måste utlösas i `s.events` variabeln.

   * Variabeln `products` måste definieras med ett tal i prisfältet.
   * Detta skulle till exempel skicka 35,99 USD till intäktsrapporten:

      ```js
       s.products="Mens;Shoes;1;35.99"
      ```

      ```js
       s.events="purchase"
      ```

* När det finns mer än en produkt i variabeln räknas alla in i intäktsrapporten. [!UICONTROL s.products] Till exempel [!DNL s.products="Mens;Socks;1;4.50,Womens;Socks;1;4.50"] skulle skicka 9 USD i intäkter till rapportering.

   >[!NOTE]
   >
   >Intäkterna multipliceras inte om kvantiteten ökas i en enskild produkt. Till exempel skickar [!DNL s.products="Womens;Socks;5;4.50"] inte $22.50 till rapportering, utan skickar $4.50. Se till att implementeringen överför de totala intäkterna för den angivna kvantiteten ( [!DNL s.products="Womens;Socks;5;22.50"]).

* [!UICONTROL Revenue] avrundar det totala beloppet för en tidsperiod till närmaste valutavärde. Den rundar inte av varje enskild produkt eller träff.
* Eftersom Analytics avrundar varje dag till närmaste helvaluta, avräknas en mycket liten summa om man jämför summan för varje dag med månadssumman. Detta beror på att månadssumman inte är summan av varje avrundad dag, utan är den absoluta summan avrundad till närmaste hela valuta.
* Du kan skapa en rapport som inte avrundar intäkten till närmaste hela valuta med hjälp av ett [beräknat mått](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/).
* Om variabeln inte används kan användare som uppdaterar sidan öka intäkterna eftersom data skickas till Adobe flera gånger. `purchaseID`
* Timuppdelningar baseras på rapportsvitens tidszon.
* Den här rapporten innehåller inga radartiklar. Den kan bara visas i trendformat.
* Kornighet mellan timme, dag, vecka, månad, kvartal och år kan tillämpas. Dessa uppgifter är tillgängliga beroende på rapporteringsdatum.
* Den här rapporten kan delas upp i följande rapporter (beroende på inställningar för organisation och rapportsviten):

   * [!UICONTROL Time Spent per Visit] rapport.
   * [!UICONTROL Pages and Site Sections] rapport.
   * [!UICONTROL Videos] rapport.
   * [!UICONTROL Page Depth and Entry Pages] rapport.
   * De flesta [!UICONTROL Traffic Sources]rapporter, inklusive [!UICONTROL Search Keywords], [!UICONTROL Search Engines]och [!UICONTROL Referring Domains] rapporter.

   * [!UICONTROL Tracking Code] och alla tillhörande klassificeringsrapporter.
   * [!UICONTROL Products variable] och alla tillhörande klassificeringsrapporter. Även [!UICONTROL Categories] rapporter.

   * Nästan alla [!UICONTROL Visitor Profile] rapporter, exklusive [!UICONTROL GeoSegmentation] rapporter.

   * Alla [!UICONTROL Custom Conversion] variabelrapporter med grundläggande underrelationer.

* Uppdelningar är inte tillgängliga per timme.

## Produktspecifika egenskaper {#section_ED87FFD020634453AABE86B0248BE69B}

* Du kommer åt den här rapporten genom att gå till **[!UICONTROL Conversion]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* [!UICONTROL Traffic Sources] uppdelningar finns under [!UICONTROL Finding Methods].

* Du kommer åt den här rapporten genom att gå till **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* Förutom alla tidigare listade uppdelningar [!UICONTROL First and Last Touch Marketing Channel] är uppdelningar tillgängliga.

* Du kan även få åtkomst till den här rapporten genom att gå till **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* Förutom tidigare nämnda uppdelningar kan [!UICONTROL List]variabler och aktuella [!UICONTROL Video] variabler användas.

* Den här rapporten kan använda segment.

* Du kan dela upp varje objekt i den här rapporten med alla andra rapporter och variabler, så att du kan se uppdelningar efter de detaljer du vill ha.
* Du kan använda all [!UICONTROL conversion] - och [!UICONTROL traffic] mätinformation tillsammans [!UICONTROL Revenue]. Du kan använda olika allokeringar för alla [!UICONTROL conversion] mätvärden.

* Den här rapporten kan använda flera mycket avancerade segment.

Om den här rapporten inte är tillgänglig på den angivna platsen kontaktar du administratören. De kan ha ändrat standardnamnet eller menystrukturen för att bättre tillgodose organisationens unika behov.
