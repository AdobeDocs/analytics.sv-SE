---
description: Innehåller omfattande, korrekta och detaljerade analyser av kundaktiviteter. Mätvärden som kampanjhantering, säljcykel, bortfall och kundkonvertering gör att ni kan mäta e-handelstransaktioner, säljkällor, reklameffektivitet, kundlojalitet med mera.
title: Konvertering
topic: Reports
uuid: 457d3033-6562-4fba-8c2e-0e7a9be44bfd
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Konvertering

Innehåller omfattande, korrekta och detaljerade analyser av kundaktiviteter. Mätvärden som kampanjhantering, säljcykel, bortfall och kundkonvertering gör att ni kan mäta e-handelstransaktioner, säljkällor, reklameffektivitet, kundlojalitet med mera.

Om du till exempel vill se vilken typ av interna kampanjer på din hemsida som kan leda till inköp, måste du först samla in de interna spårningskoderna och ange beständighet till en period av ett besök för den *`s.eVar`* som fångar interna kampanjer. När en lyckad händelse slutförs (som köp), krediteras alla konverteringsvariabler som är beständiga hos besökaren, till exempel internt kampanj-ID. Genom att köra [!UICONTROL Internal Campaign Report]programmet kan du se vilken kampanj som genererade mest konvertering på plats.

Vissa färdiga rapporter innehåller både trafik- och konverteringsstatistik (till exempel [!UICONTROL Search Engine] rapporter). Rapporterna [!UICONTROL Traffic] och [!UICONTROL Conversion] rapporterna är unika för din organisation och visas på **[!UICONTROL Traffic]** - och **[!UICONTROL Conversion]** -menyerna.

**Rapportegenskaper**

* [!UICONTROL Custom Conversion] rapporterna baseras på eVars (konverteringsvariabler).
* Konverteringsvariabler kan finnas utanför sidvyn och kopplas till mått inom den angivna förfallotiden.
* Rapporternas standardmått är intäkter. Mer information om hur du ändrar standardmått finns i [Välja standardrapportmått](https://marketing.adobe.com/resources/help/en_US/sc/user/t_metrics_set_default.html).
* Visa rapporterna i både trendformat och rankat format.
* Du kan använda klassificeringar i de här rapporterna för att byta namn på och konsolidera radobjekt.
* Rapporterna kan delas upp enligt följande om grundläggande underrelationer är aktiverade:

   * Kampanjer och produkter, med alla relaterade klassificeringar
   * Kundlojalitet
   * Alla helsubrelaterade eVars

* Det finns ytterligare rapporter som kan delas upp när fullständiga underrelationer är aktiverade:

   * Tid per besök
   * Sidor och platsavsnitt, med alla relaterade klassificeringar
   * Inmatningssidor
   * Nästan alla trafikkällor rapporterar
   * Besök nummer
   * Många besökarprofiler och -teknikrapporter
   * Alla andra eVars
   * Marknadsföringskanaler, första och sista beröring

* Följande händelser kan användas som mått:

   * instanser, det antal gånger som eVar definierades
   * Alla standardvärden för e-handel: Intäkter, beställningar, enheter, kundvagnar, kundvagnsvyer, utcheckningar, kundvagnstillägg, kundvagnsborttagningar.
   * Alla anpassade händelser: Händelser 1-80 och händelser 81-100 om H22-kod eller högre används
   * Besök och besökare: Tillgängligt beroende på organisation och rapportserie. Kontakta din kontohanterare om du vill ha mer information

* Platsen för varje [!UICONTROL Custom Conversion] rapport varierar beroende på det numeriska värdet för eVar. Vanligtvis finns de under [!UICONTROL Custom Conversion] mappen (förutsatt att menyn inte är anpassad).

