---
title: linkLeaveQueryString
description: Tillåter lagring av frågesträngar i länkspårningsdimensioner.
feature: Variables
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# linkLeaveQueryString

AppMeasurement rensar frågesträngar från URL:er för länkspårning som standard. Använd `linkLeaveQueryString` variabel för att bevara frågesträngar i länkspårningsdimensioner.

För vissa avslutslänkar och hämtningslänkar kan den viktiga delen av URL-adressen finnas i frågesträngen. En nedladdningslänk som `https://example.com/download.asp?filename=myfile.exe` innehåller viktig länkinformation i frågesträngen.

Om länkspårningsinformation inte finns i URL:er på din webbplats är det inte nödvändigt att använda den här variabeln. Genom att radera frågesträngar från URL:er för länkspårning kan du begränsa antalet unika värden som dimensionen innehåller.

Aktivering `linkLeaveQueryString` används för alla dimensioner av länkspårning (inklusive anpassade länkar, avslutslänkar och hämtningslänkar).

>[!TIP]
>
>Den här variabeln påverkar inte dimensioner utanför länkspårning. Det påverkar bara anpassade länkar, stängningslänkar och hämtningslänkar.

## Behåll URL-parametrar med taggar i Adobe Experience Platform

[!UICONTROL Keep URL Parameters] är en kryssruta under [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Configure] under Adobe Analytics.
4. Expandera [!UICONTROL Link Tracking] dragspelspanel, som visar [!UICONTROL Keep URL Parameters] kryssrutan.

Markera den här rutan om du vill inkludera frågesträngar i dimensioner för länkspårning.

## s.linkLeaveQueryString i AppMeasurement och anpassad kodredigerare

The `s.linkLeaveQueryString` är en boolesk variabel. Standardvärdet är `false`.

* Om variabeln är inställd på `true`, behålls frågesträngar i URL:er för länkspårning.
* Om variabeln är inställd på `false` eller inte har definierats, tas frågesträngar bort från URL:er för länkspårning.

```js
s.linkLeaveQueryString = true;
```

## Exempel

Var försiktig när du ställer in den här variabeln på true, eftersom den kan påverka länkspårningsfilter som [`linkInternalFilters`](linkinternalfilters.md), [`linkExternalFilters`](linkexternalfilters.md)och [`linkDownloadFiletypes`](linkdownloadfiletypes.md).

Titta på följande exempel som om det var på `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
