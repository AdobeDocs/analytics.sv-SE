---
title: trackInlineStats
description: Aktivera eller inaktivera aktivitetskartan i implementeringen.
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackInlineStats

Aktivitetskartan är en funktion i Adobe Analytics som samlar in data om var besökarna klickar och vad de klickar på. Du kan visa dessa data i Analytics-rapporter eller genom att använda en webbläsartilläggsövertäckning. Aktivera den här variabeln om du vill använda funktioner för aktivitetskarta.

När det här alternativet är aktiverat samlar AppMeasurement in information om länken och skickar dessa data i nästa bildförfrågan. Information från varje klick lagras i en cookie med etiketten `s_sq`.

## Aktivera klickkarta i Adobe Experience Platform Launch

[!UICONTROL Enable Clickmap] är en kryssruta under [!UICONTROL Link Tracking] dragspelet när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken så att [!UICONTROL Link Tracking] kryssrutan visas [!UICONTROL Enable Clickmap] .

Klicka i kryssrutan för att aktivera spårning av aktivitetskarta.

## s.trackInlineStats i AppMeasurement and Launch custom code editor

Detta `s.trackInlineStats` är ett booleskt värde som aktiverar eller inaktiverar spårning av aktivitetskarta. Dess standardvärde är `false`. Ange det här värdet `true` om du vill aktivera datainsamling för aktivitetskarta.

```js
s.trackInlineStats = true;
```
