---
title: linkDownloadFileTypes
description: Fastställ filtillägg som automatiskt spåras som nedladdningslänkar.
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# linkDownloadFileTypes

När [`trackDownloadLinks`](trackdownloadlinks.md) är aktiverat och en besökare klickar på en länk, kontrollerar AppMeasurement länkens URL för att se om det finns filtypstillägg. Om länk-URL:en innehåller en filtyp som finns i `linkDownloadFileTypes` skickas en begäran om hämtning av länkbild automatiskt.

Använd `linkDownloadFileTypes` för att anpassa vilka filtillägg du vill räkna som hämtningslänkar.

>[!NOTE]
>
>Endast faktiska klick spåras automatiskt. Följande typer av länkar spåras inte automatiskt:
>
> * Filnedladdningar som startar automatiskt när en sida läses in
> * Hämtar utlösaren efter en omdirigering
> * Högerklicka och välj &#39;Spara mål som..&#39;
> * Länkar som använder JavaScript, till exempel `javascript:openLink()`

>
> 
För dessa hämtningstyper kan du anropa metoden [`tl()`](../functions/tl-method.md) manuellt.

Om en klickad länk matchar både villkoren för avslutningslänk och nedladdningslänk får nedladdningslänkstypen prioritet.

## Hämta tillägg med taggar i Adobe Experience Platform

Hämtningstillägg är en lista med filtillägg med ett fält som du kan lägga till mer i dragspelet [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
2. Klicka på önskad egenskap.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
4. Expandera dragspelet [!UICONTROL Link Tracking], som visar fältet [!UICONTROL Download Extensions].

Lägg till filtillägg i listan genom att ange text i fältet och klicka på [!UICONTROL Add]. Ta bort filtillägg från listan genom att klicka på respektive X-ikon.

## s.linkDownloadFileTypes i AppMeasurement och anpassad kodredigerare

Variabeln `s.linkDownloadFileTypes` är en sträng med kommaavgränsade filtillägg. Använd inte blanksteg.

Om variabeln inte är definierad fungerar inte automatisk länkspårning för hämtning (även om [`trackDownloadLinks`](trackdownloadlinks.md) är `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
