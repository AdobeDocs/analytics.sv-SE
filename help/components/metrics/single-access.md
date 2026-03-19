---
title: Enkel åtkomst
description: Antalet gånger som en dimensionspost inte ändrades vid ett besök.
feature: Metrics
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
source-git-commit: 6d2c278c5525c89b73c39bbfcedbe644806bf989
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 0%

---

# Enkel åtkomst

**[!UICONTROL Single access]** [Mått](overview.md) visar antalet besök där den tillämpliga rapporteringsdimensionen endast innehöll ett enda värde för ett helt besök. Det är den bredare, dimensionsspecifika versionen av [[!UICONTROL Single page visits]](single-page-visits.md). Det här måttet är användbart i samband med alla dimensioner där du vill se värdet för en dimension när den bara ställdes in en gång under ett besök.

## Hur det här måttet beräknas

Definitionen av det här måttet beror på projektinställningen för [[!UICONTROL Count repeat instances]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings):

* **Antal upprepande instanser aktiverade**: Räknar besök där dimensionen innehåller exakt ett värde vid ett besök. Om dimensionen kvarstår kvalificeras den inte längre som en enskild åtkomst.
* **Antal upprepande instanser inaktiverade**: Räknar besök där dimensionen innehåller ett unikt värde. Du kan ställa in dimensionsobjektet på samma värde flera gånger eller låta det vara kvar och det räknas fortfarande som en enskild åtkomst.

Oavsett [!UICONTROL Count repeat instances] kvalificerar sig besöket inte längre som en enskild åtkomst om dimensionen ändras till ett andra unikt värde. Länkspårningsanrop inkluderas i den här beräkningen om dimensionen är inställd i dem.

## Skillnad mellan [!UICONTROL Single access] och [!UICONTROL Single page visit]

I samband med dimensionen [[!UICONTROL Page]](../dimensions/page.md) är [!UICONTROL Single access] och [!UICONTROL Single page visits] alltid identiska oavsett projektinställningen [!UICONTROL Count repeat instances]. Skillnaderna uppstår när du använder andra dimensioner.

* **[!UICONTROL Single access]**: Visar antalet besök där den angivna dimensionsobjektet fanns för en enskild träff. Det är kontextuellt med den dimension som du använder i ditt projekt.
* **[!UICONTROL Single page visit]**: Visar antalet besök där dimensionen [!UICONTROL Page] fanns för en enskild träff. Även om du använder en annan dimension i rapporten räknas besök som innehåller ett enda unikt [!UICONTROL Page]-dimensionsobjekt fortfarande.

Om [[!UICONTROL Count repeat instances]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings) är inaktiverat ändras måttdefinitionerna något:

* **Enkel åtkomst**: Visar antalet besök där den angivna dimensionsobjektet inte ändrades för hela besöket.
* **Enkelsidigt besök**: Visar antalet besök där dimensionen [!UICONTROL Page] inte ändrades för hela besöket.

Ta till exempel följande exempel på besök med två träffar. Dimensionen i rapporten är [[!UICONTROL Site section]](../dimensions/site-section.md) och [!UICONTROL Count repeat instances] är inaktiverad.

* En besökare träffar två sidor, men de finns båda i samma webbplatsavsnitt. Eftersom webbplatsavsnittet förblev detsamma vid besöket räknas det som en enda åtkomst. Det räknas inte som ett enda sidbesök eftersom besöket innehåller mer än ett unikt [!UICONTROL Page]-dimensionsobjekt.
* En besökare träffar två sidor i olika delar av webbplatsen, men båda sidorna råkar ha samma namn. Besöken räknas inte som en enskild åtkomst eftersom det fanns två unika avsnittsvärden. Det räknas som ett enda sidbesök eftersom det fanns ett enda unikt [!UICONTROL Page]-dimensionsobjekt.
