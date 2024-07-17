---
description: På sidan Beräknade mätvärden kan du strukturera mätvärden på många olika sätt, t.ex. dela, filtrera, tagga, godkänna, kopiera, ta bort och markera som favoriter.
title: Beräknat måttansvarig
feature: Calculated Metrics
exl-id: 32430e77-2450-4672-9c21-255e76802a4c
source-git-commit: df9c6d59ef5f5c43d0e1ef822bd23bc0e09ff20e
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 0%

---

# Beräknat måttansvarig

På sidan Beräknade mätvärden kan du strukturera mätvärden på många olika sätt, t.ex. dela, filtrera, tagga, godkänna, kopiera, ta bort och markera som favoriter.

På sidan Beräknade mätvärden visas alla segment som du äger och som har delats med dig. Användare på administratörsnivå kan se alla anpassade värden i organisationen.

<!-- add screenshot -->

## Få åtkomst till hanteraren för beräknade värden

1. I Adobe Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Beräknade mått**].

## Tillgängliga åtgärder i hanteraren för beräknade värden

I Calculated Metrics Manager kan du:

* [Filtrera beräknade värden](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-filter.md)

* [Markera beräknade värden som favoriter](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md)

* [Godkänn beräknade värden](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-approving.md)

* [Tagga beräknade värden](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-tagging.md)

* [Dela beräknade värden](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md)

* Exportera ett beräknat mått till en CSV-fil.

* [Kopiera beräknade värden](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-copy.md)

* Ta bort beräknade värden

## Konfigurera kolumner

Du kan konfigurera informationen som visas för varje beräknat mått i hanteraren för beräknade mått genom att konfigurera kolumnerna som visas.

Så här konfigurerar du synliga kolumner i hanteraren för beräknade mått:

1. I Adobe Analytics väljer du fliken **[!UICONTROL Components]** och sedan **[!UICONTROL Calculated metrics]**.

1. Välj ikonen **Anpassa kolumner** ![Anpassa kolumner](assets/customize-columns-icon.png) i hanteraren för beräknade mått och markera sedan de kolumner som du vill ska visas i hanteraren för beräknade värden. Anpassa kolumner Anpassa kolumner.

   Följande kolumner är tillgängliga:

   | Kolumnrubrik | Beskrivning |
   |---|---|
   | Favoriter | Visar stjärnikoner bredvid varje beräknat mätvärde, så att du kan markera beräknade mätvärden som favoriter. Mer information finns i [Markera beräknade värden som favoriter](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). |
   | Titel och beskrivning | Dessa värden finns i verktyget Beräknade mått. Om du vill redigera titeln och beskrivningen markerar du titellänken för att öppna verktyget Beräknade mätvärden. |
   | Rapportsvit | Anger i vilken rapportsvit mätvärdena senast sparades. |
   | Ägare | Anger vem som äger det anpassade måttet. Som icke-administratör kan du bara se mätvärden som du äger eller de som delats med dig. |
   | Taggar | Visar taggar som har tillämpats på måttet, antingen av dig eller av personer som har delat det beräknade måttet med dig. |
   | Delas med | Visar enskilda personer eller grupper (endast admin) eller Alla (endast admin) som du har delat det beräknade måttet med. <p>När ett beräknat mått delas visas en delningsikon bredvid det beräknade måttnamnet.</p> |
   | Ändrat den | Anger det datum då det anpassade måttet senast ändrades. |
   | Används i | Visar hur många komponenter det beräknade måttet används i. <p>Om det beräknade måttet till exempel används i 40 projekt och 2 varningar visas värdet för den här kolumnen som [!UICONTROL **42 komponenter**]. <p>Välj värdet i den här kolumnen för att se hur det beräknade mätvärdet används (till exempel [!UICONTROL **Projekt (40)**], [!UICONTROL **Varningar (2)**]).</p><p>Beräknade mätvärden kan användas i följande komponenttyper:</p> <ul><li>Larm</li><li>Projekt</li><li>Schemalagda projekt</li></ul><p>Den här informationen kan hjälpa dig att avgöra om en komponent är värdefull för användare i organisationen, var den används och om den behöver tas bort eller ändras.</p><p>Tänk på följande när du visar den här kolumnen:</p><ul><li>Den här informationen inkluderar inte användning från API, Report Builder eller Data Warehouse.</li><li>Kolumnen [!UICONTROL **Används i**] visas inte som standard. [Konfigurera kolumner](#configure-columns) så att de visas.</li><li>Om det inte finns några data i den här kolumnen för en viss komponent, men den har datumet [!UICONTROL **Senast använd**], kan komponenten ha använts i en analys utan att sparas.</li><li>Den här informationen är endast tillgänglig för systemadministratörer.</li></ul><p>Du kan använda [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) tillsammans med den här informationen för att hjälpa dig att hålla reda på och bättre förstå hur komponenter används i din organisation.</p> |
   | Senast använd | Visar datumet då det beräknade måttet senast användes i någon av följande komponenttyper: <ul><li>Larm</li><li>Beräknade mått</li><li>Projekt</li><li>Schemalagda projekt</li></ul> <p>Den här informationen kan hjälpa dig att avgöra om en komponent är värdefull för användare i organisationen, var den används och om den behöver tas bort eller ändras.</p><p>Tänk på följande när du visar den här kolumnen:</p><ul><li>Den här informationen inkluderar inte användning från API, Report Builder eller Data Warehouse.</li><li>För vissa komponenter kanske den här kolumnen inte innehåller data om komponenten senast användes före september 2023.</li><li>Den här informationen är endast tillgänglig för systemadministratörer.</li></ul><p>Du kan använda [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) tillsammans med den här informationen för att hjälpa dig att hålla reda på och bättre förstå hur komponenter används i din organisation. |

   {style="table-layout:auto"}
