---
title: eVar-variabler
description: Anpassade variabler som du kan använda i implementeringen.
feature: Variables
exl-id: f89457b2-4186-4276-8637-9992070e3a73
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---

# eVar

*Den här hjälpsidan beskriver hur du implementerar eVars. Mer information om hur eVars fungerar som en dimension finns i [eVars](/help/components/dimensions/evar.md) i användarhandboken för komponenter.*

Variabler är anpassade variabler som du kan använda hur du vill. Om du har en [konstruktionsdokument](/help/implement/prepare/solution-design.md), blir de flesta dimensioner som är specifika för din organisation eVars. Som standard kvarstår eVars utanför den träff de är inställda på. Du kan anpassa deras förfallodatum och tilldelning under [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) i Rapportsvitens inställningar.

Antalet tillgängliga eVars-variabler beror på ditt avtal med Adobe. Upp till 250 eVars är tillgängligt om ditt avtal med Adobe stöder det.

## Konfigurera eVars i inställningarna för rapportsviten

Innan du använder eVars i implementeringen måste du konfigurera varje eVar i rapportsvitens inställningar. Se [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) i administrationshandboken.

## eVars med Web SDK

eVars are [mappas för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) under XDM-fälten `_experience.analytics.customDimensions.eVars.eVar1` till `_experience.analytics.customDimensions.eVars.eVar250`.

## eVars med Adobe Analytics-tillägget

Du kan ange eVars antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL eVars] -avsnitt.

Du kan ange ett värde eller ett dataelement som eVar. Du kan också kopiera värdet från en annan Analytics-variabel.

## s.eVar1 - s.eVar250 i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Varje eVar är en sträng som innehåller anpassade värden som är specifika för din organisation. Deras största längd är 255 byte. värden som är längre än 255 byte trunkeras automatiskt när de skickas till Adobe.

```js
s.eVar1 = "Example custom value";
```

## Counter eVars

eVar innehåller vanligtvis ett strängvärde. Du kan dock konfigurera eVars så att den i stället innehåller en räknare. Du vill till exempel räkna antalet interna sökningar som gjorts före ett köp. I stället för att ange ett textvärde använder du följande syntax:

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

Om fler än två decimaler anges avrundas eVar till två decimaler. En räknare kan inte innehålla negativa tal.

>[!IMPORTANT]
>
>Du måste först konfigurera eVars till Counter i Admin Console innan du använder counter eVars. Se [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) i administrationshandboken.
