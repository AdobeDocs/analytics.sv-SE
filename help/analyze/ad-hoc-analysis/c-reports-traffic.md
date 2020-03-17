---
description: Rapporterna från trafikkällor ger er djupgående insikter om hur besökarna interagerar med er webbplats.
title: Trafikkällrapporter
topic: Ad hoc analysis
uuid: 246afbdc-9f7b-4956-a44a-b7aad948f392
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Trafikkällrapporter

Rapporterna från trafikkällor ger er djupgående insikter om hur besökarna interagerar med er webbplats.

## Trafikkällrapporter {#concept_0F1772141E1345C5BCF63BE7C544C0CB}

Rapporterna från trafikkällor ger er djupgående insikter om hur besökarna interagerar med er webbplats.

Med trafikkällrapporter kan du:

* Analysera viktiga aspekter av besökarnas beteende.
* Övervaka och förstå trafikmönster.
* Bestäm populärt webbplatsinnehåll.
* Segmentera besökarna enligt mätbara kriterier.

**Gemensam beständighet**

Dessutom [!UICONTROL Traffic Sources]kvarstår alla rapportvärden och får kredit tills de skrivs över eller tills besöket upphör, beroende på vilket som inträffar först. Tidigare var endast nyckelord och referensdomäner beständiga. Om en besökare till exempel gör en Google-sökning efter&quot;DVD&quot;, som tar dem till din webbplats för ett köp på 100 dollar, tilldelas 100 dollar till nyckelordet&quot;DVD&quot; och även till sökmotorn i Google. Den här funktionen går inte att ändra, oavsett [!DNL Admin Console] inställningar.

## Sök nyckelord {#concept_071FDCBD0A3B4242BA00744786D1C59C}

Visar en beskrivning av nyckelord för Alla, Betalda och Naturliga sökningar.

<!-- 

c_reports_search_keyword.xml

 -->

**[!UICONTROL Search Keywords - All]**: Visar en beskrivning av varje söknyckelord som har använts för att hitta platsen. Du kan sortera den här listan efter sidvyer eller söknyckelord genom att klicka på kolumnrubriken ovanför listan. Klicka på förstoringsglaset bredvid ett söknyckelord för att se sökresultaten för din webbplats.

**[!UICONTROL Search Keywords - Paid]**: Visar en beskrivning av varje betalt söknyckelord som används för att hitta platsen. Du kan sortera den här listan efter sidvyer eller söknyckelord genom att klicka på kolumnrubriken ovanför listan. Klicka på förstoringsglaset bredvid ett söknyckelord för att se sökresultaten för din webbplats.

**[!UICONTROL Search Keywords - Natural]**: Visar en beskrivning av varje naturligt söknyckelord som används för att hitta platsen. Du kan sortera den här listan efter sidvyer eller söknyckelord genom att klicka på kolumnrubriken ovanför listan. Klicka på förstoringsglaset bredvid ett söknyckelord för att se sökresultaten för din webbplats.

## Sökmotorer {#concept_351CDE4F5FC44371B6B657064E125134}

Visar vilka sökmotorer besökarna använder för Alla, Betalda och Naturliga sökningar.

<!-- 

c_reports_search_engines.xml

 -->

**[!UICONTROL Search Engines - All]**: Visar vilka sökmotorer som andra använder för att hitta din webbsida. I diagrammet visas den procentuella fördelningen av sökmotorer som används för att hitta din webbplats.

**[!UICONTROL Search Engines - Paid]**: Visar vilka sökmotorer med nyckelord som användare använder för att hitta din webbsida. I diagrammet visas den procentuella fördelningen av sökmotorer som används för att hitta din webbplats.

**[!UICONTROL Search Engines - Natural]**: Visar vilka sökmotorer med naturliga nyckelord som användarna använder för att hitta din webbsida. I diagrammet visas den procentuella fördelningen av sökmotorer som används för att hitta din webbplats.

## Refererande domäner {#concept_804614DF21C14C9FB542451B30F92788}

<!-- 

c_reports_ref_domains.xml

 -->

Visar de domäner som refererade till de kunder som mest påverkade webbplatsens framgångsmått. Referenser kan delas in i två huvudkategorier: Domäner och URL:er. Domäner refererar till domännamnet och visas som basdomän utan frågesträngen eller underkatalogerna kopplade. URL:er innehåller basdomännamnet samt eventuella frågesträngar och underkataloger.

## Ursprungliga referensdomäner {#concept_EB18251DF70343169B46BB59543A579A}

<!-- 

c_reports_original_ref_domains.xml

 -->

Visar de ursprungliga hänvisarna som producerade kunderna på er webbplats. Kunderna kan besöka er webbplats flera gånger och ha olika hänvisare för varje besök. Den här rapporten visar hur de hänvisades första gången de kom till er webbplats. Detta kan hjälpa er att se om de fortsatte att använda samma hänvisare och se mönster för hur kunderna hänvisas till er webbplats. Du kan visa antalet besökare som genererats av en ursprunglig referent eller ta reda på hur mycket intäkter varje ursprunglig referent hade för att producera. Referensrapporter kan fyllas i varje gång en besökare kommer till din webbplats, även om besökaren kommer till webbplatsen flera gånger under en session (innan besöket går ut).

## Referenter {#concept_40CF9C2D10B94E82819BC65A232F05C3}

Visar den domän eller URL-adress dit dina besökare kom från innan de kom till din webbplats, de metoder besökarna använder för att hitta din webbplats och antalet besök på din webbplats som kommer från dessa hänvisande platser.

<!-- 

c_reports_referrers.xml

 -->

Om en besökare till exempel klickar på en länk från plats A och kommer till din plats, är plats A referenten om den inte är definierad som en del av din domän. Under implementeringen av marknadsföringsrapporter och analyser kan er implementeringskonsult hjälpa er att definiera de domäner och URL:er som ingår i er webbplats. (Den här ändringen kan göras efter implementeringen.)

Domäner eller URL-adresser som inte ingår i de definierade domänerna och URL-adresserna betraktas som referenter. Webbsida A och webbsida B läggs till i det interna URL-filtret, men webbsida C läggs inte till. I det här fallet betraktas webbsida C som en referent.

Mer information finns i [Interna URL-filter](https://marketing.adobe.com/resources/help/en_US/reference/internal_URL_filter_admin.html) i [!DNL Admin Console] hjälpen.

> [!NOTE] Marknadsföringsrapporter och analyser registrerar en hänvisande domän som ett e-postmeddelande när besökare klickar på en e-postmeddelandelänk som innehåller protokollet [!DNL imap://] eller [!DNL mail://] kommer till din webbplats. Allt som kommer från [!DNL https://mail.yahoo.com] räknas till exempel inte som e-postreferent eftersom protokollet är [!DNL https://]. E-post från Outlook rapporteras på raden Typed/Bookmarked, medan alla referenter med ett HTTP-protokoll där domänen är en känd sökmotor rapporteras på raden Sökmotor.

## Referenstyp {#concept_689E42D8F96C450DA41C7167C7388198}

Genom att spåra och spela in besökarnas hänvisande webbplatser för varje besök kan du avgöra hur besökarna fick reda på webbplatsen för varje besök.

<!-- 

c_reports_ref_types.xml

 -->

I listan nedan definieras de olika typerna av referenser:

* *Andra webbplatsreferenter* spelas in när besökare klickar på en länk som finns på en sida på en annan webbplats (inte definierad som en del av din webbplats) och kommer till din webbplats.
* *Referenser till sökmotorer* registreras när besökare använder en sökmotor för att komma åt webbplatsen.
* *Typade/bokmärkta* referenser registreras

   * Om en besökare kommer in på platsen via en länk som inte är en webbläsare (till exempel i ett e-postmeddelande).
   * Om en besökare skriver webbplatsens URL direkt i webbläsaren.
   * Om en besökare klickar på en HTML-länk på sin egen hårddisk.
   * Om en besökare kommer åt webbplatsen genom att välja webbläsarbokmärken.

**Definitioner**

Följande radobjekt kan visas när den här rapporten körs:

**Inuti din webbplats**: De här objekten är URL:er som är taggade med de interna URL-filtren. De här objekten räknas inte som referensinstanser utan kan ses vid rapportering av andra mätvärden.

**Inget Java-skript**: Det fanns inget JavaScript, så typen var oidentifierbar (okänd). Det innebär att det inte fanns någon referensinformation från en klient i en webbläsare, som inte rapporterar att Javascript stöds. Dessa räknas inte som &quot;refererarinstanser&quot; men kan ses när andra mätvärden rapporteras.

**USENET (newsgroup)**: Det innebär att URL:en för en referent börjar med `news://`. Därför lades refererarlänken upp på en diskussionsgrupp i användargruppen i stället för på en webbsida.

> [!NOTE] Referenstypslogiken matchar andra trafikkällrapporter (till exempel [!UICONTROL Referrers] och [!UICONTROL Referring Domains]). Detta bör reducera eller eliminera förekomster av Inside Your Site och Inga JavaScript-radobjekt i [!UICONTROL Referrer Type] rapporten.

