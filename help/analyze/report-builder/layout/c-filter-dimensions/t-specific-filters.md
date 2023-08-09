---
description: Filter som använder specifika dimensionsvillkor.
title: Specifika filter
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
feature: Report Builder
role: User, Admin
exl-id: e5f2d67c-3add-4d51-8a76-ee3b2a6eef94
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 1%

---

# Specifika filter

Filter som använder specifika dimensionsvillkor.

Du kan söka efter specifika dimensionsobjekt genom att skapa ett filter som matchar exakta villkor. Du kan till exempel skapa följande typ av filter: sida i [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**Skapa ett specifikt filter**

1. Skapa eller redigera en förfrågan och gå vidare till [!UICONTROL Request Wizard: Step 2].

   ![Skärmbild som visar Filtrera efter alternativ: Program, Användare och Projekt.](/help/admin/admin/assets/filter.png)

1. På [!UICONTROL Request Wizard: Step 2]klickar du på länken bredvid dimensionen i rutnätet och väljer **[!UICONTROL Filter]**.

1. Aktivera **[!UICONTROL Specific]**.

   ![Skärmbild av dialogrutan Välj sida med alternativet Specifik markerat.](assets/choose_page_specific01.png)

1. Aktivera ett av följande specifika alternativ:

   * **Från cellintervall:** Gör att du kan markera data från celler. Du kan välja:
      * **Alla celler i intervallet:** Här kan du mappa varje cell för intervallet. Beskrivande text förklarar hur många grupper av celler du måste markera. Om du vill mappa mer än en grupp med celler trycker du på Ctrl-tangenten när du gör successiva markeringar. Om intervallet som måste mappas bara innehåller en cell är detta det enda tillgängliga alternativet
      * **Intervallets första cell:** Du behöver bara markera cellen längst upp till vänster i intervallet och sedan välja riktning för data. Om begäran innehåller flera punkter väljer du riktning för punkterna och väljer om du vill hoppa över ett visst antal celler mellan punkterna.
   * **Från lista:** Gör att du kan välja data från en lista som du kan lägga till data i.
1. Om du aktiverar **[!UICONTROL From List]** markerar du alla tillgängliga listobjekt eller klickar på **[!UICONTROL Add]**.

   När du klickar **[!UICONTROL Add]**, [!UICONTROL Select From List] formuläret visar en lista med tillgängliga dimensionsobjekt för aktuellt datumintervall för begäran, begränsat till de första 10 000 artiklarna. Du kan söka bland dessa objekt eller klicka på **[!UICONTROL More ...]**, som visar [!UICONTROL Search Form]så att du kan göra en mer detaljerad sökning efter dimensioner.
1. På [!UICONTROL Select From List], klicka **[!UICONTROL OK]**.
1. På [!UICONTROL Choose Page] -formulär, spara det specifika filtret om du vill och klicka sedan på **[!UICONTROL OK]**.
