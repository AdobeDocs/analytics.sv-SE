---
title: linkExternalFilters
description: Använd variabeln linkExternalFilters om du vill ha hjälp med automatisk spårning av avslutningslänk.
feature: Variables
exl-id: 7d4e8d96-17ee-4a04-9a57-37d2056ee9a7
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# linkExternalFilters

Med AppMeasurement kan du automatiskt spåra länkar som pekar utanför webbplatsen. Om [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) eller [`clickCollectionEnabled`](trackexternallinks.md) (Web SDK) är aktiverat skickas en bildbegäran till Adobe till höger när en besökare klickar på en länk för att lämna platsen. Variablerna `linkExternalFilters` och [`linkInternalFilters`](linkinternalfilters.md) avgör vilka länkar som betraktas som interna/externa.

Om den här variabeln innehåller ett värde fungerar automatisk spårning av avslutningslänk som tillåtelselista. Om ett länkklick inte matchar några `linkExternalFilters`-värden betraktas det inte som en avslutslänk. Hela URL:en granskas mot den här variabeln. Om [`linkLeaveQueryString`](linkleavequerystring.md) är aktiverat undersöks även frågesträngen.

>[!TIP]
>
>Använd bara den här variabeln om du vet exakt vilka domäner du vill använda som avslutningslänkar. Många organisationer anser att det räcker att använda `linkInternalFilters` för att slutföra länkspårningen, och använder inte `linkExternalFilters`.

Om du använder både `linkInternalFilters` och `linkExternalFilters` samtidigt måste den klickade länken matcha `linkExternalFilters` **och** inte matcha `linkInternalFilters` för att betraktas som en avslutslänk. Om en klickad länk matchar både villkoren för avslutningslänk och nedladdningslänk får nedladdningslänkstypen prioritet.

## Avsluta länkar i Web SDK

Länkar kvalificeras automatiskt som en avslutningslänk om länkmåldomänen skiljer sig från den aktuella `window.location.hostname`. Web SDK innehåller inga konfigurationsvariabler som kan ändra automatisk avslutningslänksidentifiering. Om du behöver anpassa domänerna som kvalificerar som en avslutningslänk kan du använda anpassad logik i `onBeforeEventSend`-återanropet.

Mer information finns i [Automatisk länkspårning](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking) i Web SDK-dokumentationen.

## Utgående länkar - Spåra med Adobe Analytics-tillägget

Fältet Spåra är en kommaavgränsad lista med filter (vanligtvis domäner) under dragspelet [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera dragspelsfliken [!UICONTROL Link Tracking] som visar fältet [!UICONTROL Outbound Links - Track].

Placera filter som du alltid vill ska vara externa i det här fältet. Avgränsa flera domäner med kommatecken utan mellanslag.

## s.linkExternalFilters i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.linkExternalFilters` är en sträng som innehåller filter (t.ex. domäner) som du betraktar som avslutslänkar. Avgränsa flera domäner med kommatecken utan mellanslag.

```js
s.linkExternalFilters = "example.com,example.net,example.org";
```

Titta på följande implementeringsexempel som om det vore på `adobe.com`:

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
