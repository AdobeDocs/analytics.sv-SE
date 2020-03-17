---
title: linkLeaveQueryString
description: Tillåter lagring av frågesträngar i länkspårningsdimensioner.
translation-type: tm+mt
source-git-commit: e500332fe16887fa004858b07b59644837e183aa

---


# linkLeaveQueryString

AppMeasurement rensar frågesträngar från URL:er för länkspårning som standard. Använd variabeln linkLeaveQueryString för att bevara frågesträngar i länkspårningsdimensioner.

För vissa avslutslänkar och hämtningslänkar kan den viktiga delen av URL-adressen finnas i frågesträngen. En nedladdningslänk som `https://example.com/download.asp?filename=myfile.exe` innehåller till exempel viktig länkinformation i frågesträngen.

Om länkspårningsinformation inte finns i URL:er på din webbplats är det inte nödvändigt att använda den här variabeln. Genom att radera frågesträngar från URL:er för länkspårning kan du begränsa antalet unika värden som dimensionen innehåller.

Aktiveringen `linkLeaveQueryString` gäller för alla länkspårningsdimensioner (inklusive anpassade länkar, avslutslänkar och hämtningslänkar).

> [!TIP] Den här variabeln påverkar inte dimensioner utanför länkspårning. Det påverkar bara anpassade länkar, stängningslänkar och hämtningslänkar.

## Behåll URL-parametrar i Adobe Experience Platform Launch

[!UICONTROL Keep URL Parameters] är en kryssruta under [!UICONTROL Link Tracking] dragspelet när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken så att [!UICONTROL Link Tracking] kryssrutan visas [!UICONTROL Keep URL Parameters] .

Markera den här rutan om du vill inkludera frågesträngar i dimensioner för länkspårning.

## s.linkLeaveQueryString i AppMeasurement and Launch custom code editor

Variabeln `s.linkLeaveQueryString` är boolesk. Dess standardvärde är `false`.

* Om variabeln är inställd på `true`bevaras frågesträngar i URL:er för länkspårning.
* Om variabeln är inställd på `false` eller inte definierad tas frågesträngar bort från URL:er för länkspårning.

```js
s.linkLeaveQueryString = true;
```

## Exempel

Var försiktig när du ställer in den här variabeln på true, eftersom den kan påverka länkspårningsfilter som `linkInternalFilters`, `linkExternalFilters`och `linkDownloadFiletypes`.

Titta på följande exempel som om det var på `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
