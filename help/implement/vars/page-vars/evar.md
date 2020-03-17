---
title: eVar
description: Anpassade variabler som du kan använda i implementeringen.
translation-type: tm+mt
source-git-commit: dcb69257fd29686ae346cf4d0cf50ed041ebcbbc

---


# eVar

Variabler är anpassade variabler som du kan använda hur du vill.

> [!TIP] Adobe rekommenderar att du i de flesta fall använder eVars över props. I tidigare versioner av Adobe Analytics hade props och eVars fördelar och nackdelar för varandra. Adobe har dock förbättrat eVars så att de fyller i nästan alla användningsområden för proppar.

Se till att du spelar in hur du använder varje eVar och deras logik i [lösningsdesigndokumentet](../../prepare/solution-design.md).

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

Du kan välja en eVar för att ange ett värde eller dataelement. Du kan också kopiera värdet från en annan Analytics-variabel.

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

## Exklusiva fördelar för proppar och eVars

I den aktuella versionen av Adobe Analytics är både props och eVars anpassade variabler med liknande funktioner. De har dock flera stora skillnader:

* Data i props finns tillgängliga för rapportering inom några minuter. Det kan ta upp till 30 minuter innan eVars visas i rapporter.
* Profiler har en gräns på 100 byte i rapporter. Variabler har en gräns på 255 byte.
* Props kan bli listruteförvrängningar, som accepterar flera värden i samma träff. Listvariabler är en separat variabel och det finns bara tre listvariabler tillgängliga.
* Som standard kvarstår inte uttryck efter den träff de ställs in. eVars har en anpassad förfallotid, vilket gör att du kan avgöra när en eVar inte längre får kredit för en efterföljande händelse. Om du däremot använder [rapporttidsbearbetning](../../../components/vrs/vrs-report-time-processing.md)kan både props och eVars använda en anpassad attribueringsmodell.
