---
description: Virtuella rapportsviter kan struktureras för att inkludera och exkludera komponenter.i Analysis Workspace.
title: Komponenturval för Virtual Report Suite
uuid: 6c6a4071-22ad-4e8c-b1ed-140b2aa04f76
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Komponenturval för Virtual Report Suite

Virtuella rapportsviter kan struktureras för att inkludera och exkludera komponenter.i Analysis Workspace.

> [!NOTE] Ändringar har gjorts som komponentadministratörer och icke-administratörer kan se i förvaltade arbetsyteprojekt och förvaltade virtuella rapportsviter (VRS). Tidigare kunde vem som helst se komponenter som inte är kuraterade genom att klicka **[!UICONTROL Show all Components]**. Med den [uppdaterade kurationsupplevelsen](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/curate-projects-vrs.html) får du mer detaljerad kontroll över vilka komponenter som är synliga.

Om du vill aktivera komponenturval

1. Gå till **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]** > **[!UICONTROL Create new virtual report suite]**.
1. Klicka på **[!UICONTROL Settings]** fliken när du har definierat **[!UICONTROL Components]** den.

1. Markera kryssrutan **[!UICONTROL Enable Customization of Virtual Report Suite Components]**:

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >Om komponentanpassning är aktiverat är den virtuella rapportsviten **bara tillgänglig i Analysis Workspace** och är inte tillgänglig i följande:

   * [!UICONTROL Reports & Analytics]
   * [!UICONTROL Ad Hoc Analysis]
   * [!UICONTROL Data Warehouse]
   * [!UICONTROL Report Builder]
   * API för analysrapportering
   När du har markerat det här alternativet kan du lägga till de komponenter som du vill ska ingå i den virtuella rapportsviten genom att dra de tillämpliga komponenterna från kolumnen&quot;Uteslutna komponenter&quot; till kolumnen&quot;inkluderade komponenter&quot;. De komponenter som kan inkluderas och exkluderas är:

   * Dimensioner
   * Mått
   * Segment
   * Datumintervall
   >[!NOTE]
   >
   >Du behöver inte *dela* kuraterade komponenter (segment, beräknade värden, datumintervall). De visas alltid i Analysis Workspace om de är strukturerade för den virtuella rapportsviten, även om de inte delas.

1. Dessutom kan du filtrera eller söka efter komponenterna och lägga till hela den filtrerade markeringen i den inkluderade kolumnen genom att klicka på **[!UICONTROL Add All]**.

   ![](assets/vrs-add-all.png)

## Byt namn på komponenter {#section_0F7CD9F684FE4765BC00A2AFED56550E}

Du kan ändra visningsnamnen för inkluderade komponenter som är specifika för den virtuella rapportsviten. Om du till exempel vill inkludera Sidnamn i den virtuella rapportsviten, men vill byta namn på den till en mer mobilvänlig kontext, kan du ändra den till Appskärmar. Det nya namnet visas på Analysis Workspace när den här virtuella rapportsviten används.

![](assets/vrs-rename-component.png)

I Analysis Workspace klickar du på informationsikonen för någon av de inkluderade komponenterna för att visa det ursprungliga namnet på den omdöpta komponenten:

![](assets/vrs-aw-renamed.png)

## Komponentgrupper {#section_483BEC76F49E46ADAAA03F0A12E48426}

Använd komponentgrupper för att göra satsvis komponenttillägg i din virtuella rapportsserie. Om du till exempel vill importera en standarduppsättning med komponenter som är specifika för mobilappsanalys väljer du mobilappsgruppen. En motsvarande uppsättning dimensioner och mått (som redan har bytt namn) läggs automatiskt till i listan med inkluderade virtuella rapportsviter.

![](assets/vrs-comp-grp.png)

## Arbetsytebeteende {#section_6C32F8B642804C0097FCB14E21028D4A}

Mer information om kurering i Analysis Workspace finns i [Curate and Share a Project](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/curate.html).
