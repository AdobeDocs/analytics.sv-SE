---
description: Beskriver hur Report Builder stöder målnings- och utfallsrapporter och hur implementeringen skiljer sig från rapporter och analyser.
title: Bana- och vägutfallsrapporter i Report Builder
feature: Report Builder
role: User, Admin
exl-id: 211b0e76-2895-401d-a5a5-73e459a486e2
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---

# Bana- och vägutfallsrapporter i Report Builder

Beskriver hur Report Builder stöder målnings- och utfallsrapporter och hur implementeringen skiljer sig från rapporter och analyser (som nu upphör).

| Namn på sökvägsrapport i rapporter och analyser (Banor > dimension >) | Stöds i Report Builder? |
|--- |--- |
| Nästa/Föregående dimensionsflöde | Anges inte som en fristående rapport. Kan reproduceras med flera begäranden med dimensionen Bana och med ett filter. |
| Nästa/Föregående dimension | Anges inte som en fristående rapport. Kan reproduceras med en Path-rapport och med ett filter. |
| Utfall | Stöds och tillhandahålls som en fristående rapport (Banor > Dimension > dimensionsavvikelse). |
| Fullständiga banor | Stöds inte. |
| PathFinder | Anges inte som en fristående rapport. Kan reproduceras som en sökvägsrapport med ett filter. |
| Banlängd | Stöds endast för siddimensionen. |
| Sidanalys > dimensionssammanfattning | Anges inte som en fristående rapport. Kan reproduceras med flera begäranden med dimensionen Bana och med ett filter. |
| Sidanalys > Läs in igen | Anges inte som en fristående rapport. Kan reproduceras med en dimensionsrapport med mätvärdet för Läs in. |
| Sidanalys > dimensionsdjup | Stöds endast för siddimensionen. |
| Sidanalys > Tid tillagd i dimension | Stöds inte. |
| Poster och utträde > Startsidor | Anges inte som en fristående rapport. Kan reproduceras som en sökvägsrapport med det fördefinierade filtret Angiven plats. |
| Poster och utträde > Ursprungliga anmälningssidor | Stöds endast för siddimensionen. |
| Poster och avslut > Besök på en sida | Anges inte som en fristående rapport. Kan reproduceras som en sökvägsrapport med ett fördefinierat filter. |
| Poster och avslut > Avsluta dimension | Anges inte som en fristående rapport. Kan reproduceras som en sökvägsrapport med det fördefinierade filtret Exited Site. |
