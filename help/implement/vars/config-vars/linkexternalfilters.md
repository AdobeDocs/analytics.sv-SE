---
title: linkExternalFilters
description: Använd variabeln linkExternalFilters om du vill ha hjälp med automatisk spårning av avslutningslänk.
feature: Variables
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---

# linkExternalFilters

Med AppMeasurement kan du automatiskt spåra länkar som pekar utanför webbplatsen. If [`trackExternalLinks`](trackexternallinks.md) är aktiverat skickas en bildförfrågan till Adobe till höger när besökaren klickar på en länk för att lämna din webbplats. The `linkExternalFilters` och [`linkInternalFilters`](linkinternalfilters.md) variabler bestämmer vilka länkar som betraktas som interna/externa.

Om den här variabeln innehåller ett värde fungerar automatisk spårning av avslutningslänk som ett tillåtelselista. Om ett länkklick inte matchar några `linkExternalFilters` är det inte en avslutslänk. Hela URL:en granskas mot den här variabeln. If [`linkLeaveQueryString`](linkleavequerystring.md) är aktiverat undersöks även frågesträngen.

>[!TIP]
>
>Använd bara den här variabeln om du vet exakt vilka domäner du vill använda som avslutningslänkar. Många företag använder `linkInternalFilters` är tillräckligt för att avsluta länkspårning och inte använda `linkExternalFilters`.

Om du använder båda `linkInternalFilters` och `linkExternalFilters` samtidigt måste den klickade länken matcha `linkExternalFilters` **och** matchar inte `linkInternalFilters` som en avslutningslänk. Om en klickad länk matchar både villkoren för avslutningslänk och nedladdningslänk får nedladdningslänkstypen prioritet.

## Utgående länkar - Spåra med taggar i Adobe Experience Platform

Fältet Spåra är en kommaavgränsad lista med filter (vanligtvis domäner) under [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Användargränssnitt för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] klickar du på [!UICONTROL Configure] under Adobe Analytics.
4. Expandera [!UICONTROL Link Tracking] dragspelspanel, som visar [!UICONTROL Outbound Links - Track] fält.

Placera filter som du alltid vill ta hänsyn till externt i det här fältet. Avgränsa flera domäner med kommatecken utan mellanslag.

## s.linkExternalFilters i AppMeasurement och anpassad kodredigerare

The `s.linkExternalFilters` variabeln är en sträng som innehåller filter (t.ex. domäner) som du betraktar som avslutslänkar. Avgränsa flera domäner med kommatecken utan mellanslag.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Tänk på följande implementeringsexempel som om det var på `adobe.com`:

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
