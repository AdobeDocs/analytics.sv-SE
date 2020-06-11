---
title: eVar
description: Anpassade variabler som du kan använda i implementeringen.
translation-type: tm+mt
source-git-commit: 10e157e370367374b55ee9c87c0e5c7ca9e99c1a
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 0%

---


# eVar

*Den här hjälpsidan beskriver hur du implementerar eVars. Mer information om hur eVars fungerar som en dimension finns i[eVars](/help/components/dimensions/evar.md)i användarhandboken för komponenter.*

Variabler är anpassade variabler som du kan använda hur du vill. Om du har ett [lösningsdesigndokument](/help/implement/prepare/solution-design.md)blir de flesta dimensioner som är specifika för din organisation eVars. Som standard kvarstår eVars utanför den träff de är inställda på. Du kan anpassa deras förfallodatum och allokering under [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) i inställningarna för rapportsviten.

Antalet tillgängliga eVars-variabler beror på ditt avtal med Adobe. Upp till 250 eVars är tillgängliga om ditt avtal med Adobe ger stöd för det.

## Konfigurera eVars i inställningarna för rapportsviten

Innan du använder eVars i implementeringen måste du konfigurera varje eVar i inställningarna för rapportsviten. Se [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) i administrationshandboken.

## eVars in Adobe Experience Platform Launch

Du kan ange eVars antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] till [!UICONTROL Action Type] [!UICONTROL Set Variables].
6. Leta rätt på [!UICONTROL eVars] avsnittet.

Du kan ställa in en eVar på ett värde eller ett dataelement. Du kan också kopiera värdet från en annan Analytics-variabel.

## s.eVar1 - s.eVar250 i den anpassade kodredigeraren AppMeasurement och Launch

Varje eVar är en sträng som innehåller anpassade värden som är specifika för din organisation. Deras största längd är 255 byte. värden som är längre än 255 byte trunkeras automatiskt när de skickas till Adobe.

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

Om fler än två decimaler anges avrundas eVar-räknaren till två decimaler. En eVar-räknare får inte innehålla negativa tal.

> [!IMPORTANT] Du måste först konfigurera eVars till Counter i Admin Console innan du använder counter eVars. Se [Konverteringsvariabler](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) i administrationshandboken.
