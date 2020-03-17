---
description: Visar de vanligaste länkarna som personer klickar på som leder till platser utanför platsen. Dessa länkar pekar vanligtvis på partners eller filialer. De kan dock vara var som helst där du har implementerat en extern länk. Du kan använda den här rapporten för att visa de populäraste filiallänkarna eller för att hjälpa till att validera antalet hänvisningar som din partners anger.
title: Avsluta länkar
topic: Reports
uuid: e1452f04-389d-4aa3-8763-732880284302
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Avsluta länkar

Visar de vanligaste länkarna som personer klickar på som leder till platser utanför platsen. Dessa länkar pekar vanligtvis på partners eller filialer. De kan dock vara var som helst där du har implementerat en extern länk. Du kan använda den här rapporten för att visa de populäraste filiallänkarna eller för att hjälpa till att validera antalet hänvisningar som din partners anger.

Det finns flera krav som måste uppfyllas för att den här sidan ska fyllas i korrekt:

* Om du använder manuell anpassad länkspårning måste en begäran skickas med parametern middle inställd på *`s.tl()`* e **.

* Om automatisk spårning av länkar används måste alla krav vara uppfyllda:
* 

   * [s.trackExternalLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_trackexlinks.html) måste anges till *true*.

   * Länken som användaren klickade på får inte matcha några värden i [variabeln s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkinfilters.html) .
   * Om [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkinfilters.html) implementeras måste den externa länken matcha minst ett av värdena som anges i variabeln.

* Om något av ovanstående krav inte uppfylls fylls träffen inte i den här rapporten.

* 
* Precis som med alla anpassade länkspårningstips tas variabeln [s.pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_pagename.html) bort från bildbegäran för att förhindra sidvisningsuppblåsning.
* Du kan visa den här rapporten i trendformat och rankat format.
* Den här rapporten kan använda ett sökfilter för att hitta specifika radobjekt.
* Du kan skapa [uppdelningar](/help/analyze/reports-analytics/reports-customize/breakdowns.md) med andra variabler via Admin Tools.
* [Förekomster](/help/components/c-variables/c-metrics/metrics-instance.md) är de enda mätvärden som är tillgängliga som standard i den här rapporten, och antalet gånger som avslutningslänken utlöses.
* Dagliga, veckovisa, månatliga och kvartalsvisa besökare kan aktiveras för den här rapporten. Det är dock bara en Adobe-representant som kan aktivera dessa till en extra kostnad. Om du aktiverar unika besökare för anpassade länkspårningsvariabler ökar fördröjningen avsevärt för rapportsviten.

