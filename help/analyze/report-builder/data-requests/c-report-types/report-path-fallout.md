---
description: Beskriver hur rapportbyggaren stöder målnings- och utfallsrapporter och hur implementeringen skiljer sig från rapporter och analyser.
title: Sökvägs- och sökvägsutfallsrapporter i Report Builder
feature: Report Builder
role: User, Admin
exl-id: 211b0e76-2895-401d-a5a5-73e459a486e2
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 7%

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
| Poster och avslut > Enkelsidiga besök | Anges inte som en fristående rapport. Kan reproduceras som en sökvägsrapport med ett fördefinierat filter. |
| Poster och avslut > Avsluta dimension | Anges inte som en fristående rapport. Kan reproduceras som en sökvägsrapport med det fördefinierade filtret Exited Site. |
