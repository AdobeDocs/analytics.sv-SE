---
title: linkDownloadFileTypes
description: Fastställ filtillägg som automatiskt spåras som nedladdningslänkar.
feature: Variables
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---

# linkDownloadFileTypes

När [`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement) eller [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK) är aktiverat och en besökare klickar på en länk. AppMeasurementet kontrollerar länkens URL för att se om det finns filtypstillägg. Om länk-URL:en innehåller en matchande filtyp skickas en begäran om hämtning av länkbild automatiskt.

Använd `linkDownloadFileTypes` om du vill anpassa vilka filtillägg du vill räkna som hämtningslänkar.

>[!NOTE]
>
>Endast faktiska klick spåras automatiskt. Följande typer av länkar spåras inte automatiskt:
>
>* Filnedladdningar som startar automatiskt när en sida läses in
>* Hämtar utlösaren efter en omdirigering
>* Högerklicka och välj &#39;Spara mål som..&#39;
>* Länkar som använder JavaScript, till exempel `javascript:openLink()`
>
>För dessa hämtningstyper kan du skicka en [`link tracking`](../functions/tl-method.md) ring.

Om en klickad länk matchar både villkoren för avslutningslänk och nedladdningslänk får nedladdningslänkstypen prioritet.

## Hämta länkkvalificerare med Web SDK-tillägget

The [!UICONTROL Download link qualifier] I textfältet används regex för att avgöra om en länk som klickats kan anses vara en nedladdningslänk.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** knapp under [!UICONTROL Adobe Experience Platform Web SDK].
1. Under [!UICONTROL Data Collection]anger du det önskade värdet i dialogrutan **[!UICONTROL Download link qualifier]** textfält.

## Hämta länkkvalificerare som implementerar Web SDK manuellt

[Konfigurera](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) SDK med [`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking). Fältet använder regex på den klickade URL:en för att avgöra om det är en giltig nedladdningslänk. If `downloadLinkQualifier` är inte definierad, standardvärdet är inställt på `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`.

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## Hämta tillägg med Adobe Analytics-tillägget

Hämtningstillägg är en lista med filtillägg med ett fält där du kan lägga till mer i listan [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till [!UICONTROL Extensions] klickar du på **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera [!UICONTROL Link Tracking] dragspelspanel, som visar **[!UICONTROL Download Extensions]** fält.

Lägg till filtillägg i listan genom att skriva text i fältet och klicka på **[!UICONTROL Add]**. Ta bort filtillägg från listan genom att klicka på deras respektive **&#39;X&#39;** -ikon.

## s.linkDownloadFileTypes i AppMeasurementet och den anpassade kodredigeraren i Analytics-tillägget

The `s.linkDownloadFileTypes` variabeln är en sträng med kommaavgränsade filtillägg. Använd inte blanksteg.

Om variabeln inte är definierad fungerar inte automatisk länkspårning för hämtning (även om [`trackDownloadLinks`](trackdownloadlinks.md) är `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
