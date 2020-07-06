---
title: linkExternalFilters
description: Använd variabeln linkExternalFilters om du vill ha hjälp med automatisk spårning av avslutningslänk.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---


# linkExternalFilters

Med AppMeasurement kan du automatiskt spåra länkar som pekar utanför webbplatsen. Om [`trackExternalLinks`](trackexternallinks.md) är aktiverat skickas en bildförfrågan till Adobe direkt när en besökare klickar på en länk för att lämna din webbplats. Variablerna `linkExternalFilters` och [`linkInternalFilters`](linkinternalfilters.md) bestämmer vilka länkar som betraktas som interna/externa.

Om den här variabeln innehåller ett värde fungerar automatisk spårning av avslutningslänk som ett tillåtelselista. Om ett länkklick inte matchar några `linkExternalFilters` värden betraktas det inte som en avslutslänk. Hela URL:en granskas mot den här variabeln. Om [`linkLeaveQueryString`](linkleavequerystring.md) är aktiverat undersöks även frågesträngen.

>[!TIP]
>
>Använd bara den här variabeln om du vet exakt vilka domäner du vill använda som avslutningslänkar. Många organisationer tycker att det `linkInternalFilters` räcker med att använda för att spåra avslut, och använder inte `linkExternalFilters`.

Om du använder både `linkInternalFilters` och `linkExternalFilters` samtidigt måste den klickade länken matcha `linkExternalFilters` och **inte matcha** `linkInternalFilters` för att betraktas som en avslutslänk. Om en klickad länk matchar både villkoren för avslutningslänk och nedladdningslänk får nedladdningslänkstypen prioritet.

## Utgående länkar - spår i Adobe Experience Platform Launch

Fältet Spåra är en kommaavgränsad lista med filter (vanligtvis domäner) under [!UICONTROL Link Tracking] dragspelet när Adobe Analytics-tillägget konfigureras.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken, som visar [!UICONTROL Link Tracking] [!UICONTROL Outbound Links - Track] fältet.

Placera filter som du alltid vill ta hänsyn till externt i det här fältet. Avgränsa flera domäner med kommatecken utan mellanslag.

## s.linkExternalFilters i AppMeasurement and Launch custom code editor

Variabeln `s.linkExternalFilters` är en sträng som innehåller filter (t.ex. domäner) som du betraktar som avslutslänkar. Avgränsa flera domäner med kommatecken utan mellanslag.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Tänk på följande implementeringsexempel som om det vore på `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkExternalFilters = "example.com,example.net";
</script>

<!-- The following link is NOT considered an exit link, even though the link is outside adobe.com -->
<a href = "example.org">Example link 1</a>

<!-- The following link is an exit link because it matches the linkExternalFilters allowlist -->
<a href = "example.com">Example link 2</a>
```
