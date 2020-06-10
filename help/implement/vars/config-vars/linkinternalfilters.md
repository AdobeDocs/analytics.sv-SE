---
title: linkInternalFilters
description: Använd variabeln linkInternalFilters om du vill ha hjälp med automatisk spårning av avslutningslänk.
translation-type: tm+mt
source-git-commit: f7c2a366b409995c1fe790db97de5c708882ab3d
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---


# linkInternalFilters

Med AppMeasurement kan du automatiskt spåra länkar som pekar utanför webbplatsen. Om [`trackExternalLinks`](trackexternallinks.md) är aktiverat skickas en bildförfrågan till Adobe direkt när en besökare klickar på en länk för att lämna din webbplats. Variablerna [`linkExternalFilters`](linkexternalfilters.md) och `linkInternalFilters` bestämmer vilka länkar som betraktas som interna/externa.

Om den här variabeln innehåller ett värde fungerar automatisk avslutningslänkspårning som en blocklist. Om ett länkklick inte matchar några `linkInternalFilters` värden betraktas det som en avslutslänk. Hela URL:en granskas mot den här variabeln. Om [`linkLeaveQueryString`](linkleavequerystring.md) är aktiverat undersöks även frågesträngen.

Om du använder både `linkInternalFilters` och `linkExternalFilters` samtidigt måste den klickade länken matcha `linkExternalFilters` och **inte matcha** `linkInternalFilters` för att betraktas som en avslutslänk. Om en klickad länk matchar både villkoren för avslutningslänk och nedladdningslänk får nedladdningslänkstypen prioritet.

>[!NOTE] `linkInternalFilters` och [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md) är separata funktioner som fyller olika syften. Variabeln fungerar specifikt för att spåra `linkInternalFilters` en avslutningslänk. Interna URL-filter är en administratörsinställning som hjälper dig med trafikkällans dimensioner, som Referensdomän.

## Utgående länkar - Spåra aldrig i Adobe Experience Platform Launch

Fältet Aldrig spårning är en kommaavgränsad lista med filter (vanligtvis domäner) under [!UICONTROL Link Tracking] dragspelet när Adobe Analytics-tillägget konfigureras.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken, som visar [!UICONTROL Link Tracking] [!UICONTROL Outbound Links - Never Track] fältet.

Placera filter som du aldrig vill ska spåras som avslutningslänkar i det här fältet. Avgränsa flera domäner med kommatecken utan mellanslag.

## s.linkInternalFilters i AppMeasurement and Launch custom code editor

Variabeln `s.linkInternalFilters` är en sträng som innehåller filter (till exempel domäner) som du anser vara interna för platsen. Separera flera filter med kommatecken utan mellanslag.

```js
s.linkInternalFilters = "example.com,example.net,example.org";
```

Tänk på följande implementeringsexempel som om det vore på `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.com">Example link 2</a>
```
