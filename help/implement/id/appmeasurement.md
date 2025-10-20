---
title: Besökaridentifiering med AppMeasurement
description: Identifiera besökare korrekt när ni implementerar Adobe Analytics med AppMeasurement.
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 0%

---

# Besökaridentifiering med AppMeasurement

AppMeasurement är Adobe Analytics gamla JavaScript-bibliotek för datainsamling. Även om AppMeasurement i sig själv erbjuder ett inbyggt sätt att identifiera besökare, avvisar många moderna webbläsare de cookies från tredje part som det försöker ange. Adobe rekommenderar starkt att du använder Adobe Experience Cloud Visitor ID Service i alla implementeringar för att uppfylla moderna webbläsarsekretessstandarder. Alla versioner av AppMeasurement medföljer `VisitorAPI.js`, det JavaScript-bibliotek som användes för att implementera Visitor ID-tjänsten.

## Identifiera besökare med hjälp av besökar-ID-tjänsten (rekommenderas)

Kontrollera att du är förberedd med följande:

* Hämta den [senaste versionen av AppMeasurement](https://github.com/adobe/appmeasurement). Det hämtade biblioteket innehåller både `AppMeasurement.js` och `VisitorAPI.js`.
* En [rapportsvit-ID](/help/admin/tools/manage-rs/new-rs/new-report-suite.md) för utveckling.
* Den önskade kantdomänen för [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md).
* Ditt IMS-organisations-ID:
   1. Logga in på [experience.adobe.com](https://experience.adobe.com) med dina Adobe ID-inloggningsuppgifter.
   1. Tryck på `[Cmd]` + `[I]` (iOS) eller `[Ctrl]` + `[I]` (Windows) någonstans i Experience Cloud-gränssnittet.
   1. En **[!UICONTROL User data debugger]** visas. Klicka på fliken **[!UICONTROL Assigned orgs]**.  
   1. Utöka den önskade IMS-organisationen.
   1. Leta reda på fältet **[!UICONTROL ID]**.

När du har resurserna ovan innehåller följande grundläggande exempelsida de minsta anrop som krävs för att skicka data till Adobe Analytics:

```html
<html>
  <head>
    <title>Example AppMeasurement implementation page</title>
    <script src="AppMeasurement.js"></script>
    <script src="VisitorAPI.js"></script>
  </head>
  <body>
    <h1>Hello world!</h1>
    <script>
      var s = s_gi("examplersid"); // Include development report suite ID here
      s.trackingServerSecure = "example.data.adobedc.net"; // Include edge domain here
      s.visitor = Visitor.getInstance("ADB3LETTERSANDNUMBERS@AdobeOrg"); // Include IMS org ID here
      s.pageName = document.title;
      s.t();
    </script>
  </body>
</html>
```

>[!TIP]
>
>Du kan spåra om en träff använder tjänsten för besökar-ID genom att tilldela förekomsten av `Visitor` till en anpassad variabel i [`doPlugins`](/help/implement/vars/functions/doplugins.md):
>
>```js
>s.doPlugins = function() {
>   s.prop1 = typeof(Visitor) != "undefined" ? "VisitorAPI present" : "VisitorAPI missing";
>};
>```

## Identifiera besökare med hjälp av cookien `s_vi` (rekommenderas inte)

>[!IMPORTANT]
>
>Adobe rekommenderar att du inte använder den här metoden för att identifiera besökare.

Om din organisation inte använder besökar-ID-tjänsten använder AppMeasurement en egen form av besökaridentifiering. När en besökare kommer till din webbplats för första gången söker biblioteket efter en [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics)-cookie. Den här cookien är inställd på domänmatchande [`trackingServerSecure`](/help/implement/vars/config-vars/trackingserversecure.md) (för HTTPS) eller [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) (för HTTP).

* Om du deltar i det [hanterade certifikatprogrammet](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert) är din spårningsserver vanligtvis en förstapartsdomän, vilket gör `s_vi` cookies från första part.
* Om du inte deltar i det hanterade certifikatprogrammet är spårningsservern vanligtvis en underdomän till `adobedc.net`, `omtrdc.net` eller `2o7.net`, vilket gör `s_vi`-cookien till en cookie från tredje part. På grund av moderna webbläsarsekretessstandarder avvisas cookies från tredje part av de flesta webbläsare. När den har avvisats försöker AppMeasurement ange en cookie för återfall (`fid`) för första part i stället.

Om du har angett `trackingServerSecure` korrekt krävs inga ytterligare åtgärder för besöksidentifiering.

## Identifiera besökare med `visitorID` (rekommenderas inte)

>[!IMPORTANT]
>
>Adobe rekommenderar att du inte använder den här metoden för att identifiera besökare.

Om du använder variabeln [`visitorID`](/help/implement/vars/config-vars/visitorid.md) kan din organisation utföra oberoende kontroll för att identifiera besökare. Om du använder `visitorID` bör du tänka på följande begränsningar:

* Varje träff måste innehålla samma `visitorID`-värde för att räknas som en enskild besökare.
   * Alla träffar som inte innehåller `visitorID` försöker automatiskt att använda en annan metod för identifiering av besökare, och behandlar dem som separata besökare.
   * Alla träffar som innehåller ett annat `visitorID`-värde än en tidigare träff behandlas som separata besökare.
   * Adobe erbjuder inget sätt att sammanfoga träffar med olika besökar-ID:n.
* Delade målgrupper, Analytics for Target och Customer-attribut stöds inte för besökare som identifieras med `visitorID`.

Se [`visitorID`](/help/implement/vars/config-vars/visitorid.md) för implementeringsinstruktioner med den här variabeln.
