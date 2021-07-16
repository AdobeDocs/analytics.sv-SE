---
title: Merchandising eVars and Product Finding Methods
description: En djupdykning i begreppen bakom försäljning av eVars och hur de bearbetar och allokerar data.
source-git-commit: eb508167930019c51823e652fc16122e9e416d07
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Merchandising eVars and product finding methods

I det här detaljerade dokumentet förklaras begreppen bakom försäljning av eVars, som bearbetar och tilldelar data på ett annat sätt än vanliga eVars. Det förklarar också hur eVars marknadsför produktsökningsmetoder.

Även om de flesta webbplatser för detaljhandeln har många sätt att hitta produkter anser Adobe att följande är de grundläggande metoder för produktupptäckt som alla kunder inom detaljhandeln bör följa i Adobe Analytics:

* Interna söknyckelord
* Interna koder för kampanjspårning
* Marknadsföring/bläddringskategorier
* Merförsäljning

I det här dokumentet kan vi mappa några eVars till lösningarna enligt följande:

* eVar2: Interna söknyckelord
* eVar3: Interna koder för kampanjspårning
* eVar4: Marknadsföring/bläddringskategorier
* eVar5: Korsförsäljning

Vi kan använda en extra eVar för att mäta prestandan för alla produktsökningsmetoder i förhållande till varandra. Förutom de sökmetoder som beskrivs ovan innehåller eVar andra sökmetoder i jämförelsen, till exempel länkar till produktinformationssidor från externa webbplatser.

* eVar1: Metoder för produktsökning

I stället för att konfigurera variablerna så att de blir standard-eVars, ska du konfigurera dem så att de marknadsför eVars. Med hjälp av eVars kan du tilldela alla framgångsrika aktiviteter till värden som hämtas av eVars på *per-product*-nivå i stället för på *per-visit/per-order*-nivå. I detta dokument klargörs skillnaden mellan fördelningen per produkt och per order genomgående.

För att visa hur du ställer in dessa variabler finns det ett exempel där en besökare bestämmer sig för att använda de interna söksandalerna för nyckelord för att hitta en produkt på webbplatsen. På sidan med sökresultat för nyckelord måste du hämta data i minst två eVars:

* `eVar2` är lika med nyckelordet som användes i sökningen (&quot;sandaler&quot;)
* `eVar1` är lika med den produktsökningsmetod som används (&quot;intern nyckelordssökning&quot;).

När du ställer in dessa två variabler som är lika med dessa specifika värden, vet du att besökaren använder det interna nyckelordssökordet för&quot;sandaler&quot; för att hitta en produkt. Samtidigt vet du att besökaren inte använder de andra produktsökningsmetoderna för att hitta produkter (besökaren bläddrar till exempel inte igenom produktkategorier exakt samtidigt som de gör en nyckelordssökning). För att säkerställa att rätt tilldelning sker per produkt bör dessa oanvända metoder inte få någon uppskattning för att hitta en produkt som hittats via en intern nyckelordssökning. Du måste därför infoga logik i koden (som AppMeasurement, AEP Web SDK och så vidare) som automatiskt anger de eVars som är associerade med dessa andra sökmetoder som är lika med ett icke-sökmetod-värde.

När en användare t.ex. söker efter produkter med nyckelordet&quot;sandals&quot;, ska Analytics-kodens logik ange de variabler som är lika med följande på den interna sökresultatsidan för nyckelord:

* eVar2=&quot;sandaler&quot;: nyckelordet&quot;sandals&quot; användes i den interna nyckelordssökningen
* eVar1=&quot;intern nyckelordssökning&quot;: sökmetoden&quot;internal keyword search&quot; användes
* eVar3=&quot;icke-intern kampanj&quot;: en intern kampanj användes inte för att komma åt sökresultatsidan
* eVar4=&quot;ej webbläsare&quot;: det gick inte att komma åt en bläddringskategori på sökresultatsidan
* eVar5=&quot;ej korsförsäljning&quot;: det gick inte att klicka på en korsförsäljningslänk på sökresultatsidan

## Inställningar för eVars

Innan du fortsätter med&quot;sandaler&quot;-exemplet finns de olika inställningar som du kan använda med dina eVars-produkter för varuexponering.  Följande skärmbild kommer från Report Suite Manager. Gå till Analytics > Admin > Report Suites > Edit Settings > Conversion > Conversion Variables > Add new > Enable Merchandising.

![](assets/merch-evars1.png)

Avsnitten under tabellen innehåller mer information om de här inställningarna.

| Inställning | Beskrivning |
|--- | --- |
| Namn | The Name, or the reporting dimension that the variable is intended to be associated with. Om `eVar1` är avsedd för att hämta produktsökningsmetoder, ska namnfältet för `eVar1` anges till &quot;Produktsökningsmetoder&quot;. |
| Merchandising | Den typ av syntax som ska användas för att hämta värden för eVar |
| Allokering | Hjälpmedel avgör vilket värde på eVar som ska få krediter när en lyckad händelse inträffar. |
| Förfaller efter | Avgör när befintliga produktbindningar och bindningar till eVar för varuexponering inte längre ska gälla. |
| Typ | Den typ av uppgifter som samlas in i eVar för försäljning |
| Marknadsföringsbindningshändelse | Händelsen/händelserna som avgör när en produkt ska bindas till ett värde för eVar |
| Återställ | En utlösare som återställer alla backend-data för eVar vid den tidpunkten |
| Aktivera marknadsföring | En flagga som måste ställas in på&quot;Aktiverad&quot; för att omvandla eVar från en standardeVar till en Merchandising-eVar |

### Aktivera marknadsföring

När inställningen Aktivera marknadsföring är aktiverad visas alla inställningar som beskrivs nedan i Report Suite Manager. När inställningen Aktivera marknadsföring är inaktiverad är endast standardinställningarna för eVar tillgängliga.

### Merchandising

Det här alternativet är inte tillgängligt för vanliga eVars-variabler. Med inställningen [!UICONTROL Merchandising] kan du välja antingen [!UICONTROL Conversion Variable Syntax] eller [!UICONTROL Product Syntax] som metod för att hämta eVar värde.

**[!UICONTROL Conversion Variable Syntax]** innebär att du anger eVar värde i en egen variabel. Om du till exempel har konverteringsvariabelsyntax anges `eVar1`-värdet för &quot;intern nyckelordssökning&quot; enligt följande i sidkoden (eller AppMeasurement-koden, AEP Web SDK-koden, och så vidare):

`s.eVar1="internal keyword search";`

Med **[!UICONTROL Product Syntax]** är dock eVar inställd endast i variabeln Adobe Analytics. Variabeln Analytics-produkter är uppdelad i sex olika delar per produkt:

`s.products="[category];[productID];[quantity];[revenue];[events];[eVars]"`

* [!UICONTROL Category] är en föråldrad funktion och rekommenderas inte längre som ett användbart alternativ för att hålla reda på produktkategorins prestanda.  Dess existens visar varför i de flesta implementeringar av variabeln products kommer ett semikolon före delen productID i variabelvärdet.
* [!UICONTROL Quantity] och  [!UICONTROL Revenue] är användbara när ett produktköp spåras.
* [!UICONTROL Events] är användbart för att registrera anpassade stegvisa värden eller valutakäntehändelser som inte ska räknas som intäkter (t.ex. frakt, rabatter)

Merchandising eVars that are configured to use Product Syntax are set within the final portion of the products variable. Anta till exempel att en besökare använde en intern nyckelordssökning för att hitta produkt-ID &quot;12345&quot;. Det syntaxbaserade sättet att ange eVar1 i det här exemplet skulle se ut så här:

`s.products=";12345;;;;eVar1=internal keyword search";`

Observera att vi fortfarande har semikolonavgränsade platshållare för produktvariabelns kvantitet, intäkter och händelsedelar.  Utan dessa platshållare ignoreras inställningen `eVar1` för intern nyckelordssökning helt.

### Allokering

Termen Allocation för att marknadsföra eVars är vilseledande, särskilt för att marknadsföra eVars som använder konverteringsvariabelsyntax. Alla standardvariabler kan ha en egen allokeringsinställning. Vid försäljning av eVars med konverteringsvariabelsyntax används dock endast allokeringsinställningen &quot;Senaste (senaste)&quot;, oavsett vilka allokeringsinställningar som har gjorts i Report Suite Manager.

Att förstå vad den här inställningen gör innebär att förstå skillnaden mellan eVar- och försäljningsbindning för eVar. För försäljning av eVars är&quot;Merchandising eVar Binding&quot; ett mer passande namn för den här inställningen för&quot;Allocation&quot;.

**Standardinställning för allokering av eVar**

När en eVar med standardsyntax samlas in från en bildbegäran infogar Adobe Analytics bearbetningsservrar data i en annan databaskolumn, som kallas `post_evar`-kolumn. Eftersom eVars är avsedda att vara beständiga - de upphör att gälla vid något tillfälle efter den aktuella träffen i de flesta fall - anger servrarna den här `post_evar`-kolumnen vid varje efterföljande bildbegäran. Den är lika med det sista värdet som skickas till motsvarande eVar. När en lyckad händelse inträffar för standard-eVars använder Adobe Analytics kolumnen `post_evar` i stället för den vanliga eVar för att avgöra vilket eVar som ska tillgodoräknas för händelsen.

För standard-eVars avgör inställningen Allocation om det första eller sista eVar som samlades in under en viss period ska infogas i kolumnen `post_evar`. Om allokeringsinställningen för en standard är lika med &quot;Originalvärde (första)&quot; infogas det första eVar som samlas in från besökaren i `post_evar`-kolumnen för alla efterföljande bildbegäranden. Detta fortsätter för alla framtida förfrågningar som skickas från besökarens webbläsare tills eVar förfaller enligt inställningen&quot;Förfaller efter&quot;.

Om standardinställningen Allokering är lika med &quot;Senaste (senaste)&quot; fylls det senaste eVar som samlats in från besökaren i kolumnen `post_evar` för alla efterföljande bildbegäranden. Allokeringen &quot;Senaste (sista)&quot; innebär att värdet `post_evar` ändras varje gång dess motsvarande eVar anges till ett nytt värde i en bildbegäran. Tilldelningen av &quot;Originalvärde (första)&quot; innebär att kolumnen `post_evar` inte ändras över träffar trots att dess motsvarande eVar kan anges till ett annat värde i en framtida bildbegäran.

**Inställningar för allokering av eVar (bindning) för marknadsföring**

Som vi nämnt tidigare har alla eVars-handlare med konverteringsvariabelsyntax bara allokeringen&quot;Senaste (senaste)&quot;.  Det är det som&quot;Allocation&quot;-inställningen faktiskt betyder för försäljning av eVars: Som tidigare antytts bestämmer den här inställningen inte vilka värden som infogas i `post_evar`-kolumnen när en besökare fortsätter att använda webbplatsen. I stället avgör inställningen Allokering för att marknadsföra eVars vilka eVar som binds till en produkt och hur sådana produkter allokerar sina lyckade händelser tillbaka till de eVar de är bundna till.

Låt oss diskutera vad som händer om en eVar allokeringsinställning (dvs. bindning) är lika med &quot;Originalvärde (första)&quot;. Alla produkter som anges bredvid `post_evar`-kolumnen och som inte tidigare har bundits till kolumnen post_evar som motsvarar den förbearbetade eVar binds till värdet i kolumnen `post_evar`. Denna bindning mellan eVar och produkt ändras aldrig förrän eVar förfaller enligt inställningarna &quot;Förfaller efter&quot; i inställningarna för Report Suite.

Varje gång en bildbegäran uppfyller de kriterier som annars skulle binda en redan bunden eVar till det senast angivna värdet, tvingar inställningen&quot;Originalvärde (första)&quot; Adobe Analytics datainsamlingsservrar att ignorera alla sådana försök att göra det. Motsatsen inträffar när eVars marknadsförs med inställningen Allocation (binding) som är lika med&quot;Most Recent (Last)&quot;. Varje gång en bildbegäran uppfyller villkoren som binder en produkt till en eVar binds (och binds om) produkten till det senaste värdet som skickas till eVar, eller det värde som (alltid) finns i `post_evar`-kolumnen.

Som vi nämnt tidigare kan ni med hjälp av e-handlare tilldela framgångsrika event till eVar per produkt istället för per besök/per order. Så när en bunden produkt har en lyckad händelse (till exempel kundvagnstillägg eller kundköp) som är kopplad till den, ger händelsen om framgång både produkten och de eVar som produkten är bunden till vid den tidpunkten.

### Förfaller efter

Med inställningen för förfallodatum för en eVar kan du välja när både produkt-/eVar-bindningarna ska upphöra att gälla och när kolumnen post_evar inte längre ska fyllas i automatiskt efter att en eVar har skickats till en bildbegäran. Förfallotid för en eVar kan antingen inträffa när en lyckad händelse (som du väljer) spelas in eller när en viss tidsperiod - som du väljer - godkänns. Adobe Analytics tillåter endast en förfalloinställning i taget per eVar.

För produktsökningsmetoden bör det bästa sättet att ange en eVar förfallotid vara att ställa in den på antingen den tid som en produkt finns i en webbplatsens kundvagn innan webbplatsen automatiskt tar bort den från kundvagnen ELLER när köphändelsen äger rum. Om något av alternativen för förfallodatum är inställt kommer alla produkter som besökaren köper att få den kredit för order/enhet/intäkt som tilldelats de värden för eVar som produkterna var bundna till vid den tidpunkten.

### Typ

Inställningen för datatyp avgör vilken datatyp som infogas i eVar. I de flesta fall, om inte alla, när du skapar en eVar för försäljning, ska det här värdet vara lika med&quot;Text&quot;. Det är sällsynt att använda en typ av&quot;Räknare&quot; för en eVar, men beroende på spårningsbehovet kan den användas på ett effektivt sätt för att räkna ut eVar per produkt.  Diskussionslösningar med typen &quot;Räknare&quot; omfattas inte av detta dokument.

### Marknadsföringsbindningshändelse

Med inställningen för bindningshändelse för marknadsföring kan du ange de villkor som skulle göra att en produkt binds till en eVar värde. Dessa villkor är begränsade till att vissa framgångshändelser utlöses eller endast eVars. Körvariabler (t.ex. props) har ingen effekt på försäljningsbindningarna.

En av de mer användbara funktionerna för inställningen för bindningshändelse för marknadsföring är möjligheten att binda en produkt till ett värde för eVar genom mer än en händelse. Inställningen kan t.ex. göra att produkter kan bindas till ett försäljningsvärde antingen via en produktvyhändelse, en kundvagnstilläggshändelse eller en köphändelse. Inställningen kan även - och gör som standard - binda en eVar till ett marknadsföringsvärde när någon annan händelse/eVar - eller försäljning - ingår i samma bildförfrågan som produkten.

### Återställ

Med inställningen Återställ kan du omedelbart ange att alla eVar för alla besökare som för närvarande har ett `post_evar`-värde i Adobe Analytics backend-databas ska förfalla. Dessutom tas alla nuvarande produkt-/eVar-bindningar bort.

>[!IMPORTANT]
>Adobe rekommenderar inte att du använder inställningen Återställ om du inte helt tänker börja om med ett helt &quot;rent lager&quot; med data från den tidpunkt då återställningen utförs.

## Vilka inställningar ska du använda?

Bland de många inställningskombinationer som finns kan du undra vilka inställningar som är&quot;bästa praxis&quot;.

Om du vill binda&quot;intern nyckelordssökning&quot; till produkt-ID 12345 ställs variabeln products in så här:

`s.products=";12345;;;;eVar1=internal keyword search";`

Alla lyckade händelser (kundvagnsöppningar, inköp) som fångas samtidigt som productID 12345 krediteras både produkt-ID 12345 och `eVar1`-värdet för&quot;intern nyckelordssökning&quot;. Det enda sättet på vilket ett annat `eVar1`-värde fick kredit för lyckade händelser som är kopplade till produkt-ID 12345 är om `eVar1` senare angavs till ett **annat**-värde i variabeln products (tillsammans med produkt-ID 12345). Exempel:

`s.products=";12345;;;;eVar1=internal campaign";`

Den här konfigurationen ändrar bindningen av produkt-ID 12345 från `eVar1`-värdet för &quot;intern nyckelordssökning&quot; till `eVar1`-värdet för &quot;intern kampanj&quot;. Denna ombindning sker varje gång produktsyntax används och inställningen Allokering (bindning) för eVar är inställd på &quot;Senaste (senaste)&quot;. Vad händer om inställningen Allokering (bindning) i stället är inställd på &quot;Originalvärde (första)&quot;? Inställningen eVar1 som är lika med&quot;intern kampanj&quot; tillsammans med produkt-ID 12345 binder inte om produkt-ID 12345 till eVar1-värdet för&quot;intern kampanj&quot;. Bindningen behålls med det ursprungligen bundna värdet -&quot;intern nyckelordssökning&quot;.

### Problem med att använda produktsyntax

Utan noggrann planering kan flera problem uppstå när du använder produktsyntax. Låt oss ta fallet med att använda flera eVars för att spåra produktsökningsmetoder på webbplatsen. Här måste varje enskild eVar för sökmetoden anges samtidigt för att ge en viss eVar (och den andra sökmetoden eVars ingen kredit). Produktsyntax kan användas i sådana scenarier, men den resulterande koden för distributionen är mer komplicerad.

Om vi använder vårt ursprungliga&quot;sandaler&quot;-exempel och anpassar det till produktsyntax (förutsatt att besökaren hittade en produkt med ID:t &quot;sandal123&quot; med nyckelordstermen &quot;sandals&quot;) måste den resulterande variabeln anges enligt följande:

`s.products=";sandal123;;;;eVar2=sandals|eVar1=internal search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";`

Syntaxen för variabeln products är lång i det här exemplet, men den binder alla eVar som visas till produkt-ID:t för &quot;sandal123&quot;. Från och med då krediteras alla framgångshändelser (t.ex. kundvagn, inköp) som har hämtats samtidigt som&quot;sandal123&quot;-produkten till de eVar som senast var bundna till produkten.  Detta kodexempel visar om ett köp av 1 enhet av&quot;sandal123&quot;-produkten (för 79,95 USD) äger rum efter det att eVars ovan var bunden till&quot;sandal123&quot;-produkten:

```
s.products=";sandal123;1;79.95";
s.events="purchase";
```

Följande värden skulle alla ha 1 order, 1 enhet och 79,95 USD av intäkter:

* eVar2-värde för&quot;sandals&quot;
* eVar1-värdet för&quot;intern nyckelordssökning&quot;
* eVar3-värdet för&quot;icke-intern kampanj&quot;
* eVar4-värdet för non-browse

Det här är korrekt attribuering, vilket inte är något problem. Det största problemet med detta är snarare att avgöra hur och när produktsökningsmetodens eVars ska anges.

I de flesta fall med produktsyntax måste eVars för produktsökningsmetod anges på en produktinformationssida i stället för på sidan där sökningsmetoden faktiskt användes (t.ex. på sökresultatsidan, bläddringssidan, den interna kampanjstartsidan osv.). Det är rimligt att anta att en produkt inte har&quot;hittats&quot; förrän besökaren interagerar med en produkt i någon utsträckning. Därför bör dessa eVars (med produktsyntax) inte anges på sökmetodsidan eftersom flera produkter (vanligtvis) visas på sådana sidor. Vi vill binda sökmetodvärdet till endast de produkter som besökaren har interagerat med.

När besökarna visar en sökmetodsida kan de dessutom antingen klicka på en länk som leder dem till en enskild produktinformationssida eller lägga till en enskild produkt i kundvagnen direkt från sökmetodsidan. Om en besökare lägger till produkten&quot;sandal123&quot; i kundvagnen direkt från en sökresultatsida med sökord, använder du nyckelordsexemplet&quot;sandal123&quot;, koden för att hämta kundvagnen (via händelsen onClick för knappen Lägg till i kundvagnen, etc) måste antingen genereras dynamiskt när kundvagnen läggs till eller kodas direkt via sidkoden eller ett tagghanteringssystem.  Oavsett vilken kod som ska utlösas i sådana fall skulle koden se ut ungefär så här:

```
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell";
s.tl(true,"o","Cart Add")
```

Den här koden binder eVar som visas ovan till sandal123-produkten. För att kunna ange dessa värden korrekt när klickhändelsen inträffar måste utvecklaren dock:

* Lägg till serversideslogik på sökresultatsidan som bestämmer vilka värden som måste infogas i produktsökningsmetoden eVars, och
* Sammanställ hela produktvariabeln som visas ovan utan syntaxfel.

Om en besökare bestämmer sig för att&quot;hitta&quot; produkten genom att klicka på en länk till produktinformationssidan måste utvecklaren dessutom:

* Skicka informationen om produktsökningsmetoden (se ovan) från sökmetodsidan till produktinformationssidan och * * Sammanställ samma variabelvärde för produkter från objekt som just skickats från föregående sida.

Den här lösningen kräver en hög grad av komplexitet som kanske inte är möjlig.

### Där produktsyntax är användbar

Produktsyntax är fortfarande användbar när

* Flera produkter med samma produkt-ID interagerar samtidigt.
* De eVars som ska bindas till sådana produkter måste ha olika värden per produkt-ID.

Många klädprodukter har till exempel &quot;Underordnade SKU:er&quot;, som anger storlek, färg, stil och andra attribut. Dessa attribut skiljer en underordnad produkt från andra jämställda produkter som tillhör samma överordnade produkt. Säg att du bestämmer dig för att köpa en medelblå t-shirt plus en stor röd t-shirt. Anta att båda skjortorna har det överordnade produkt-ID:t &quot;tshirts123&quot; och att eVar10 har konfigurerats för att hämta underordnade SKU:er. Variablerna som anges på bekräftelsesidan för inköp ställs in enligt följande:

```
s.events='purchase';
s.products=';tshirt123;1;20;;eVar10=tshirt123-m-blue,;tshirt123;1;20;;eVar10=tshirt123-l-red"
```

I det här fallet får både `eVar10`-värden (childSKU) för&quot;tshirt123-m-blue&quot; och&quot;tshirt123-l-red&quot; erkännande för köp av deras respektive instanser av produkt-ID&quot;tshirt123&quot;.

### Utmaningar med tilldelning av&quot;senaste&quot;

Du kan stöta på ytterligare problem genom att använda inställningen Allokering (bindning) för&quot;Senaste (senaste)&quot;. I många webbläsar-upplevelser&quot;hittar&quot; besökarna en produkt som de redan har tittat på och/eller lagt till i kundvagnen. Detta sker vanligtvis via ett senare besök eller precis innan de bestämmer sig för att slutföra ett köp. Anta att de vid sitt första besök på webbplatsen hittade produkten&quot;sandal123&quot; via nyckelordssökningen&quot;sandaler&quot;. De lade omedelbart till den i kundvagnen från sidan med sökresultat för nyckelord. Koden som används för att hämta kundvagnen ställs in enligt följande:

```
s.linkTrackVars="products,events";
s.linkTrackEvents=s.events="scAdd";
s.products=";sandal123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross
```

Därför är alla eVar som visas i den här bildbegäran bundna till produkten&quot;sandal123&quot;.

Tänk dig att besökaren inte köper produkten under besöket, utan kommer tillbaka till webbplatsen tre dagar senare. De vet att de redan har lagt till&quot;sandals123&quot;-produkten i kundvagnen. Men de vill ändå lära sig mer om det innan de gör köpet. Istället för att använda en nyckelordssökning för att hitta produkten bläddrar besökaren igenom webbplatsen. De slutar med att de handlar i &quot;kvinna > skor > sandaler&quot; och handlar i webbläsaren precis innan de hittar produkten på nytt. När de&quot;hittar om&quot; produktinformationssidan för&quot;sandal123&quot;-produkten ställs variablerna in enligt följande (vid sidinläsning):

```
s.events="prodView";
s.products=";sandal123;;;;eVar4=womens > shoes > sandals|eVar1=browse|eVar3=non-internal campaign|eVar2=non-search|eVar5=non-cross-sell";
```

Med inställningen Allocation (binding) på&quot;Most Recent (Last)&quot; binds produkten &quot;sandal123&quot; till helt andra eVar än vad den ursprungligen var bunden till. Om besökaren sedan slutför köpet av&quot;sandal123&quot; ges dessutom alla inköpskrediter till dessa nybundna eVar i stället för de värden som ursprungligen var bundna.

Frågan här är: Vilka eVar ska få krediter för köpet?&quot; Kom ihåg att besökaren ursprungligen hittade &quot;sandal123&quot;-produkten via en intern nyckelordssökning. Sedan lade de till den i kundvagnen direkt från sökresultatsidan. Därför bör eVar1-värdet för&quot;intern nyckelordssökning&quot; (och eVar2-värdet för&quot;sandaler&quot;) krediteras köpet. Allokeringsinställningarna (bindning) ställdes in på&quot;Senaste (senaste)&quot;. eVar1-värdet för&quot;browse&quot; (och eVar4-värdet för&quot;kvinna > skor > sandaler&quot;) ger inköpskrediten i stället. Orsaken är att de var de sista värdena som var bundna till&quot;sandal123&quot; innan besökaren slutförde köpet.

En lösning på det här problemet är att ändra inställningen Allokering (bindning) för den säljande eVar från&quot;Senaste (senaste)&quot; till&quot;Originalvärde (första)&quot;. På så sätt krediteras de ursprungliga eVar som är bundna till&quot;sandal123&quot;-produkten när köpet äger rum, oavsett hur många gånger besökaren&quot;hittar om&quot; produkten.

Om besökaren lägger till en produkt i kundvagnen men aldrig köper den, tillåter eVar att ett nytt sökmetodvärde binds till produkten. eVar förfallodatum bör motsvara den tid som en webbplats tillåter att en produkt hamnar i kundvagnen innan den tas bort automatiskt.

### Använda konverteringsvariabelsyntax

Vi går tillbaka till&quot;Produktsyntax&quot; jämfört med Fråga om konverteringsvariabelsyntax. Adobe har upptäckt en enklare metod för att både samla in produktsökningsmetoden och marknadsföra eVars och binda deras värden till produkter som besökarna har hittat: Om du använder Konvertera variabelsyntax minskas det implementeringsarbete som klientens utvecklare ansvarar för. Den erbjuder fortfarande samma eller bättre information än produktsyntaxmetoden. Utvecklarna behöver bara följa de distributionsanvisningar de fått, och resten av koden kan placeras i Adobe AppMeasurement/AEP Web SDK-filen.

Låt oss till exempel titta på den rekommenderade lösningen för att spåra interna nyckelordssökningsprestanda. Det står att på resultatsidan för nyckelordssökningen hämtar koden nyckelordet som sökts efter via en prop (till exempel prop4) och en annan prop (till exempel prop5). De här stegen spårar antalet resultat som visas i sökningen. När en Adobe Analytics-bildbegäran genereras på sökresultatsidan användes datalagretobjekten (eller sidkoden) som utvecklarna använde för att fylla i variablerna ovan (stegen).

Ytterligare logik som finns i AppMeasurement/AEP Web SDK-filen kan fylla i resten av variablerna (eVars/dimensions) som måste anges samtidigt.\
Om en ny besökare till exempel skulle göra en nyckelordssökning efter&quot;sandaler&quot;, som returnerade 25 resultat på sökresultatsidan, skulle koden som ska aktiveras (via sidkoden ELLER datalagrets hämtning) se ut så här:

```
s.prop4="sandals";
s.prop5="25";
```

Logiken i AppMeasurement/Analytics SDK-filen kan sedan automatiskt omvandla kodfragmentet till följande:

```
s.prop4="sandals";
s.prop5="25";
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Du behöver inte bekymra dig om att skicka data från sida till sida och försöka skapa en ganska stor, otymplig sträng som ska infogas i variabeln products. I stället kan utvecklare implementera sin del av spårningslösningarna - det som infogas i propparna - och överlåta resten av implementeringen till den anpassade kod som tillhandahålls av Adobe Consulting.

Som förklarats ovan har alla eVars-produkter som använder konverteringsvariabelsyntax allokeringsinställningen &quot;Senaste (senaste)&quot;. När en eVar har angetts som lika med ett värde kvarstår värdet för alla efterföljande träffar (via kolumnen post_evar). Den kvarstår tills den har ett annat värde eller tills eVar förfaller. Alla produkter som någon interagerar med efter att eVars har angetts binds därför till de värden för&quot;Senaste (senaste)&quot; som skickats till eVar om de inte redan har bundits till dessa eVars.

Med hjälp av vårt ovanstående exempel är `eVar2`-värdet för&quot;sandals&quot; och eVar1-värdet för&quot;internal keyword search&quot; osv. finns kvar på alla sidor som visas efter att nyckelordssökningen har utförts. De behålls tills eVars skrivs över med andra värden. En besökare klickar på en länk till produktinformationssidan för produkt-ID:t &quot;sandal123&quot; från sökresultatsidan för nyckelord.  Därefter binds produkt-ID:t &quot;sandal123&quot; (om det inte har bundits ännu) till vart och ett av värdena i kolumnerna post_evar, eller till de eVar som samlades in från föregående sida (sökresultat).

Det finns en sak till att tänka om för konverteringsvariabelsyntaxen. Bindningshändelser måste ställas in för att ett eVar-värde ska kunna bindas till en produkt. Att bara ställa in en eVar (i sin egen variabel) tillsammans med en produkt (i variabeln products) i en Adobe Analytics-bildbegäran behöver inte nödvändigtvis binda eVar till produkten.  Inställningen för bindningshändelse för marknadsföring, som ställs in i Report Suite Manager, avgör i stället vilka villkor som binder ett eVar till en produkt

Eftersom vi vill binda produktsökningsmetodens värden till eVar när en produktinteraktion sker - vilket innebär att en produkt har hittats - är det säkert att anta att de vanligaste&quot;produktinteraktionerna&quot; som kan äga rum antingen är en produktvy (när besökarna går till en produktinformationssida) eller en kundvagn (när besökarna lägger till en produkt i kundvagnen direkt från en produktsökningssida).  Därför kan vi välja dessa två händelser (prodView, scAdd) som de&quot;grundläggande&quot; bindningshändelserna för varuexponering.
När någon av dessa bindningshändelser finns i en bildbegäran kommer alla produkt-ID:n som finns i samma begäran (inom variabeln products) och inte redan har bundits till en eVar att bindas till de senaste värdena som skickats till eVar merchandising (enligt kolumnerna post_evar). Alla försök att binda om dessa produkter efter att den ursprungliga bindningen har gjorts kommer att ignoreras när inställningen Allokering (bindning) har angetts till &quot;Originalvärde (första)&quot;.

### Inställningar för bästa praxis

Här följer de bästa metoderna. De implementerar produktsökningsmetoden så enkelt som möjligt med den mest kraftfulla uppsättningen resultat. Adobe rekommenderar att kunderna konfigurerar var och en av sina produktsökningsmetoder för försäljning av eVars (i allmänhet) enligt följande:

* Marknadsföring aktiverad: Aktiverad
* Merchandising [syntax]: Konverteringsvariabelsyntax
* Allokering [bindning]: Ursprungligt värde (första)
* Förfaller efter: Den tid en produkt stannar i en kundvagn innan den tas bort automatiskt (t.ex. 14 dagar, 30 dagar osv.).  Om det inte finns någon sådan tid, förfaller du efter köphändelsen
* Typ: Text
* Bindningshändelser för marknadsföring:  Produktvy, kundvagn, tillägg och inköp

## Vad gör Binding Events egentligen?

När en bindningshändelse finns i samma serveranrop som produktvariabeln binds värdena för eVar Merchandising (med konverteringsvariabelsyntax) i sin post-kolumn till produktvariabeln. Utifrån det tidigare exemplet antar vi att ett serveranrop innehåller följande värden för Merchandising-eVar:

```
s.eVar2="sandals";
s.eVar1="internal keyword search";
s.eVar3="non-internal campaign";
s.eVar4="non-browse";
s.eVar5="non-cross sell";
```

Som förklarats tidigare kvarstår de ovanstående eVars-variablerna utanför den aktuella träffen via deras respektive post_evar-kolumn. Adobe servrar omvandlar därför eVars ovan till följande:

```
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Dessa postkolumner lagras i Adobe-databasen och kvarstår efter den aktuella träffen där de ursprungligen angavs. Detta förutsätter att ingen förfallotid eller variabelåterställning sker.  Adobe har dessa post_evar-värden &quot;tillgängliga&quot; när de bearbetar eventuella framtida serveranrop som innehåller både bindningshändelsen och produktvariabeln.

Bindningen som äger rum är endast mellan dessa post_evar-värden och innehållet i variabeln products. Bindningshändelsen&quot;binder&quot; inte nödvändigtvis till varken eVars- eller produktvariabeln. Det är&quot;katalysatorn&quot; som instruerar Adobe-servrarna att binda värdena post_evar till produkterna.

Anta att följande variabler ställs in för en framtida träff:

```
s.products=";sandals123"
s.events="prodView";
```

Med tanke på kolumnerna post_evar ser Adobe-bearbetningsservrarna den här träffen på följande sätt:

```
s.products=";sandals123"
s.events="prodView";
post_eVar2="sandals";
post_eVar1="internal keyword search";
post_eVar3="non-internal campaign";
post_eVar4="non-browse";
post_eVar5="non-cross sell";
```

Anta att eVar1, eVar2, eVar3, eVar4 och eVar5 har konfigurerats att använda `prodView` som en bindningshändelse. Om någon av dessa eVars inte är konfigurerad att använda prodView som en bindningshändelse sker ingen bindning mellan den (felkonfigurerade) eVar och produktvariabeln.

Bindning ger mycket intressanta resultat, som visas i kolumnen post_products. Bindningen omformar ovanstående kod och ställer in några fler postkolumner enligt följande:

```
post_events="prodView"
post_products=";sandals123;;;;eVar2=sandals|eVar1=internal keyword search|eVar3=non-internal campaign|eVar4=non-browse|eVar5=non-cross-sell"
```

Värdet i kolumnen post_products kanske är välbekant för dig. Bläddra uppåt i det här dokumentet och jämför värdet post_products och värdet s.products enligt .  Du kommer att märka att kolumnen post_products är inställd med produktvariabelsyntax! Det innebär att Bindning&quot;kopierar&quot; eVar för konverteringsvariabelsyntax till produktvariabeln via produktsyntax. Den här kopieringsåtgärden utförs endast när produktvariabeln och en bindningshändelse (som anges via eVar) finns i samma begäran. Då är värdena i kolumnen efter_eVar bundna till produkten. Den här bindningen representeras via produktsyntax som lagras i kolumnen post_products.
