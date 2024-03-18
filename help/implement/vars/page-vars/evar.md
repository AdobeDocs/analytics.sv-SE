---
title: eVar (variabel)
description: Anpassade variabler som du kan använda i implementeringen.
feature: Variables
exl-id: f89457b2-4186-4276-8637-9992070e3a73
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---

# eVar

*Den här hjälpsidan beskriver hur du implementerar eVars. Mer information om hur eVars fungerar som en dimension finns i [eVars](/help/components/dimensions/evar.md) i användarhandboken för komponenter.*

Variabler är anpassade variabler som du kan använda hur du vill. Om du har en [konstruktionsdokument](/help/implement/prepare/solution-design.md), blir de flesta dimensioner som är specifika för din organisation eVars. Som standard kvarstår eVars utanför den träff de är inställda på. Du kan anpassa deras förfallodatum och tilldelning under [Konverteringsvariabler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) i Rapportsvitens inställningar.

Antalet tillgängliga eVars-variabler beror på ditt avtal med Adobe. Upp till 250 eVars är tillgängligt om ditt avtal med Adobe stöder det.

## Konfigurera eVars i inställningarna för rapportsviten

Innan du använder eVars i implementeringen måste du konfigurera varje eVar i rapportsvitens inställningar. Se [Konverteringsvariabler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) i administrationshandboken.

## eVars med Web SDK

Variabler mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `xdm._experience.analytics.customDimensions.eVars.eVar1` till `xdm._experience.analytics.customDimensions.eVars.eVar250`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.eVar1` till `data.__adobe.analytics.eVar250`eller `data.__adobe.analytics.v1` till `data.__adobe.analytics.v250`

## eVars med Adobe Analytics-tillägget

Du kan ange eVars antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] nedrullningsbar lista till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL eVars] -avsnitt.

Du kan ställa in en eVar på ett värde eller ett dataelement. Du kan också kopiera värdet från en annan Analytics-variabel.

## s.eVar1 - s.eVar250 i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Varje eVar är en sträng som innehåller anpassade värden som är specifika för din organisation. Deras maxlängd är 255 byte. Värden som är längre än 255 byte trunkeras automatiskt när de skickas till Adobe.

```js
s.eVar1 = "Example custom value";
```

## Counter eVars

eVar-värden innehåller vanligtvis ett strängvärde. Du kan dock konfigurera eVars så att den i stället innehåller en räknare. Du vill till exempel räkna antalet interna sökningar som gjorts före ett köp. I stället för att ange ett textvärde använder du följande syntax:

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

Om fler än två decimaler anges avrundas eVarna till två decimaler. En eVar-räknare får inte innehålla negativa tal.

>[!IMPORTANT]
>
>Du måste först konfigurera eVars till Counter i Admin Console innan du använder counter eVars. Se [Konverteringsvariabler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) i administrationshandboken.
