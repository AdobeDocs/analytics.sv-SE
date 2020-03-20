---
title: Avsluta länkar
description: Rapportera om de vanligaste länkarna som andra klickar på för att lämna din webbplats.
translation-type: tm+mt
source-git-commit: be4c3ec95b9e93dda7603c0bdb178c0a54d800a0

---


# Avsluta länkar

Visar de vanligaste länkarna som personer klickar på för att lämna din webbplats. Dessa länkar pekar vanligen på partners eller filialer. De kan dock finnas var som helst där du har en extern länk. Du kan använda den här rapporten för att visa de populäraste filiallänkarna eller för att hjälpa till att validera antalet hänvisningar som din partners anger.

Det finns flera krav som måste uppfyllas för att den här sidan ska fyllas i korrekt:
* Om du använder manuell anpassad länkspårning måste en begäran skickas med parametern middle inställd på `tl()` `e`.
* Om automatisk spårning av länkar används måste alla krav vara uppfyllda:
   * Variabeln [trackExternalLinks](/help/implement/vars/config-vars/trackexternallinks.md) måste aktiveras.
   * Länken som användaren klickade på får inte matcha några värden i [linkInternalFilters](/help/implement/vars/config-vars/linkinternalfilters.md) -variabeln.
   * Om variabeln [linkExternalFilters](/help/implement/vars/config-vars/linkexternalfilters.md) finns måste den externa länken matcha minst ett av de värden som anges i variabeln.
* Om något av ovanstående krav inte uppfylls fyller träffen inte i den här rapporten.
* Precis som för alla anpassade länkspårningstips tas variabeln [pageName](/help/implement/vars/page-vars/pagename.md) bort från bildbegäran för att förhindra uppblåsning av sidvyns mätvärden.
* Du kan visa den här rapporten i trendformat och rankat format.
* Den här rapporten kan använda ett sökfilter för att hitta specifika radobjekt.
* Du kan skapa [uppdelningar](/help/analyze/reports-analytics/reports-customize/breakdowns.md) med andra variabler.
