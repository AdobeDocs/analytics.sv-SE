---
title: Merchandising eVars and Product Finding Methods
description: En djupdykning i begreppen bakom försäljning av eVars och hur de bearbetar och allokerar data.
feature: Admin Tools
exl-id: 9e1a39aa-451f-49bb-8e39-797b6bbd5499
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '5254'
ht-degree: 0%

---

# Merchandising eVars and product finding methods

I det här mycket detaljerade dokumentet förklaras begreppen bakom försäljning av eVars, som bearbetar och tilldelar data på ett annat sätt än vanliga eVars. Det förklarar också hur eVars marknadsför produktsökningsmetoder.

## Översikt

Med hjälp av eVars kan ni allokera alla framgångsrika aktiviteter till de värden som hämtas av eVars på en *per produkt* nivå i stället för *per besök/per beställning* nivå.

Även om de flesta webbplatser för detaljhandeln har många sätt att hitta produkter anser Adobe att följande är de grundläggande metoder för produktupptäckt som alla kunder inom detaljhandeln bör följa i Adobe Analytics:

* Interna söknyckelord
* Interna koder för kampanjspårning
* Marknadsföring/bläddringskategorier
* Merförsäljning av länkar

I det här dokumentet kan vi mappa några eVars till lösningarna enligt följande:

* eVar2: Interna söknyckelord
* eVar3: Intern kampanjspårningskoder
* eVar4: Kategorier för marknadsföring/sökning
* eVar5: Korsförsäljning

Vi kan använda en extra eVar för att mäta resultatet av alla produktsökningsmetoder i förhållande till varandra. Förutom de sökmetoder som beskrivs ovan innehåller eVarna andra sökmetoder i jämförelsen, t.ex. länkar till produktinformationssidor från externa webbplatser.

* eVar1: Sökmetoder

I stället för att konfigurera variablerna så att de blir standard-eVars, ska du konfigurera dem så att de marknadsför eVars.

För att visa hur du ställer in dessa variabler finns det ett exempel där en besökare bestämmer sig för att använda de interna söksandalerna för nyckelord för att hitta en produkt på webbplatsen. På sidan med sökresultat för nyckelord måste du hämta data i minst två eVars:

* `eVar2` är lika med nyckelordet som användes i sökningen (&quot;sandaler&quot;)
* `eVar1` är lika med den sökmetod som används (&quot;intern nyckelordssökning&quot;).

När du ställer in dessa två variabler som är lika med dessa specifika värden, vet du att besökaren använder det interna nyckelordssökordet för&quot;sandaler&quot; för att hitta en produkt. Samtidigt vet du att besökaren inte använder de andra produktsökningsmetoderna för att hitta produkter (besökaren bläddrar till exempel inte igenom produktkategorier exakt samtidigt som de gör en nyckelordssökning). För att säkerställa att rätt tilldelning sker per produkt bör dessa oanvända metoder inte få någon uppskattning för att hitta en produkt som hittats via en intern nyckelordssökning. Du måste därför infoga logik i koden (som AppMeasurement, Adobe Experience Platform Web SDK och så vidare) som automatiskt anger de eVars som är associerade med dessa andra sökmetoder som lika med ett icke-sökmetod-värde.

När en användare t.ex. söker efter produkter med nyckelordet &quot;sandals&quot;, ska Analytics-kodens logik ange de variabler som är lika med följande på den interna sökresultatsidan för nyckelord:

* eVar2=&quot;sandaler&quot;: nyckelordet&quot;sandaler&quot; användes i den interna nyckelordssökningen
* eVar1=&quot;intern nyckelordssökning&quot;: sökmetoden&quot;intern nyckelordssökning&quot; användes
* eVar3=&quot;icke-intern kampanj&quot;: ingen intern kampanj användes för att komma åt sökresultatsidan
* eVar4=&quot;non-browse&quot;: ingen bläddringskategori fanns på sökresultatsidan
* eVar5=&quot;non-cross-sell&quot;: en korsförsäljningslänk klickades inte på sökresultatsidan

## Inställningar för eVars

Här är de olika inställningarna som du kan använda med dina eVars-produkter. Följande skärmbild kommer från Report Suite Manager. Öppna den genom att gå till [!UICONTROL Analytics] > [!UICONTROL Admin] > [!UICONTROL Report Suites] > [!UICONTROL Edit Settings] > [!UICONTROL Conversion] > [!UICONTROL Conversion Variables] > [!UICONTROL Add new] > [!UICONTROL Enable Merchandising].

![Merch eVars](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/assets/merch-evars1.png)

Mer information om de här inställningarna finns i avsnitten nedanför tabellen.

| Inställning | Beskrivning |
|--- | --- |
| Namn | The Name, or the reporting dimension that the variable is intended to be associated with. If `eVar1` används för att hämta produktsökningsmetoder och sedan namnfältet för `eVar1` ska anges till &quot;Product Finding Methods&quot;. |
| Merchandising | Den typ av syntax som ska användas för att hämta eVar för varuexponering |
| Allokering | Hjälper till att avgöra vilket värde för eVar som ska få krediter när en lyckad händelse inträffar. |
| Förfaller efter | Avgör när befintliga bindningar för eVar och försäljning inte längre ska gälla. |
| Typ | Den typ av uppgifter som samlas in i eVarna för marknadsföring |
| Marknadsföringsbindningshändelse | Händelsen/händelserna som avgör när en produkt ska bindas till ett försäljningsvärde för eVar |
| Återställ | En utlösare som återställer alla backend-data för eVarna vid den tidpunkten |
| Aktivera marknadsföring | En flagga som måste ställas in på&quot;Aktiverad&quot; för att omvandla eVarna från en standardeVar till en Merchandising-eVar |

### Aktivera marknadsföring

När inställningen Aktivera marknadsföring är aktiverad visas alla inställningar som beskrivs nedan i Report Suite Manager. När inställningen &quot;Aktivera marknadsföring&quot; är &quot;Inaktiverad&quot; är endast standardinställningarna för eVar tillgängliga.

### Merchandising

Det här alternativet är inte tillgängligt för standard-eVars. The [!UICONTROL Merchandising] med den här inställningen kan du välja [!UICONTROL Conversion Variable Syntax] eller [!UICONTROL Product Syntax] som en metod för att fånga eVarnas värde.

**[!UICONTROL Conversion Variable Syntax]** innebär att du anger eVar-värdet i en egen variabel. Om du t.ex. använder Konvertera variabelsyntax `eVar1` värdet för&quot;intern nyckelordssökning&quot; anges enligt följande i sidkoden (eller i AppMeasurementet, Adobe Experience Platform Web SDK-koden och så vidare):

`s.eVar1="internal keyword search";`

Med **[!UICONTROL Product Syntax]** eVarna anges dock endast i variabeln Adobe Analytics-produkter. Variabeln Analytics-produkter är uppdelad i sex olika delar per produkt:

`s.products="[category];[name];[quantity];[revenue];[events];[eVars]"`

* [!UICONTROL Category] och [!UICONTROL Name] identifiera den angivna produkten.
* [!UICONTROL Quantity] och [!UICONTROL Revenue] är användbara när ett produktköp spåras.
* [!UICONTROL Events] är användbart för att registrera anpassade stegvisa värden eller valutakäntehändelser som inte ska räknas som intäkter (t.ex. frakt, rabatter)

Merchandising eVars that are configured to use Product Syntax are set within the final portion of the products variable. Anta till exempel att en besökare använde en intern nyckelordssökning för att hitta produkt-ID &quot;12345&quot;. Det syntaxbaserade sättet att ställa in eVar1 i det här exemplet skulle se ut så här:

`s.products=";12345;;;;eVar1=internal keyword search";`

Observera att vi fortfarande har semikolonavgränsade platshållare för produktvariabelns kvantitet, intäkter och händelsedelar.  Utan dessa platshållare `eVar1` inställningen för intern nyckelordssökning ignoreras fullständigt.

### Allokering

Termen Allocation för att marknadsföra eVars är vilseledande, särskilt för att marknadsföra eVars som använder konverteringsvariabelsyntax. Alla standardvariabler kan ha en egen allokeringsinställning. Vid försäljning av eVars med konverteringsvariabel syntax används endast allokeringsinställningen &quot;Senaste (senaste)&quot;, oavsett vad som anges i allokeringsinställningarna i Report Suite Manager.

Att förstå vad den här inställningen gör innebär att förstå skillnaden mellan eVar-allokering och bindning för eVar. För försäljning av eVars är&quot;Merchandising eVar Binding&quot; ett mer passande namn för denna&quot;Allocation&quot;-inställning.

#### Standardinställning för allokering av eVar

När en eVar med standardsyntax samlas in från en bildbegäran infogar Adobe Analytics bearbetningsservrar data i en annan databaskolumn, som kallas `post_evar` kolumn. Eftersom eVars är avsedda att vara beständiga - de upphör att gälla vid något tillfälle efter den aktuella träffen i de flesta fall - anger servrarna detta `post_evar` -kolumn vid varje efterföljande bildbegäran. Den ställs in som lika med det sista värdet som skickas till dess motsvarande eVar. När en lyckad händelse inträffar för standard-eVars använder Adobe Analytics `post_evar` i stället för den vanliga eVar-kolumnen för att fastställa det eVar-värde som ska tilldelas för händelsen.

För standard-eVars avgör inställningen Allocation om det första eller sista eVarna som samlades in under en viss period ska infogas i `post_evar` kolumn. Om allokeringsinställningen för en standard-eVar är lika med &quot;Originalvärde (första)&quot; infogas det första eVar-värdet som samlas in från besökaren i `post_evar` -kolumn för alla efterföljande bildbegäranden. Detta fortsätter för alla framtida förfrågningar som skickas från besökarens webbläsare tills eVarna förfaller enligt inställningen&quot;Förfaller efter&quot;.

Om en standardinställning för Allokering är lika med &quot;Senaste (senaste)&quot;, fylls det senaste eVarna som samlats in från eVarna i `post_evar` -kolumn för alla efterföljande bildbegäranden. Allokeringen &quot;Senaste (sista)&quot; innebär att `post_evar` värdet ändras varje gång dess motsvarande eVar anges till ett nytt värde i en bildbegäran. &quot;Originalvärde (första)&quot;-allokeringen innebär att `post_evar` -kolumnen ändras inte över flera träffar även om motsvarande eVar kan anges till ett annat värde i en framtida bildbegäran.

#### Inställningar för allokering av eVar (bindning) för marknadsföring

Som vi nämnt tidigare har alla eVars-handlare med konverteringsvariabelsyntax bara allokeringen&quot;Senaste (senaste)&quot;. Därför bestämmer allokeringsinställningen för att marknadsföra eVars inte vilka värden som infogas i kolumnen post_evar när en besökare fortsätter att använda webbplatsen. I stället avgör den här inställningen vilket eVar-värde som binds till en produkt och hur sådana produkter allokerar sina lyckade händelser tillbaka till de eVar de är bundna till.

Följande inträffar när en allokeringsinställning (dvs. bindning) för en eVar anges som &quot;Originalvärde (första): Alla produkter som anges bredvid kolumnen post_evar och som inte tidigare har bundits till kolumnen post_evar för motsvarande &quot;förbearbetad&quot; eVar binds till värdet i kolumnen post_evar.  Denna bindning mellan eVar och produkt ändras aldrig förrän eVarna förfaller enligt inställningen &quot;Förfaller efter&quot; i inställningarna för Report Suite.

Varje gång en bildbegäran uppfyller de kriterier som annars skulle binda en redan bunden eVar till det senast angivna värdet, tvingar inställningen Originalvärde (första) Adobe Analytics datainsamlingsservrar att ignorera alla sådana försök att göra det. Motsatsen inträffar när eVars marknadsförs med inställningen Allocation (binding) som är lika med&quot;Most Recent (Last)&quot;. Varje gång en bildbegäran uppfyller villkoren som binder en produkt till en eVar binds (och binds om) produkten till det senaste värdet som skickats till eVarna, eller det värde som (alltid) finns i `post_evar` kolumn.

Som vi nämnt tidigare kan ni med hjälp av eVars-produkter tilldela framgångsrika event till eVar-värden per produkt i stället för per besök/per beställning. Så när en bunden produkt har en lyckad händelse (till exempel kundvagnstillägg eller kundköp) som är kopplad till den, ger händelsen om att den lyckades sin kredit till både produkten och de värden för eVar som produkten är bunden till vid den tidpunkten.

### Förfaller efter

Med förfalloinställningen för en eVar kan du välja

* När både produkt- och eVar-bindningarna ska upphöra att gälla, och

* När kolumnen post_evar inte längre ska fyllas i automatiskt efter att en eVar har skickats in i en bildbegäran.

EVarna kan förfalla när en lyckad händelse registreras eller när en viss tidsperiod förfaller. Adobe Analytics tillåter endast en förfalloinställning i taget, per eVar.

För produktsökningsmetoden bör det bästa sättet att ange en eVars förfallotid vara att ställa in den som lika med

* ANTINGEN hur länge en produkt förvaras i kundvagnen på en webbplats innan sajten automatiskt tar bort den från vagnen (t.ex. 14 dagar, 30 dagar osv.)
* ELLER när köphändelsen äger rum.

Med båda inställningarna tilldelas eventuella produkter som besökaren köper en kreditering för order/enhet/intäkt till de värden för eVar som produkterna var bundna till vid den tidpunkten.

### Typ

Inställningen för datatyp avgör vilken typ av eVar som infogas i eVarna. I de flesta fall bör det här värdet vara lika med &quot;Text&quot;. Det är sällsynt att använda &quot;Counter&quot; för en eVar som handlar. &quot;Räknare&quot; kan dock användas för att fördela lyckade resultat till motvärden för eVar per produkt.  Diskussionslösningar med typen &quot;Räknare&quot; omfattas inte av det här dokumentet.

### Marknadsföringsbindningshändelse

Med inställningen för bindningshändelse för marknadsföring kan du ange villkoren för att en produkt ska bindas till värdet av en eVar. Dessa villkor är begränsade till aktivering av specifika framgångshändelser eller enbart eVars. Körvariabler (t.ex. props) påverkar inte bindningarna till försäljningen.

Observera att inställningen för bindningshändelse vid marknadsföring kan binda en produkt till ett eVar-värde via mer än en händelse. Exempel:

* Via en produktvyhändelse
* Via en kundvagnstilläggshändelse
* Via en köphändelse

Som standard binder inställningen en eVar till ett försäljningsvärde när någon annan händelse/eVar (försäljning eller standard) ingår i samma bildförfrågan som produkten.

### Återställ

Med inställningen Återställ kan du omedelbart &quot;förfalla&quot; alla eVar för alla besökare som har en `post_evar` i Adobe Analytics backend-databas. Dessutom elimineras alla nuvarande bindningar för produkt/eVar.

>[!IMPORTANT]
>Adobe rekommenderar inte att du använder inställningen Återställ om du inte helt tänker börja om med ett helt &quot;rent lager&quot; med data från den tidpunkt då återställningen utförs.

## Vilka inställningar ska du använda?

Bland de många inställningskombinationer som finns kan du undra vilka inställningar som är bäst?

Om du vill binda&quot;intern nyckelordssökning&quot; till produkt-ID 12345 ställs variabeln products in så här:

`s.products=";12345;;;;eVar1=internal keyword search";`

Alla framgångshändelser (kundvagn lägger till, köp) som hämtas samtidigt som productID 12345 krediteras både produkt-ID 12345 och eVar1-värdet för&quot;intern nyckelordssökning&quot;. Det enda sättet för ett annat eVar1-värde att ta emot krediter för lyckade händelser som är kopplade till produkt-ID 12345 är om eVar1 senare ställs in på ett annat värde i produktvariabeln (tillsammans med produkt-ID 12345).

Exempel:

```js
s.products=";12345;;;;eVar1=internal campaign";
```

Den här variabelinställningen ändrar bindningen för produkt-ID 12345 från eVar1-värdet för&quot;intern nyckelordssökning&quot; till eVar1-värdet för&quot;intern kampanj&quot;. Den här ombindningsändringen sker även när eVarna har konfigurerats att använda produktsyntax och inställningen Allokering (bindning) för&quot;Senaste (senaste)&quot;. Om inställningen Allocation (binding) i stället var inställd på &quot;Original Value (First)&quot; kommer det inte att binda om produkt-ID 12345 till eVar1-värdet för &quot;internal campaign&quot; om eVar1 är lika med &quot;internal campaign&quot;. Bindningen behåller i stället det ursprungliga värdet -&quot;intern nyckelordssökning&quot;.

### Problem med att använda produktsyntax

Utan noggrann planering kan flera problem uppstå när du använder produktsyntax. Låt oss ta fallet med att använda flera eVars för att spåra produktsökningsmetoder på webbplatsen. Här måste varje enskild eVar av produktsökningsmetod anges samtidigt för att ge en särskild resultatmetods eVar-kredit (och den andra sökmetoden eVars utan kredit). Produktsyntax kan användas i sådana scenarier, men den resulterande koden för distributionen är mer komplicerad.

Om vi använder vårt ursprungliga&quot;sandaler&quot;-exempel och anpassar det till produktsyntax (förutsatt att besökaren hittade en produkt med ID:t &quot;sandal123&quot; med nyckelordstermen &quot;sandals&quot;) måste den resulterande variabeln anges enligt följande:

`s.products=";sandal123;;;;eVar2=sandals|eVar1=internal search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";`

Syntaxen för variabeln products är lång i det här exemplet, men den binder alla eVar-värden som visas till produkt-ID:t för &quot;sandal123&quot;. Därefter krediteras alla framgångshändelser (t.ex. kundvagnstillägg, inköp) som har hämtats samtidigt som&quot;sandal123&quot;-produkten till de eVar som senast var bundna till produkten.  Detta kodexempel visar om ett köp av 1 enhet av&quot;sandal123&quot;-produkten (för 79,95 USD) äger rum efter det att eVars ovan var bunden till&quot;sandal123&quot;-produkten:

```js
s.products=";sandal123;1;79.95";
s.events="purchase";
```

Följande värden skulle alla ha 1 order, 1 enhet och 79,95 USD av intäkter:

* eVar2-värdet för &quot;sandaler&quot;
* eVar1-värdet för&quot;intern nyckelordssökning&quot;
* eVar3-värdet för&quot;icke-intern kampanj&quot;
* eVar4-värdet för non-browse
* eVar5-värdet av&quot;icke-korsförsäljning&quot;

Det här är korrekt attribuering, vilket inte är något problem. Det största problemet med den här metoden är snarare att avgöra hur och när produktsökningsmetodens eVars ska anges.

I de flesta fall med produktsyntax måste eVars för produktsökningsmetod anges på en produktinformationssida i stället för på sidan där sökningsmetoden faktiskt användes (t.ex. på sökresultatsidan, bläddringssidan, den interna kampanjstartsidan osv.). Det är rimligt att anta att en produkt inte har&quot;hittats&quot; förrän besökaren interagerar med en produkt i någon utsträckning. Därför bör dessa eVars (med produktsyntax) inte anges på sökmetodsidan eftersom flera produkter (vanligtvis) visas på sådana sidor. Vi vill binda sökmetodvärdet till endast de produkter som besökaren har interagerat med.

När besökarna visar en sökmetodsida kan de dessutom antingen klicka på en länk som leder dem till en enskild produktinformationssida eller lägga till en enskild produkt i kundvagnen direkt från sökmetodsidan. Om en besökare lägger till produkten&quot;sandal123&quot; i kundvagnen direkt från en sökresultatsida med sökord, använder du nyckelordsexemplet&quot;sandal123&quot;, koden för att hämta kundvagnen (via händelsen onClick för knappen Lägg till i kundvagnen, etc) måste antingen genereras dynamiskt när kundvagnen läggs till eller kodas direkt via sidkoden eller ett tagghanteringssystem.  Oavsett vilken kod som ska utlösas i sådana fall skulle koden se ut ungefär så här:

```js
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
s.tl(true,"o","Cart Add")
```

Den här koden binder de eVar-värden som visas ovan till&quot;sandal123&quot;-produkten. För att kunna ange dessa värden korrekt när klickhändelsen inträffar måste utvecklaren dock:

* Lägg till serversideslogik på sökresultatsidan som bestämmer vilka värden som måste infogas i produktsökningsmetoden eVars, och
* Sammanställ hela produktvariabeln som visas ovan utan syntaxfel.

Om en besökare bestämmer sig för att&quot;hitta&quot; produkten genom att klicka på en länk till produktinformationssidan måste utvecklaren dessutom:

* skicka informationen om produktsökningsmetoden (se ovan) från sökmetodsidan till produktinformationssidan, och
* Återskapa samma variabelvärde för produkter från objekt som just skickats från föregående sida.

### Där produktsyntax är användbar

Produktsyntax är fortfarande användbar när

* Flera produkter med samma produkt-ID interagerar samtidigt.
* De eVars som ska bindas till sådana produkter måste ha olika värden per produkt-ID.

Många klädprodukter har till exempel &quot;Underordnade SKU:er&quot;, som anger storlek, färg, stil och andra attribut. Dessa attribut skiljer en underordnad produkt från andra produkter som tillhör samma överordnade produkt. Säg att du bestämmer dig för att köpa en medelblå t-shirt plus en stor röd t-shirt. Anta att båda skjortorna har det överordnade produkt-ID:t &quot;tshirts123&quot; och `eVar10` har konfigurerats för att hämta underordnade SKU:er. Variablerna som anges på bekräftelsesidan för inköp ställs in enligt följande:

```js
s.events="purchase";
s.products=";tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red";
```

I det här fallet `eVar10` (childSKU)-värden för&quot;tshirt123-m-blue&quot; och&quot;tshirt123-l-red&quot; krediteras vid köp av respektive förekomst av produkt-ID&quot;tshirt123&quot;.

### Utmaningar med tilldelning av&quot;senaste&quot;

Du kan stöta på ytterligare problem genom att använda inställningen Allokering (bindning) för&quot;Senaste (senaste)&quot;. I många webbläsar-upplevelser&quot;hittar&quot; besökarna en produkt som de redan har tittat på och/eller lagt till i kundvagnen. Detta sker vanligtvis via ett senare besök eller precis innan de bestämmer sig för att slutföra ett köp. Anta att en besökare hittar produkten&quot;sandal123&quot; via nyckelordssökningen i&quot;sandaler&quot; under ett besök på webbplatsen. De lägger omedelbart till den i kundvagnen från sökresultatsidan för nyckelord. Koden som används för att hämta kundvagnen ställs in enligt följande:

```js
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross";
```

Därför är alla värden för eVar som visas i den här bildbegäran bundna till produkten&quot;sandal123&quot;.

Föreställ dig nu att besökaren inte köper produkten under det här besöket, men kommer tillbaka till webbplatsen tre dagar senare med&quot;sandals123&quot;-produkten fortfarande i kundvagnen. Besökaren vill veta mer om produkten innan han genomför köpet. I stället för att söka efter produkten med hjälp av en nyckelordssökning bläddrar besökaren igenom webbplatsen. De slutar med att de handlar i &quot;kvinna > skor > sandaler&quot; och handlar i webbläsaren precis innan de hittar produkten på nytt. När de&quot;hittar om&quot; produktinformationssidan för&quot;sandal123&quot;-produkten ställs variablerna in enligt följande (vid sidinläsning):

```js
s.events="prodView";
s.products=";sandal123;;;;eVar4=womens > shoes > sandals|eVar1=browse|eVar3=non-internal campaign|eVar2=non-search|eVar5=non-cross-sell";
```

Med inställningen Allocation (binding) på &quot;Most Recent (Last)&quot; binds produkten &quot;sandal123&quot; till helt andra eVar än vad den ursprungligen var bunden till. Om besökaren sedan slutför köpet av&quot;sandal123&quot;, ges alla inköpskrediter till dessa nybundna eVar i stället för de ursprungligen bundna värdena!

Frågan här är: Vilka eVar ska få krediter för köpet?&quot; Kom ihåg att besökaren ursprungligen hittade &quot;sandal123&quot;-produkten via en intern nyckelordssökning. Sedan lade de till den i kundvagnen direkt från sökresultatsidan. Därför bör eVar1-värdet för&quot;intern nyckelordssökning&quot; (och eVar2-värdet för&quot;sandaler&quot;) få krediter för köpet. Allokeringsinställningarna (bindning) ställdes in på&quot;Senaste (senaste)&quot;. EVar1-värdet för &quot;browse&quot; (och eVar4-värdet för &quot;kvinna > skor > sandaler&quot;) får i stället inköpskrediten. Orsaken är att de var de sista värdena som var bundna till&quot;sandal123&quot; innan besökaren slutförde köpet.

En lösning på det här problemet är att ändra inställningen Allokering (bindning) för eVarna från&quot;Senaste (senaste)&quot; till&quot;Ursprungligt värde (första)&quot;. På så sätt får de ursprungliga eVarna som är bundna till&quot;sandal123&quot;-produkten kredit när köpet äger rum, oavsett hur många gånger besökaren&quot;hittar om&quot; produkten.

Om besökaren lägger till en produkt i kundvagnen men aldrig köper den, kan ett nytt sökmetodvärde bindas till eVarna. EVarnas utgångsdatum bör vara lika med den tidpunkt då en webbplats låter en produkt vara kvar i kundvagnen innan den tas bort automatiskt.

### Använda konverteringsvariabelsyntax

Vi går tillbaka till frågan&quot;Produktsyntax&quot; jämfört med&quot;Konverteringsvariabel syntax&quot;. Adobe har upptäckt en enklare metod för att både samla in produktsökningsmetoden och marknadsföra eVars och binda deras värden till produkter som besökare har hittat: Om du använder konverteringsvariabelsyntax minskas det implementeringsarbete som klientens utvecklare ansvarar för. Den erbjuder fortfarande samma eller bättre information än produktsyntaxmetoden. Utvecklarna behöver bara följa de distributionsanvisningar de fått, och resten av koden kan placeras i Adobe AppMeasurement/Adobe Experience Platform Web SDK-filen.

Låt oss till exempel titta på den rekommenderade lösningen för att spåra interna nyckelordssökningsprestanda. Det står att på resultatsidan för nyckelordssökningen hämtar koden nyckelordet som sökts efter via ett steg (till exempel prop4) och ett annat steg (till exempel prop5). De här stegen spårar antalet resultat som visas i sökningen. När en Adobe Analytics-bildbegäran genereras på sökresultatsidan användes datalagretobjekten (eller sidkoden) som utvecklarna använde för att fylla i variablerna ovan (stegen).

Ytterligare logik i AppMeasurementet/Adobe Experience Platform Web SDK-filen kan fylla i resten av variablerna (eVars/dimensions) som måste anges samtidigt.\
Om en ny besökare till exempel skulle göra en nyckelordssökning efter&quot;sandaler&quot;, som returnerade 25 resultat på sökresultatsidan, skulle koden som ska aktiveras (via sidkoden ELLER datalagrets hämtning) se ut så här:

```js
s.prop4="sandals";
s.prop5="25";
```

Logiken i AppMeasurement-/Analytics SDK-filen kan sedan automatiskt omvandla kodfragmentet till följande:

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

Som förklarats ovan har alla eVars-produkter som använder konverteringsvariabelsyntax allokeringsinställningen &quot;Senaste (senaste)&quot;. När en eVar har angetts som lika med ett värde kvarstår värdet för alla efterföljande träffar (via kolumnen post_evar). Den kvarstår tills den har ett annat värde eller tills eVarna förfaller. Alla produkter som någon interagerar med efter att eVars har angetts binds därför till värdena&quot;Senaste (senaste)&quot; som skickats till eVarna om de inte redan har bundits till dessa eVars.

Med hjälp av exemplet ovan `eVar2` värdet för&quot;sandals&quot; och eVar1-värdet för&quot;internal keyword search&quot;, osv. finns kvar på alla sidor som visas efter att nyckelordssökningen har utförts. De behålls tills eVars skrivs över med andra värden. En besökare klickar på en länk till produktinformationssidan för produkt-ID:t &quot;sandal123&quot; från sökresultatsidan för nyckelord.  Därefter binds produkt-ID:t &quot;sandal123&quot; (om det inte har bundits ännu) till vart och ett av värdena i kolumnerna post_evar eller till de eVar som samlades in från den föregående (sökresultatsidan).

Det finns en sak till att tänka om för konverteringsvariabelsyntaxen. Bindningshändelser måste ställas in för att ett eVar-värde ska kunna bindas till en produkt. Att bara ställa in en eVar (i sin egen variabel) tillsammans med en produkt (i variabeln products) i en Adobe Analytics-bildbegäran behöver inte nödvändigtvis binda eVarna till produkten.  Inställningen för bindningshändelse för marknadsföring, som ställs in i Report Suite Manager, avgör i stället vilka villkor som binder ett eVar-värde till en produkt

Eftersom vi vill binda produktsökningsmetodens eVar till produkter när en produktinteraktion sker - vilket innebär att en produkt har hittats - är det säkert att anta att de vanligaste&quot;produktinteraktionerna&quot; som kan äga rum är antingen en produktvy (när besökarna går till en produktinformationssida) eller en kundvagn (när besökarna lägger till en produkt i kundvagnen direkt från en produktsökningssida).

Därför kan vi välja dessa två händelser (prodView, scAdd) som de&quot;grundläggande&quot; bindningshändelserna för varuexponering.
Här är vad som händer när någon av dessa bindningshändelser ingår i en bildbegäran. Alla produkt-ID:n som finns i samma begäran (inom variabeln products) och som inte har bundits till en eVar för försäljning binds till de senaste värdena som skickas till eVarna för försäljning (kolumnerna post_evar). Alla försök att binda om dessa produkter efter att den ursprungliga bindningen har gjorts ignoreras när inställningen Allocation (binding) har angetts till Original Value (First).

### Inställningar för bästa praxis

Här följer de bästa metoderna. De implementerar enkelt metoden för produktsökning med bästa resultat. Adobe rekommenderar att kunderna konfigurerar var och en av sina produktsökningsmetoder för försäljning av eVars (i allmänhet) enligt följande:

* Marknadsföring aktiverad: Aktiverad
* Merchandising [syntax]: Konverteringsvariabelsyntax
* Allokering [bindning]: Originalvärde (första)
* Förfaller efter: Den tid en produkt stannar i en kundvagn innan den tas bort automatiskt (t.ex. 14 dagar, 30 dagar osv.).  Om det inte finns någon sådan tid, förfaller du efter köphändelsen
* Typ: Text
* Marknadsföringsbindningshändelser: produktvy, kundvagn, tillägg och inköp

## Vad gör Binding Events egentligen?

När en bindningshändelse finns i samma serveranrop som produktvariabeln binds värdena för Merchandising eVar (med hjälp av konverteringsvariabelsyntax) i sin post-kolumn till produktvariabeln. Utifrån det tidigare exemplet antar vi att ett serveranrop innehåller följande värden för Merchandising eVar:

```js
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Som förklarats tidigare kvarstår de ovanstående eVars-variablerna utanför den aktuella träffen via deras respektive post_evar-kolumn. Adobe servrar omvandlar därför eVars ovan till följande:

```js
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Dessa postkolumner lagras i Adobe-databasen och kvarstår efter den aktuella träffen där de ursprungligen angavs. Detta förutsätter att det inte sker någon återställning av förfallodatum eller variabel.  Adobe har dessa post_evar-värden &quot;tillgängliga&quot; när de bearbetar eventuella framtida serveranrop som innehåller både bindningshändelsen och produktvariabeln.

Bindningen som äger rum är endast mellan dessa post_evar-värden och innehållet i variabeln products. Bindningshändelsen&quot;binder&quot; inte nödvändigtvis till varken eVars- eller produktvariabeln. Det är&quot;katalysatorn&quot; som instruerar Adobe-servrarna att binda värdena post_evar till produkterna.

Anta att följande variabler ställs in för en framtida träff:

```js
s.products=";sandals123"
s.events="prodView";
```

I kolumnerna post_evar ser Adobe-bearbetningsservrarna den här träffen på följande sätt:

```js
s.products=";sandals123";
s.events="prodView";
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Anta att eVar1, eVar2, eVar3, eVar4 och eVar5 har konfigurerats för användning `prodView` som en bindningshändelse. Om någon av dessa eVars inte är konfigurerad att använda prodView som en bindningshändelse sker ingen bindning mellan den (felkonfigurerade) eVarna och produktvariabeln.

Bindning ger mycket intressanta resultat, som visas i kolumnen post_products. Bindningen omformar ovanstående kod och ställer in några fler postkolumner enligt följande:

```js
post_events="prodView";
post_products=";sandals123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
```

Värdet i kolumnen post_products kanske är välbekant för dig. Bläddra uppåt i det här dokumentet och jämför värdet post_products och värdet s.products enligt nedan. Observera att kolumnen post_products är inställd med produktvariabelsyntax!

Det innebär att Binding &quot;kopierar&quot; värdena för Conversion Variable Syntax eVar till variabeln products via Product Syntax. Den här kopieringsåtgärden utförs endast när produktvariabeln och en bindningshändelse (som anges via eVar-konfigurationen) finns i samma begäran. Då är värdena i kolumnen efter_eVar bundna till produkten. Den här bindningen representeras via produktsyntax som lagras i kolumnen post_products.

## Merchandising eVars, the Instances metric, and Attribution

När en vanlig eVar skickas i ett Analytics-serveranrop får värdet i kolumnen post_evar alltid en instans som har tilldelats det. Förekomster representerar det antal gånger som en eVar har ställts in som lika med ett visst värde i en bildbegäran.

Anta till exempel att `eVar10` är en standardeVar med [!UICONTROL Last Touch] attribuering. Om du anger `s.eVar10="hello world"` på alla sidor skickas värdet &quot;hello world&quot; till kolumnen post_evar10 när Adobe bearbetar träffen. Instansmåttet är lika med &quot;1&quot; för varje enskild `eVar10` inställning för `hello world`. Tänk på att en instans inte alltid spelas in när kolumnen post_evar har ett värde. I stället avgör kolumnen post_evar vilket värde som hämtar instansen när en instans spelas in.

Instanser för en eVar som säljer attribuerar de värden som eVarna samlar in. Men detta händer bara när en produkt som var bunden till värdet av eVarna för försäljning&quot;interagerar&quot; med samtidigt.

Ange till exempel `s.eVar1="Internal Keyword Search"` i sig inte tillskriver eVar1-värdet för &quot;Internal Keyword Search&quot; något förekomstmått. En instans registreras vid den punkten. Om inte en produkt är bunden till värdet för intern nyckelordssökning samtidigt `eVar1` är inställt, tilldelas instansen till den ospecificerade bucket. Med andra ord `eVar1` värdet för &quot;Internal Keyword Search&quot; kan hämta en instans. Men detta händer bara när en produkt som är bunden till värdet för &quot;Intern nyckelordssökning&quot; visas i produktvariabeln i samma bildbegäran.

Utan ytterligare konfigurationer är alltså det färdiga instansmåttet för en eVar som handlar mindre användbart. Som tur är har Adobe släppts [Attribut](/help/analyze/analysis-workspace/attribution/overview.md). Det gör att du kan använda flera attribueringsmodeller för alla anpassade mätvärden som Adobe Analytics samlar in. Mätvärden som tillämpar dessa attribueringsmodeller använder inte värdena i kolumnerna post_evar eller värdena som är bundna till en viss produkt. I stället används endast de värden som skickas via själva bildbegäran (eller värden som hämtas via Adobe Analytics bearbetningsregler). Du kan använda funktionerna i Attribution för att få ett korrekt tilldelat instansmått för alla eVars-handlare som använder konverteringsvariabelsyntax.

![Val av attribut](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/assets/attribution-select.png)

När du lägger till ett instansmått för en eVar i en rapport blir rätt attribueringsmodell&quot;Last Touch&quot;-modellen. Inställningen för fönstret Sök efter för modellen spelar ingen roll i det här fallet. Orsaken är att en&quot;tvingad&quot; Last Touch-attribueringsmodell alltid ger instanskrediter till varje enskilt värde som skickas via en begäran. Detta är oavsett om eVarnas faktiska attribuerings-/bindningsinställningar är lika med &quot;Senaste (senaste)&quot; till &quot;Originalvärde (första)&quot;.
