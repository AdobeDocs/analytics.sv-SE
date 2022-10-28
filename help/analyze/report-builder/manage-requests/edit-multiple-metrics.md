---
description: Med funktionen Redigera mått över flera begäranden kan du enkelt lägga till, ta bort eller ersätta mått i en befintlig begäran eller i en hel grupp med förfrågningar.
title: Redigera mätvärden för flera förfrågningar
feature: Report Builder
role: User, Admin
exl-id: e537b67a-aa07-4acd-a476-7497426e2f7d
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 4%

---

# Redigera mätvärden för flera förfrågningar

Med funktionen Redigera mått över flera begäranden kan du enkelt lägga till, ta bort eller ersätta mått i en befintlig begäran eller i en hel grupp med förfrågningar.

## Lägg till mått {#section_3FBDA9668039404895059618D70FCBCD}

Kom ihåg

* Det går bara att lägga till mått i begäranden om pivotlayout. Om några av de valda förfrågningarna är anpassade layouter går det inte att lägga till mått. Anledningen är att Report Builder inte vet var i kalkylbladet det nya måttet ska placeras, eftersom layouten anpassas.
* Om du bara har valt begäranden om anpassad layout **[!UICONTROL Add Metric/s]** är inte tillgängligt.
* Om du lägger till mätvärden kommer storleken på en begäran att öka och det kan leda till att den överlappar en annan begäran. Se till att din begäran har tillräckligt med utrymme för att det ska gå att lägga till mätvärden.
* Om det tillagda måttet redan finns i en av de valda förfrågningarna läggs det inte till i den förfrågan.

Så här lägger du till ett eller flera mått:

1. Markera en eller flera begäranden i Excel och högerklicka för att välja **[!UICONTROL Edit Metrics]**. (Eller klicka på **[!UICONTROL Manage]** > **[!UICONTROL Edit Multiple]** > `<choose metric>` > **[!UICONTROL Edit Group]** för att markera gruppen med begäranden som ska ändras.)
1. Välj **[!UICONTROL Add Metric(s)]**och välj de mätvärden som ska läggas till.

   ![Lägg till mått](assets/add_metric.png)

1. Uppdatera begäran för att se faktiska data. Du kommer att se offlinedata tills du uppdaterar.

## Ersätt mått {#section_D773AAC7B30C4FBEBDB66B203C217818}

Kom ihåg

* Endast 1:1-ersättningar tillåts, inte 1:många eller många:1.
* Om det mätvärde som ska ersättas inte finns i någon av de valda förfrågningarna ändras inte den här förfrågan.
* Det nya måttet placeras på samma plats som det substituerade måttet. Detta innebär:

   * **I en pivotlayout**: Om en begäran om pivotlayout ger utdata för datum, besök, besökare, daglig unik och&quot;besökare&quot; ersätts av&quot;intäkt&quot;, blir den uppdaterade begärandelayouten: datum, besök, intäkter, daglig unik tid.
   * **I en anpassad layout**: om&quot;besökarmåttet&quot; genererades i cell F11, kommer den uppdaterade begärandelayouten att visa&quot;intäkter&quot; i samma cell F11.

* Om vissa åtgärder har vidtagits för det ersatta mätvärdet (genomsnittlig, förpended text, post-pended text, microcharting) kommer dessa åtgärder också att tillämpas på det nya mätvärdet.

Ersätta ett mått

1. Markera en eller flera begäranden i Excel och högerklicka för att välja **[!UICONTROL Edit Metrics]**. (Eller klicka på **[!UICONTROL Manage]** > **[!UICONTROL Edit Multiple]** > **`<choose metric>`** > **[!UICONTROL Edit Group]** för att markera gruppen med begäranden som ska ändras.)

1. Välj **[!UICONTROL Replace Metric]**.

   ![Ersätt mått](assets/replace_metric.png)

1. Välj vilket mätvärde som ska ersättas och vilket mätvärde som ska ersättas med.
1. Uppdatera begäran. Du kommer att se offlinedata tills du uppdaterar.

## Ta bort mått {#section_D3CD5BAC7670416593B633B2B8423C60}

Kom ihåg

* Om något av de mätvärden som markerats för borttagning inte finns i någon av de markerade förfrågningarna ändras inte den här begäran.
* Om du tar bort ett mått i en pivotlayout flyttas layouten för mått som finns efter de borttagna måtten.

   **Exempel**: Om en begäran om pivotlayout visar datum, besök, besökare, daglig unik och du tar bort&quot;besök&quot;, kommer den uppdaterade layouten för begäran att visa: datum, besökare, dagligt unikt.

Så här tar du bort mått:

1. Markera en eller flera begäranden i Excel och högerklicka för att välja **[!UICONTROL Edit Metrics]**. (Eller klicka på **[!UICONTROL Manage]** > **[!UICONTROL Edit Multiple]** > **`<choose metric>`** > **[!UICONTROL Edit Group]** för att markera gruppen med begäranden som ska ändras.)

1. Välj **[!UICONTROL Remove Metric(s)]**.

   ![Ta bort mått](assets/remove_metric.png)

1. Välj ett eller flera mått som ska tas bort från begäran.
1. Uppdatera begäran. Du kommer att se offlinedata tills du uppdaterar.
