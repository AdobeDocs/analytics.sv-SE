---
description: Filter som använder specifika dimensionsvillkor.
title: Specifika filter
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
feature: Report Builder
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 3%

---


# Specifika filter

Filter som använder specifika dimensionsvillkor.

Du kan söka efter specifika dimensionsobjekt genom att skapa ett filter som matchar exakta villkor. Du kan till exempel skapa följande typ av filter: sida i [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**Skapa ett specifikt filter**

1. Skapa eller redigera en begäran och gå vidare till [!UICONTROL Request Wizard: Step 2].

   ![Stegresultat](assets/dimension_filter.png)

1. Klicka på länken bredvid dimensionen i rutnätet på [!UICONTROL Request Wizard: Step 2] och välj sedan **[!UICONTROL Filter]**.

   ![Stegresultat](assets/choose_page_specific01.png)

1. Aktivera **[!UICONTROL Specific]** och aktivera sedan något av följande alternativ:

   * **Från cellintervall:** Markera data från celler. Du kan välja:
   * **Alla celler i intervallet:** Du kan mappa alla celler för intervallet. Beskrivande text förklarar hur många grupper av celler du måste markera. Om du vill mappa mer än en grupp med celler trycker du på Ctrl-tangenten när du gör successiva markeringar. Om intervallet som måste mappas bara innehåller en cell är detta det enda tillgängliga alternativet
   * **Intervallets första cell:** Du behöver bara markera cellen längst upp till vänster i intervallet och sedan välja en riktning för data. Om begäran innehåller flera punkter väljer du riktning för punkterna och väljer om du vill hoppa över ett visst antal celler mellan punkterna.
   * **Från lista:** Här kan du välja data från en lista som du kan lägga till data i.
1. Om du aktiverar **[!UICONTROL From List]** markerar du alla tillgängliga listade objekt eller klickar på **[!UICONTROL Add]**.

   När du klickar på **[!UICONTROL Add]** visar formuläret [!UICONTROL Select From List] en lista över tillgängliga dimensionsobjekt för aktuellt datumintervall för begäran, begränsat till de första 10 000 objekten. Du kan söka bland dessa objekt eller klicka på **[!UICONTROL More ...]**, som visar [!UICONTROL Search Form], så att du kan skapa en mer detaljerad sökning efter dimensioner.
1. Klicka på **[!UICONTROL OK]** på [!UICONTROL Select From List].
1. Spara det specifika filtret i [!UICONTROL Choose Page]-formuläret om du vill och klicka sedan på **[!UICONTROL OK]**.
