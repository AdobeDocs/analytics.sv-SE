---
title: Merchandising eVars and Product Finding Methods
description: En djupdykning i begreppen bakom försäljning av eVars och hur de bearbetar och allokerar data.
source-git-commit: 6f98366a58c7c249c474d9f4474faa1676cdf1ea
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 0%

---

# Merchandising eVars and product finding methods

I det här dokumentet förklaras begreppen bakom försäljning av eVars, som bearbetar och tilldelar data på ett annat sätt än vanliga eVars-variabler. Det förklarar också hur eVars marknadsför produktsökningsmetoder.

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

Termen&quot;Allocation&quot; för att marknadsföra eVars är en felaktig term, särskilt för att marknadsföra eVars som använder konverteringsvariabelsyntax. Alla eVars som använder standardsyntax kan ha egna inställningar för individuell allokering, men när eVars säljs med konverteringsvariabel syntax används endast allokeringsinställningen &quot;Senaste (senaste)&quot; oavsett allokeringsinställningarna i Report Suite Manager.

För att förstå vad den här inställningen innebär måste du förstå skillnaden mellan eVar- och försäljningsbindning.  För försäljning av eVars kan&quot;Merchanding eVar Binding&quot; betraktas som ett mer passande namn för den här inställningen.
När en eVar med standardsyntax samlas in från en bildbegäran infogar Adobe Analytics bearbetningsservrar data i en annan databaskolumn, som kallas post_evar-kolumn, tillsammans med den vanliga eVar.  Eftersom eVars är avsedda att vara beständiga (d.v.s. de upphör att gälla någon gång efter den aktuella träffen i de flesta fall), kommer servrarna att ange kolumnen post_evar för varje efterföljande bildbegäran och ställa in den på samma värde som det senaste värdet som skickades till motsvarande eVar. När en lyckad händelse inträffar använder Adobe Analytics kolumnen post_evar i stället för den vanliga kolumnen för eVar för att avgöra vilket eVar som ska tillgodoräknas för händelsen.
För standard-e (dvs. icke-marknadsföringsvariabler) avgör inställningen Allocation om det första eller sista eVar som samlades in under en viss period ska infogas i kolumnen post_evar. Om allokeringsinställningen för en standard är lika med &quot;Originalvärde (första)&quot; infogas det första eVar som samlas in från besökaren i kolumnen post_evar för alla efterföljande bildbegäranden.  Detta fortsätter för alla framtida förfrågningar som skickas från besökarens webbläsare tills eVar förfaller enligt inställningen&quot;Förfaller efter&quot;.\
Om standardinställningen Allokering är lika med &quot;Senaste (senaste)&quot;, fylls det senaste eVar som samlats in från besökaren i kolumnen post_evar för alla efterföljande bildbegäranden. Allokeringen &quot;Senaste (sista)&quot; innebär att värdet post_evar ändras varje gång dess motsvarande eVar anges till ett nytt värde i en bildbegäran.  &quot;Originalvärde (första)&quot; innebär att kolumnen post_evar inte ändras över träffar trots att motsvarande eVar kan anges till ett annat värde i en framtida bildbegäran.
Som tidigare nämnts har alla eVars som handlar med konverteringsvariabelsyntax bara allokeringen&quot;Senaste (senaste)&quot; (enligt standarddefinitionen för eVar).  Därför måste jag förklara vad&quot;Allocation&quot;-inställningen faktiskt betyder för eVars-handeln.  Som tidigare antytts bestämmer den här inställningen inte vilka värden som infogas i kolumnen post_evar när en besökare fortsätter att använda webbplatsen.  I stället avgör inställningen Allokering för försäljning av eVars vilka eVar som binds till en produkt och hur sådana produkter allokeras


