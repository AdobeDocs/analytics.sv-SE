---
title: trackingServerSecure
description: Domänen som används för att skicka data till Adobe via HTTPS.
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
source-git-commit: 7918b18e73618368543a996ca121b64b7afb33ab
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 0%

---

# trackingServerSecure

Variabeln `trackingServerSecure` avgör vilken domän AppMeasurement använder för att skicka data till Adobe via HTTPS. Om den här variabeln inte är korrekt definierad kan din implementering uppleva dataförlust.

Före [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/sv/docs/id-service/using/home) fastställde variabeln också var cookies från tredje part angavs. Adobe rekommenderar starkt att du använder ID-tjänsten i alla implementeringar där det är möjligt.

## Edge domain using the Web SDK extension

SDK använder [!UICONTROL Edge domain] för att hantera både spårningsservern och den säkra spårningsservern. Du kan ange det önskade [!UICONTROL Edge domain]-värdet när du konfigurerar Web SDK-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Välj önskad taggegenskap.
1. Gå till fliken [!UICONTROL Extensions] och välj sedan knappen **[!UICONTROL Configure]** under [!UICONTROL Adobe Experience Platform Web SDK].
1. Ange det önskade textfältet **[!UICONTROL Edge domain]**.

Mer information finns i [Konfigurera Adobe Experience Platform Web SDK-tillägget](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=sv-SE) i dokumentationen för Web SDK.

>[!TIP]
>
>Om din organisation går över till Web SDK från en AppMeasurement- eller Analytics-tilläggsimplementering kan det här fältet använda samma värde som finns i `trackingServerSecure` (eller `trackingServer`).

## Edge domain implementerar Web SDK manuellt

Konfigurera SDK med [`edgeDomain`](https://experienceleague.adobe.com/sv/docs/experience-platform/web-sdk/commands/configure/edgedomain). Fältet är en sträng som avgör vilken domän som data ska skickas till.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## SSL-spårningsserver som använder Adobe Analytics-tillägget

[!UICONTROL SSL Tracking Server] är ett fält under dragspelet [!UICONTROL General] när Adobe Analytics-tillägget konfigureras.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Välj önskad taggegenskap.
1. Gå till fliken [!UICONTROL Extensions] och välj sedan knappen **[!UICONTROL Configure]** under Adobe Analytics.
1. Expandera dragspelsfliken [!UICONTROL General] som visar fältet [!UICONTROL SSL Tracking Server].

Om fältet lämnas tomt blir standardvärdet i [!UICONTROL Tracking Server]. Om både [!UICONTROL SSL Tracking Server] och [!UICONTROL Tracking Server] är tomma blir standardvärdet `[rsid].data.adobedc.net`.

## s.trackingServerSecure i AppMeasurement och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.trackingServerSecure` är en sträng som innehåller den domän som data ska skickas till Adobe. Det är bara en domän, utelämna protokoll, sökväg, port och snedstreck. Om variabeln är tom används värdet i variabeln `s.trackingServer`. Om både `s.trackingServerSecure` och `s.trackingServer` är tomma blir standardvärdet `[rsid].2o7.net`.

```js
// Example value when participating in the Adobe-managed certificate program
s.trackingServerSecure = "data.example.com";

// Example value sending data directly to Adobe
s.trackingServerSecure = "example.data.adobedc.net";
```

## Överväganden som avgör värdet för `trackingServerSecure`

Värdet som du använder för `trackingServerSecure` (eller `edgeDomain`) beror på flera faktorer:

* Ditt deltagande i det [Adobe-hanterade certifikatprogrammet](https://experienceleague.adobe.com/sv/docs/core-services/interface/data-collection/adobe-managed-cert)
* Om du har [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/sv/docs/id-service/using/home) implementerad och konfigurerad korrekt

**Om din organisation deltar i det Adobe-hanterade certifikatprogrammet** anger du värdet till den förstapartsdomän som valdes när certifikatet konfigurerades. Vanligtvis är det här värdet en underdomän som ägs av din organisation. Exempel: `data.example.com`. CNAME-poster i organisationen omdirigerar dessa data till Adobe.

**Om du inte deltar i certifikatprogrammet** anger du värdet till en underdomän till `data.adobedc.net`. Adobe rekommenderar att du använder din organisations företags-ID för att få en konsekvent hantering. Exempel: `example.data.adobedc.net`. Följ de här stegen för att fastställa ditt företags-ID:

1. Logga in på [experience.adobe.com](https://experience.adobe.com) med dina Adobe ID-inloggningsuppgifter.
1. Tryck på `[Cmd]` + `[I]` (iOS) eller `[Ctrl]` + `[I]` (Windows) någonstans i Experience Cloud-gränssnittet.
1. En **[!UICONTROL User data debugger]** visas. Klicka på fliken **[!UICONTROL Assigned orgs]**.  
1. Utöka den önskade IMS-organisationen.
1. Leta reda på fältet **[!UICONTROL Tenant]**. Det här värdet är den rekommenderade underdomänen till `data.adobedc.net` att använda.

>[!NOTE]
>
>Använd inga underdomäner djupare än `example.data.adobedc.net`. `custom.example.data.adobedc.net` är till exempel inte en giltig spårningsserver.

Äldre implementeringar kan ha värden som `sc.omtrdc.net` eller `2o7.net`. Dessa användes huvudsakligen i tidigare versioner av Adobe Analytics och är fortfarande giltiga.

Adobe rekommenderar starkt att du upprätthåller denna information i ett [lösningsdesigndokument](../../prepare/solution-design.md) för att det ska vara konsekvent i hela organisationen.

## Justeringar för att inte använda tjänsten för besökar-ID

Adobe rekommenderar starkt att du använder [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/sv/docs/id-service/using/home) i alla implementeringar. ID-tjänsten kan implementeras på flera olika sätt:

* Manuella AppMeasurement-implementeringar använder `VisitorAPI.js` och anropar metoden `getInstance`. Mer information finns i [Implementera Experience Cloud identitetstjänst för analyser](https://experienceleague.adobe.com/sv/docs/id-service/using/implementation/setup-analytics).
* Implementeringar som använder Adobe Analytics-taggtillägget använder [Adobe Experience Cloud ID-tjänsttillägget](https://experienceleague.adobe.com/sv/docs/experience-platform/tags/extensions/client/id-service/overview). När du har lagt till någon konfiguration krävs ingen ytterligare konfiguration.
* För implementeringar som använder någon form av Web SDK (`alloy.js` eller Web SDK-taggtillägget) har ID-tjänsten redan incheckats internt. Ingen konfiguration krävs utöver inställningen av värdet `edgeDomain`.

**Om din implementering inte använder identitetstjänsten** bör du tänka på följande effekter för implementeringen:

* Om inte identitetstjänsten används, fastställer `trackingServerSecure` platsen för cookie. Om du anger den här variabeln som en tredjepartsdomän måste AppMeasurement använda en reservcookie, eftersom de flesta moderna webbläsare avvisar cookies från tredje part.
* Intern länkspårning och Activity Map kan vara mindre tillförlitligt.
