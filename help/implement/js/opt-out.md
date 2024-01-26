---
title: Avanmäl länkar
description: Lär dig hur du skapar en implementerad länk för avanmälan för besökare på din webbplats.
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 0%

---

# Implementera länkar för avanmälan

>[!IMPORTANT]
>
> **Den här hjälpsidan ger Adobe Analytics-kunder möjlighet att förse sina användare med avanmälningslänkar. Om du inte är kund hos Adobe Analytics kan du läsa [Sekretessalternativ för Adobe](https://www.adobe.com/privacy/opt-out.html) för att styra hur Adobe använder informationen.**

Vissa besökare på din webbplats föredrar att inte ha sin surfinformation med i din datauppsättning. Adobe erbjuder möjlighet att ge besökare på er webbplats möjlighet att avanmäla sig från den information de analyserar.

Avanmäl länkar är ett sätt som gör att besökare på webbplatsen kan utelämna sina data från Analytics-rapporter. Länkarna är begränsade till implementering av AppMeasurement. Adobe rekommenderar att du använder [Adobe Experience Cloud anmälningstjänst](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html) i stället. Opt-in-tjänsten är stabilare och fungerar på flera Adobe Experience Cloud-produkter, inklusive Adobe Analytics och AppMeasurement.

När en besökare når en avanmälnings-URL uppmanas de att installera en avanmälnings-cookie. Om en användare väljer att inte spåras och en avanmälningscookie är inställd fortsätter AppMeasurementet att skicka data till Adobe. Dessa data behandlas dock inte och inkluderas inte i rapporter.

>[!TIP]
>
>Adobe erbjuder även sekretessinställningar per rapport. Se [Sekretessinställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md) i användarhandboken för Admin.

## URL för avanmälan

Avanmälningssidan för din organisation beror på [`trackingServer`](../vars/config-vars/trackingserver.md) variabelvärde i implementeringen.

* I Analytics-tillägget:
   1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
   1. Klicka på den önskade taggegenskapen.
   1. Klicka på [!UICONTROL Extensions] tabbtangenten och klicka sedan på [!UICONTROL Configure] under Adobe Analytics.
   1. Klicka på [!UICONTROL General] och lägg märke till [!UICONTROL Tracking Server] värde.

* I en JavaScript-implementering:
   1. På webbservern öppnar du filen AppMeasurement.js som används på webbplatsen i en kod- eller textredigerare.
   1. Anteckna `trackingServer` variabelvärde.

* Använda [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html):
   1. Navigera till webbplatsen med webbläsaren Chrome.
   1. Öppna Experience Cloud Debugger och gå till [!UICONTROL Network tab].
   1. Anteckna [!UICONTROL Request URL - Hostname] värde.

När implementeringen är klar `trackingServer` domän, lägg till sökvägen `/optout.html` till slutet. Exempel:

* Cookies från tredje part: `https://example.data.adobedc.net/optout.html`
* cookies från första part: `https://stats.example.com/optout.html`

## Avanmäl frågesträngsparametrar

Det finns inställningar som du automatiskt kan läsa in på den här sidan med hjälp av frågesträngar.

### Språk

Byt språk automatiskt på avanmälningssidan genom att inkludera `locale` frågesträngparameter. Tilldela den här frågesträngsparametern ett av följande värden:

* `en_US` (Engelska, standard)
* `bg_BG` (bulgariska)
* `zh_CN` (Förenklad kinesiska)
* `zh_TW` (Traditionell kinesiska)
* `cs_CZ` (Tjeckiska)
* `da_NK` (Danska)
* `nl_NL` (Nederländska)
* `et_EE` (estniska)
* `fi_FI` (finska)
* `fr_FR` (franska)
* `de_DE` (Tyska)
* `el_GR` (Grekiska)
* `it_IT` (italienska)
* `jp_JP` (Japanska)
* `ko_KR` (koreanska)
* `lv_LV` (Lettiska)
* `lt_LT` (Litauiska)
* `nb_NO` (Norska)
* `pl_PL` (Polska)
* `pt_BR` (Portugisiska)
* `sk_SK` (Slovakiska)
* `es_ES` (Spanska)

Till exempel: `https://example.data.adobedc.net/optout.html?locale=ko_KR` läser in avanmälningssidan på koreanska.

### Popup

Lägger till knappen Stäng fönster på sidan, vilket gör att avanmälningssidan kan göras till ett popup-fönster. Använd `popup` frågesträngsparameter och ge den värdet `1`.

Till exempel: `https://example.data.adobedc.net/optout.html?popup=1` läser in avanmälningssidan med knappen Stäng fönster.

>[!NOTE]
>
>Historiskt sett har den här frågesträngsparametern tvingat fram ett popup-fönster. De flesta moderna webbläsare ger dock användaren kontroll över popup-fönster.

### Avanmäl dig med ett klick

Låter användaren omedelbart välja bort spårning. Lägg till två frågesträngsparametrar `opt_out` och `confirm_change`, vilket ger varje värde `1`.

Till exempel: `https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` installerar avanmälningscookien direkt på besökarens sida.

### Anmäl dig med ett klick

Tillåter användaren att omedelbart välja tillbaka till spårning genom att ta bort denna cookie. Lägg till två frågesträngsparametrar `opt_in` och `confirm_change`, vilket ger varje värde `1`.

Till exempel: `https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` tar omedelbart bort avanmälningscookien för besökaren.
