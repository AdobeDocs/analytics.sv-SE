---
title: AMO Meta Ads Click ID
description: Adobe Media Optimizer Meta Ads Click ID, som används i Adobe Advertising-integreringar.
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---

# AMO Meta Ads Click ID

**[!UICONTROL AMO Meta Ads Click ID]** är en annonsklicksidentifierare som används i Adobe Advertising-integreringar. Dimensionen skapas automatiskt när [Analytics för Advertising](https://experienceleague.adobe.com/sv/docs/advertising/integrations/analytics/overview)-integreringen aktiveras. Det är i första hand användbart som en obearbetad spårningsidentifierare i stället för som en läsbar rapportdimension.

## Fyll den här dimensionen med data

Den här dimensionen samlar in värden på flera sätt:

* För genomklickningstrafik samlas data in från frågesträngsparametern `fbclid` i [sid-URL](page-url.md), vanligtvis på den sida genom vilken reklamdriven trafik kommer in på webbplatsen.
* Genomklickningstrafik kan också hämtas när URL:en inte innehåller spårningskoder, men Adobe Advertising JavaScript upptäcker ett klick inom de föregående två minuterna.

## Dimension-objekt

Dimension-objekt innehåller annonsidentifierare som genererats av Meta (Facebook) annonsnätverk. Hur långa dessa streckade värden är kan variera, men är vanligtvis hundratals tecken långa. Exempel på (trunkerade) värden är:

```text
IwY2xjawP0bVtleHRuA2FlbQIxMAB[...]AVp_aem_l5TPw-muraFjBGOq8l1w0g
PAb21jcAQB1LNleHRuA2FlbQIxMQB[...]PoFocE1FH44g_aem_FNMJG5EydJ_59aBwKIf4uA
```
