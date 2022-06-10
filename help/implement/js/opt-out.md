---
title: Avanmäl länkar
description: Lär dig hur du skapar en implementerad länk för avanmälan för besökare på din webbplats.
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 0%

---

# Implementera länkar för avanmälan

>[!IMPORTANT]
>
>Adobe rekommenderar att man använder sig av anmälningstjänsten, särskilt för organisationer som berörs av GDPR-reglerna. Se [Översikt över anmälningstjänsten](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html) i användarhandboken för Experience Cloud Identity Service.

Vissa besökare på din webbplats föredrar att inte ha sin surfinformation med i din datauppsättning. Adobe erbjuder möjlighet att ge besökare på er webbplats möjlighet att avanmäla sig från den information de samlar in. Alla implementeringstyper finns tillgängliga. din organisation ansvarar för din egen sekretesspolicy och för att den förblir i enlighet med dina signerade villkor.

När en besökare når en avanmälnings-URL uppmanas de att installera en avanmälnings-cookie. Om en användare väljer att inte spåras och en avanmälningscookie ställs in, fortsätter JavaScript-filen att skicka data till Adobe-servrar. Dessa data behandlas dock inte och inkluderas inte i rapporter.

>[!TIP]
>
>Adobe erbjuder även sekretessinställningar per rapport. Se [Sekretessinställningar](../../admin/admin/privacy-settings.md) i användarhandboken för Admin.

## URL för avanmälan

Avanmälningssidan för din organisation beror på [`trackingServer`](../vars/config-vars/trackingserver.md) variabelvärde i implementeringen.

* I Analytics-tillägget:
   1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt AdobeID.
   1. Klicka på den önskade taggegenskapen.
   1. Klicka på [!UICONTROL Extensions] tabbtangenten och sedan klicka [!UICONTROL Configure] under Adobe Analytics.
   1. Klicka på [!UICONTROL General] dragspelspanelen och lägg märke till [!UICONTROL Tracking Server] värde.

* I en JavaScript-implementering:
   1. På webbservern öppnar du filen AppMeasurement.js som används på webbplatsen i en kod- eller textredigerare.
   1. Anteckna `trackingServer` variabelvärde.

* Använda [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html):
   1. Navigera till webbplatsen med webbläsaren Chrome.
   1. Öppna Experience Cloud Debugger och gå till [!UICONTROL Network tab].
   1. Anteckna [!UICONTROL Request URL - Hostname] värde.

När implementeringen är klar `trackingServer` domän, lägg till sökvägen `/optout.html` till slutet. Exempel:

* Cookies från tredje part: `https://example.data.adobedc.net/optout.html`
* cookies från första part: `https://stats.example.com/optout.html`

## Avanmäl frågesträngsparametrar

Det finns inställningar som du automatiskt kan läsa in på den här sidan med hjälp av frågesträngar.

### Språk

Byt språk automatiskt på avanmälningssidan genom att inkludera `locale` frågesträngsparameter. Tilldela den här frågesträngsparametern ett av följande värden:

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

Till exempel: `https://example.data.adobedc.net/optout.html?locale=ko_KR` läser in avanmälningssidan på koreanska.

>[!TIP]
>
>The `en_US` frågesträngsvärdet är inte obligatoriskt eftersom sidan läses in på engelska som standard.

### Popup

Lägger till knappen Stäng fönster på sidan, vilket gör att avanmälningssidan kan göras till ett popup-fönster. Använd `popup` frågesträngsparameter och ge den värdet `1`.

Till exempel: `https://example.data.adobedc.net/optout.html?popup=1` läser in avanmälningssidan med knappen Stäng fönster.

>[!NOTE]
>
>Historiskt sett har den här frågesträngsparametern tvingat fram ett popup-fönster. De flesta moderna webbläsare ger dock användaren kontroll över popup-fönster.

### Avanmälan med ett klick

Låter användaren omedelbart välja bort spårning. Lägg till två frågesträngsparametrar `opt_out` och `confirm_change`, vilket ger var och en värdet av `1`.

Till exempel: `https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` installerar avanmälningscookien direkt på besökarens sida.

### Anmäl dig med ett klick

Tillåter användaren att omedelbart välja tillbaka till spårning genom att ta bort denna cookie. Lägg till två frågesträngsparametrar `opt_in` och `confirm_change`, vilket ger var och en värdet av `1`.

Till exempel: `https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` tar omedelbart bort avanmälningscookien för besökaren.
