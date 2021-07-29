---
title: linkInternalFilters
description: Använd variabeln linkInternalFilters om du vill ha hjälp med automatisk spårning av avslutningslänk.
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---

# linkInternalFilters

Med AppMeasurement kan du automatiskt spåra länkar som pekar utanför webbplatsen. Om [`trackExternalLinks`](trackexternallinks.md) är aktiverat skickas en bildbegäran till Adobe till höger när en besökare klickar på en länk för att lämna platsen. Variablerna [`linkExternalFilters`](linkexternalfilters.md) och `linkInternalFilters` bestämmer vilka länkar som betraktas som interna/externa.

Om den här variabeln innehåller ett värde fungerar automatisk spårning av avslutningslänk som en blockeringslista. Om ett länkklick inte matchar några `linkInternalFilters`-värden betraktas det som en avslutslänk. Hela URL:en granskas mot den här variabeln. Om [`linkLeaveQueryString`](linkleavequerystring.md) är aktiverat undersöks även frågesträngen.

Om du använder både `linkInternalFilters` och `linkExternalFilters` samtidigt måste den klickade länken matcha `linkExternalFilters` **och** inte matchar `linkInternalFilters` för att betraktas som en avslutslänk. Om en klickad länk matchar både villkoren för avslutningslänk och nedladdningslänk får nedladdningslänkstypen prioritet.

Aktivitetskartan använder den här variabeln för att avgöra vilka länkar som är interna för din plats. Adobe rekommenderar att du ställer in den här variabeln för implementeringar som använder aktivitetskarta.

>[!NOTE]
>
>`linkInternalFilters` och  [interna URL-](/help/admin/admin/internal-url-filter-admin.md) filter är separata funktioner som fyller olika syften. Variabeln `linkInternalFilters` fungerar specifikt för att avsluta länkspårning. Interna URL-filter är en administratörsinställning som hjälper dig med trafikkällans dimensioner, som Referensdomän.

## Utgående länkar - Spåra aldrig med taggar i Adobe Experience Platform

Fältet Aldrig spårning är en kommaavgränsad lista med filter (vanligtvis domäner) under dragspelet [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
4. Expandera dragspelet [!UICONTROL Link Tracking], som visar fältet [!UICONTROL Outbound Links - Never Track].

Placera filter som du aldrig vill ska spåras som avslutningslänkar i det här fältet. Avgränsa flera domäner med kommatecken utan mellanslag.

## s.linkInternalFilters i AppMeasurement och anpassad kodredigerare

Variabeln `s.linkInternalFilters` är en sträng som innehåller filter (till exempel domäner) som du anser vara interna för platsen. Separera flera filter med kommatecken utan mellanslag.

```js
s.linkInternalFilters = "example.com,example.net";
```

Tänk på följande implementeringsexempel som om det var på `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.org">Example link 2</a>
```
