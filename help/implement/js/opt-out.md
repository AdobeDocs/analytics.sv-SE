---
title: Avanmäl länkar
description: Lär dig hur du skapar en implementerad länk för avanmälan för besökare på din webbplats.
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# Implementera länkar för avanmälan

> [!IMPORTANT] Adobe rekommenderar att man använder sig av anmälningstjänsten, särskilt för organisationer som berörs av GDPR-regler. Se Översikt över [anmälningstjänsten](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) i användarhandboken för Experience Cloud Identity Service.

Vissa besökare på din webbplats föredrar att inte ha sin surfinformation med i din datauppsättning. Adobe erbjuder besökare på er webbplats möjlighet att avanmäla sig från den information de samlar in. Alla implementeringstyper finns tillgängliga. din organisation ansvarar för din egen sekretesspolicy och för att den förblir i enlighet med dina signerade villkor.

När en besökare når en avanmälnings-URL uppmanas de att installera en avanmälnings-cookie. Om en användare väljer att inte spåras och en avanmälningscookie anges, fortsätter JavaScript-filen att skicka data till Adobe-servrar. Dessa data behandlas dock inte och inkluderas inte i rapporter.

> [!TIP] Adobe erbjuder också sekretessinställningar per rapport. Se [Sekretessinställningar](../../admin/admin/privacy-settings.md) i användarhandboken för Admin.

## URL för avanmälan

Avanmälningssidan för din organisation beror på det [`trackingServer`](../vars/config-vars/trackingserver.md) variabla värdet i implementeringen.

* I Adobe Experience Platform Launch:
   1. Logga in på [launch.adobe.com](https://launch.adobe.com) och klicka på önskad egenskap.
   2. Klicka på [!UICONTROL Extensions] fliken och sedan på [!UICONTROL Configure] under Adobe Analytics.
   3. Klicka på [!UICONTROL General] dragspelet och notera [!UICONTROL Tracking Server] värdet.

* I en JavaScript-implementering:
   1. På webbservern öppnar du filen AppMeasurement.js som används på webbplatsen i en kod- eller textredigerare.
   2. Observera `trackingServer` variabelvärdet.

* Använda [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html):
   1. Navigera till webbplatsen med webbläsaren Chrome.
   2. Öppna Experience Cloud Debugger och gå till [!UICONTROL Network tab].
   3. Notera [!UICONTROL Request URL - Hostname] värdet.

När du har hittat implementeringens `trackingServer` domän lägger du till sökvägen `/optout.html` till slutet. Exempel:

* Cookies från tredje part: `https://example.sc.omtrdc.net/optout.html`
* cookies från första part: `https://stats.example.com/optout.html`

## Avanmäl frågesträngsparametrar

Det finns inställningar som du automatiskt kan läsa in på den här sidan med hjälp av frågesträngar.

### Språk

Växla automatiskt språk för avanmälningssidan genom att ta med `locale` frågesträngsparametern. Tilldela den här frågesträngsparametern ett av följande värden:

* en_US (engelska, standard)
* bg_BG (bulgariska)
* zh_CN (förenklad kinesiska)
* zh_TW (traditionell kinesiska)
* cs_CZ (Czech)
* da_NK (danska)
* nl_NL (nederländska)
* et_EE (estniska)
* fi_FI (Finnish)
* fr_FR (franska)
* de_DE (German)
* el_GR (grekisk)
* it_IT (italienska)
* jp_JP (japanska)
* ko_KR (koreanska)
* lv_LV (lettiska)
* lt_LT (litauiska)
* nb_NO (Norwegian)
* pl_PL (polska)
* pt_BR (portugisiska)
* sk_SK (Slovakiska)
* es_ES (spanska)

Till exempel läses avanmälningssidan in på koreanska. `https://example.sc.omtrdc.net/optout.html?locale=ko_KR`

> [!TIP] Frågesträngsvärdet är inte obligatoriskt eftersom sidan läses in på engelska som standard. `en_US`

### Popup

Lägger till knappen Stäng fönster på sidan, vilket gör att avanmälningssidan kan göras till ett popup-fönster. Använd frågesträngsparametern och ge den värdet `popup` `1`.

Du kan till exempel `https://example.sc.omtrdc.net/optout.html?popup=1` läsa in avanmälningssidan med knappen Stäng fönster.

> [!NOTE] Historiskt sett har den här frågesträngsparametern tvingat fram ett popup-fönster. De flesta moderna webbläsare ger dock användaren kontroll över popup-fönster.

### Avanmälan med ett klick

Låter användaren omedelbart välja bort spårning. Lägg till de två frågesträngsparametrarna `opt_out` och `confirm_change`ge varje värde `1`.

Exempel: installerar `https://example.sc.omtrdc.net/optout.html?opt_out=1&confirm_change=1` omedelbart avanmälningscookien på besökarens sida.

### Anmäl dig med ett klick

Tillåter användaren att omedelbart välja tillbaka till spårning genom att ta bort denna cookie. Lägg till de två frågesträngsparametrarna `opt_in` och `confirm_change`ge varje värde `1`.

Till exempel tar `https://example.sc.omtrdc.net/optout.html?opt_in=1&confirm_change=1` omedelbart bort avanmälningscookien för besökaren.
