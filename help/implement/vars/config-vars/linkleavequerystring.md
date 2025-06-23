---
title: linkLeaveQueryString
description: Tillåter lagring av frågesträngar i länkspårningsdimensioner.
feature: Appmeasurement Implementation
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 0%

---

# linkLeaveQueryString

AppMeasurement raderar frågesträngar från URL:er för länkspårning som standard. Använd variabeln `linkLeaveQueryString` för att bevara frågesträngar i länkspårningsdimensioner.

För vissa avslutslänkar och hämtningslänkar kan den viktiga delen av URL-adressen finnas i frågesträngen. En nedladdningslänk som `https://example.com/download.asp?filename=myfile.exe` innehåller till exempel viktig länkinformation i frågesträngen.

Om länkspårningsinformation inte finns i URL:er på din webbplats är det inte nödvändigt att använda den här variabeln. Genom att radera frågesträngar från URL:er för länkspårning kan du begränsa antalet unika värden som dimensionen innehåller.

Aktivering av `linkLeaveQueryString` gäller för alla dimensioner av länkspårning (inklusive anpassade länkar, slutlänkar och hämtningslänkar).

>[!TIP]
>
>Den här variabeln påverkar inte dimensioner utanför länkspårning. Det påverkar bara anpassade länkar, stängningslänkar och hämtningslänkar.

## Hantera länkfrågesträngar med Web SDK

Frågesträngar tas inte bort från XDM-fältet `web.webInteraction.URL`. Om du vill ta bort frågesträngar från det här XDM-fältet kan du redigera det med `onBeforeEventSend`.

## Behåll URL-parametrar med Adobe Analytics-tillägget

[!UICONTROL Keep URL Parameters] är en kryssruta under dragspelet [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera dragspelsfliken [!UICONTROL Link Tracking], som visar kryssrutan [!UICONTROL Keep URL Parameters].

Markera den här rutan om du vill inkludera frågesträngar i dimensioner för länkspårning.

## s.linkLeaveQueryString i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.linkLeaveQueryString` är boolesk. Dess standardvärde är `false`.

* Om variabeln är inställd på `true` bevaras frågesträngar i URL:er för länkspårning.
* Om variabeln är inställd på `false` eller inte definierad tas frågesträngar bort från URL:er för länkspårning.

```js
s.linkLeaveQueryString = true;
```

## Exempel

Var försiktig när du ställer in den här variabeln på true, eftersom den kan påverka länkspårningsfilter som [`linkInternalFilters`](linkinternalfilters.md), [`linkExternalFilters`](linkexternalfilters.md) och [`linkDownloadFiletypes`](linkdownloadfiletypes.md).

Titta på följande exempel som om det vore på `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
