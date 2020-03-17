---
description: På anmälningssidan visas hur många procent och hur många besök du har gjort, vilka sidor på webbplatsen som är de första som visas vid nya besök.
title: Poster och utträden
topic: Reports
uuid: 756de55b-136b-427b-a80c-f822260131b1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Poster och utträden

>[!NOTE]
>För träffar med flera värden i variabeln products, gäller Poster och Exits alla produktvärden i en träff i stället för bara den första.

På anmälningssidan visas hur många procent och hur många besök du har gjort, vilka sidor på webbplatsen som är de första som visas vid nya besök.

Du kan visa:

* **Ingångssidor** (eller avsnitt): Visar, i procent och totalt, vilka sidor på webbplatsen som är de första sidorna vid ett nytt besök. Du kan använda den här rapporten för att identifiera vilka av dina webbsidor som är de vanligaste ingångspunkterna, optimera de primära startpunkterna på din webbplats och dirigera trafik till dina huvudmeddelanden.

   Ett praktiskt sätt att använda måttet för sidvyn är att köra en **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Pages Entry]** -rapport, sortera efter den och se vilka startsidor som genererar de flesta sidvyerna.

* **Ursprungliga startsidor**: Visar den första sidan som visas för förstagångsbesökare på webbplatsen. Varje användare räknas bara en gång om de inte tar bort sina cookies eller spåras inte med cookies.
* **Enkelsidiga besök**: Visar sidor som oftast både är in- och avslutssidor för besökarsessioner.
* **Avsluta sidor**: Visar de sidor på webbplatsen som var de sista sidor som besökarna visade innan de lämnade webbplatsen, i procent och vid det totala antalet besök. Avsluta sidor har en besöksuppdelad omfattning, vilket innebär att de finns kvar i alla träffar för ett besök.

**Mätvärden för en rapport över anmälningssidor**

* **Poster**: samma som förekomster eller förekomster, hur många gånger den angivna sidan är startsidan för ett besök.
* **Besök**: Hur många besök var den här sidan på startsidan, ska det här måttet vara lika med posterna.
* **Avslutar**: Antal gånger ett avslutningsförsök har inträffat där startsidan är den angivna. Om du vill se hur många gånger startsidan också är avslutningssidan, använder du satsmåtten i stället för att avsluta.

**Segmentering i en rapport över anmälningssidor**

Köra [!UICONTROL Entry Pages Report] endast rapporter på startsidor, även om du använder segment på en sida som inte är en startsida.

Anta till exempel att en besökssekvens är följande:

[!DNL Page A] > [!DNL Page B] > [!DNL Page C]

Om Sida B och Sida C används i ett segment rapporteras bara sida A i ett [!UICONTROL Entry Pages Report]segment, eftersom sida A är startsidan.
