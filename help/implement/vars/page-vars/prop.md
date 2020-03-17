---
title: prop
description: Anpassade variabler som du kan använda i implementeringen.
translation-type: tm+mt
source-git-commit: ddab63a4fe3b8f1a3187893eba1ac3a1eda3bc41

---


# prop

Props är anpassade variabler som du kan använda hur du vill.

> [!TIP] Adobe rekommenderar att du använder eVars i de flesta fall. I tidigare versioner av Adobe Analytics hade props och eVars fördelar och nackdelar för varandra. Adobe har dock förbättrat eVars så att de fyller i nästan alla användningsområden för proppar. Se [eVars](evar.md) för en funktionsjämförelse mellan dessa två anpassade variabeltyper.

Om din organisation använder props måste du registrera deras användning och logik i [lösningsdesigndokumentet](../../prepare/solution-design.md).

## Profiler i Adobe Experience Platform Launch

Du kan ange props antingen när du konfigurerar Analytics-tillägget (globala variabler) eller under regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] till [!UICONTROL Action Type] [!UICONTROL Set Variables].
6. Leta rätt på [!UICONTROL Props] avsnittet.

Du kan välja ett uttryck för att ange ett värde eller dataelement. Du kan också kopiera värdet från en annan Analytics-variabel.

## s.prop1 - s.prop75 in AppMeasurement and Launch custom code editor

Varje prop-variabel är en sträng som innehåller anpassade värden som är specifika för din organisation. Deras maximala längd är 100 byte. värden som är längre än 100 byte trunkeras automatiskt när de skickas till Adobe.

```js
s.prop1 = "Example custom value";
```

## Visa utkast

Listtecken är en inställning som används för att tillåta variabeln att innehålla flera värden i samma träff. Om den här inställningen inte är aktiverad, eller om fel avgränsare används, behandlas variabeln som ett enskilt värde.

### Konfigurera listproffs

Aktivera listtips i inställningarna för rapportsviten. Se [Trafikvariabler](/help/admin/admin/c-traffic-variables/traffic-var.md) i användarhandboken för Admin. Kontrollera att den önskade avgränsaren är korrekt konfigurerad. Adobe har ingen standardavgränsare.

> [!TIP] Vanliga avgränsare som används i implementeringar är kommatecken (`,`), kolon (`:`), semikolon (`;`) eller rör (`|`). Du kan använda valfri avgränsare som passar din implementering bäst.

### Ange listans förtecken

När du har konfigurerat liststeg i rapportsvitens inställningar med den önskade avgränsaren finns det inga andra implementeringsskillnader än att använda avgränsaren.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

> [!IMPORTANT] Listproppar har fortfarande en maxlängd på 100 byte. Det är lättare att nå den här gränsen och trimma eftersom de kan innehålla flera värden. Använd förkortningar eller förkorta värden om du kanske når denna gräns på 100 byte.
