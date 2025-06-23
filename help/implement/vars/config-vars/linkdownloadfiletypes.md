---
title: linkDownloadFileTypes
description: Fastställ filtillägg som automatiskt spåras som nedladdningslänkar.
feature: Appmeasurement Implementation
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---

# linkDownloadFileTypes

När [`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement) eller [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK) är aktiverat och en besökare klickar på en länk kontrollerar AppMeasurement länkens URL för att se om det finns filtypstillägg. Om länk-URL:en innehåller en matchande filtyp skickas en begäran om hämtning av länkbild automatiskt.

Använd `linkDownloadFileTypes` för att anpassa vilka filtillägg du vill räkna som hämtningslänkar.

>[!NOTE]
>
>Endast faktiska klick spåras automatiskt. Följande typer av länkar spåras inte automatiskt:
>
>* Filnedladdningar som startar automatiskt när en sida läses in
>* Hämtar utlösaren efter en omdirigering
>* Högerklicka och välj &#39;Spara mål som..&#39;
>* Länkar som använder JavaScript, till exempel `javascript:openLink()`
>
>För dessa hämtningstyper kan du skicka ett [`link tracking`](../functions/tl-method.md)-samtal manuellt.

Om en klickad länk matchar både villkoren för avslutningslänk och nedladdningslänk får nedladdningslänkstypen prioritet.

## Hämta länkkvalificerare med Web SDK-tillägget

Textfältet [!UICONTROL Download link qualifier] använder regex för att avgöra om en länk som klickats på är en nedladdningslänk.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under [!UICONTROL Adobe Experience Platform Web SDK].
1. Ange önskat värde i textfältet **[!UICONTROL Download link qualifier]** under [!UICONTROL Data Collection].

## Ladda ned länkkvalificerare som implementerar Web SDK manuellt

[Konfigurera](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=sv-SE) SDK med [`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=sv-SE#automaticLinkTracking). Fältet använder regex på den klickade URL:en för att avgöra om det är en giltig nedladdningslänk. Om `downloadLinkQualifier` inte definieras ställs standardvärdet in på `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`.

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## Hämta tillägg med Adobe Analytics-tillägget

Hämtningstillägg är en lista med filtillägg med ett fält som du kan lägga till mer i dragspelet [!UICONTROL Link Tracking] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
2. Klicka på den önskade taggegenskapen.
3. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
4. Expandera dragspelsfliken [!UICONTROL Link Tracking] som visar fältet **[!UICONTROL Download Extensions]**.

Lägg till filtillägg i listan genom att ange text i fältet och klicka på **[!UICONTROL Add]**. Ta bort filtillägg från listan genom att klicka på respektive **&#39;X&#39;** -ikon.

## s.linkDownloadFileTypes i AppMeasurement och den anpassade kodredigeraren i Analytics-tillägget

Variabeln `s.linkDownloadFileTypes` är en sträng med kommaavgränsade filtillägg. Använd inte blanksteg.

Om variabeln inte definieras fungerar inte automatisk länkspårning för hämtning (även om [`trackDownloadLinks`](trackdownloadlinks.md) är `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
