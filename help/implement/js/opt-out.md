---
title: Avanmäl länkar
description: Lär dig hur du skapar en implementerad länk för avanmälan för besökare på din webbplats.
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
hide: true
hidefromtoc: true
role: Developer
source-git-commit: 48f1974a0c379a4e619d9a04ae80e43cce9527c1
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 0%

---

# Implementera länkar för avanmälan

>[!IMPORTANT]
>
> I den här artikeln beskrivs hur **Adobe Analytics-kunder som (planerar att) implementera Adobe Analytics** på sin webbplats får instruktioner om hur de kan erbjuda webbplatsanvändare avanmälningslänkar. <p><p>
> Om du **besöker en webbplats som har implementerat Adobe Analytics** och du vill avanmäla dig **<span style="color:red">är den här artikeln INTE till dig</span>**. Se [Sekretessalternativ för Adobe](https://www.adobe.com/privacy/opt-out.html) för att kontrollera hur Adobe använder dina uppgifter.

Vissa besökare på din webbplats föredrar att inte ha sin surfinformation med i din datauppsättning. Adobe erbjuder möjlighet att ge besökare på er webbplats möjlighet att avanmäla sig från den information de analyserar.

Avanmäl länkar är ett sätt som gör att besökare på webbplatsen kan utelämna sina data från Analytics-rapporter. Länkarna är begränsade till AppMeasurementen implementeringar. Adobe rekommenderar att du använder [Adobe Experience Cloud-tjänsten ](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html) i stället. Opt-in-tjänsten är stabilare och fungerar på flera Adobe Experience Cloud-produkter, inklusive Adobe Analytics och AppMeasurement.

När en besökare når en avanmälnings-URL uppmanas de att installera en avanmälnings-cookie. Om en användare väljer att inte spåras och en avanmälningscookie är inställd fortsätter AppMeasurementet att skicka data till Adobe. Dessa data behandlas dock inte och inkluderas inte i rapporter.

>[!TIP]
>
>Adobe erbjuder även sekretessinställningar per rapport. Se [Sekretessinställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md) i användarhandboken för Admin.

## URL för avanmälan

Avanmälningssidan för din organisation beror på variabelvärdet [`trackingServer`](../vars/config-vars/trackingserver.md) i implementeringen.

* I Analytics-tillägget:
   1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
   1. Klicka på den önskade taggegenskapen.
   1. Klicka på fliken [!UICONTROL Extensions] och sedan på [!UICONTROL Configure] under Adobe Analytics.
   1. Klicka på dragspelet [!UICONTROL General] och notera värdet [!UICONTROL Tracking Server].

* I en JavaScript-implementering:
   1. På webbservern öppnar du filen AppMeasurement.js som används på webbplatsen i en kod- eller textredigerare.
   1. Observera variabelvärdet `trackingServer`.

* Använda [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html):
   1. Navigera till webbplatsen med Chrome webbläsare.
   1. Öppna Experience Cloud Debugger och gå till [!UICONTROL Network tab].
   1. Observera värdet [!UICONTROL Request URL - Hostname].

När du har hittat implementeringens `trackingServer`-domän lägger du till sökvägen `/optout.html` i slutet. Exempel:

* Cookies från tredje part: `https://example.data.adobedc.net/optout.html`
* cookies från första part: `https://stats.example.com/optout.html`

## Avanmäl frågesträngsparametrar

Det finns inställningar som du automatiskt kan läsa in på den här sidan med hjälp av frågesträngar.

### Språk

Växla automatiskt språk för avanmälningssidan genom att ta med frågesträngsparametern `locale`. Tilldela den här frågesträngsparametern ett av följande värden:

* `en_US` (engelska, standard)
* `bg_BG` (bulgariska)
* `zh_CN` (förenklad kinesiska)
* `zh_TW` (traditionell kinesiska)
* `cs_CZ` (tjeckiska)
* `da_NK` (danska)
* `nl_NL` (nederländska)
* `et_EE` (estniska)
* `fi_FI` (finska)
* `fr_FR` (franska)
* `de_DE` (tyska)
* `el_GR` (grekiska)
* `it_IT` (italienska)
* `jp_JP` (japanska)
* `ko_KR` (koreanska)
* `lv_LV` (lettiska)
* `lt_LT` (litauiska)
* `nb_NO` (norska)
* `pl_PL` (polska)
* `pt_BR` (portugisiska)
* `sk_SK` (slovakiska)
* `es_ES` (spanska)

`https://example.data.adobedc.net/optout.html?locale=ko_KR` läser till exempel in avanmälningssidan på koreanska.

### Popup

Lägger till knappen Stäng fönster på sidan, vilket gör att avanmälningssidan kan göras till ett popup-fönster. Använd frågesträngparametern `popup` och ge den värdet `1`.

`https://example.data.adobedc.net/optout.html?popup=1` läser till exempel in avanmälningssidan med knappen Stäng fönster.

>[!NOTE]
>
>Historiskt sett har den här frågesträngsparametern tvingat fram ett popup-fönster. De flesta moderna webbläsare ger dock användaren kontroll över popup-fönster.

### Avanmäl dig med ett klick

Låter användaren omedelbart välja bort spårning. Lägg till de två frågesträngsparametrarna `opt_out` och `confirm_change` och ge var och en värdet `1`.

Till exempel installerar `https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` omedelbart avanmälningscookien på besökarens sida.

### Anmäl dig med ett klick

Tillåter användaren att omedelbart välja tillbaka till spårning genom att ta bort denna cookie. Lägg till de två frågesträngsparametrarna `opt_in` och `confirm_change` och ge var och en värdet `1`.

`https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` tar till exempel omedelbart bort avanmälningscookien för besökaren.
