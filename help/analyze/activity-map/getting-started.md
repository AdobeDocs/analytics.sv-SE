---
title: Komma igång med Activity Map
description: Kom igång med Activity Map-övertäckningen och -dimensionerna.
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 0%

---

# Komma igång med Activity Map

Activity Map i Adobe Analytics består av fyra huvuddelar:

* **Rapportsvitens inställning**: Du måste aktivera Activity Map i rapportsvitens inställningar. När det här alternativet är aktiverat skapar rapportsviten flera reserverade variabler för Activity Map-dimensioner och mått.
* **Implementering**: Samla in Activity Map-data på din webbplats eller egenskap. Att anpassa hur data samlas in kan förbättra kvaliteten på och upplevelsen av rapporter.
* **Workspace-dimensioner och mått**: När implementeringen är korrekt konfigurerad kan du använda Activity Map-dimensioner och mått i Analysis Workspace.
* **Övertäckning**: Adobe har ett webbläsartillägg för att visa data från Activity Map i webbplatsens sammanhang.

## Aktivera rapportsvitsinställning

Rapporteringssviten måste ha Activity Map aktiverat innan du kan börja samla in data. Om implementeringen skickar data från Activity Map till en rapportserie utan Activity Map-rapportering aktiverad, inkluderas inte data från Activity Map i träffen.

**[!UICONTROL Admin]** > **[!UICONTROL Report suites]** > Välj rapportserie > **[!UICONTROL Edit settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map reporting]** > **[!UICONTROL Enable Activity Map Reports]**

Om du aktiverar Activity Map-rapporter skapas flera reserverade variabler för backend-funktionen. Mer information finns i [Activity Map Reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md) i Adobe Analytics administratörshandbok.

## Kodinstallation

Implementeringen måste vara korrekt konfigurerad för att skicka data från Activity Map till Adobe.

+++Web SDK-taggtillägg

Datainsamlingen i Activity Map kräver **[!UICONTROL Adobe Experience Platform Web SDK]**-tillägget v2.23 eller senare. Tilläggsversioner ned till v2.16 har begränsat stöd. Dessa tidigare tilläggsversioner skickar data från Activity Map i en annan händelse än resten av dina data. Den här extra händelsen ökar antalet träffar som du skickar till Adobe Analytics eller Adobe Experience Platform.

Konfigurationsinställningen **[!UICONTROL Click data collection]** hanterar Activity Map-datainsamling och är vanligtvis aktiverad som standard. Du kan kontrollera att det är aktiverat i tilläggets konfigurationsinställningar:

1. Logga in på [experience.adobe.com](https://experience.adobe.com)
1. Välj **[!UICONTROL Data Collection]** på snabbåtkomstmenyn eller produktväljaren högst upp till höger.
1. Välj **[!UICONTROL Tags]** i den vänstra navigeringsmenyn.
1. Markera den tagg du vill redigera.
1. Välj **[!UICONTROL Extensions]** i den vänstra navigeringsmenyn.
1. Välj **[!UICONTROL Adobe Experience Platform Web SDK]** i listan över installerade tillägg och välj sedan **[!UICONTROL Configure]** till höger.
1. Leta reda på avsnittet [!UICONTROL Data Collection] och se till att kryssrutan **[!UICONTROL Enable click data collection]** är aktiverad.
1. Välj **[!UICONTROL Save]**.
1. Om det behövs kan du bygga upp ändringarna i ett bibliotek och publicera ändringarna i produktionen.

Mer information finns i [Konfigurera Web SDK-taggtillägget](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection).

+++

+++Web SDK JavaScript-bibliotek (`alloy.js`)

Activity Map datainsamling kräver Web SDK JavaScript-biblioteket v2.20 eller senare. Biblioteksversioner ned till v2.15 har begränsat stöd. Dessa tidigare biblioteksversioner skickar data från Activity Map i en separat händelse från resten av dina data. Den här extra händelsen ökar antalet träffar som du skickar till Adobe Analytics eller Adobe Experience Platform.

Konfigurationsvariabeln [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) för Web SDK hanterar den automatiska samlingen av Activity Map-data. Den är aktiverad som standard om den inte uttryckligen är inaktiverad.

```js
alloy("configure", {
  "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
  "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg",
  "clickCollectionEnabled": true
});
```

+++

+++Adobe Analytics-taggtillägg

Konfigurationsinställningen **[!UICONTROL Use Activity Map]** hanterar Activity Map-datainsamling och är vanligtvis aktiverad som standard. Den är tillgänglig för alla taggtillägg v1.9.0 eller senare. Du kan kontrollera att det är aktiverat i tilläggets konfigurationsinställningar:

1. Logga in på [experience.adobe.com](https://experience.adobe.com)
1. Välj **[!UICONTROL Data Collection]** på snabbåtkomstmenyn eller produktväljaren högst upp till höger.
1. Välj **[!UICONTROL Tags]** i den vänstra navigeringsmenyn.
1. Markera den tagg du vill redigera.
1. Välj **[!UICONTROL Extensions]** i den vänstra navigeringsmenyn.
1. Välj **[!UICONTROL Adobe Analytics]** i listan över installerade tillägg och välj sedan **[!UICONTROL Configure]** till höger.
1. Kontrollera att kryssrutan **[!UICONTROL Use Activity Map]** är aktiverad.
1. Välj **[!UICONTROL Save]**.
1. Om det behövs kan du bygga upp ändringarna i ett bibliotek och publicera ändringarna i produktionen.

Mer information finns i översikten över [Adobe Analytics-tillägget](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview).

+++

+++Adobe Analytics JavaScript-bibliotek (`AppMeasurement.js`)

Modulen Activity Map hanterar datainsamling från Activity Map och ingår i alla AppMeasurementen v1.6 eller senare. Du kan kontrollera filen `AppMeasurement.js` och se till att den ingår.

1. Navigera till den [senaste utgåvan av Adobe Analytics-AppMeasurementet](https://github.com/adobe/appmeasurement/releases/latest) på GitHub.
1. Hämta biblioteksfilen för det komprimerade AppMeasurementet och öppna sedan `AppMeasurement.js` som finns i den.
1. Modulen Activity Map finns i den övre delen av filen. Kontrollera att den här modulen ingår i det AppMeasurement som används på platsen.

+++

## Tillgängliga dimensioner

När Activity Map är aktiverat för både rapportsviten och implementeringen kan du börja använda följande dimensioner i Analysis Workspace:

* [[!UICONTROL Activity Map Link]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Activity Map Region]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Activity Map Page]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL Activity Map Link By Region]](/help/components/dimensions/activity-map-link-by-region.md)

## Hämta och installera webbläsartillägget eller tillägget

Förutom de dimensioner som är tillgängliga i Analysis Workspace kan du även visa data från Activity Map som en övertäckning på din webbplats. Om du vill visa den här övertäckningen hämtar och installerar du webbläsartillägget eller tillägget Activity Map.

**[!UICONTROL Tools]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Download Activity Map]**

Den här länken tar dig till webbläsarens tillägg eller tilläggsplats där du kan installera det. När du har installerat tillägget eller tillägget visas det i webbläsarens övre högra hörn där du kan logga in och aktivera övertäckningen.
