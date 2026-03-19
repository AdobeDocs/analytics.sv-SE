---
title: AMO EF-ID
description: Adobe Media Optimizer EF ID, som används i Adobe Advertising-integreringar.
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# AMO EF-ID

**[!UICONTROL AMO EF ID]** är en annonsklicksidentifierare som används i Adobe Advertising-integreringar. Det är en unik variabel som Adobe Advertising använder för att associera aktiviteter med en onlineklickning eller annonsexponering på besökarnivå. Dimensionen skapas automatiskt när [Analytics för Advertising](https://experienceleague.adobe.com/sv/docs/advertising/integrations/analytics/overview)-integreringen aktiveras.

## Fyll den här dimensionen med data

Den här dimensionen samlar in värden på flera sätt:

* För genomklickningstrafik samlas data in från frågesträngsparametern `ef_id` i [sid-URL](page-url.md), vanligtvis på den sida genom vilken reklamdriven trafik kommer in på webbplatsen.
* Genomklickningstrafik kan också hämtas när URL:en inte innehåller spårningskoder, men Adobe Advertising JavaScript upptäcker ett klick inom de föregående två minuterna.
* För genomskinlig trafik som stöds, kompletterar Adobe Advertising värdena på backend-objektet med ett extra ID (`SDID`).

>[!NOTE]
>
>EF ID:n är skiftlägeskänsliga. Om implementeringen tvingar URL-spårning till gemener, känner Adobe Advertising inte igen EF-ID:t.

## Dimension-objekt

Dimension-objekt innehåller annonsklickidentifierare som genererats av annonsnätverk som stöds. Strängformatet beror på nätverket och kanalen som genererade det.

### Google Ads - sökannonser

```text
{gclid}:G:{s}
```

* **`gclid`**: Google-klicknings-ID (GCLID).
* **`s`**: Nätverkstypen (`"s"` för sökning).

### Microsoft Advertising sökannonser

```text
{msclkid}:G:{s}
```

* **`msclkid`**: Microsoft-klicknings-ID (MSCLKID).
* **`s`**: Nätverkstypen (`"s"` för sökning).

### Visa annonser och sökannonser i andra sökmotorer

```text
{amovid}:{ts}:{channel}
```

* **`amovid`**: Besökar-ID:t för Adobe Advertising, även kallat surfer-ID.
* **`ts`**: Tidsstämpeln som genererats av Adobe Advertising.
* **`channel`**: Den kanaltyp som ansvarar för klickningen eller exponeringen:
   * **`d`**: Ett klick på en DSP-bildskärm (klickfrekvens).
   * **`i`**: Ett intryck på en DSP-displayannons (visningsgenomgång).
   * **`s`**: Ett klick på en sökannons (genomklickning av sökning).

### Exempel

```text
CjwKCAiAkbbMBhB2EiwANbxtbb9L573Dys0rjTDqcMo3x7tv2yEfh1RGb8exG9N892NoMqAzMBEGmhoCWxwQAvD_BwE:G:s
06207ca63ae6f4fa832197585547393c:20260301111101:i
WcmibgAAAHJK1RyY:1551968087687:d
```
