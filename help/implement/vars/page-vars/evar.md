---
title: eVar-variabler
description: Anpassade variabler som du kan använda i implementeringen.
feature: Variables
exl-id: f89457b2-4186-4276-8637-9992070e3a73
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# eVar

*Den här hjälpsidan beskriver hur du implementerar eVars. Mer information om hur eVars fungerar som en dimension finns i [eVars](/help/components/dimensions/evar.md) i användarhandboken för komponenter.*

Variabler är anpassade variabler som du kan använda hur du vill. Om du har en [konstruktionsdokument](/help/implement/prepare/solution-design.md), blir de flesta dimensioner som är specifika för din organisation eVars. Som standard kvarstår eVars utanför den träff de är inställda på. Du kan anpassa deras förfallodatum och tilldelning under [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) i Rapportsvitens inställningar.

Antalet tillgängliga eVars-variabler beror på ditt avtal med Adobe. Upp till 250 eVars är tillgängligt om ditt avtal med Adobe stöder det.

## Konfigurera eVars i inställningarna för rapportsviten

Innan du använder eVars i implementeringen måste du konfigurera varje eVar i rapportsvitens inställningar. Se [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) i administrationshandboken.

## eVars using tags in Adobe Experience Platform

Du kan ange eVars antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] och sedan klicka på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] eller klicka på +-ikonen.
5. Ange [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på [!UICONTROL eVars] -avsnitt.

Du kan ange ett värde eller ett dataelement som eVar. Du kan också kopiera värdet från en annan Analytics-variabel.

## s.eVar1 - s.eVar250 i AppMeasurement och en anpassad kodredigerare

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
