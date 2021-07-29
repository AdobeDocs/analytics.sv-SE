---
title: linkExternalFilters
description: Använd variabeln linkExternalFilters om du vill ha hjälp med automatisk spårning av avslutningslänk.
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---

# linkExternalFilters

Med AppMeasurement kan du automatiskt spåra länkar som pekar utanför webbplatsen. Om [`trackExternalLinks`](trackexternallinks.md) är aktiverat skickas en bildbegäran till Adobe till höger när en besökare klickar på en länk för att lämna platsen. Variablerna `linkExternalFilters` och [`linkInternalFilters`](linkinternalfilters.md) bestämmer vilka länkar som betraktas som interna/externa.

Om den här variabeln innehåller ett värde fungerar automatisk spårning av avslutningslänk som ett tillåtelselista. Om ett länkklick inte matchar några `linkExternalFilters`-värden betraktas det inte som en avslutslänk. Hela URL:en granskas mot den här variabeln. Om [`linkLeaveQueryString`](linkleavequerystring.md) är aktiverat undersöks även frågesträngen.

>[!TIP]
>
>Använd bara den här variabeln om du vet exakt vilka domäner du vill använda som avslutningslänkar. Många organisationer tycker att `linkInternalFilters` är tillräckligt för att slutföra länkspårningen och använder inte `linkExternalFilters`.

Om du använder både `linkInternalFilters` och `linkExternalFilters` samtidigt måste den klickade länken matcha `linkExternalFilters` **och** inte matchar `linkInternalFilters` för att betraktas som en avslutslänk. Om en klickad länk matchar både villkoren för avslutningslänk och nedladdningslänk får nedladdningslänkstypen prioritet.

## Utgående länkar - Spåra med taggar i Adobe Experience Platform

Fältet Spåra är en kommaavgränsad lista med filter (vanligtvis domäner) under dragspelet [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
4. Expandera dragspelet [!UICONTROL Link Tracking], som visar fältet [!UICONTROL Outbound Links - Track].

Placera filter som du alltid vill ta hänsyn till externt i det här fältet. Avgränsa flera domäner med kommatecken utan mellanslag.

## s.linkExternalFilters i AppMeasurement och anpassad kodredigerare

Variabeln `s.linkExternalFilters` är en sträng som innehåller filter (t.ex. domäner) som du betraktar som avslutslänkar. Avgränsa flera domäner med kommatecken utan mellanslag.

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
