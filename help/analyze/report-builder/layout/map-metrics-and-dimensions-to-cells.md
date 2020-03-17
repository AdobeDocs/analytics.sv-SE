---
description: Kontrollera att kalkylbladet inte är skyddat innan du börjar mappa objekt till kalkylbladet. Om skyddsschemat för kalkylbladet förhindrar användaråtgärder kan du inte markera celler i kalkylbladet. Ta först bort skyddet från bladet och lägg sedan till cellmappningar.
title: Mappa mått till celler
topic: Report builder
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mappa mått till celler

Kontrollera att kalkylbladet inte är skyddat innan du börjar mappa objekt till kalkylbladet. Om skyddsschemat för kalkylbladet förhindrar användaråtgärder kan du inte markera celler i kalkylbladet. Ta först bort skyddet från bladet och lägg sedan till cellmappningar.

Antalet områden och celler som ska mappas skiljer sig åt beroende på vilket mätvärde du väljer, granulariteten, datumintervallet och de filter du har angett. Om du t.ex. väljer [!UICONTROL Site Metric] > [!UICONTROL Traffic Report], anger [!UICONTROL Week] granularitet och anger datumintervall för [!UICONTROL Last 2 Weeks]uppmanas du att mappa tre celler (när du använder [!UICONTROL Custom Layout]) på [!UICONTROL Request Wizard: Step 2]. Begäran hämtar data för vecka ett och data för vecka två, där varje datapunktsvärde = värdet för en sidvy. Den tredje cellen fungerar som radrubrik som du kan konfigurera med [!UICONTROL Format Options].

Om du av misstag mappar inkompatibla platser i kalkylbladet genererar Report builder ett fel.

Följande avsnitt innehåller mer information:

* [Markera ett cellintervall](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [Tekniker för att markera celler](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [Problem vid mappning](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## Markera ett cellintervall {#section_1E37FB46DA194FB7A1050B8833A48AC6}

När du aktiverar [!UICONTROL Request Wizard: Step 2][!UICONTROL Custom Layout] för en begäran kan du mappa begäran till ett cellintervall.

Klicka på **[!UICONTROL Range Selector]** ![select_cell_icon.png](assets/select_cell_icon.png)

bredvid det objekt som du vill mappa.

* **Alla celler i intervallet:** Kräver att du markerar en grupp celler för en [!UICONTROL Custom Layout] formatförfrågan.
* **Intervallets första cell:** Gör att du kan markera cellen längst upp till vänster i intervallet och visar orienteringen för att ange den vågräta eller lodräta orienteringen för in- och utdataceller (kolumn eller rad). [!UICONTROL Range] Använd det här alternativet om du vill att Report Builder ska markera celler åt dig.
* **Intervallorientering:** Du kan orientera cellintervallen som kolumner eller rader.
* **Välj intervallets övre cellplacering:** Visar cellreferenser.

## Tekniker för att markera celler {#section_760421C3D7F84D67A639174710C93B22}

Du markerar data genom att klicka på **[!UICONTROL Range Selection]** ikonen ![select_cell_icon.png](assets/select_cell_icon.png)

och klicka och dra musen över cellområdet i kalkylbladet. En kontinuerlig markering kontureras av en svart kant.

![](assets/twenty_cells.gif)

Separata markerade rader har en tunn vit ram runt varje rad.

![](assets/twoXten_cells_highlighted.gif)

Om du vill mappa separata rader i en begäran använder du [!UICONTROL Control] tangenten, klickar och drar sedan markören över cellerna. Det gör du om din begäran kräver fyra områden med tio celler var, i stället för ett kontinuerligt område med 40 celler tillsammans.

![](assets/map4.png)

När du har markerat celler klickar du på **[!UICONTROL Range Selector]** igen i [!UICONTROL Range Selection] formuläret för att gå tillbaka till [!UICONTROL Request Wizard: Step 2].

## Problem vid mappning {#section_CC1BCF841291447EB3A994EB08F3A099}

Om du av misstag väljer att mappa till en cell som redan har en aktiv mappning, kommer du att märka att ingen cellreferens visas i textrutan bredvid intervallväljarikonen. När du klickar [!UICONTROL OK]visas felet&quot;Det markerade intervallet överlappar en annan begärans intervall. Ändra ditt val.&quot;

* Om du fortfarande behöver använda cellen högerklickar du på cellen eller cellerna och väljer **[!UICONTROL Delete Request]**.

Om du vill undvika det här meddelandet kan du göra på två sätt:

* Planera rapportens format genom att lägga till formatering till cellerna med förfrågningar och mappningar
* Testa områden i kalkylbladet som innehåller mappningar

Om du vill testa områden med inbäddade begäranden kan du:

* Starta [!UICONTROL Request Manager] och klicka på enskilda begäranden i tabellen. Om du klickar på begäran markeras cellerna i det kalkylblad där begäran mappas.
* Markera cellerna i kalkylbladet som du vill använda för en ny mappning och klicka på [!UICONTROL From Sheet]. Den [!UICONTROL Request Manager] här funktionen markerar den begäran i listan som har ett utdataobjekt som korsar den markerade cellen. Om ingen begäran är markerad är cellen tillgänglig.
* Markera celler i kalkylbladet, högerklicka på snabbmenyn och kontrollera om det [!UICONTROL Edit Request] är tillgängligt. I så fall är en begäran kopplad till dessa celler.
