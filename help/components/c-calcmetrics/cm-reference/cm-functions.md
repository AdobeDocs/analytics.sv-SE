---
description: Med beräkningsverktyget kan du använda statistiska och matematiska funktioner för att skapa avancerade beräknade värden.
title: Referensfunktioner
uuid: 5c2b4a0e-613c-4b27-95b8-01d480aeab78
translation-type: tm+mt
source-git-commit: 83066f8e372fb5f8af3b7db2c165ab1cd8b76a10

---


# Referens: grundläggande funktioner

Med beräkningsverktyget kan du använda statistiska och matematiska funktioner för att skapa avancerade beräknade värden.

Här är en lista i alfabetisk ordning över funktionerna och deras definitioner.

> [!NOTE] Där [!DNL metric] identifieras som ett argument i en funktion tillåts även andra uttryck av mätvärden. Till exempel [!DNL MAXV(metrics)] tillåter även [!DNL MAXV(PageViews + Visits).]

## Tabellfunktioner kontra radfunktioner {#section_8977BE40A47E4ED79EB543A9703A4905}

En tabellfunktion är en funktion där utdata är desamma för alla rader i tabellen. En radfunktion är en funktion där utdata är olika för alla rader i tabellen.

## Absolut värde (rad) {#concept_4CC47884F7CA49D5B84AC898EA596673}

Returnerar det absoluta värdet av ett tal. Det absoluta värdet för ett tal är talet med ett positivt värde.

```
ABS(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det mått som du vill ha det absoluta värdet för. |

## Högsta kolumn {#concept_B25518D717D24F82B65CDE49A153D3A3}

Returnerar det största värdet i en uppsättning dimensionselement för en måttkolumn. MAXV utvärderas lodrätt i en enda kolumn (mått) över dimensionselement.

```
MAXV(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Ett mått som du skulle vilja ha utvärderat. |

## Minsta kolumn {#concept_5B1033F8ACE9485F9AD3CDC0D146391B}

Returnerar det minsta värdet i en uppsättning dimensionselement för en måttkolumn. MINV utvärderas lodrätt i en enda kolumn (mått) över dimensionselement.

```
MINV(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Ett mått som du skulle vilja ha utvärderat. |

## Kolumnsumma {#concept_391F04FBC3CC43368CA0C5AACE74D4B1}

Lägger till alla numeriska värden för ett mått i en kolumn (över elementen i en dimension).

```
SUM(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det mått som du vill ha det totala värdet eller summan för. |

## Antal (tabell) {#concept_2C6ED2B88AB74481BD130969FB071A41}

Returnerar antalet, eller antalet, värden som inte är noll för ett mätvärde i en kolumn (antalet unika element som rapporteras inom en dimension).

```
COUNT(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det mått som du vill räkna. |

## Exponent (rad) {#concept_17554F9D234449FB8DDEE895816B3FF1}

Returnerar *e* upphöjt till ett angivet tal. Konstanten *e* är lika med 2,71828182845904, basen för den naturliga logaritmen. EXP är den inverterade LN, den naturliga logaritmen av ett tal.

```
EXP(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Exponenten som används på basen *e*. |

## Exponentiering {#concept_941578534F1E4583B1BEB067C8113A21}

Strömoperator

<pre>
pow(x,y) =<sup>xy</sup> = x*x*x*... (y gånger)
</pre>

## Medel (tabell) {#concept_F4FF950580304D0B99DA7FBB5DB8730A}

Returnerar det aritmetiska medelvärdet, eller medelvärdet, för ett mått i en kolumn.

```
MEAN(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det mätvärde som du vill ha medelvärdet för. |

## Median (tabell) {#concept_183EC31208524EDB8463D986DE2E895F}

Returnerar medianvärdet för ett mått i en kolumn. Medianvärdet är talet i mitten av en uppsättning tal, det vill säga hälften av talen har värden som är större än eller lika med medianvärdet och hälften är mindre än eller lika med medianvärdet.

```
MEDIAN(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det mätvärde som du vill ha medianen för. |

## Modulo {#concept_DE0825D7A51643219CB01F59667EA352}

Resten av col1 / col2, med division Euclidean.

Returnerar resten efter att x delats med y.

```
x = floor(x/y) + modulo(x,y)
```

Returvärdet har samma tecken som indata (eller är noll).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

Använd om du alltid vill få ett positivt tal

```
modulo(modulo(x,y)+y,y)
```

## Procent (tabell) {#concept_51DF57B606D14F898E5010DBA61CA979}

Returnerar den n:te percentilen av värden för ett mätvärde. Du kan använda den här funktionen för att fastställa ett tröskelvärde för godkännande. Du kan t.ex. bestämma att undersöka dimensionselement som får en poäng över 90-percentilen.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>mått</i> </td> 
   <td colname="col2"> Den måttkolumn som definierar relativ position. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> Procentvärdet i intervallet 0 till 100. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (tabell) {#concept_BFD37F0F23A24AD181407142233FA151}

Returnerar kvartilen med värden för ett mått. Du kan till exempel använda kvartilarna för att hitta de 25 % av de bästa produkterna som genererar störst intäkter. MINV, MEDIAN och MAXV returnerar samma värde som QUARTILE när quart är lika med 0 (noll), 2 respektive 4.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>mått</i> </td> 
   <td colname="col2"> Måttet som du vill ha kvartilsvärdet för. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Anger vilket *värde som ska returneras. </td> 
  </tr> 
 </tbody> 
</table>

*Om *quart* = 0 returnerar QUARTILE minimivärdet. Om *quart* = 1 returnerar QUARTILE den första kvartilen (25 percentiler). Om *quart* = 2 returnerar QUARTILE den första kvartilen (50 percentiler). Om *quart* = 3 returnerar QUARTILE den första kvartilen (75 percentiler). Om *quart* = 4 returnerar QUARTILE det maximala värdet.

## Ansökningstillfälle {#concept_2F12F2A6ACD445A0A8FF648AE4D4CB9E}

Returnerar närmaste heltal för ett givet värde. Om du till exempel vill undvika att rapportera valutadecimaler för intäkter och en produkt har 569,34 USD, använder du formeln Round( *Intäkter*) för att avrunda intäkten till närmaste dollar, eller 569 dollar. En produkt som rapporterar 569,51 USD avrundas till närmaste dollar, eller 570 USD.

```
ROUND(metric)
```

| Argument | Beskrivning |
|---|---|
| *tal* | Det mätvärde som du vill runda av. |

Round without a digits parameter is the same as round with a digits parameter of 0, DVS. round to the leading integer. Med en sifferparameter returneras så många siffror till höger om decimaltecknet. Om siffrorna är negativa returneras 0 till vänster om decimaltecknet.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Antal rader {#concept_0DBF5995881C47CF95F793125F3A0E2B}

Returnerar antalet rader för en given kolumn (antalet unika element som rapporteras inom en dimension). &quot;Uniques beyond&quot; räknas som 1.

## Max rad {#concept_984D045D7EDD4A1ABED454CDF2EC23C5}

Det maximala antalet kolumner i varje rad.

## Min rad {#concept_A6FB9E72C70A43D0B31565E70B8122BD}

Minimivärdet för kolumnerna i varje rad.

## Radsumma {#concept_E9EAB0FC5233498F907E7A078698A98E}

Summan av kolumnerna på varje rad.

## Kvadratrot (rad) {#concept_6460DFA51EC24527A2317970FB76D404}

Returnerar den positiva kvadratroten av ett tal. Kvadratroten av ett tal är värdet av talet upphöjt till 1/2.

```
SQRT(metric)
```

| Argument | Beskrivning |
|---|---|
| *tal* | Måttet som du vill ha kvadratroten för. |

## Standardavvikelse (tabell) {#concept_A383A8BCC6FA42D7B73F7C83997D782A}

Returnerar standardavvikelsen, eller kvadratroten av variansen, baserat på en exempelpopulation med data.

Ekvationen för STDEV är:

![](assets/std_dev.png)

där x är medelvärdet för provet (*mätvärdet*) och *n* är provstorleken.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Beskrivning</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> mått</i></b> </td> 
   <td> <p> Det mått som du vill använda för standardavvikelsen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Varians (tabell) {#concept_269751EDC5A34E689112AE16E04A11B0}

Returnerar variansen baserat på en exempelpopulation med data.

Ekvationen för VARIANS är:

![](assets/variance_eq.png)

där x är medelvärdet för provet, MEAN(*metrisk*) och *n* är samplingsstorleken.

```
VARIANCE(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det mått som du vill ha variansen för. |

För att kunna beräkna en varians tittar du på en hel sifferkolumn. Från den listan med tal beräknar du först medelvärdet. När du har ett genomsnitt går du igenom varje inlägg och gör följande:

1. Subtrahera medelvärdet från talet.

2. Fyrkantiga resultatet.

3. Lägg till det till summan.

När du har itererat över hela kolumnen får du en totalsumma. Sedan dividerar du summan med antalet objekt i kolumnen. Talet är variansen för kolumnen. Det är ett enda tal. Den visas dock som en kolumn med siffror.

Anta att du har en kolumn med tre objekt:

1

2

3

Medelvärdet för den här kolumnen är 2. Kolumnens varians är ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3. I Ad hoc-analys ser detta ut så här:

1 2/3

2 2/3

3 2/3
