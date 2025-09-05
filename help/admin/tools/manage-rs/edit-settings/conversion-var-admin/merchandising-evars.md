---
title: Merchandising eVars and Product Finding Methods
description: En djupdykning i begreppen bakom försäljning av eVars och hur de bearbetar och allokerar data.
feature: Admin Tools
role: Admin
exl-id: 9e1a39aa-451f-49bb-8e39-797b6bbd5499
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '5248'
ht-degree: 0%

---

# Merchandising eVars and product finding methods

I det här mycket detaljerade dokumentet förklaras begreppen bakom försäljning av eVars, som bearbetar och tilldelar data på ett annat sätt än vanliga eVars. Det förklarar också hur eVars marknadsför produktsökningsmetoder.

## Översikt

Med hjälp av eVars-produkter kan du tilldela alla framgångsrika aktiviteter till värden som hämtas av eVars på en *per-product* -nivå i stället för en *per-visit/per-order* -nivå.

Även om de flesta webbplatser för detaljhandeln har många sätt att hitta produkter anser Adobe att följande är de grundläggande metoder för produktsökning som alla kunder inom detaljhandeln bör följa i Adobe Analytics:

* Interna söknyckelord
* Interna koder för kampanjspårning
* Marknadsföring/bläddringskategorier
* Merförsäljning av länkar

I det här dokumentet kan vi mappa några eVars till lösningarna enligt följande:

* eVar2: Interna söknyckelord
* eVar3: Intern kampanjspårningskoder
* eVar4: Kategorierna Merchandising/Browser
* eVar5: Korsförsäljning

Vi kan använda ytterligare en eVar för att mäta prestandan för alla produktsökningsmetoder i förhållande till varandra. Förutom de sökmetoder som beskrivs ovan innehåller eVar även andra sökmetoder i jämförelsen, som länkar till produktinformationssidor från externa webbplatser.

* eVar1: Produktsökningsmetoder

I stället för att konfigurera variablerna så att de blir standard-eVars, ska du konfigurera dem så att de marknadsför eVars.

För att visa hur du ställer in dessa variabler finns det ett exempel där en besökare bestämmer sig för att använda de interna söksandalerna för nyckelord för att hitta en produkt på webbplatsen. På sidan med sökresultat för nyckelord måste du hämta data i minst två eVars:

* `eVar2` är lika med nyckelordet som användes i sökningen (&quot;sandaler&quot;)
* `eVar1` är lika med den produktsökningsmetod som används (&quot;intern nyckelordssökning&quot;).

När du ställer in dessa två variabler som är lika med dessa specifika värden, vet du att besökaren använder det interna nyckelordssökordet för&quot;sandaler&quot; för att hitta en produkt. Samtidigt vet du att besökaren inte använder de andra produktsökningsmetoderna för att hitta produkter (besökaren bläddrar till exempel inte igenom produktkategorier exakt samtidigt som de gör en nyckelordssökning). För att säkerställa att rätt tilldelning sker per produkt bör dessa oanvända metoder inte få någon uppskattning för att hitta en produkt som hittats via en intern nyckelordssökning. Därför måste du infoga logik i koden (som AppMeasurement, Adobe Experience Platform Web SDK och så vidare) som automatiskt ställer in de eVars som är associerade med dessa andra sökmetoder som lika med ett icke-sökmetod-värde.

När en användare t.ex. söker efter produkter med nyckelordet &quot;sandals&quot;, ska Analytics-kodens logik ange de variabler som är lika med följande på den interna sökresultatsidan för nyckelord:

* eVar2=&quot;sandals&quot;: nyckelordet&quot;sandals&quot; användes i den interna nyckelordssökningen
* eVar1=&quot;intern nyckelordssökning&quot;: sökmetoden&quot;intern nyckelordssökning&quot; användes
* eVar3=&quot;icke-intern kampanj&quot;: en intern kampanj användes inte för att komma åt sökresultatsidan
* eVar4=&quot;non-browse&quot;: ingen bläddringskategori fanns på sökresultatsidan
* eVar5=&quot;non-cross-sell&quot;: en korsförsäljningslänk klickades inte på sökresultatsidan

## Inställningar för eVars

Här är de olika inställningarna som du kan använda med dina eVars-produkter. Följande skärmbild kommer från Report Suite Manager. Gå till [!UICONTROL Analytics] > [!UICONTROL Admin] > [!UICONTROL Report Suites] > [!UICONTROL Edit Settings] > [!UICONTROL Conversion] > [!UICONTROL Conversion Variables] > [!UICONTROL Add new] > [!UICONTROL Enable Merchandising].

![Merch eVars](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/assets/merch-evars1.png)

Mer information om de här inställningarna finns i avsnitten nedanför tabellen.

| Inställning | Beskrivning |
|--- | --- |
| Namn | The Name, or the reporting dimension that the variable is intended to be associated with. Om `eVar1` är avsedd för att hämta produktsökningsmetoder, ska namnfältet för `eVar1` anges till &quot;Produktsökningsmetoder&quot;. |
| Merchandising | Den typ av syntax som ska användas för att hämta eVar-värden för försäljning |
| Allokering | Hjälper till att avgöra vilket värde som ska användas för försäljning av eVar när en lyckad händelse inträffar. |
| Förfaller efter | Avgör när befintliga eVar-bindningar för produkter och marknadsföring inte längre ska gälla. |
| Typ | Den typ av data som samlas in i eVar |
| Marknadsföringsbindningshändelse | Händelsen/händelserna som avgör när en produkt ska bindas till ett marknadsföringsvärde för eVar |
| Återställ | En utlösare som återställer alla backend-data för eVar vid den tidpunkten |
| Aktivera marknadsföring | En flagga som måste ställas in på&quot;Enabled&quot; för att omvandla eVar från en eVar till en Merchandising eVar |

### Aktivera marknadsföring

När inställningen Aktivera marknadsföring är aktiverad visas alla inställningar som beskrivs nedan i Report Suite Manager. När inställningen &quot;Aktivera marknadsföring&quot; är &quot;Inaktiverad&quot; är endast eVar standardinställningar tillgängliga.

### Merchandising

Det här alternativet är inte tillgängligt för standard-eVars. Med inställningen [!UICONTROL Merchandising] kan du välja antingen [!UICONTROL Conversion Variable Syntax] eller [!UICONTROL Product Syntax] som metod för att hämta värdet för eVar-försäljning.

**[!UICONTROL Conversion Variable Syntax]** betyder att du anger eVar-värdet i dess egen variabel. Om du till exempel har konverteringsvariabelsyntax anges värdet `eVar1` för &quot;intern nyckelordssökning&quot; enligt följande i sidkoden (eller AppMeasurement-koden, Adobe Experience Platform Web SDK-koden o.s.v.):

`s.eVar1="internal keyword search";`

Med **[!UICONTROL Product Syntax]** anges dock eVar endast i variabeln Adobe Analytics-produkter. Variabeln Analytics-produkter är uppdelad i sex olika delar per produkt:

`s.products="[category];[name];[quantity];[revenue];[events];[eVars]"`

* [!UICONTROL Category] och [!UICONTROL Name] identifierar den angivna produkten.
* [!UICONTROL Quantity] och [!UICONTROL Revenue] är användbara när ett produktköp spåras.
* [!UICONTROL Events] är användbart för att registrera anpassade stegvisa värden eller valutakäntehändelser som inte ska räknas som intäkter (som frakt, rabatter osv.)

Merchandising eVars that are configured to use Product Syntax are set within the final portion of the products variable. Anta till exempel att en besökare använde en intern nyckelordssökning för att hitta produkt-ID &quot;12345&quot;. Det syntaxbaserade sättet att ställa in eVar1 i det här exemplet skulle se ut så här:

`s.products=";12345;;;;eVar1=internal keyword search";`

Observera att vi fortfarande har semikolonavgränsade platshållare för produktvariabelns kvantitet, intäkter och händelsedelar.  Utan dessa platshållare ignoreras inställningen `eVar1` för intern nyckelordssökning helt.

### Allokering

Termen Allocation för att marknadsföra eVars är vilseledande, särskilt för att marknadsföra eVars som använder konverteringsvariabelsyntax. Alla standardvariabler kan ha en egen allokeringsinställning. Vid försäljning av eVars med konverteringsvariabel syntax används endast allokeringsinställningen &quot;Senaste (senaste)&quot;, oavsett vad som anges i allokeringsinställningarna i Report Suite Manager.

Att förstå vad den här inställningen gör innebär att förstå skillnaden mellan eVar-allokering och att sälja eVar-bindning. För försäljning av eVars är&quot;Merchandising eVar Binding&quot; ett mer passande namn för den här inställningen för&quot;Allocation&quot;.

#### Standardinställning för eVar-allokering

När en eVar med standardsyntax samlas in från en bildbegäran infogar Adobe Analytics bearbetningsservrar data i en annan databaskolumn, som kallas en `post_evar`-kolumn. Eftersom eVars är avsedda att vara beständiga - de upphör att gälla vid något tillfälle efter den aktuella träffen i de flesta fall - anger servrarna den här `post_evar`-kolumnen för varje efterföljande bildbegäran. Den är lika med det sista värdet som skickas till motsvarande eVar. När en lyckad händelse inträffar för standard-eVars använder Adobe Analytics kolumnen `post_evar` i stället för den vanliga eVar-kolumnen för att fastställa det eVar-värde som händelsen ska tilldelas.

För standard-eVars avgör inställningen Allocation om det första eller det sista eVar-värdet som samlades in under en viss period ska infogas i kolumnen `post_evar`. Om allokeringsinställningen för en standard-eVar är lika med &quot;Originalvärde (första)&quot; infogas det första eVar-värdet som samlas in från besökaren i kolumnen `post_evar` för alla efterföljande bildbegäranden. Detta fortsätter för alla framtida förfrågningar som skickas från besökarens webbläsare tills eVar förfaller enligt inställningen&quot;Förfaller efter&quot;.

Om en standardinställning för eVar-allokering är lika med&quot;Senaste (senaste)&quot; fylls det senaste eVar-värdet som samlats in från besökaren i kolumnen `post_evar` för alla efterföljande bildbegäranden. Allokeringen &quot;Senaste (sista)&quot; innebär att värdet `post_evar` ändras varje gång dess motsvarande eVar ställs in på ett nytt värde i en bildbegäran. Allokeringen &quot;Originalvärde (första)&quot; innebär att kolumnen `post_evar` inte ändras i alla träffar även om motsvarande eVar kan anges till ett annat värde i en framtida bildbegäran.

#### Marknadsföringsinställning för eVar-allokering (bindning)

Som vi nämnt tidigare har alla eVars-handlare med konverteringsvariabelsyntax bara allokeringen&quot;Senaste (senaste)&quot;. Därför bestämmer allokeringsinställningen för att marknadsföra eVars inte vilka värden som infogas i kolumnen post_evar när en besökare fortsätter att använda webbplatsen. I stället avgör den här inställningen vilket eVar-värde som binds till en produkt och hur sådana produkter tilldelar sina framgångshändelser tillbaka till de eVar-värden de är bundna till.

Följande inträffar när en inställning för försäljningsallokering (dvs. bindning) för eVar är inställd på &quot;Originalvärde (första): Alla produkter som är inställda bredvid kolumnen post_evar och som inte tidigare har bundits till kolumnen post_evar för motsvarande &quot;förbearbetad&quot; kommer eVar att bindas till värdet i kolumnen post_evar.  Bindningen mellan eVar-värdet och produkten ändras aldrig förrän eVar förfaller enligt inställningen &quot;Förfaller efter&quot; i inställningarna för Report Suite.

Varje gång en bildbegäran uppfyller de kriterier som annars skulle binda en redan bunden produkt till det senast angivna eVar-värdet, tvingar inställningen&quot;Originalvärde (första)&quot; Adobe Analytics datainsamlingsservrar att ignorera alla sådana försök. Motsatsen inträffar när eVars marknadsförs med inställningen Allocation (binding) som är lika med&quot;Most Recent (Last)&quot;. Varje gång en bildbegäran uppfyller villkoren som binder en produkt till en eVar-produkt binds (och binds om) produkten till det senaste värdet som skickats till eVar, eller det värde som (alltid) finns i kolumnen `post_evar`.

Som vi nämnt tidigare kan ni med hjälp av eVars-produkter tilldela framgångsrika event till eVar-värden per produkt istället för per besök/per order. Så när en bunden produkt har en lyckad händelse (till exempel kundvagnstillägg eller kundköp) som är kopplad till den, ger händelsen om att den lyckades sin kredit till både produkten och de eVar-värden som produkten är bunden till vid den tidpunkten.

### Förfaller efter

Med förfalloinställningen för en varuexponering i eVar kan du välja

* När bindningarna för både produkten/eVar ska upphöra att gälla, och

* När kolumnen post_evar inte längre ska fyllas i automatiskt efter att en eVar har skickats in i en bildbegäran.

Förfallotid för en eVar kan inträffa när en lyckad händelse registreras eller när en viss tidsperiod förfaller. Adobe Analytics tillåter endast en förfalloinställning i taget, per eVar.

För produktsökningsmetoden bör det bästa sättet att ange en förfallotid för försäljning som eVar ska vara att ställa in den på lika med

* ANTINGEN hur länge en produkt förvaras i kundvagnen på en webbplats innan sajten automatiskt tar bort den från vagnen (t.ex. 14 dagar, 30 dagar osv.)
* ELLER när köphändelsen äger rum.

Med båda inställningarna tilldelas eventuella produkter som besökaren köper en order-/enhets-/intäktskredit till de försäljningsvärden för eVar som produkterna var bundna till vid den tidpunkten.

### Typ

EVar-typinställningen avgör vilken typ av data som infogas i eVar. I de flesta fall bör det här värdet vara lika med &quot;Text&quot;. Det är sällsynt att använda&quot;Counter&quot; för en försäljning av eVar. &quot;Counter&quot; kan dock användas för att tilldela framgång till Counter eVar-värden per produkt.  Diskussionslösningar med typen &quot;Räknare&quot; omfattas inte av det här dokumentet.

### Marknadsföringsbindningshändelse

Med inställningen för bindningshändelse för marknadsföring kan du ange villkoren för att en produkt ska vara bunden till ett försäljningsvärde för eVar. Dessa villkor är begränsade till aktivering av specifika framgångshändelser eller enbart eVars. Körvariabler (t.ex. props) påverkar inte bindningarna till försäljningen.

Observera att inställningen för bindningshändelse vid marknadsföring kan binda en produkt till ett eVar-värde via mer än en händelse. Exempel:

* Via en produktvyhändelse
* Via en kundvagnstilläggshändelse
* Via en köphändelse

Som standard binds en produkt till ett eVar-värde när någon annan händelse/eVar (försäljning eller standard) ingår i samma bildförfrågan som produkten.

### Återställ

Med inställningen Återställ kan du omedelbart förfalla alla eVar-värden för alla besökare som för närvarande har värdet `post_evar` i Adobe Analytics backend-databas. Alla bindningar till produkter/eVar tas också bort.

>[!IMPORTANT]
>Adobe rekommenderar inte att du använder inställningen Återställ om du inte helt tänker börja om med ett helt &quot;rent lager&quot; med data från den tidpunkt då återställningen utförs.

## Vilka inställningar ska du använda?

Bland de många inställningskombinationer som finns kan du undra vilka inställningar som är bäst?

Om du vill binda&quot;intern nyckelordssökning&quot; till produkt-ID 12345 ställs variabeln products in så här:

`s.products=";12345;;;;eVar1=internal keyword search";`

Alla framgångshändelser (kundvagn lägger till, köp) som hämtas samtidigt som productID 12345 krediteras både produkt-ID 12345 och eVar1-värdet för&quot;intern nyckelordssökning&quot;. Det enda sättet för ett annat eVar1-värde att ta emot krediter för lyckade händelser som är kopplade till produkt-ID 12345 är om eVar1 senare ställs in på ett annat värde i variabeln products (tillsammans med produkt-ID 12345).

Exempel:

```js
s.products=";12345;;;;eVar1=internal campaign";
```

Den här variabelinställningen ändrar bindningen av produkt-ID 12345 från eVar1-värdet för&quot;intern nyckelordssökning&quot; till eVar1-värdet för&quot;intern kampanj&quot;. Den här ombindningsändringen äger också rum när eVar har konfigurerats att använda produktsyntax och inställningen Allocation (binding) för Most Recent (Last). Om inställningen Allocation (binding) i stället var inställd på &quot;Original Value (First)&quot;, kommer inte inställning av eVar1 som &quot;internal campaign&quot; tillsammans med produkt-ID 12345 att binda om produkt-ID 12345 till eVar1-värdet för &quot;internal campaign&quot;. Bindningen behåller i stället det ursprungliga värdet -&quot;intern nyckelordssökning&quot;.

### Problem med att använda produktsyntax

Utan noggrann planering kan flera problem uppstå när du använder produktsyntax. Låt oss ta fallet med att använda flera eVars för att spåra produktsökningsmetoder på webbplatsen. Här måste varje enskild produktsökningsmetod eVar anges samtidigt för att man ska kunna få en viss sökmetod som eVar (och den andra sökmetoden eVars no credit). Produktsyntax kan användas i sådana scenarier, men den resulterande koden för distributionen är mer komplicerad.

Om vi använder vårt ursprungliga&quot;sandaler&quot;-exempel och anpassar det till produktsyntax (förutsatt att besökaren hittade en produkt med ID:t &quot;sandal123&quot; med nyckelordstermen &quot;sandals&quot;) måste den resulterande variabeln anges enligt följande:

`s.products=";sandal123;;;;eVar2=sandals|eVar1=internal search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";`

Syntaxen för variabeln products är lång i det här exemplet, men den binder alla eVar-värden som visas till produkt-ID:t för &quot;sandal123&quot;. Från och med då krediteras alla framgångshändelser (t.ex. kundvagn, inköp) som har tagits samtidigt som&quot;sandal123&quot;-produkten till de eVar-värden som senast var bundna till produkten.  Detta kodexempel visar om ett köp av 1 enhet av&quot;sandal123&quot;-produkten (för 79,95 USD) äger rum efter det att eVars ovan var bunden till&quot;sandal123&quot;-produkten:

```js
s.products=";sandal123;1;79.95";
s.events="purchase";
```

Följande värden skulle alla ha 1 order, 1 enhet och 79,95 USD av intäkter:

* eVar2-värde för&quot;sandaler&quot;
* eVar1-värdet för&quot;intern nyckelordssökning&quot;
* eVar3-värdet för&quot;icke-intern kampanj&quot;
* eVar4-värdet för non-browse
* eVar5-värdet för&quot;non-cross-sell&quot;

Det här är korrekt attribuering, vilket inte är något problem. Det största problemet med den här metoden är snarare att avgöra hur och när produktsökningsmetodens eVars ska anges.

I de flesta fall med produktsyntax måste eVars för produktsökningsmetod anges på en produktinformationssida i stället för på sidan där sökningsmetoden faktiskt användes (t.ex. på sökresultatsidan, bläddringssidan, den interna kampanjstartsidan osv.). Det är rimligt att anta att en produkt inte har&quot;hittats&quot; förrän besökaren interagerar med en produkt i någon utsträckning. Därför bör dessa eVars (med produktsyntax) inte anges på sökmetodsidan eftersom flera produkter (vanligtvis) visas på sådana sidor. Vi vill binda sökmetodvärdet till endast de produkter som besökaren har interagerat med.

När besökarna visar en sökmetodsida kan de dessutom antingen klicka på en länk som leder dem till en enskild produktinformationssida eller lägga till en enskild produkt i kundvagnen direkt från sökmetodsidan. Om en besökare lägger till produkten&quot;sandal123&quot; i kundvagnen direkt från en sökresultatsida med sökord, måste koden för att hämta kundvagnen (via händelsen onClick i knappen Add-to-Cart, osv.) antingen genereras dynamiskt när kundvagnen läggs till eller&quot;kodas&quot; direkt via sidkoden eller ett tagghanteringssystem.  Oavsett vilken kod som ska utlösas i sådana fall skulle koden se ut ungefär så här:

```js
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
s.tl(true,"o","Cart Add")
```

Den här koden binder eVar-värdena ovan till sandal123-produkten. För att kunna ange dessa värden korrekt när klickhändelsen inträffar måste utvecklaren dock:

* Lägg till serversideslogik på sökresultatsidan som bestämmer vilka värden som måste infogas i produktsökningsmetoden eVars, och
* Sammanställ hela produktvariabeln som visas ovan utan syntaxfel.

Om en besökare bestämmer sig för att&quot;hitta&quot; produkten genom att klicka på en länk till produktinformationssidan måste utvecklaren dessutom:

* skicka informationen om produktsökningsmetoden (se ovan) från sökmetodsidan till produktinformationssidan, och
* Återskapa samma variabelvärde för produkter från objekt som just skickats från föregående sida.

### Där produktsyntax är användbar

Produktsyntax är fortfarande användbar när

* Flera produkter med samma produkt-ID interagerar samtidigt.
* De eVars som ska bindas till sådana produkter måste ha olika värden per produkt-ID.

Många klädprodukter har till exempel &quot;Underordnade SKU:er&quot;, som anger storlek, färg, stil och andra attribut. Dessa attribut skiljer en underordnad produkt från andra produkter som tillhör samma överordnade produkt. Säg att du bestämmer dig för att köpa en medelblå t-shirt plus en stor röd t-shirt. Anta att båda skjortorna har det överordnade produkt-ID:t &quot;tshirts123&quot; och att `eVar10` har konfigurerats för att hämta underordnade SKU:er. Variablerna som anges på bekräftelsesidan för inköp ställs in enligt följande:

```js
s.events="purchase";
s.products=";tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red";
```

I det här fallet krediteras båda `eVar10` (childSKU)-värdena för&quot;tshirt123-m-blue&quot; och&quot;tshirt123-l-red&quot; för köp av deras respektive instanser av produkt-ID&quot;tshirt123&quot;.

### Utmaningar med tilldelning av&quot;senaste&quot;

Du kan stöta på ytterligare problem genom att använda inställningen Allokering (bindning) för&quot;Senaste (senaste)&quot;. I många webbläsar-upplevelser&quot;hittar&quot; besökarna en produkt som de redan har tittat på och/eller lagt till i kundvagnen. Detta sker vanligtvis via ett senare besök eller precis innan de bestämmer sig för att slutföra ett köp. Anta att en besökare hittar produkten&quot;sandal123&quot; via nyckelordssökningen i&quot;sandaler&quot; under ett besök på webbplatsen. De lägger omedelbart till den i kundvagnen från sökresultatsidan för nyckelord. Koden som används för att hämta kundvagnen ställs in enligt följande:

```js
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross";
```

Därför är alla eVar-värden som visas i den här bildbegäran bundna till produkten&quot;sandal123&quot;.

Föreställ dig nu att besökaren inte köper produkten under det här besöket, men kommer tillbaka till webbplatsen tre dagar senare med&quot;sandals123&quot;-produkten fortfarande i kundvagnen. Besökaren vill veta mer om produkten innan han genomför köpet. I stället för att söka efter produkten med hjälp av en nyckelordssökning bläddrar besökaren igenom webbplatsen. De slutar med att de handlar i &quot;kvinna > skor > sandaler&quot; och handlar i webbläsaren precis innan de hittar produkten på nytt. När de&quot;hittar om&quot; produktinformationssidan för&quot;sandal123&quot;-produkten ställs variablerna in enligt följande (vid sidinläsning):

```js
s.events="prodView";
s.products=";sandal123;;;;eVar4=womens > shoes > sandals|eVar1=browse|eVar3=non-internal campaign|eVar2=non-search|eVar5=non-cross-sell";
```

Med inställningen Allocation (binding) på&quot;Most Recent (Last)&quot; binds produkten &quot;sandal123&quot; till helt andra eVar-värden än vad den ursprungligen var bunden till. Om besökaren sedan slutför köpet av&quot;sandal123&quot;, ges alla inköpskrediter till dessa nybundna eVar-värden i stället för de värden som ursprungligen var bundna.

Frågan här är: Vilka eVar-värden ska få krediter för köpet?&quot; Kom ihåg att besökaren ursprungligen hittade &quot;sandal123&quot;-produkten via en intern nyckelordssökning. Sedan lade de till den i kundvagnen direkt från sökresultatsidan. Därför bör eVar1-värdet för&quot;intern nyckelordssökning&quot; (och eVar2-värdet för&quot;sandaler&quot;) krediteras köpet. Allokeringsinställningarna (bindning) ställdes in på&quot;Senaste (senaste)&quot;. EVar1-värdet för&quot;browse&quot; (och eVar4-värdet för&quot;kvinna > skor > sandaler&quot;) får i stället inköpskrediten. Orsaken är att de var de sista värdena som var bundna till&quot;sandal123&quot; innan besökaren slutförde köpet.

En lösning på det här problemet är att ändra inställningen Allokering (bindning) för eVar från&quot;Senaste (senaste)&quot; till&quot;Originalvärde (första)&quot;. På så sätt får de ursprungliga eVar-värdena som är bundna till&quot;sandal123&quot;-produkten kredit när köpet äger rum, oavsett hur många gånger besökaren&quot;hittar om&quot; produkten.

Om besökaren lägger till en produkt i kundvagnen men aldrig köper den, tillåter eVar utgångsdatum att ett nytt sökmetodvärde binds till produkten. EVar förfallodatum bör vara lika med den tidpunkt då en webbplats låter en produkt ligga kvar i kundvagnen innan den tas bort automatiskt.

### Använda konverteringsvariabelsyntax

Vi går tillbaka till frågan&quot;Produktsyntax&quot; jämfört med&quot;Konverteringsvariabel syntax&quot;. Adobe har upptäckt en enklare metod för att både samla in produktsökningsmetoden och marknadsföra eVars och binda deras värden till produkter som besökare har hittat: Om du använder konverteringsvariabelsyntax minskas det implementeringsarbete som klientens utvecklare ansvarar för. Den erbjuder fortfarande samma eller bättre information än produktsyntaxmetoden. Utvecklarna behöver bara följa de anvisningar de fått och resten av koden kan läggas in i Adobe AppMeasurement/Adobe Experience Platform Web SDK-filen.

Låt oss till exempel titta på den rekommenderade lösningen för att spåra interna nyckelordssökningsprestanda. Det står att på resultatsidan för nyckelordssökningen hämtar koden nyckelordet som sökts efter via ett steg (till exempel prop4) och ett annat steg (till exempel prop5). De här stegen spårar antalet resultat som visas i sökningen. När en Adobe Analytics-bildbegäran genereras på sökresultatsidan användes datalagretobjekten (eller sidkoden) som utvecklarna använde för att fylla i variablerna ovan (stegen).

Ytterligare logik i AppMeasurement/Adobe Experience Platform Web SDK-filen kan fylla i resten av variablerna (eVars/dimensions) som måste anges samtidigt.\
Om en ny besökare till exempel skulle göra en nyckelordssökning efter&quot;sandaler&quot;, som returnerade 25 resultat på sökresultatsidan, skulle koden som ska aktiveras (via sidkoden ELLER datalagrets hämtning) se ut så här:

```js
s.prop4="sandals";
s.prop5="25";
```

Logiken i AppMeasurement/Analytics SDK-filen kan sedan automatiskt omvandla kodfragmentet till följande:

```js
s.prop4="sandals";
s.prop5="25";
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Du behöver inte bekymra dig om att skicka data från sida till sida och försöka skapa en ganska stor, otymplig sträng som ska infogas i variabeln products. I stället kan utvecklare implementera sin del av spårningslösningarna - det som infogas i propparna - och överlåta resten av implementeringen till den anpassade kod som tillhandahålls av Adobe Consulting.

Som förklarats ovan har alla eVars-produkter som använder konverteringsvariabelsyntax allokeringsinställningen &quot;Senaste (senaste)&quot;. När en eVar har angetts som lika med ett värde kvarstår värdet för alla efterföljande träffar (via kolumnen post_evar). Den kvarstår tills den har ett annat värde eller tills eVar upphör att gälla. Alla produkter som någon interagerar med efter att eVars har angetts binds därför till de värden för&quot;Senaste (senaste)&quot; som skickats till eVar om de inte redan har bundits till dessa eVars.

Med hjälp av exemplet ovan är värdet `eVar2` för&quot;sandals&quot; och eVar1-värdet för&quot;internal keyword search&quot; osv. finns kvar på alla sidor som visas efter att nyckelordssökningen har utförts. De behålls tills eVars skrivs över med andra värden. En besökare klickar på en länk till produktinformationssidan för produkt-ID:t &quot;sandal123&quot; från sökresultatsidan för nyckelord.  Därefter binds produkt-ID:t &quot;sandal123&quot; (om det inte har bundits ännu) till vart och ett av värdena i kolumnerna post_evar eller till de eVar-värden som samlades in från föregående sida (sökresultat).

Det finns en sak till att tänka om för konverteringsvariabelsyntaxen. Bindningshändelser måste ställas in för att ett eVar-värde ska kunna bindas till en produkt. Att bara ställa in en eVar (i sin egen variabel) tillsammans med en produkt (i variabeln products) i en Adobe Analytics-bildförfrågan behöver inte nödvändigtvis binda eVar-värdet till produkten.  Inställningen för bindningshändelse för marknadsföring, som ställs in i Report Suite Manager, avgör i stället villkoren som binder ett eVar-värde till en produkt

Eftersom vi vill binda eVar-värdena för produktsökningsmetoden till produkter när en produktinteraktion sker - vilket innebär att en produkt har hittats - är det säkert att anta att de vanligaste&quot;produktinteraktionerna&quot; som kan äga rum antingen är en produktvy (när besökarna går till en produktinformationssida) eller en kundvagn (när besökarna lägger till en produkt i kundvagnen direkt från en produktsökningssida).

Därför kan vi välja dessa två händelser (prodView, scAdd) som de&quot;grundläggande&quot; bindningshändelserna för varuexponering.
Här är vad som händer när någon av dessa bindningshändelser ingår i en bildbegäran. Alla produkt-ID:n som finns i samma begäran (inom variabeln products) och som inte har bundits till en varuexponering, kommer att bindas till de senaste värdena som skickas till eVar (kolumnerna post_evar). Alla försök att binda om dessa produkter efter att den ursprungliga bindningen har gjorts ignoreras när inställningen Allocation (binding) har angetts till Original Value (First).

### Inställningar för bästa praxis

Här följer de bästa metoderna. De implementerar enkelt metoden för produktsökning med bästa resultat. Adobe rekommenderar att kunderna konfigurerar sina produktsökningsmetoder för marknadsföring av eVars (i allmänhet) enligt följande:

* Marknadsföring aktiverad: Aktiverad
* Marknadsföring av [syntax]: Konverteringsvariabelsyntax
* Allokering [bindning]: Ursprungligt värde (första)
* Förfaller efter: Den tid en produkt stannar i en kundvagn innan den tas bort automatiskt (t.ex. 14 dagar, 30 dagar osv.).  Om det inte finns någon sådan tid, förfaller du efter köphändelsen
* Typ: Text
* Marknadsföringsbindningshändelser: produktvy, kundvagn, tillägg och inköp

## Vad gör Binding Events egentligen?

När en bindningshändelse finns i samma serveranrop som produktvariabeln binder Merchandising eVar-värdena (med hjälp av konverteringsvariabelsyntax) i sin post-kolumn till produktvariabeln. Utifrån det tidigare exemplet antar vi att ett serveranrop innehåller följande värden för Merchandising eVar:

```js
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Som förklarats tidigare kvarstår de ovanstående eVars-variablerna utanför den aktuella träffen via deras respektive post_evar-kolumn. Därför omvandlar Adobe servrar eVars ovan till följande:

```js
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Dessa inläggskolumner lagras i Adobe-databasen och finns kvar efter den aktuella träffen där de ursprungligen angavs. Detta förutsätter att det inte sker någon återställning av förfallodatum eller variabel.  Adobe-servrar har dessa post_evar-värden &quot;tillgängliga&quot; när de bearbetar eventuella framtida serveranrop som innehåller både bindningshändelsen och produktvariabeln.

Bindningen som äger rum är endast mellan dessa post_evar-värden och innehållet i variabeln products. Bindningshändelsen&quot;binder&quot; inte nödvändigtvis till varken eVars- eller produktvariabeln. Det är&quot;katalysatorn&quot; som instruerar Adobe-servrarna att binda värdena post_evar till produkterna.

Anta att följande variabler ställs in för en framtida träff:

```js
s.products=";sandals123"
s.events="prodView";
```

I kolumnerna post_evar ser Adobe bearbetningsservrar den här träffen på följande sätt:

```js
s.products=";sandals123";
s.events="prodView";
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Anta att eVar1, eVar2, eVar3, eVar4 och eVar5 har konfigurerats att använda `prodView` som en bindningshändelse. Om någon av dessa eVars inte är konfigurerad att använda prodView som en bindningshändelse sker ingen bindning mellan denna (felkonfigurerade) eVar och produktvariabeln.

Bindning ger mycket intressanta resultat, som visas i kolumnen post_products. Bindningen omformar ovanstående kod och ställer in några fler postkolumner enligt följande:

```js
post_events="prodView";
post_products=";sandals123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
```

Värdet i kolumnen post_products kanske är välbekant för dig. Bläddra uppåt i det här dokumentet och jämför värdet post_products och värdet s.products enligt nedan. Observera att kolumnen post_products är inställd med produktvariabelsyntax!

Detta innebär att Binding &quot;kopierar&quot; eVar-värden för Conversion Variable Syntax till produktvariabeln via Product Syntax. Den här kopieringsåtgärden utförs endast när produktvariabeln och en bindningshändelse (som anges via eVar-konfigurationen) finns i samma begäran. Då är värdena i kolumnen post_eVar bundna till produkten. Den här bindningen representeras via produktsyntax som lagras i kolumnen post_products.

## Merchandising eVars, the Instances metric, and Attribution

När en standard-eVar skickas i ett Analytics-serveranrop får värdet i kolumnen post_evar alltid en instans som tillskrivs det. Förekomster representerar det antal gånger som en eVar har ställts in som lika med ett visst värde i en bildbegäran.

Anta till exempel att `eVar10` är en standard-eVar med [!UICONTROL Last Touch]-attribuering. Om du anger `s.eVar10="hello world"` på en sida skickas värdet för hello world till kolumnen post_evar10 när Adobe bearbetar träffen. Instansmåttet är lika med &quot;1&quot; för varje enskild `eVar10`-inställning av `hello world`. Tänk på att en instans inte alltid spelas in när kolumnen post_evar har ett värde. I stället avgör kolumnen post_evar vilket värde som hämtar instansen när en instans spelas in.

Instanser för en varuexponering eVar tilldelar attribuering till de värden som eVar samlar in. Men detta händer bara när en produkt som var bunden till eVar-värdet på marknaden&quot;interagerar&quot; med samtidigt.

Om du till exempel ställer in `s.eVar1="Internal Keyword Search"` i sig får ingen instans-metrisk kredit till eVar1-värdet för&quot;Intern nyckelordssökning&quot;. En instans registreras vid den punkten. Om en produkt inte är bunden till det interna nyckelordssökningsvärdet samtidigt som `eVar1` anges, kommer instansen att tilldelas till den ospecificerade bucket. Värdet `eVar1` för Intern nyckelordssökning kan med andra ord hämta en instans. Men detta händer bara när en produkt som är bunden till värdet för &quot;Intern nyckelordssökning&quot; visas i produktvariabeln i samma bildbegäran.

Utan ytterligare konfigurationer är alltså det färdiga instansmåttet för en eVar-produkt inte alls användbart. Som tur är släppte Adobe [Attribution](/help/analyze/analysis-workspace/attribution/overview.md). Det gör att du kan använda flera attribueringsmodeller för alla anpassade mätvärden som Adobe Analytics samlar in. Mätvärden som tillämpar dessa attribueringsmodeller använder inte värdena i kolumnerna post_evar eller värdena som är bundna till en viss produkt. I stället används endast de värden som skickas via själva bildbegäran (eller värden som hämtas via Adobe Analytics bearbetningsregler). Du kan använda funktionerna i Attribution för att få ett korrekt tilldelat instansmått för alla eVars-handlare som använder konverteringsvariabelsyntax.

![Attribution select](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/assets/attribution-select.png)

När du lägger till ett instansmått för en försäljning av eVar i en rapport blir rätt attribueringsmodell&quot;Last Touch&quot;-modellen. Inställningen för fönstret Sök efter för modellen spelar ingen roll i det här fallet. Orsaken är att en&quot;tvingad&quot; Last Touch-attribueringsmodell alltid ger instanskrediter till varje enskilt värde som skickas via en begäran. Detta är oavsett om de faktiska attributerings-/bindningsinställningarna för eVar är lika med &quot;Senaste (senaste)&quot; till &quot;Originalvärde (första)&quot;.
