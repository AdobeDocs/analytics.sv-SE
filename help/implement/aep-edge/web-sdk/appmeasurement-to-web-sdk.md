---
title: Migrera från AppMeasurement till Web SDK
description: Uppdatera din Adobe Analytics-implementering från AppMeasurementets JavaScript-bibliotek till Web SDK JavaScript-biblioteket.
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '1323'
ht-degree: 0%

---

# Migrera från AppMeasurement till Web SDK

Den här implementeringsvägen innefattar en metodisk migreringsmetod för att gå från implementering av AppMeasurement till en Web SDK JavaScript-biblioteksimplementering. Andra implementeringsvägar beskrivs på separata sidor:

* [Analystillägg till Web SDK-tillägg](analytics-extension-to-web-sdk.md): Ta ett smidigt och metodiskt tillvägagångssätt för att gå från taggtillägget Adobe Analytics till taggtillägget Web SDK. På så sätt slipper du använda XDM tills din organisation är redo att använda Adobe Experience Platform-tjänster, till exempel Customer Journey Analytics. Använd `data` i stället för `xdm` objekt som data ska skickas till Adobe.
* [Web SDK JavaScript-bibliotek](web-sdk-javascript-library.md): En ny Web SDK-installation med JavaScript-biblioteket för Web SDK (`alloy.js`). Hantera implementeringen själv i stället för att använda tagggränssnittet. Det kräver fältgruppen Adobe Analytics ExperienceEvent, som innehåller typiska analysvariabler som ska inkluderas i XDM-schemat.
* [SDK-taggtillägg för webben](web-sdk-tag-extension.md): En ny Web SDK-installation där du hanterar implementeringen med hjälp av taggar i Adobe Experience Platform Data Collection. Det kräver fältgruppen Adobe Analytics ExperienceEvent, som innehåller typiska analysvariabler som ska inkluderas i XDM-schemat.

## Fördelar och nackdelar med implementeringsvägen

Att använda den här migreringsmetoden har både fördelar och nackdelar. Väg noga in varje alternativ för att avgöra vilken metod som är bäst för er organisation.

| Fördelar | Nackdelar |
| --- | --- |
| <ul><li>**Använder din befintliga implementering**: Även om det här tillvägagångssättet kräver vissa implementeringsändringar behöver det inte finnas en helt ny implementering från början. Du kan använda ditt befintliga datalager och kod med minimala ändringar av implementeringslogiken.</li><li>**Kräver inget schema**: För den här migreringsfasen till Web SDK behöver du inget XDM-schema. I stället kan du fylla i `data` som skickar data direkt till Adobe Analytics. När migreringen till Web SDK är klar kan du skapa ett schema för din organisation och använda datastream-mappning för att fylla i tillämpliga XDM-fält. Om det krävs ett schema i det här skedet av migreringsprocessen måste din organisation använda ett Adobe Analytics XDM-schema. Om du använder det här schemat blir det svårare för din organisation att använda ditt eget schema i framtiden.</li></ul> | <ul><li>**Implementeringsändringar kräver åtgärd från utvecklaren**: Om du vill göra ändringar i Web SDK-implementeringen måste du samarbeta med ditt utvecklingsteam för att redigera koden på din webbplats. Den metod som [migrerar till taggtillägget Web SDK](analytics-extension-to-web-sdk.md) undviker denna nackdel.</li><li>**Implementering av teknisk skuld**: Eftersom den här metoden använder en modifierad form av din befintliga implementering kan det vara svårare att spåra implementeringslogik och utföra ändringar i framtiden vid behov.</li><li>**Mappning krävs för att skicka data till plattformen**: När din organisation är redo att använda Customer Journey Analytics måste du skicka data till en datauppsättning i Adobe Experience Platform. Den här åtgärden kräver att alla fält i `data` objektet vara en post i datastream-mappningsverktyget som tilldelar det till ett XDM-schemafält. Mappning behöver bara göras en gång för det här arbetsflödet, och implementeringen behöver inte ändras. Det är dock ett extra steg som inte krävs när du skickar data i ett XDM-objekt.</li></ul> |

Adobe rekommenderar att du följer den här implementeringsvägen i följande scenarier:

* Du har en befintlig implementering med hjälp av JavaScript-biblioteket i Adobe Analytics AppMeasurement. Om du har en implementering med hjälp av taggtillägget Adobe Analytics följer du [Migrera från Adobe Analytics-taggtillägget till Web SDK-taggtillägget](analytics-extension-to-web-sdk.md) i stället.
* Du tänker använda Customer Journey Analytics i framtiden, men vill inte ersätta din Analytics-implementering med en Web SDK-implementering från grunden. Att ersätta implementeringen från grunden i Web SDK kräver mest arbete, men erbjuder även den mest livskraftiga långsiktiga implementeringsarkitekturen. Om din organisation är beredd att använda en ren Web SDK-implementering kan du läsa [Importera data via Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) i användarhandboken för Customer Journey Analytics.

## Steg som krävs för att migrera till Web SDK

Följande steg innehåller konkreta mål att arbeta mot. Klicka på varje steg om du vill ha detaljerade anvisningar om hur du slutför det.

+++**1. Skapa och konfigurera ett datastream**

Skapa ett datastream i Adobe Experience Platform Data Collection. När du skickar data till den här dataströmmen vidarebefordrar den data till Adobe Analytics. I framtiden vidarebefordrar samma datastream data till Customer Journey Analytics.

1. Navigera till [experience.adobe.com](https://experience.adobe.com) och logga in med dina inloggningsuppgifter.
1. Använd hemsidan eller produktväljaren längst upp till höger för att navigera till **[!UICONTROL Data Collection]**.
1. I vänster navigering väljer du **[!UICONTROL Datastreams]**.
1. Välj **[!UICONTROL New Datastream]**.
1. Ange önskat namn och välj **[!UICONTROL Save]**.
1. När datastream har skapats väljer du **[!UICONTROL Add Service]**.
1. Välj **[!UICONTROL Adobe Analytics]**.
1. Ange samma rapportsviter-ID som den webbplats du för närvarande skickar analysdata till. Klicka på **[!UICONTROL Save]**.

![Lägg till Adobe Analytics](assets/datastream-rsid.png) {style="border:1px solid gray"}

Din datastream är nu redo att ta emot och skicka data till Adobe Analytics. Observera dataStream ID, eftersom detta ID krävs när du konfigurerar Web SDK i koden.

+++

+++**2. Installera Web SDK JavaScript-biblioteket**

Referera till den senaste versionen av `alloy.js` så att dess metodanrop kan användas. Se [Installera Web SDK med JavaScript-biblioteket](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) för information och kodblock som ska användas.

+++

+++**3. Konfigurera Web SDK**

Konfigurera implementeringen så att den pekar på datastream som skapades i föregående steg med hjälp av Web SDK [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) -kommando. The `configure` -kommandot måste anges på varje sida, så att du kan inkludera det bredvid bibliotekets installationskod.

Använd [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) och [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) egenskaper i Web SDK `configure` kommando:

* Ange `edgeConfigId` till det datastream-ID som hämtats från föregående steg.
* Ange `orgId` till din organisations IMS-organisation.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Du kan också ange andra egenskaper i dialogrutan [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) beroende på organisationens implementeringskrav.

+++

+++**4. Uppdatera kodlogik för att använda en JSON-nyttolast**

Ändra implementeringen av Analytics så att den inte förlitar sig på `AppMeasurement.js` eller `s` -objekt. I stället anger du variabler till ett korrekt formaterat JavaScript-objekt, som konverteras till ett JSON-objekt när det skickas till Adobe. Med [Datalager](../../prepare/data-layer.md) på din webbplats är mycket användbart när du ställer in värden, eftersom du kan fortsätta att referera till samma värden.

För att skicka data till Adobe Analytics måste Web SDK-nyttolasten använda `data.__adobe.analytics` med alla analysvariabler angivna i det här objektet. Variabler i det här objektet delar identiska namn och format som deras AppMeasurement-variabelmotsvarigheter. Om du till exempel anger `products` ska du inte dela upp den i enskilda objekt på samma sätt som med XDM. I stället tar du med den som en sträng exakt om du anger `s.products` variabel:

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

I slutändan innehåller den här nyttolasten alla önskade värden och alla referenser till `s` -objekt i implementeringen tas bort. Du kan använda någon av resurserna som JavaScript tillhandahåller för att ställa in det här nyttolastobjektet, inklusive punktnotation för att ställa in enskilda värden.

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {analytics: {}}}};
dataObj.data.__adobe.analytics.pageName = window.document.title;
dataObj.data.__adobe.analytics.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{analytics:{...a}}}};
```

+++

+++**5. Uppdatera metodanrop för att använda Web SDK**

Uppdatera alla instanser som du anropar [`s.t()`](../../vars/functions/t-method.md) och [`s.tl()`](../../vars/functions/tl-method.md)och ersätta dem med [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) -kommando. Det finns tre scenarier:

* **Spårning av sidvy**: Ersätt spårningsanropet för sidvyn med Web SDK `sendEvent` kommando:

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Automatisk länkspårning**: [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) konfigurationsegenskapen är aktiverad som standard. Den ställer automatiskt in rätt länkspårningsvariabler för att skicka data till Adobe Analytics. Om du vill inaktivera automatisk länkspårning anger du den här egenskapen som `false` inom [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) -kommando.

* **Manuell länkspårning**: Web SDK har inte olika kommandon mellan sidvyanrop och icke-sidvisningsanrop. Ange den skillnaden i nyttolastobjektet.

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.analytics.linkName = "Example custom link";
  dataObj.data.__adobe.analytics.linkType = "o";
  dataObj.data.__adobe.analytics.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6. Validera och publicera ändringar**

När du har tagit bort alla referenser till AppMeasurementet och `s` publicera ändringarna i utvecklingsmiljön för att validera att den nya implementeringen fungerar. När du har kontrollerat att allt fungerar som det ska kan du publicera dina uppdateringar i produktionen.

Om migreringen är korrekt `AppMeasurement.js` behövs inte längre på din plats och alla referenser till skriptet kan tas bort.

+++

I nuläget finns er Analytics-implementering helt och hållet i Web SDK och är väl förberedd att gå över till Customer Journey Analytics i framtiden.
