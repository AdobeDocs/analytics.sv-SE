---
title: Dynamiska variabler
description: Kopiera variabler utan att öka längden på bildbegäran.
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# Dynamiska variabler

Med dynamiska variabler kan du kopiera värden från en variabel till en annan utan att öka längden på bildbegäran. De är användbara när du hämtar samma data i flera variabler.

I tidigare versioner av Analytics var längden på bildförfrågningen viktig för att förhindra trunkerade data. Förbättringar av AppMeasurement tillåter mycket längre frågesträngar för bildbegäranden, så dynamiska variabler behövs vanligtvis inte.

Dynamiska variabler har stöd för frågesträngsparametrar eller HTTP-rubriker i en bildbegäran. Se frågeparametrar [för](../../validate/query-parameters.md) datainsamling för en fullständig lista över tillgängliga parametrar att referera till. Se [Standardfält](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields) för begäran på Wikipedia för en fullständig lista över tillgängliga fält för HTTP-begäran som ska refereras.

När Adobe känner igen ett dynamiskt variabelprefix kopieras automatiskt frågesträngen eller HTTP-rubrikvärdet i rapportsviten. Den här åtgärden utförs före all annan bearbetning, inklusive bearbetningsregler och VISTA-regler.

> [!TIP] Tänk på maxgränserna för tecken när du kopierar variabler. Om du till exempel kopierar `eVar1` till `prop1`kan `prop1` det ha ett trunkerat värde eftersom det har en gräns på 100 byte (medan `eVar1` har en gräns på 255 byte).

## Dynamiska variabler i Adobe Experience Platform Launch

Du kan använda dynamiska variabler i alla dimensionsfält som accepterar en sträng. Dimensionsvärden ställs vanligtvis in när Analytics-tillägget (globala variabler) konfigureras eller under regler.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Rules] fliken och klicka sedan på önskad regel (eller skapa en regel).
4. Under [!UICONTROL Actions]klickar du på en befintlig [!UICONTROL Adobe Analytics - Set Variables] åtgärd eller på +-ikonen.
5. Ställ in listrutan till Adobe Analytics och [!UICONTROL Extension] till [!UICONTROL Action Type] [!UICONTROL Set Variables].
6. Leta reda på önskat dimensionsvärde.

Placera det dynamiska variabelprefixet i textfältet följt av frågesträngsparametern eller HTTP-huvudet som du vill referera till. Som standard är det dynamiska variabelprefixet `D=`.

## Dynamiska variabler i den anpassade kodredigeraren AppMeasurement och Launch

Dynamiska variabler är textsträngar som tilldelas andra variabler. Standardprefixet för den dynamiska variabeln är `D=`. Dynamiska variabler är skiftlägeskänsliga.

```js
// Copy eVar1 into eVar2. The query string parameter of eVar1 is v1.
s.eVar1 = "Example value";
s.eVar2 = "D=v1";

// Take the user agent string found in the image request HTTP header and place it in eVar1.
s.eVar1 = "D=User-Agent";

// Copy the page URL and place it in eVar1. The query string parameter of page URL is g.
s.eVar1 = "D=g";
```

> [!NOTE] Dynamiska variabler visas som strängar vid felsökning av implementeringen. Värdena kopieras på serversidan av Adobes datainsamlingsservrar.
