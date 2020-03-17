---
description: Filter som använder specifika dimensionsvillkor.
title: Specifika filter
topic: Report builder
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Specifika filter

Filter som använder specifika dimensionsvillkor.

Du kan söka efter specifika dimensionsobjekt genom att skapa ett filter som matchar exakta villkor. Du kan till exempel skapa följande typ av filter: sida in [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**Skapa ett specifikt filter**

1. Skapa eller redigera en förfrågan och fortsätt till [!UICONTROL Request Wizard: Step 2].

   ![Stegresultat](assets/dimension_filter.png)

1. Klicka på länken [!UICONTROL Request Wizard: Step 2]bredvid dimensionen i rutnätet och välj sedan **[!UICONTROL Filter]**.

   ![Stegresultat](assets/choose_page_specific01.png)

1. Aktivera **[!UICONTROL Specific]** och aktivera sedan något av följande alternativ:

   * **Från cellintervall:** Gör att du kan markera data från celler. Du kan välja:
   * **Alla celler i intervallet:** Här kan du mappa varje cell för intervallet. Beskrivande text förklarar hur många grupper av celler du måste markera. Om du vill mappa mer än en grupp med celler trycker du på Ctrl-tangenten när du gör successiva markeringar. Om intervallet som måste mappas bara innehåller en cell är detta det enda tillgängliga alternativet
   * **Intervallets första cell:** Du behöver bara markera cellen längst upp till vänster i intervallet och sedan välja riktning för data. Om begäran innehåller flera punkter väljer du riktning för punkterna och väljer om du vill hoppa över ett visst antal celler mellan punkterna.
   * **Från lista:** Gör att du kan välja data från en lista som du kan lägga till data i.
1. Om du aktiverar **[!UICONTROL From List]** markerar du alla tillgängliga listobjekt eller klickar på **[!UICONTROL Add]**.

   När du klickar **[!UICONTROL Add]** visar [!UICONTROL Select From List] formuläret en lista med tillgängliga dimensionsvärden för det aktuella datumintervallet för begäran, begränsat till de första 10 000 objekten. Du kan söka bland dessa objekt eller klicka **[!UICONTROL More ...]** så visas [!UICONTROL Search Form]texten så att du kan göra en mer detaljerad sökning efter dimensioner.
1. Klicka på [!UICONTROL Select From List]på **[!UICONTROL OK]**.
1. Spara det specifika filtret i [!UICONTROL Choose Page] formuläret om du vill och klicka sedan på **[!UICONTROL OK]**.
