---
description: Bidragsanalys är en intensiv maskininlärningsprocess som utformats för att identifiera medverkande till en iakttagen avvikelse i Adobe Analytics. Avsikten är att hjälpa användaren att hitta fokusområden eller möjligheter till ytterligare analys mycket snabbare än vad som annars skulle vara möjligt.
title: Statistiska tekniker som används vid bidragsanalys
uuid: f77eb4e4-4fd6-4397-b8a8-a063f199b676
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Statistiska tekniker som används vid bidragsanalys

Bidragsanalys är en intensiv maskininlärningsprocess som utformats för att identifiera medverkande till en iakttagen avvikelse i Adobe Analytics. Avsikten är att hjälpa användaren att hitta fokusområden eller möjligheter till ytterligare analys mycket snabbare än vad som annars skulle vara möjligt.

Detta uppnås med bidragsanalys genom att en tvådelad algoritm utförs för varje enskilt dimensionsobjekt som är tillgängligt för användarens bidragsanalysrapport. Algoritmen fungerar i följande ordning:

1. För varje dimension beräknas Cramers V-provningsvärde. I följande exempel kan du ta en beredskapstabell med sidvisningar per land under två tidsperioder:

   ![](assets/contingency_table.png)

   I tabell 1 kan Cramer&#39;s V användas för att mäta kopplingen mellan sidvyerna för länder för period 1 (t.ex. historik) och period 2 (t.ex. den dag avvikelsen inträffade). Ett lågt värde för Cramer&#39;s V innebär en låg associationsnivå. Cramerns V varierar från 0 (ingen association) till 1 (fullständig association). Cramerns V-statistik kan beräknas:

   ![](assets/cramers-v.png)

1. För varje dimensionspost används personens restvärde (PR) för att mäta kopplingen mellan det avvikande mätvärdet och varje dimensionspost. PR följer en standardnormalfördelning, som gör det möjligt för algoritmen att jämföra PR för två slumpmässiga variabler även om avvikelserna inte är jämförbara. I praktiken är felet okänt och uppskattas med hjälp av en begränsad provkorrigering.

   I det föregående exemplet, tabell 1, ges PR, med en begränsad provkorrigering för land i och tidsperiod 2, av

   ![](assets/persons-residual.png)

   Här,

   ![](assets/pr-example.png)

   (En liknande formel kan erhållas för tidsperiod 1.)

   För de slutliga resultaten vägs poängen för varje dimensionspost sedan med Cramer-objektets V-mått och skalas om till ett tal mellan 0 och 1 för att ge poäng.

