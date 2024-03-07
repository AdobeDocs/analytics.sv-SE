---
title: Hur tidsåtgången beräknas i Adobe Analytics
description: En sammanställd sida med tid för mått och mått.
feature: Metrics
exl-id: 71e9b856-8a0a-47be-a73f-4dc7d639a5de
source-git-commit: 750c4b0ffb52c3f2cf25abcd76ef149a4521109e
workflow-type: tm+mt
source-wordcount: '1612'
ht-degree: 4%

---

# Tidsåtgång - översikt

Olika [!UICONTROL 'time spent'] [mått](overview.md) och finns för alla Adobe Analytics-produkter.

## Mätvärden för hur lång tid som har tillbringats

| Mått | Definition | Finns i |
|---|---|---|
| [!UICONTROL Total seconds spent] | Representerar den totala tiden som besökare interagerar med en viss dimensionspost. Inkluderar förekomsten av ett värde och beständighet i alla efterföljande träffar. När det gäller proppar räknas även den tid som tillbringats över efterföljande länkhändelser. | Analysis Workspace, Report Builder (kallas&quot;total tid spenderad&quot;), Data Warehouse |
| [!UICONTROL Time spent per visit] (sekunder) | Ungefär *Antal sekunder per besök*<br> Representerar den genomsnittliga tiden som besökare interagerar med en viss dimensionspost under varje besök. **Anteckning**: Det här måttet kan inte beräknas oberoende av varandra eftersom nämnaren för den här funktionen är ett internt mått. | Analysis Workspace |
| [!UICONTROL Time spent per visitor] (sekunder) | Ungefär *Totalt antal sekunder som använts/unik besökare*<br> Representerar den genomsnittliga tiden som besökare interagerar med ett visst dimensionsobjekt under besökarens livstid (längden på deras cookie). **Anteckning**: Det här måttet kan inte beräknas oberoende av varandra eftersom nämnaren för den här funktionen är ett internt mått. | Analysis Workspace |
| [!UICONTROL Time Spent/User (State)] | Ungefär *Totalt antal mobilappssekunder som använts/unika mobilappsbesökare*<br> Representerar den genomsnittliga tiden mobilappsbesökare interagerar med ett visst dimensionsobjekt under besökarens livstid (längden på deras cookie). **Anteckning**: Det här måttet kan inte beräknas oberoende av varandra eftersom nämnaren för den här funktionen är ett internt mått. | Analysis Workspace |
| [!UICONTROL Average time spent on site] (sekunder) | Representerar den totala tiden som besökare interagerar med en viss dimensionspost, per sekvens med en dimensionspost. Det är inte bara begränsat till &quot;webbplats&quot;-medelvärden som namnet antyder. Mer information om sekvenser finns i avsnittet &quot;Hur tidsåtgången beräknas&quot;.<br>**Anteckning**: Detta mätresultat skiljer sig med största sannolikhet från&quot;Time Spent per Visit&quot; på en dimensionspostnivå på grund av skillnaderna i nämnaren i beräkningen. | Analysis Workspace, Report Builder (visas på några minuter) |
| [!UICONTROL Average time on site] | Detta är samma mätvärde som *Genomsnittlig tid på plats (sekunder)*, förutom formaterad som Tid (`hh:mm:ss`) | Analysis Workspace |
| [!UICONTROL Average time spent on page] | Undertryckt mätvärde.<br> I stället rekommenderar vi att du använder&quot;Genomsnittlig tid på plats&quot; om en dimensionspost behöver genomsnittstid. | Report Builder (när det finns en dimension i begäran) |
| [!UICONTROL Total session length], alias. [!UICONTROL Previous session length] | Endast Mobile App SDK. <br>Fastställd nästa gång appen startas för föregående session. Det här måttet beräknas i sekunder och räknas inte när programmet körs i bakgrunden. Detta är ett mått på sessionsnivå.<br>Exempel: Vi installerar programmet ABC och startar och använder det i 2 minuter och stänger sedan programmet. Inga data skickas om den här sessionstiden. Nästa gång vi startar programmet, [!UICONTROL Previous Session Length] skickas med värdet 120. | Analysis Workspace, Report Builder, användargränssnittet för mobiltjänster |
| [!UICONTROL Average session length] (mobil) | *Total sessionslängd / (startar - första starten)*<br> Endast Mobile App SDK. Detta är ett mått på sessionsnivå. | Report Builder, användargränssnitt för mobiltjänster |

## Dimensioner för använd tid

| Dimension | Definition | Finns i |
| --- | --- | --- |
| [!UICONTROL Time spent per visit - granular] | Den totala tid som tillbringats under besöket trunkerades till närmaste sekund och tillämpades på varje träff som ingick i besöket. Detta är en besöksnivådimension. | Analysis Workspace |
| [!UICONTROL Time spent per visit - bucketed] | Det granulerade måttet inkapslat i 9 olika intervall. Detta är en besöksnivådimension. Intervall:<ul><li>Mindre än 1 minut</li><li>1-5 minuter</li><li>5-10 minuter</li><li>10-30 minuter</li><li>30-60 minuter</li><li>1-2 timmar</li><li>2-5 timmar</li><li>5-10 timmar</li><li>10-15 timmar</li></ul>**Anteckning**: Det kan inte finnas fler bucklor än så, eftersom ett besök går ut efter 12 timmars aktivitet. | Analysis Workspace, Report Builder |
| [!UICONTROL Time spent on page - granular] | Total tid som tillbringats för varje träff, trunkerad till närmaste sekund. Det här är en träffnivådimension och innehåller både sidvyer och länkhändelser. Trots sitt namn är det inte begränsat till siddimensionen. | Analysis Workspace |
| [!UICONTROL Time spent on page - bucketed] | Den granulerade dimensionen är inkapslad i 10 olika intervall, men den blockerade dimensionen räknar bara sidvyer (och utelämnar länkarhändelser). Det här är en träffnivådimension. Intervall:<ul><li>mindre än 15 sekunder</li><li>15 till 29 sekunder</li><li>30 till 59 sekunder</li><li>1 till 3 minuter</li><li>3 till 5 minuter</li><li>5 till 10 minuter</li><li>10 till 15 minuter</li><li>15 till 20 minuter</li><li>20 till 30 minuter</li><li>mer än 30 minuter</li></ul> | Analysis Workspace |

## Hur&quot;Tidsåtgång&quot; beräknas

Adobe Analytics använder explicita värden (inklusive länkhändelser och videovyer) för att beräkna [!UICONTROL Time Spent].

>[!NOTE]
>
>Utan länkar som [!UICONTROL Video Views] eller [!UICONTROL Exit Links]går det inte att känna till hur lång tid som har tillbringats på ett besök senast. Av liknande skäl [!UICONTROL Bounce Visits] (d.v.s. besök med en enda träff) har inte heller någon associerad&quot;tid&quot;.

The **täljare** i beräkning av total tid är antalet sekunder som har använts.

The **nämnare** finns inte som separat mått i Adobe Analytics. Nämnaren är sekvenser för&quot;tidsåtgången&quot; på träffnivå. En sekvens är en sekvens med träffar där en viss variabel innehåller samma värde (antingen genom att den ställs in, sprids framåt eller beständig). &quot;Sprid framåt&quot; avser varaktigheten för avtryck mellan sidvyer (dvs. över efterföljande länkhändelser) för beräkning av hur lång tid som läggs på.

* I fallet med [!UICONTROL Page Name] eller andra dimensioner på träffnivå är nämnaren i stort sett [!UICONTROL 'Instances'] eller [!UICONTROL 'Page Views'], men med omladdningar och borttagna värden (t.ex. länkhändelser) som räknas som en enskild interaktion (en sekvens).

* Studs- och exit-träffar tas också bort från nämnaren eftersom &quot;tidsåtgången&quot; inte kan identifieras.

## Vanliga frågor

+++Kan alla mått för hur lång tid som spenderas användas på alla dimensioner?

De tidsmått som kan användas för alla dimensioner är:

* [!UICONTROL Total seconds spent]

* [!UICONTROL Time spent per visit] (sekunder)

* [!UICONTROL Time spent per visitor] (sekunder)

* [!UICONTROL Average time spent on site] (sekunder)

+++

+++Vilken tid används bäst för indelning med andra dimensioner?

The [!UICONTROL Time Spent on Page – granular] dimension är en träffnivådimension. Om du delar upp det här med en annan dimension kommer du att se i vilka sekunder en träff varade där även nedbrytningsdimensionen fanns.
I exemplet nedan associeras söktermen&quot;klassificeringar&quot; med träfftider på 54 sekunder, 59 sekunder osv., vilket kanske anger att besökarna spenderar tid på att läsa innehåll som returnerats för den perioden.

![](assets/time-spent1.png)

+++

+++Vad är lämpligt för måttet [!UICONTROL Time Spent on Page – granular]?

Alla mätvärden. Dimensionen visar hur lång tid som har ägnats åt den exakta träffen där händelsen inträffade. Högre tidsåtgång innebär att en besökare stannar längre på en sida (träff) där händelsen inträffade.

![](assets/time-spent2.png)

+++

+++Hur [!UICONTROL Average Time Spent on Site] skiljer sig från [!UICONTROL Time Spent per Visit]?

Skillnaden är nämnaren i måttet:

* [!UICONTROL Average time spent on site] använder de sekvenser som innehåller en dimensionsartikel.

* [!UICONTROL Time spent per visit] använder besöksantalet

Därför kan dessa mätvärden ge liknande resultat på besöksnivå, men de kommer att vara annorlunda på träffnivå.

+++

+++Varför ska man göra totalsummor med [!UICONTROL Average Time Spent on Site] matchar inte det överordnade radobjektet?

För [!UICONTROL Average Time Spent on Site] är beroende av obrutna sekvenser av en dimension, och den inre rapporten är inte beroende av den yttre rapporten när de här körningarna beräknas.

Ta till exempel följande besök.

| hit# | 1 | 2 | 3 |
|---|---|---|---|
| **Sekunder som använts** | 30 | 100 | 10 |
| **Sidnamn** | Startsida | Produkt | Startsida |
| **datum** | 1 januari | 1 januari | 1 januari |

Vid beräkning av den tid som tillbringats för hemsidan skulle det vara (30+10)/2=20, men om du delar upp den per dag skulle det ge (30+10)/1=40 eftersom dagen har en enda obruten serie som börjar den 1 januari.

Därför kan dessa mätvärden ge liknande resultat på besöksnivå, men de kommer att vara annorlunda på träffnivå.

+++

## Exempel på [!UICONTROL Time Spent] beräkning

Anta att följande uppsättning serversamtal är för en enskild besökare vid ett enda besök:

| Besök träffnummer | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **Besök förfluten tid (i sek)** | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **Sekunder som använts** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **Träff-typ** | Sida | Länk | Sida | Sida | Sida | Sida | Sida |
| **Sidnamn** | Startsida | - | Produkt | Startsida | Hem (ladda om) | Kundvagn | Orderbekräftelse |
|  |  |  |  |  |  |  |  |
| **prop1** | A (uppsättning) | A (Sprid över) | inte inställd | B (ange) | B (ange) | A(set) | C (ange) |
| **prop1 sekunder** | 30 | 50 | - | 10 | 40 | 60 | - |
|  |  |  |  |  |  |  |  |
| **eVar1** | Röd (ange) | Röd (beständig) | (utgången) | Blå (ange) | Blå (ange) | Blå (beständig) | Röd (ange) |
| **eVar1 sekunder** | 30 | 50 | - | 10 | 40 | 60 | - |

Baserat på tabellen ovan beräknas tidsåtgången enligt följande:

| prop1 | Totalt antal sekunder som använts | Tid per besök | Tid per besökare | Antal sekvenser | Genomsnittlig tid på webbplatsen |
|---|---|---|---|---|---|
| A | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| Otilldelad tid | 100 | - | - | - | - |

| eVar1 | Totalt antal sekunder som använts | Tid per besök | Tid per besökare | Antal sekvenser | Genomsnittlig tid på webbplatsen |
|---|---|---|---|---|---|
| Röd | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| Blå | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| Otilldelad tid | 100 | - | - | - | - |

Tid per besök (i korthet): 290 Tid som spenderas på sidan (i korthet): 10, 30, 40, 50, 60, 100

Ytterligare några kommentarer som stöder exemplet:

* Alla tidsberäkningar baseras på den tid som förflutit, som börjar vid noll första besöket.

* &quot;Sekunder som har använts&quot; är skillnaden mellan tidsstämpeln för den aktuella träffen och tidsstämpeln för nästa träff. Därför har den senaste besöksträffen (och studenterna) ingen tid tillbringats.

* En &quot;sekvens&quot; är en sekventiell uppsättning träffar där en viss variabel innehåller samma värde (antingen genom att den ställs in, sprids framåt eller beständig). Exempel: prop1 &quot;A&quot; har två sekvenser: träffar 1 och 2 och trycker på 6. Värden för den senaste träffen av besöket startar inte en ny sekvens eftersom den senaste träffen inte har någon tid. Genomsnittlig tid som använts på webbplatsen använder sekvenser i nämnaren.

   * För den tid som används är props&quot;spridda framåt&quot; från sidträffar till efterföljande länkträffar som visas ovan för prop1 vid träff 2. Detta gör att det värde som ställdes in för prop1 vid träff 1 (&quot;A&quot;) kan samla tiden som användes för träff 2.

   * eVars ackumulerar tid som tillbringats på en träff där eVarna är inställd eller bestående. eVarnas beständighet definieras av inställningarna för eVar i Analytics > Admin.
