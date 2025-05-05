---
title: Vanliga frågor om Activity Map
description: Frågor och svar om Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: f242ec6613cf046224f76f7edc7813a34c65fff8
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 0%

---

# Vanliga frågor om Activity Map

Frågor och svar om Activity Map.

+++Hur ger jag Activity Map behörighet?

Behörigheter att använda Activity Map och dess associerade dimensioner hanteras i [Adobe Admin Console](/help/admin/admin-console/home.md).

[behörighetsobjekten](/help/admin/admin-console/permissions/product-profile.md) som krävs för Activity Map är:

* **[!UICONTROL Analytics Tools]** > **[!UICONTROL Activity Map]**
* **[!UICONTROL Analytics Tools]** > **[!UICONTROL Segment Publishing]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Scroll Reach]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Link By Region]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Region]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Link]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Page]**

Mer information finns i [Behörigheter för produktprofiler för analysverktyg](/help/admin/admin-console/permissions/analytics-tools.md).

+++

+++Har alla Analytics-kunder tillgång till Activity Map?

Organisationer som har ett kontrakt för Adobe Analytics Standard, Premium och Ultimate har tillgång till Activity Map. De här avtalstyperna representerar de flesta av Adobe Analytics kunder.

+++

+++Hur stöder Activity Map Single-Page Applications (SPA)?

Med några få sekunders mellanrum söker Activity Map igenom webbsidan efter ändringar. Activity Map hittar nytt innehåll på sidan utan att behöva läsa in det på nytt, men det nya innehållet tilldelas alltid till det första siddimensionsvärdet.

* Activity Map kontrollerar om synligheten för länkar som de känner till har ändrats. Om en synlighetsändring hittas uppdateras kolumnen Present (Länkar på sida) för den länken med [!UICONTROL Displayed] eller [!UICONTROL Hidden].

* När användarinteraktion skapar nytt innehåll läggs alla nya element som AppMeasurementet fastställer som en länk till tabellen [!UICONTROL Links On Page] till. Activity Map skickar en ny databegäran som innehåller de nya länkarna. De nya länkarna visas i tabellen [!UICONTROL Links On Page] när databegäran returneras.

+++

+++Tillhandahåller Activity Map data om länkar som visas men inte klickas?

Nej, Adobe spårar inte automatiskt länkar som bara visades.

+++

+++Vilka webbläsare och versioner stöder Activity Map?

Activity Map har stöd för den senaste versionen av de flesta moderna webbläsare.

+++

+++Ökar Activity Map serveranrop?

Activity Map skickar inte serversamtal själv. I stället inkluderas datavariabler för kontext i Activity Map i sidvisningsanropen för Analytics på efterföljande sida. Vissa tidigare versioner av Activity Map på webben SDK skickar dock ett separat anrop till Activity Map data. Om du använder den senaste versionen av Web SDK sammanfogas data från Activity Map med följande händelse.

+++

+++Varför saknas vissa rangnummer i övertäckningen?

Vissa länkar, till exempel de som finns på menyer, är dolda på sidan. Därför visas inte motsvarande länkövertäckningar. Rankningen beräknas för alla länkar på sidan, inklusive dolda länkar.

+++

+++Hur bestäms länkrankningen i rapporten Alla länkar?

* **I övertonings- och bubblingsläge**: Mätkolumnen bestämmer rangordningen. För länkar med samma måttvärde baseras rangordningen ytterligare på länk-ID i alfabetisk ordning.
* **I läget Gainer &amp; Loser**: Kolumnen Procent vunnen avgör rangordningen. För länkar med samma ökning baseras rangordningen ytterligare på länk-ID i alfabetisk ordning.

+++

+++Hur fungerar Activity Map med sidor som använder flera rapportsviter?

Som standard använder Activity Map den rapportserie som är associerad med den första taggen på sidan. Du kan välja en annan rapportserie på fliken **[!UICONTROL Activity Map Settings]** > **[!UICONTROL Others]**.

+++

+++Hur länge söker Activity Map efter Adobe Analytics på sidan?

Aktivitetskartan söker efter Adobe Analytics i upp till 20 sekunder efter en händelse om att sidan har slutförts.

+++

+++Hur hanterar Activity Map dynamiskt innehåll?

Activity Map kontrollerar varannan sekund om det finns några förändringar i webbsidans tillstånd, till exempel:

* HTML-innehåll som har blivit synligt
* dolt HTML-innehåll
* Nytt HTML-innehåll som injicerats

Om innehållet är dolt eller visas ändrar tillägget automatiskt läget för berörda länkar (och därmed övertäckningar) från dolt till visat eller från dolt till dolt. Om nytt innehåll injiceras hämtar programmet de associerade länkarna, hämtar analysdata för dem och lägger till övertäckningar för dessa länkar.

+++

+++Vilka mått baseras sidflödesrapporten på?

Alla data som visas baseras på sidvisningar.

+++

+++Kan jag exportera Activity Map data via dataflöden?

Ja. De [dataflödeskolumner](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) som Activity Map använder är:

* Activity Map-länk: `clickmaplink`
* Activity Map-sida: `clickmappage`
* Activity Map: `clickmapregion`
* Länk Activity Map efter region: `clickmaplinkbyregion`

+++

+++Fungerar segment i Live-läge?

Nej, segment fungerar inte i Live-läge.

+++

+++Är Activity Map kompatibelt med virtuella rapportsviter?

Ja. På grund av begränsningar i den virtuella rapportsviten är dock inte Activity Map Live-läget kompatibelt med virtuella rapportsviter.

+++

+++Hur inaktiverar jag Activity Map?

Vilken metod som ska avaktiveras för Activity Map beror på vilken implementeringstyp du har:

* **Webbtillägg för SDK**: Avmarkera kryssrutorna **[!UICONTROL Collect internal link clicks]**, **[!UICONTROL Collect external link clicks]** och **[!UICONTROL Collect download link clicks]** i inställningarna för tilläggskonfigurationen.
* **Webbbibliotek för SDK JavaScript**: Ange [`clickCollectionEnabled`](https://experienceleague.adobe.com/sv/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) till `false`.
* **Analystillägg**: Avmarkera kryssrutan **[!UICONTROL Use Activity Map]** i inställningarna för tilläggskonfigurationen.
* **AppMeasurement**: Ta bort eller kommentera bort modulen Activity Map i `AppMeasurement.js`, eller skriv över modulfunktionsanropet med en tom brödtext:

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

+++

+++Vilka är systemkraven för att använda övertäckningen Activity Map?

Du kan använda den senaste versionen av Chrome, Edge eller Firefox med tillägget Activity Map.

+++

+++Vad ska jag tänka på när jag använder Activity Map för personligt identifierbar information?

Tänk på följande scenarier där personligt identifierbara data kan samlas in med Activity Map:

* **E-postlänkar**: Om det går att klicka på en e-postadress för att öppna användarens e-postklient kan Activity Map samla in den e-postadress som användaren klickade på.
* **Länkar för användar-ID**: När en besökare har loggat in kan Activity Map registrera alla länkar som innehåller besökarens användar-ID.
* **Känsliga informationslänkar**: För finansinstitut kan känslig information som kontonummer spåras om de är en länk och besökarna klickar på dem.
* **Länkar som innehåller personlig information**: För hälso- och sjukvårdswebbplatser kan länkar innehålla personlig information. Om en besökare klickar på dessa länkar samlar Activity Map in länktexten.

+++

+++Vilka data spårar Activity Map som standard?

Activity Map spårar följande element:

* En `<a>`- eller `<area>`-tagg med egenskapen `href`. Ankartagglänkar (`#`) spåras inte som standard.
* Ett `onclick`-attribut som anger en `s_objectID`-variabel
* En `<input>`-tagg eller en `submit`-knapp med ett värde eller underordnad text
* En `<input>`-tagg med typen `image` och en `src`-egenskap
* En `<button>`-tagg utan attributet `type="button"`. Om du vill spåra `<button>`-taggar bör du använda attribut som `role="button"` eller `submit="button"` i stället.

+++

+++Vad är några exempel på länkar som Activity Map automatiskt spårar?

Nedan följer några exempel där Activity Map har all information som krävs för att spåra en länk.

```html
<a href="home.html">Home</a>

<input type="submit" value="Submit"/>

<input type="image" src="submit-button.png"/>

<p onclick="var s_objectID='Market rates';">
  <span class="title">Current Market Rates</span>
  <span class="subtitle">1.45 USD</span>
</p>

<div onclick="s.tl(true,'o','Chat button')">
  <span class="title">Chat with an agent now</span>
  <span class="subtitle">Current wait: 0 minutes</span>
</div>
```

+++

+++Vilka är några exempel på länkar som INTE spåras automatiskt i Activity Map?

* Ankartaggen har ingen giltig `href`
* Det finns varken någon [`s_objectID`](/help/implement/vars/page-vars/s-objectid.md)- eller [`tl()`](/help/implement/vars/functions/tl-method.md)-metod
* Egenskapen `src` saknas för ett formulärelement

Nedan följer några exempel där Activity Map inte kan spåra klickningar:

```html
<!-- Anchor tag does not have a valid href -->
<a name="innerAnchor">Section header</a>

<!-- Neither s_objectID or tl() method present -->
<p onclick="showPanel('stock price')">
  <span class="title">Current company stock price</span>
  <span class="subtitle">987.65 USD</span>
</p>

<!-- Neither s_objectID or tl() method present -->
<input type="radio" onclick="changeState(this)" name="group1" value="A"/>
<input type="radio" onclick="changeState(this)" name="group1" value="B"/>
<input type="radio" onclick="changeState(this)" name="group1" value="C"/>

<!-- src property missing on a form input element -->
<input type="image"/>
```

+++
