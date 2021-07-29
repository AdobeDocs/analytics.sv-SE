---
title: trackInlineStats
description: Aktivera eller inaktivera aktivitetskartan i implementeringen.
keywords: inaktivera aktivitetskarta
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 1%

---

# trackInlineStats

Aktivitetskartan är en funktion i Adobe Analytics som samlar in data om var besökarna klickar och vad de klickar på. Du kan visa dessa data i Analytics-rapporter eller genom att använda en webbläsartilläggsövertäckning. Aktivera den här variabeln om du vill använda funktioner för aktivitetskarta.

När det här alternativet är aktiverat samlar AppMeasurement in information om länken och skickar dessa data i nästa bildförfrågan. Information från varje klick lagras i en cookie med etiketten `s_sq`.

## Aktivera Clickmap med hjälp av taggar i Adobe Experience Platform

[!UICONTROL Enable Clickmap] är en kryssruta under  [!UICONTROL Link Tracking] dragspelet när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
4. Expandera dragspelet [!UICONTROL Link Tracking], som visar kryssrutan [!UICONTROL Enable Clickmap].

Klicka i kryssrutan för att aktivera spårning av aktivitetskarta.

## s.trackInlineStats i AppMeasurement och anpassad kodredigerare

`s.trackInlineStats` är ett booleskt värde som aktiverar eller inaktiverar spårning av aktivitetskarta. Dess standardvärde är `false`. Ange det här värdet till `true` om du vill aktivera datainsamling för aktivitetskarta.

```js
s.trackInlineStats = true;
```
