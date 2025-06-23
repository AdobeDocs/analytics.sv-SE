---
title: linkInternalFilters
description: Använd variabeln linkInternalFilters om du vill ha hjälp med automatisk spårning av avslutningslänk.
feature: Appmeasurement Implementation
exl-id: eaa6e64a-ebd5-4e6b-913f-1a6c315579c8
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 0%

---

# linkInternalFilters

Med AppMeasurement kan man automatiskt spåra länkar som pekar utanför er webbplats. Om [`trackExternalLinks`](trackexternallinks.md) (AppMeasurement) eller [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK) är aktiverat skickas en bildbegäran till Adobe direkt när en besökare klickar på en länk för att lämna din webbplats. Variablerna [`linkExternalFilters`](linkexternalfilters.md) och `linkInternalFilters` avgör vilka länkar som betraktas som interna/externa.

Om den här variabeln innehåller ett värde fungerar automatisk spårning av avslutningslänk som blockeringslista. Om ett länkklick inte matchar några `linkInternalFilters`-värden betraktas det som en avslutslänk. Hela URL:en granskas mot den här variabeln. Om [`linkLeaveQueryString`](linkleavequerystring.md) är aktiverat undersöks även frågesträngen.

Om du använder både `linkInternalFilters` och `linkExternalFilters` samtidigt måste den klickade länken matcha `linkExternalFilters` **och** inte matcha `linkInternalFilters` för att betraktas som en avslutslänk. Om en klickad länk matchar både villkoren för avslutningslänk och nedladdningslänk får nedladdningslänkstypen prioritet.

Aktivitetskartan använder den här variabeln för att avgöra vilka länkar som är interna för din plats. Adobe rekommenderar att du ställer in den här variabeln för implementeringar som använder aktivitetskarta.

>[!NOTE]
>
>`linkInternalFilters` och [ interna URL-filter ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) är separata funktioner som fyller olika syften. Variabeln `linkInternalFilters` fungerar specifikt för att avsluta länkspårning. Interna URL-filter är en administratörsinställning som hjälper dig med trafikkällans dimensioner, som Referensdomän.

## Avsluta länkar i SDK för webben

Länkar kvalificeras automatiskt som en avslutningslänk om länkmåldomänen skiljer sig från den aktuella `window.location.hostname`. SDK för webben innehåller inga konfigurationsvariabler som kan ändra automatisk avslutningslänksidentifiering. Om du behöver anpassa domänerna som kvalificerar som en avslutningslänk kan du använda anpassad logik i `onBeforeEventSend`-återanropet.

Mer information finns i [Automatisk länkspårning](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking) i dokumentationen för Web SDK.

## Utgående länkar - Spåra aldrig med Adobe Analytics-tillägget

Fältet Aldrig spårning är en kommaavgränsad lista med filter (vanligtvis domäner) under dragspelsfliken [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera dragspelsfliken [!UICONTROL Link Tracking] som visar fältet [!UICONTROL Outbound Links - Never Track].

Placera filter som du aldrig vill ska spåras som avslutningslänkar i det här fältet. Avgränsa flera domäner med kommatecken utan mellanslag.

## s.linkInternalFilters i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.linkInternalFilters` är en sträng som innehåller filter (till exempel domäner) som du anser vara interna för din plats. Separera flera filter med kommatecken utan mellanslag.

```js
s.linkInternalFilters = "example.com,example.net";
```

Titta på följande implementeringsexempel som om det vore på `adobe.com`:

```html
<script>
  s.trackExternalLinks = true;
  s.linkInternalFilters = "adobe.com";
</script>

<!-- The following link is an exit link because it does not match the anything under linkInternalFilters -->
<a href = "example.org">Example link 2</a>
```
