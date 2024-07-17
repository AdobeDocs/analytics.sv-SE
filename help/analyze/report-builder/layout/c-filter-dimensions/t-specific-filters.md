---
description: Filter som använder specifika dimensionsvillkor.
title: Specifika filter
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
feature: Report Builder
role: User, Admin
exl-id: e5f2d67c-3add-4d51-8a76-ee3b2a6eef94
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---

# Specifika filter

Filter som använder specifika dimensionsvillkor.

Du kan söka efter specifika dimensionsobjekt genom att skapa ett filter som matchar exakta villkor. Du kan till exempel skapa följande typ av filter: sida i [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**Så här skapar du ett specifikt filter**

1. Skapa eller redigera en begäran och fortsätt till [!UICONTROL Request Wizard: Step 2].

   ![Skärmbild som visar Filtrera efter alternativ: Program, Användare och Projekt.](/help/admin/admin/assets/filter.png)

1. Klicka på länken bredvid dimensionen i rutnätet på [!UICONTROL Request Wizard: Step 2] och välj sedan **[!UICONTROL Filter]**.

1. Aktivera **[!UICONTROL Specific]**.

   ![Skärmbild i dialogrutan Välj sida med alternativet Specifik markerat.](assets/choose_page_specific01.png)

1. Aktivera ett av följande specifika alternativ:

   * **Från cellintervall:** Du kan välja data från celler. Du kan välja:
      * **Alla celler i intervallet:** Du kan mappa alla celler för intervallet. Beskrivande text förklarar hur många grupper av celler du måste markera. Om du vill mappa mer än en grupp med celler trycker du på Ctrl-tangenten när du gör successiva markeringar. Om intervallet som måste mappas bara innehåller en cell är detta det enda tillgängliga alternativet
      * **Intervallets första cell:** Du behöver bara markera cellen längst upp till vänster i intervallet och sedan välja en riktning för data. Om begäran innehåller flera punkter väljer du riktning för punkterna och väljer om du vill hoppa över ett visst antal celler mellan punkterna.
   * **Från lista:** Här kan du välja data från en lista som du kan lägga till data i.
1. Om du aktiverar **[!UICONTROL From List]** markerar du alla tillgängliga listade objekt eller klickar på **[!UICONTROL Add]**.

   När du klickar på **[!UICONTROL Add]** visar formuläret [!UICONTROL Select From List] en lista över tillgängliga dimensionsobjekt för aktuellt datumintervall för begäran, begränsat till de första 10 000 objekten. Du kan söka bland dessa objekt eller klicka på **[!UICONTROL More ...]**, som visar [!UICONTROL Search Form], så att du kan skapa en mer detaljerad sökning efter dimensioner.
1. Klicka på **[!UICONTROL OK]** på [!UICONTROL Select From List].
1. Spara det specifika filtret i formuläret [!UICONTROL Choose Page] om du vill och klicka sedan på **[!UICONTROL OK]**.
