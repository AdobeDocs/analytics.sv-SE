---
title: Dynamiska variabler
description: Kopiera variabler utan att öka längden på bildbegäran.
exl-id: 41aab44d-01fd-45fe-892d-637d69488d98
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 1%

---

# Dynamiska variabler

Med dynamiska variabler kan du kopiera värden från en variabel till en annan utan att öka längden på bildbegäran. De är användbara när du hämtar samma data i flera variabler.

I tidigare versioner av Analytics var längden på bildförfrågningen viktig för att förhindra trunkerade data. Förbättringar av AppMeasurement tillåter mycket längre frågesträngar för bildbegäranden, så dynamiska variabler behövs vanligtvis inte.

Dynamiska variabler har stöd för frågesträngsparametrar eller HTTP-rubriker i en bildbegäran. Se [frågeparametrar för datainsamling](../../validate/query-parameters.md) för en fullständig lista över tillgängliga parametrar att referera till. I [Standardfält för begäran](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields) på Wikipedia finns en fullständig lista över tillgängliga fält för HTTP-begäran som ska refereras.

När Adobe känner igen ett dynamiskt variabelprefix kopieras automatiskt frågesträngen eller HTTP-rubrikvärdet i rapportsviten. Den här åtgärden utförs före all annan bearbetning, inklusive bearbetningsregler och VISTA-regler.

>[!TIP]
>
>Tänk på maxgränserna för tecken när du kopierar variabler. Om du till exempel kopierar `eVar1` till `prop1` kan `prop1` ha ett trunkerat värde eftersom det har en gräns på 100 byte (medan `eVar1` har en gräns på 255 byte).

## Dynamiska variabler med hjälp av taggar i Adobe Experience Platform

Du kan använda dynamiska variabler i alla dimensionsfält som accepterar en sträng. Objekt i Dimensionen anges vanligtvis när Analytics-tillägget (globala variabler) eller enligt regler konfigureras.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Rules] och klicka sedan på önskad regel (eller skapa en regel).
4. Klicka på en befintlig [!UICONTROL Adobe Analytics - Set Variables]-åtgärd under [!UICONTROL Actions] eller klicka på +-ikonen.
5. Ange listrutan [!UICONTROL Extension] till Adobe Analytics och [!UICONTROL Action Type] till [!UICONTROL Set Variables].
6. Leta reda på önskad dimensionsobjekt.

Placera det dynamiska variabelprefixet i textfältet följt av frågesträngsparametern eller HTTP-huvudet som du vill referera till. Som standard är det dynamiska variabelprefixet `D=`.

## Dynamiska variabler i AppMeasurement och anpassad kodredigerare

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

>[!NOTE]
>
>Dynamiska variabler visas som strängar vid felsökning av implementeringen. Värdena kopieras på serversidan av datainsamlingsservrar från Adobe.
