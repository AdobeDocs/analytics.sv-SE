---
title: Dynamiska variabler
description: Kopiera variabler utan att öka längden på bildbegäran.
feature: Appmeasurement Implementation
exl-id: 41aab44d-01fd-45fe-892d-637d69488d98
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---

# Dynamiska variabler

Med dynamiska variabler kan du kopiera värden från en variabel till en annan utan att öka längden på bildbegäran. De är användbara när du hämtar samma data i flera variabler.

I tidigare versioner av Analytics var längden på bildförfrågningen viktig för att förhindra trunkerade data. Förbättringar av AppMeasurement tillåter mycket längre frågesträngar för bildbegäranden, så dynamiska variabler behövs vanligtvis inte.

Dynamiska variabler har stöd för frågesträngsparametrar eller HTTP-rubriker i en bildbegäran. I [frågeparametrar för datainsamling](../../validate/query-parameters.md) finns en fullständig lista över tillgängliga parametrar som ska refereras. Se [Standardfält för begäran](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields) på Wikipedia för en fullständig lista över tillgängliga fält för HTTP-begäran som ska refereras.

När Adobe känner igen ett dynamiskt variabelprefix kopieras automatiskt frågesträngen eller HTTP-rubrikvärdet i rapportsviten. Den här åtgärden utförs före all annan bearbetning, inklusive bearbetningsregler och VISTA-regler.

>[!TIP]
>
>Tänk på maxgränserna för tecken när du kopierar variabler. Om du till exempel kopierar `eVar1` till `prop1` kan `prop1` ha ett trunkerat värde eftersom det har en gräns på 100 byte (medan `eVar1` har en gräns på 255 byte).

## Dynamiska variabler med Web SDK

Använd datastream-mappning för att skicka data till flera Analytics-variabler från ett enda XDM-fält.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på **[!UICONTROL Datastreams]** i den vänstra listen.
1. Klicka på önskat datastream.
1. Klicka på **[!UICONTROL Edit Mapping]** till höger.
1. Mappa önskad [!UICONTROL Source Field] till önskad [!UICONTROL Target Field]. Ett enda källfält kan mappas till valfritt antal målfält.

## Dynamiska variabler med Adobe Analytics-tillägget

Du kan använda dynamiska variabler i alla dimensionsfält som accepterar en sträng. Dimension-objekt anges vanligtvis när Analytics-tillägget (globala variabler) eller under regler konfigureras.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange Adobe Analytics i listrutan [!UICONTROL Extension] och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på önskad dimensionsobjekt.

Placera det dynamiska variabelprefixet i textfältet följt av frågesträngsparametern eller HTTP-huvudet som du vill referera till. Som standard är det dynamiska variabelprefixet `D=`.

## Dynamiska variabler i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Dynamiska variabler är textsträngar som tilldelas andra variabler. Standardprefixet för dynamisk variabel är `D=`. Dynamiska variabler är versalkänsliga.

```js
// Copy eVar1 into eVar2. The query string parameter of eVar1 is v1.
s.eVar1 = "Example value";
s.eVar2 = "D=v1";

// Take the user agent string found in the image request HTTP header and place it in eVar1.
s.eVar1 = "D=User-Agent";

// Copy the page URL and place it in eVar1. The query string parameter of page URL is g.
s.eVar1 = "D=g";
```

>[!NOTE]
>
>Dynamiska variabler visas som strängar vid felsökning av implementeringen. Värdena kopieras på serversidan av Adobe datainsamlingsservrar.
