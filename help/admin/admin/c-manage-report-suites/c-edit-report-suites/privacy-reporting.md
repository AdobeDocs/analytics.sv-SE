---
description: Aktivera dimensioner för innehållshantering.
title: Sekretessrapportering
feature: Admin Tools
exl-id: 307c9ae2-2135-4a0b-9d2d-3c13a27b8361
source-git-commit: b5aba8a42f524ef3367a779e6fb1a731de680750
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 0%

---

# Sekretessrapportering

Sekretessrapporteringen gör att du kan aktivera [Medgivandehantering - anmälan](/help/components/dimensions/cm-opt-in.md), [Medgivandehantering avanmäl dig](/help/components/dimensions/cm-opt-out.md) och [Annonsmedgivande](/help/components//dimensions/ad-consent.md) dimensioner för rapportering.

>[!NOTE]
>
>Vi har lagt till en ny flagga för godkännande av annonsplattform. Om du vill att den nya variabeln ska börja gälla måste du aktivera datasekretesrapporter igen.

Så här öppnar du den här sidan:

1. Logga in på Adobe Analytics och navigera till **[!UICONTROL Admin]** > **[!UICONTROL Report suites]**.
1. Välj en eller flera önskade rapportsviter och välj sedan **[!UICONTROL Edit settings]** > **[!UICONTROL Privacy management]** > **[!UICONTROL Privacy reporting]**.

   ![Redigera inställningar](assets/rsm-privacy-select.png)

1. Klicka på **[!UICONTROL Enable Data Privacy Reports]**.

   >[!NOTE]
   >
   >När variablerna har aktiverats kan de inte stängas av.

   ![Aktivera](assets/rsm-privacy-enable.png)

1. När det är aktiverat visas ett bekräftelsemeddelande. Dimensionerna är tillgängliga i rapporter.

   ![Rapport](assets/consent-management.png)

## Dimension för annonsmedgivande

The [Dimension för annonsmedgivande](/help/components/dimensions/ad-consent.md) visar om samtycke samlas in för att skicka data till tredjepartsleverantörer av annonser, som Google, Meta och andra.