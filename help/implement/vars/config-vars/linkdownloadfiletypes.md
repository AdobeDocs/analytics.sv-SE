---
title: linkDownloadFileTypes
description: Fastställ filtillägg som automatiskt spåras som nedladdningslänkar.
translation-type: tm+mt
source-git-commit: 8f7baa770f800ffe800e760f1eca59911d3db348

---


# linkDownloadFileTypes

När `trackDownloadLinks` är inställt på `true` och en besökare klickar på en länk, kontrollerar AppMeasurement länkens URL för att se om det finns filtypstillägg. Om länk-URL:en innehåller en filtyp som hittades i `linkDownloadFileTypes`skickas en begäran om hämtning av länkbild automatiskt.

Anpassa `linkDownloadFileTypes` vilka filtillägg du vill räkna som nedladdningslänkar.

> [!NOTE] Endast faktiska klick spåras automatiskt. Följande typer av länkar spåras inte automatiskt:
>
> * Filnedladdningar som startar automatiskt när en sida läses in
> * Hämtar utlösaren efter en omdirigering
> * Högerklicka och välj &#39;Spara mål som..&#39;
> * Länkar som använder JavaScript, till exempel `javascript:openLink()`
>
> 
För dessa hämtningstyper kan du anropa `tl()` funktionen manuellt.

Om en klickad länk matchar både villkoren för avslutningslänk och nedladdningslänk får nedladdningslänkstypen prioritet.

## Ladda ned tillägg i Adobe Experience Platform Launch

Hämtningstillägg är en lista med filtillägg med ett fält som lägger till mer i dragspelet när du konfigurerar Adobe Analytics-tillägget [!UICONTROL Link Tracking] .

1. Logga in på [launch.adobe.com](https://launch.adobe.com) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på önskad egenskap.
3. Gå till [!UICONTROL Extensions] fliken och klicka sedan på [!UICONTROL Configure] knappen under Adobe Analytics.
4. Expandera dragspelsfliken, som visar [!UICONTROL Link Tracking] [!UICONTROL Download Extensions] fältet.

Lägg till filtillägg i listan genom att skriva text i fältet och klicka på [!UICONTROL Add]. Ta bort filtillägg från listan genom att klicka på respektive X-ikon.

## s.linkDownloadFileTypes i AppMeasurement and Launch custom code editor

Variabeln `s.linkDownloadFileTypes` är en sträng med kommaavgränsade filtillägg. Använd inte blanksteg.

Om den här variabeln inte är definierad fungerar inte automatisk länkspårning för hämtning (även om den `trackDownloadLinks` är `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v"
```
