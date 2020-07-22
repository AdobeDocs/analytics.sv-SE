---
title: Enkel åtkomst
description: Antalet gånger som en dimensionspost inte ändrades vid ett besök.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---


# Enkel åtkomst

Mätvärdet för enkel åtkomst visar antalet besök där dimensionsobjektet endast innehöll ett unikt värde för hela besöket. Det här måttet är användbart i samband med alla dimensioner där du vill se vilka dimensionsobjekt som stagnerar under ett besök.

## Hur det här måttet beräknas

Det här måttet räknar antalet besök där dimensionsobjektet innehöll ett enda unikt värde. Du kan ställa in dimensionsobjektet flera gånger eller låta det finnas kvar och fortfarande räknas som en enskild åtkomst. Så snart en dimensionsuppgift ändras till ett andra unikt värde räknas inte längre besöket som en enda åtkomst.

## Skillnad mellan Single Access och Single page visit

När det gäller dimensionen [Sida](../dimensions/page.md) är&quot;Enkel åtkomst&quot; och&quot;Besök enstaka sida&quot; exakt identiska. Skillnaderna uppstår när du använder andra dimensioner.

* **Enkel åtkomst**: Visar antalet besök där den angivna dimensionsposten inte ändrades för hela besöket. Det är kontextuellt med den dimension som du använder i ditt projekt.
* **Besök** en sida: Visar antalet besök där siddimensionen inte ändrades för hela besöket. Även om du använder en annan dimension i rapporten räknas besök som innehåller ett enda unikt sidodimensionsobjekt.

Ta till exempel följande exempel på två träffbesök. Dimensionen i din rapport är [Site-avsnittet](../dimensions/site-section.md).

* En besökare träffar två sidor, men de finns båda i samma webbplatsavsnitt. Eftersom webbplatsavsnittet förblev detsamma vid besöket räknas det som en enda åtkomst. Det räknas inte som ett besök på en sida eftersom besöket innehåller mer än ett unikt sidobjekt.
* En besökare träffar två sidor i olika delar av webbplatsen, men båda sidorna råkar ha samma namn. Besöken räknas inte som en enskild åtkomst eftersom det fanns två unika avsnittsvärden. Det räknas som ett besök på en sida eftersom det fanns ett enda unikt sidobjekt.
