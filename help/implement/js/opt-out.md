---
title: Avanmäl länkar
description: Lär dig hur du skapar en implementerad länk för avanmälan för besökare på din webbplats.
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '583'
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

Avanmälningssidan för din organisation beror på variabelvärdet [`trackingServer`](../vars/config-vars/trackingserver.md) i implementeringen.

* I användargränssnittet för datainsamling:
   1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
   1. Klicka på önskad egenskap.
   1. Klicka på fliken [!UICONTROL Extensions] och sedan på [!UICONTROL Configure] under Adobe Analytics.
   1. Klicka på dragspelet [!UICONTROL General] och notera [!UICONTROL Tracking Server]-värdet.

* I en JavaScript-implementering:
   1. På webbservern öppnar du filen AppMeasurement.js som används på webbplatsen i en kod- eller textredigerare.
   1. Observera variabelvärdet `trackingServer`.

* Använda [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html):
   1. Navigera till webbplatsen med webbläsaren Chrome.
   1. Öppna Experience Cloud Debugger och gå till [!UICONTROL Network tab].
   1. Observera [!UICONTROL Request URL - Hostname]-värdet.

När du har hittat implementeringens `trackingServer`-domän lägger du till sökvägen `/optout.html` i slutet. Exempel:

* Cookies från tredje part: `https://example.data.adobedc.net/optout.html`
* cookies från första part: `https://stats.example.com/optout.html`

## Avanmäl frågesträngsparametrar

Det finns inställningar som du automatiskt kan läsa in på den här sidan med hjälp av frågesträngar.

### Språk

Växla språk för avanmälningssidan automatiskt genom att ta med frågesträngsparametern `locale`. Tilldela den här frågesträngsparametern ett av följande värden:

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

`https://example.data.adobedc.net/optout.html?locale=ko_KR` läser till exempel in avanmälningssidan på koreanska.

>[!TIP]
>
>Frågesträngsvärdet `en_US` är inte obligatoriskt eftersom sidan läses in på engelska som standard.

### Popup

Lägger till knappen Stäng fönster på sidan, vilket gör att avanmälningssidan kan göras till ett popup-fönster. Använd frågesträngsparametern `popup` och ge den värdet `1`.

`https://example.data.adobedc.net/optout.html?popup=1` läser till exempel in avanmälningssidan med knappen Stäng fönster.

>[!NOTE]
>
>Historiskt sett har den här frågesträngsparametern tvingat fram ett popup-fönster. De flesta moderna webbläsare ger dock användaren kontroll över popup-fönster.

### Avanmälan med ett klick

Låter användaren omedelbart välja bort spårning. Lägg till de två frågesträngsparametrarna `opt_out` och `confirm_change` och ge varje värde `1`.

`https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` installerar till exempel omedelbart avanmälningscookien på besökarens sida.

### Anmäl dig med ett klick

Tillåter användaren att omedelbart välja tillbaka till spårning genom att ta bort denna cookie. Lägg till de två frågesträngsparametrarna `opt_in` och `confirm_change` och ge varje värde `1`.

`https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` tar till exempel omedelbart bort den avanmälande cookien för besökaren.
