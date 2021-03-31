---
description: Beskriver hur rapportbyggaren stöder målnings- och utfallsrapporter och hur implementeringen skiljer sig från rapporter och analyser.
title: Sökvägs- och sökvägsutfallsrapporter i Report Builder
uuid: 9ca6cb97-8f31-46f6-977a-e81a89a176d1
feature: Report Builder
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 8%

---


# Sökvägs- och sökvägsutfallsrapporter i Report Builder

Beskriver hur rapportbyggaren stöder målnings- och utfallsrapporter och hur implementeringen skiljer sig från rapporter och analyser.

| Namn på sökvägsrapport i rapporter och analyser (Banor > dimension >) | Stöds i Report Builder? |
|--- |--- |
| Nästa/Föregående dimensionsflöde | Anges inte som en fristående rapport. Kan reproduceras med flera begäranden med dimensionen Bana och med ett filter. |
| Nästa/Föregående dimension | Anges inte som en fristående rapport. Kan reproduceras med en Path-rapport och med ett filter. |
| Utfall | Stöds och tillhandahålls som en fristående rapport (Banor > Dimension > dimensionsavvikelse). |
| Fullständiga sökvägar | Stöds inte. |
| PathFinder | Anges inte som en fristående rapport. Kan reproduceras som en sökvägsrapport med ett filter. |
| Sökvägslängd | Stöds endast för siddimensionen. |
| Sidanalys > dimensionssammanfattning | Anges inte som en fristående rapport. Kan reproduceras med flera begäranden med dimensionen Bana och med ett filter. |
| Sidanalys > Läs in igen | Anges inte som en fristående rapport. Kan reproduceras med en dimensionsrapport med mätvärdet för Läs in. |
| Sidanalys > dimensionsdjup | Stöds endast för siddimensionen. |
| Sidanalys > Tid som använts på dimensionen | Stöds inte. |
| Poster och utträde > Startsidor | Anges inte som en fristående rapport. Kan reproduceras som en sökvägsrapport med det fördefinierade filtret Angiven plats. |
| Poster och avslut > Ursprungliga anmälningssidor | Stöds endast för siddimensionen. |
| Poster och avslut > Besök på en sida | Anges inte som en fristående rapport. Kan reproduceras som en sökvägsrapport med ett fördefinierat filter. |
| Poster och avslut > Avsluta dimension | Anges inte som en fristående rapport. Kan reproduceras som en sökvägsrapport med det fördefinierade filtret Exited Site. |
