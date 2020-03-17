---
description: Med anpassade trafikrapporter kan varje organisation rapportera om ytterligare dimensioner som inte implementeras som standard. Anpassade trafikrapporter kan användas på flera sätt, vanligtvis för att mäta trafik och kundvägar.
title: Anpassad trafik
topic: Reports
uuid: 627e8f34-e8f7-4f79-919b-f6237f85685d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Anpassad trafik

Med anpassade trafikrapporter kan varje organisation rapportera om ytterligare dimensioner som inte implementeras som standard. Anpassade trafikrapporter kan användas på flera sätt, vanligtvis för att mäta trafik och kundvägar.

## Egenskaper för anpassade trafikrapporter {#section_4CBFC4EDFB1C49CD88F9874B6EF6FDEC}

* Rapporterna om anpassad trafik bygger enbart på [props](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_propn.html) (trafikvariabler).
* Rapporternas standardmått är sidvyer (eller instanser i version 15). Version 14 sidvyer och version 15-instanser är identiska, eftersom de räknar det totala antalet gånger som variabeln har definierats. Sidvyer i version 15 räknar bara antalet *`s.t()`* bildbegäranden (exklusive *`s.tl()`* begäranden).

* Sökfunktionen kan aktiveras om den ingår i organisationens kontrakt och begärs av en användare som stöds. När målning är aktiverat för en trafikvariabel är följande mått tillgängliga:
* 

   * Genomsnittligt siddjup
   * Genomsnittlig tid
   * Poster
   * Avslutar
   * Läs in igen
   * Enkel åtkomst
   * Besök

* Ni kan använda deltagarstatistik i trafikrapporter. Denna användning måste begäras och inkluderas i organisationens kontrakt.
* Dessa rapporter kan visas i både trendformat och rankningsformat.
* Sökfilter kan användas för att hitta specifika radobjekt.
* Klassificeringar kan användas i de här rapporterna, så att du kan byta namn på och konsolidera radobjekt.
* Korrelationer kan aktiveras för alla dessa rapporter, så att du kan se relationer mellan andra trafikvariabler.
* Platsen för varje anpassad trafikrapport varierar beroende på propets numeriska tilldelade värde. Vanligtvis finns de under [!UICONTROL Traffic] eller [!UICONTROL Custom Traffic] i en mapp).

