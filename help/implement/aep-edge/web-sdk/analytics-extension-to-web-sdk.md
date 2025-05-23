---
title: Migrera från Adobe Analytics-taggtillägget till Web SDK-taggtillägget
description: Uppdatera Analytics-implementeringen för Adobe Experience Platform Data Collection-taggar så att de använder Web SDK-tillägget.
exl-id: 691c29ca-d169-4ef8-9f91-d0375166796d
source-git-commit: 7bd4a188e5a2171260f1f0696d8bebad854dba4a
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 0%

---

# Migrera från Adobe Analytics-taggtillägget till Web SDK-taggtillägget

Den här implementeringsvägen innefattar en metod för metodmigrering för att gå från taggtillägget Adobe Analytics till taggtillägget Web SDK. Andra implementeringsvägar beskrivs på separata sidor:

* [AppMeasurement till Web SDK JavaScript-bibliotek](appmeasurement-to-web-sdk.md): Ett smidigt och metodiskt sätt att migrera till Web SDK, förutom att taggar inte används. I stället tar du bort Adobe Analytics datainsamlingsbibliotek (`AppMeasurement.js`) manuellt och ersätter det med Web SDK JavaScript-biblioteket (`alloy.js`).
* [Web SDK-taggtillägg](web-sdk-tag-extension.md): En ny Web SDK-installation där du hanterar implementeringen med hjälp av taggar i Adobe Experience Platform Data Collection. Det kräver fältgruppen Adobe Analytics ExperienceEvent, som innehåller typiska analysvariabler som ska inkluderas i XDM-schemat.
* [JavaScript-bibliotek för Web SDK](web-sdk-javascript-library.md): En ny SDK-installation med JavaScript-biblioteket för Web SDK (`alloy.js`). Hantera implementeringen själv i stället för att använda tagggränssnittet. Det kräver fältgruppen Adobe Analytics ExperienceEvent, som innehåller typiska analysvariabler som ska inkluderas i XDM-schemat.

## Fördelar och nackdelar med implementeringsvägen

Att använda den här migreringsmetoden har både fördelar och nackdelar. Väg noga in varje alternativ för att avgöra vilken metod som är bäst för er organisation.

| Fördelar | Nackdelar |
| --- | --- |
| <ul><li>**Inga kodändringar på din plats**: Eftersom implementeringen redan har installerade taggar kan alla migreringsuppdateringar göras i tagggränssnittet.</li><li>**Använder din befintliga implementering**: Den här metoden kräver ingen ny implementering. Även om det kräver nya regelåtgärder kan du återanvända befintliga dataelement och regelvillkor med minimala ändringar.</li><li>**Kräver inget schema**: För den här migreringsfasen till Web SDK behövs inget XDM-schema. I stället kan du fylla i objektet `data`, som skickar data direkt till Adobe Analytics. När migreringen till Web SDK är klar kan du skapa ett schema för din organisation och använda datastream-mappning för att fylla i tillämpliga XDM-fält. Om det krävs ett schema i det här skedet av migreringsprocessen måste din organisation använda ett Adobe Analytics XDM-schema. Om du använder det här schemat blir det svårare för din organisation att använda ditt eget schema i framtiden.</li></ul> | <ul><li>**Implementeringens tekniska skuld**: Eftersom den här metoden använder en modifierad form av din befintliga implementering, kan det vara svårare att spåra implementeringslogik och utföra ändringar vid behov. Anpassad kod kan vara särskilt svår att felsöka.</li><li>**Kräver mappning för att skicka data till plattformen**: När din organisation är redo att använda Customer Journey Analytics måste du skicka data till en datauppsättning i Adobe Experience Platform. Den här åtgärden kräver att alla fält i objektet `data` är en post i datastream-mappningsverktyget som tilldelar det till ett XDM-schemafält. Mappning behöver bara göras en gång för det här arbetsflödet, och implementeringen behöver inte ändras. Det är dock ett extra steg som inte krävs när du skickar data i ett XDM-objekt.</li></ul> |

Adobe rekommenderar att du följer den här implementeringsvägen i följande scenarier:

* Du har en befintlig implementering med hjälp av taggtillägget Adobe Analytics. Om du har en implementering med AppMeasurement följer du [Migrera från AppMeasurement till Web SDK](appmeasurement-to-web-sdk.md) i stället.
* Du tänker använda Customer Journey Analytics i framtiden, men vill inte ersätta din Analytics-implementering med en Web SDK-implementering från grunden. Att ersätta implementeringen från grunden i Web SDK kräver mest arbete, men erbjuder även den mest livskraftiga långsiktiga implementeringsarkitekturen. Om din organisation vill använda en ren Web SDK-implementering läser du [Importera data via Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) i användarhandboken för Customer Journey Analytics.

## Steg som krävs för att migrera till Web SDK

Följande steg innehåller konkreta mål att arbeta mot. Klicka på varje steg om du vill ha detaljerade anvisningar om hur du slutför det.

+++**1. Skapa och konfigurera en datastream**

Skapa ett datastream i Adobe Experience Platform Data Collection. När du skickar data till den här dataströmmen vidarebefordrar den data till Adobe Analytics. I framtiden vidarebefordrar samma datastream data till Customer Journey Analytics.

1. Navigera till [experience.adobe.com](https://experience.adobe.com) och logga in med dina autentiseringsuppgifter.
1. Använd hemsidan eller produktväljaren i det övre högra hörnet för att navigera till **[!UICONTROL Data Collection]**.
1. Välj **[!UICONTROL Datastreams]** i den vänstra navigeringen.
1. Välj **[!UICONTROL New Datastream]**.
1. Ange önskat namn och välj sedan **[!UICONTROL Save]**.
1. Välj **[!UICONTROL Add Service]** när dataströmmen har skapats.
1. Välj **[!UICONTROL Adobe Analytics]** på den nedrullningsbara menyn för tjänster.
1. Ange samma rapportsviter-ID som den webbplats du för närvarande skickar analysdata till. Klicka på **[!UICONTROL Save]**.

![Lägg till Adobe Analytics-tjänst](assets/datastream-rsid.png) {style="border:1px solid lightslategray"}

Din datastream är nu redo att ta emot och skicka data till Adobe Analytics.

+++

+++**2. Lägg till Web SDK-tillägget i taggegenskapen**

I det här avsnittet förbereds taggen för den mesta migreringen som görs i nästa steg.

1. Klicka på ikonen för hamburgaren i det övre vänstra hörnet i Adobe Experience Platform-gränssnittet och välj sedan **[!UICONTROL Tags]**.
1. Välj önskad taggegenskap.
1. Välj **[!UICONTROL Extensions]** i den vänstra navigeringen för taggegenskapen.
1. Välj **[!UICONTROL Catalog]** i den övre delen om du vill se en lista över alla tillgängliga tillägg.
1. Sök efter och välj tillägget **[!UICONTROL Adobe Experience Platform Web SDK]** och klicka sedan på **[!UICONTROL Install]** till höger.

   ![Katalog](assets/catalog.png) {style="border:1px solid lightslategray"}

1. Konfigurationsinställningarna för tillägget visas. Leta reda på avsnittet Datastreams och markera datastream som du skapade i föregående steg.

   ![Val av dataström](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Välj **[!UICONTROL Save]**.

Din taggegenskap har nu Web SDK installerat.

+++

+++**3. Skapa ett dataobjektdataelement**

Dataobjektets dataelement tillhandahåller ett intuitivt ramverk för att konfigurera en nyttolast som Web SDK använder för att skicka till en datastam. De flesta regler som du uppdaterar i följande steg interagerar med det här dataelementet.

1. Välj **[!UICONTROL Data Elements]** i den vänstra navigeringen i tagggränssnittet.
1. Välj **[!UICONTROL Add Data Element]**
1. Ge dataelementet följande inställningar:
   * [!UICONTROL Name]: Allt du vill, till exempel &quot;Datalager&quot; eller &quot;Dataobjekt&quot;
   * [!UICONTROL Extension]: [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Data Element Type]: [!UICONTROL Variable]
   * Kryssrutor kan behållas som de är
1. Välj följande inställningar till höger:
   * Egenskapens alternativknapp: [!UICONTROL Data]
   * Lösning: [!UICONTROL Adobe Analytics]
1. Välj **[!UICONTROL Save]**.

![Skapa dataelement](assets/create-data-element.png) {style="border:1px solid lightslategray"}

Din taggegenskap har nu allt som behövs för att uppdatera varje regel.

+++

+++**4. Uppdatera regler för att använda Web SDK-tillägget i stället för Analytics-tillägget**

Det här steget innehåller det mesta som krävs för att migrera till Web SDK och kräver kunskap om hur implementeringen fungerar. Nedan visas ett exempel på hur du redigerar en typisk taggregel. Uppdatera alla taggregler i implementeringen för att ersätta alla referenser till Adobe Analytics-tillägget med Web SDK-tillägget.

1. Välj **[!UICONTROL Rules]** i den vänstra navigeringen i tagggränssnittet.
1. Markera en regel som du vill redigera.
1. Välj åtgärden **[!UICONTROL Adobe Analytics - Set Variables]**
1. Observera alla analysvariabler som anges i den här regeln. Inkludera båda variablerna som angetts i listrutorna och variablerna som angetts i anpassad kod.
1. Ändra [!UICONTROL Action Configuration] till följande inställningar:
   * [!UICONTROL Extension]: [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Action type]: Uppdatera variabel
1. Se till att dataobjektet är markerat i listrutan till höger.
1. Ställ in Analytics-variablerna på samma värden som de konfigurerades i Analytics-tillägget.
   * Variabler som anges i tagggränssnittet kan direkt översättas till samma värden.
   * Strängvariabler som angetts i anpassad kod kräver minimala justeringar. Använd `data.__adobe.analytics` i stället för att använda objektet `s`. `s.eVar1` skulle till exempel översätta till `data.__adobe.analytics.eVar1`.
   * Konfigurationsvariabler för analyser och metodanrop i anpassad kod kan kräva modifierad implementeringslogik. Se respektive [variabel](/help/implement/vars/overview.md) för att avgöra hur motsvarande värde ska uppnås med Web SDK.
1. När all regellogik har replikerats med Web SDK-tillägget väljer du **[!UICONTROL Keep Changes]**.
1. Upprepa dessa steg för varje åtgärdskonfiguration som använder tillägget Adobe Analytics för att ange värden. I det här steget ingår både variabler som angetts med tagggränssnittet och variabler som ställts in med anpassad kod. Anpassade kodblock kan inte referera till objektet `s` någonstans.

Stegen ovan gäller bara regler som anger värden. Följande steg ersätter alla åtgärder som använder [!UICONTROL Action Configuration] [!UICONTROL Send Beacon].

1. Välj en regel som skickar en fyr.
1. Välj åtgärden **[!UICONTROL Adobe Analytics - Send Beacon]**.
1. Observera det aktuella värdet för alternativknappen [!UICONTROL Tracking] till höger ([`s.t()`](../../vars/functions/t-method.md) eller [`s.tl()`](../../vars/functions/tl-method.md)).
1. Ändra [!UICONTROL Action Configuration] till följande inställningar:
   * [!UICONTROL Extension]: [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Action type]: [!UICONTROL Send event]
1. Till höger ändrar du åtgärdsinställningarna till följande:
   * [!UICONTROL Type]: Använd **[!UICONTROL Web Webpagedetails Page Views]** för `s.t()`. Använd **[!UICONTROL Web Webinteraction Link Clicks]** för `s.tl()`. Om du använder [`s.tl()`](../../vars/functions/tl-method.md) måste du även inkludera följande fält i dataobjektet. Dessa fält listas under [!UICONTROL Additional properties] när åtgärdskonfigurationen [!UICONTROL Update variable] utförs:
      * [Länknamn](../../vars/functions/tl-method.md)
      * [Länktyp](../../vars/functions/tl-method.md)
      * [Länk-URL](../../vars/config-vars/linkurl.md)
1. Välj **[!UICONTROL Keep Changes]**.
1. Upprepa dessa steg för varje åtgärdskonfiguration som använder Adobe Analytics för att skicka en signal.

+++

+++**5. Publish uppdaterade regler**

Publicering av uppdaterade regler följer samma arbetsflöde som andra ändringar av taggkonfigurationen.

1. Välj **[!UICONTROL Publishing Flow]** i den vänstra navigeringen i tagggränssnittet.
1. Välj **[!UICONTROL Add Library]**.
1. Ge den här taggen ett namn, till exempel&quot;Uppgradera till Web SDK&quot;.
1. Välj **[!UICONTROL Add All Changed Resources]**.
1. Välj **[!UICONTROL Save]**.
1. Publiceringsarbetsflödet visar en orange punkt som anger att den håller på att byggas. När punkten blir grön är dina ändringar tillgängliga i utvecklingsmiljön.
1. Testa ändringarna i utvecklingsmiljön för att säkerställa att alla regler aktiveras korrekt och att dataobjektet fylls med förväntade värden.
1. När det är klart skickar du biblioteket för godkännande, bygg till staging, och sedan godkänner och publicerar det i produktion.

![Publiceringsflöde](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Inaktivera analystillägget**

När taggimplementeringen är klar på Web SDK kan du inaktivera Adobe Analytics-tillägget.

1. Välj **[!UICONTROL Extensions]** i den vänstra navigeringen i tagggränssnittet.
1. Leta reda på och välj tillägget [!UICONTROL Adobe Analytics]. Välj **[!UICONTROL Disable]** till höger.
1. Följ samma publiceringsarbetsflöde ovan för att publicera borttagningen av tillägget [!UICONTROL Adobe Analytics].
1. När tillägget har inaktiverats i produktionen kan du avinstallera det helt. Välj tillägget, välj menyn med tre punkter till höger och välj sedan **[!UICONTROL Uninstall]**.
1. Följ samma publiceringsarbetsflöde ovan för att publicera dessa ändringar i produktionen.

+++

I nuläget finns er Analytics-implementering helt och hållet i Web SDK och är väl förberedd att gå över till Customer Journey Analytics i framtiden.
