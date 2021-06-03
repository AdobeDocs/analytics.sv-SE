---
description: Du får åtkomst till dessa funktioner genom att markera Visa avancerat i listrutan Funktioner.
title: Referera till avancerade funktioner
uuid: 7d1071b9-1737-4b7c-b318-87907dae5619
exl-id: a6d0c2ad-864d-4cab-84e0-dd6ce0a4c6b1
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '2906'
ht-degree: 1%

---

# Referens: avancerade funktioner

Du får åtkomst till dessa funktioner genom att kontrollera **[!UICONTROL Show Advanced]** i listrutan **[!UICONTROL Functions]**.

## Tabellfunktioner kontra radfunktioner {#section_8977BE40A47E4ED79EB543A9703A4905}

En tabellfunktion är en funktion där utdata är desamma för alla rader i tabellen. En radfunktion är en funktion där utdata är olika för alla rader i tabellen.

## Vad betyder parametern Include-Zeros? {#section_C7A2B05929584C65B308FD372CB8E8E3}

Den anger om nollor ska inkluderas i beräkningen. Ibland betyder noll&quot;ingenting&quot;, men ibland är det viktigt.

Om du till exempel har ett intäktsmått och sedan lägger till ett sidvymått i rapporten finns det plötsligt fler rader för dina intäkter som alla är noll. Du vill antagligen inte att detta ska påverka MEAN, MIN, QUARTILE osv. beräkningar som du har i intäktskolumnen. I det här fallet kontrollerar du parametern include-zeros.

Å andra sidan, om du har två mätvärden som du är intresserad av, kan det vara svårt att säga att en har ett högre genomsnitt eller ett lägre värde, eftersom vissa av raderna var nollor, så du skulle inte kontrollera parametern så att den inkluderar nollorna.

## OCH {#concept_E14513FE464F4491AD0D4130D4EE621C}

Returnerar värdet för dess argument. Använd NOT för att kontrollera att ett värde inte är lika med ett visst värde.

>[!NOTE]
>
>0 (noll) betyder False och alla andra värden är True.

```
AND(logical_test1,[logical_test2],...)
```

| Argument | Beskrivning |
|---|---|
| *logical_test1* | Obligatoriskt. Alla värden eller uttryck som kan utvärderas till TRUE eller FALSE. |
| *logical_test2* | Valfritt. Ytterligare villkor som du vill utvärdera som TRUE eller FALSE |

## Ungefärlig distinkt (dimension) {#concept_000776E4FA66461EBA79910B7558D5D7}

Returnerar det ungefärliga distinkta antalet dimensionsobjekt för den valda dimensionen. Funktionen använder HyperLogLog-metoden (HLL) för att beräkna distinkta antal.  Den är konfigurerad för att garantera att värdet ligger inom 5 % av det faktiska värdet 95 % av tiden.

```
Approximate Count Distinct (dimension)
```

| Argument |  |
|---|---|
| *dimension* | Dimensionen som du vill ha det ungefärliga distinkta artikelantalet för. |

### Exempel på användningsfall {#section_424E3FC5092948F0A9D655F6CCBA0312}

Approximate Count Distinct (kundens ID-eVar) är ett vanligt användningsfall för den här funktionen.

Definition för ett nytt beräknat mått för&quot;Approximate Customers&quot;:

![](assets/approx-count-distinct.png)

Så här kan måttet&quot;Approximate Customers&quot; användas vid rapportering:

![](assets/approx-customers.png)

### Uniques överskreds {#section_9C583858A9F94FF7BA054D1043194BAA}

Precis som Count() och RowCount() gäller gränserna [&quot;uniques överstigit&quot; för Approximate Count Distinct(). ](https://experienceleague.adobe.com/docs/analytics/technotes/low-traffic.html) Om gränsen för antal unika tecken överskrids inom en viss månad för en dimension räknas värdet som 1 dimensionspost.

### Jämföra räkningsfunktioner {#section_440FB8FB44374459B2C6AE2DA504FC0B}

Approximate Count Distinct() är en förbättring av funktionerna Count() och RowCount() eftersom måttet som skapas kan användas i alla dimensionella rapporter för att återge ett ungefärligt antal objekt för en separat dimension. Exempel: antalet kund-ID:n som används i en rapport av typ av mobil enhet.

Den här funktionen är marginellt mindre exakt än Count() och RowCount() eftersom den använder HLL-metoden, medan Count() och RowCount() är exakta tal.

## Båge cosinus (rad) {#concept_1DA3404F3DDE4C6BAF3DBDD655D79C7B}

Returnerar arcus cosinus, eller inverterad cosinus, för ett mätresultat. Arcus cosinus är den vinkel vars cosinus är tal. Den returnerade vinkeln anges i radianer i intervallet 0 (noll) till pi. Om du vill konvertera resultatet från radianer till grader multiplicerar du det med 180/PI( ).

```
ACOS(metric)
```

| Argument |  |
|---|---|
| *mått* | cosinus för vinkeln som du vill ha från -1 till 1. |

## Båge sinus (rad) {#concept_90F00DEC46BA47F8A21493647D9668CD}

Returnerar arcus sinus, eller inverterad sinus, för ett tal. Arcussinus är vinkeln vars sinus är tal. Den returnerade vinkeln anges i radianer i intervallet -pi/2 till pi/2. Om du vill uttrycka arcussinus i grader multiplicerar du resultatet med 180/PI( ).

```
ASIN(metric) 
```

| Argument |  |
|---|---|
| *mått* | cosinus för vinkeln som du vill ha från -1 till 1. |

## Bågtangent (rad) {#concept_3408520673774A10998E9BD8B909E90C}

Returnerar talets arcus tangens, eller inverterade tangent. Arcus tangent är vinkeln vars tangent är tal. Den returnerade vinkeln anges i radianer i intervallet -pi/2 till pi/2. Om du vill uttrycka arcus tangens i grader multiplicerar du resultatet med 180/PI( ).

```
ATAN(metric)
```

| Argument |  |
|---|---|
| *mått* | cosinus för vinkeln som du vill ha från -1 till 1. |

## Exponentiell regression: Förutsedd Y (rad) {#concept_25615693312B4A7AB09A2921083502AD}

Beräknar de förväntade y-värdena (metric_Y), med tanke på de kända x-värdena (metric_X), med hjälp av metoden &quot;minst fyrkanter&quot; för att beräkna raden för bästa passform baserat på .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som oberoende data. |
| *metric_Y* | Ett mätvärde som du vill ange som beroende data. |

## Cdf-T {#concept_4E2F2673532A48B5AF786521DE428A66}

Returnerar procentandelen av värden i en elevs t-fördelning, med n frihetsgrader som har ett z-score mindre än x.

```
cdf_t( -∞, n ) = 0 
cdf_t(  ∞, n ) = 1 
cdf_t( 3, 5 ) ? 0.99865 
cdf_t( -2, 7 ) ? 0.0227501 
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z {#concept_99C97ACC40A94FADBCF7393A17BC2D12}

Returnerar procentandelen av värden i en normal fördelning som har ett z-score mindre än x.

```
cdf_z( -∞ ) = 0 
cdf_z( ∞ ) = 1 
cdf_z( 0 ) = 0.5 
cdf_z( 2 ) ? 0.97725 
cdf_z( -3 ) ? 0.0013499 
 
```

## Tak (rad) {#concept_A14CDB1E419B4AA18D335E5BA2548346}

Returnerar det minsta heltalet som inte är mindre än ett givet värde. Om du till exempel vill undvika att rapportera valutadecimaler för intäkter och en produkt har 569,34 USD använder du formeln CEILING( *Intäkter*) för att avrunda intäkter upp till närmaste dollar, eller 570 USD.

```
CEILING(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det mätvärde som du vill runda av. |

## Cosine (rad) {#concept_DD07AA1FB08145DC89B69D704545FD0A}

Returnerar cosinus för den angivna vinkeln. Om vinkeln är i grader multiplicerar du vinkeln med PI( )/180.

```
COS(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill ha cosinus för. |

## Kubrot {#concept_BD93EFA45DF7447A8F839E1CA5B5F795}

Returnerar den positiva kubroten för ett tal. Kubroten för ett tal är värdet för det talet upphöjt till upphöjt till upphöjt till 1/3.

```
CBRT(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Måttet som du vill ha kubroten för. |

## Kumulativ {#concept_3D3347797B6344CE88B394C3E39318ED}

Returnerar summan av x för de sista N-raderna (enligt ordningen i dimensionen, med hash-värden för strängbaserade fält).

Om N &lt;= 0 används alla föregående rader. Eftersom den ordnas efter dimensionen är den bara användbar för dimensioner som har en naturlig ordning som datum eller längd.

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) | 
|------+------+--------------+--------------| 
| May  | $500 | $500         | $500         | 
| June | $200 | $700         | $700         | 
| July | $400 | $1100        | $600         | 
 
```

## Kumulativt genomsnitt {#concept_ABB650962DC64FD58A79C305282D3E61}

Returnerar medelvärdet för de sista N raderna.

Om N &lt;= 0 används alla föregående rader. Eftersom den ordnas efter dimensionen är den bara användbar för dimensioner som har en naturlig ordning som datum eller längd.

>[!NOTE]
>
>Detta fungerar inte som du kan förvänta dig med tariffvärden som intäkter/besökare: i stället för att summera intäkterna under det senaste N:et och summera besökarna under det senaste N:et och sedan dela upp dem. Använd i stället

```
cumul(revenue)/cumul(visitor)
```

## Jämn {#concept_A3B97152B5F74E04A97018B35734BEEB}

Returnerar objekt som matchar exakt för ett numeriskt värde eller strängvärde.

## Exponentiell regression_korrelationskoefficient (tabell) {#concept_C18BBFA43C1A499293290DF49566D8D8}

Returnerar korrelationskoefficienten *r* mellan två metriska kolumner ( *metrisk_A* och *metrisk_B*) för regressionsekvationen.

```
CORREL.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mått som du vill korrelera med *metric_Y*. |
| *metric_Y* | Ett mått som du vill korrelera med *metric_X*. |

## Exponentiell regression: Intercept (tabell) {#concept_0047206C827841AD936A3BE58EEE1514}

Returnerar spärren *b* mellan två måttkolumner ( *metric_X* och *metric_Y*) för

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som oberoende data. |
| *metric_Y* | Ett mätvärde som du vill ange som beroende data. |

## Exponentiell regression: Lutning (tabell) {#concept_230991B0371E44308C52853EFA656F04}

Returnerar lutningen *a* mellan två måttkolumner ( *metric_X* och *metric_Y*) för .

```
SLOPE.EXP(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som oberoende data. |
| *metric_Y* | Ett mätvärde som du vill ange som beroende data. |

## Våning (rad) {#concept_D368150EC3684077B284EE471463FC31}

Returnerar det största heltalet som inte är större än ett givet värde. Om du till exempel vill undvika att rapportera valutadecimaler för intäkter och en produkt har 569,34 USD använder du formeln FLOOR( *Intäkter*) för att avrunda intäkten nedåt till närmaste USD, eller 569 USD.

```
FLOOR(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det mätvärde som du vill runda av. |

## Större än {#concept_A83734A0C0C14646B76D2CC5E677C644}

Returnerar objekt vars numeriska antal är större än det angivna värdet.

## Större än eller lika med {#concept_8CA6DF1F84784D50849BF1C566AE1D37}

Returnerar objekt vars numeriska värde är större än eller lika med det angivna värdet.

## Hyperbolisk cosinus (rad) {#concept_79DD5681CE9640BDBA3C3F527343CA98}

Returnerar hyperbolisk cosinus för ett tal.

```
COSH(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill hitta hyperbolisk cosinus för. |

## Hyperbolisk sinus (rad) {#concept_96230731600C45E3A4E823FE155ABA85}

Returnerar hyperbolisk sinus för ett tal.

```
SINH(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill hitta hyperbolisk sinus för. |

## Hyperbolisk tangens (rad) {#concept_BD249013732F462B9863629D142BCA6A}

Returnerar hyperbolisk tangens för ett tal.

```
TANH(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill hitta hyperbolisk tangent för. |

## IF (rad) {#concept_6BF0F3EAF3EF42C288AEC9A79806C48E}

IF-funktionen returnerar ett värde om ett villkor som du anger utvärderas till TRUE och ett annat värde om villkoret utvärderas till FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

| Argument | Beskrivning |
|---|---|
| *logical_test* | Obligatoriskt. Alla värden eller uttryck som kan utvärderas till TRUE eller FALSE. |
| *[value_if_true]* | Värdet som du vill returnera om argumentet *logical_test* utvärderas till TRUE. (Detta argument är som standard 0 om det inte inkluderas.) |
| *[value_if_false]* | Värdet som du vill returnera om argumentet *logical_test* utvärderas till FALSE. (Detta argument är som standard 0 om det inte inkluderas.) |

## Mindre än {#concept_A4A85C0FDF944AACAD4B8B55699D1B11}

Returnerar objekt vars numeriska antal är mindre än det angivna värdet.

## Mindre än eller lika med {#concept_99D12154DE4848B1B0A6327C4322D288}

Returnerar objekt vars numeriska värde är mindre än eller lika med det angivna värdet.

## Linjär regression_Korrelationskoefficient {#concept_132AC6B3A55248AA9C002C1FBEB55C60}

Y = a X + b. Returnerar korrelationskoefficienten

## Linear regression_Intercept {#concept_E44A8D78B802442DB855A07609FC7E99}

Y = a X + b. Returnerar b.

## Linear regression_Predicated Y {#concept_9612B9BF106D4D278648D2DF92E98EFC}

Y = a X + b. Returnerar Y.

## Linear regression_Slope {#concept_12352982082A4DDF824366B073B4C213}

Y = a X + b. Returnerar a.

## Loggbas 10 (rad) {#concept_4C65DF9659164261BE52AA5A95FD6BC1}

Returnerar 10-logaritmen för ett tal.

```
LOG10(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det positiva realtal som du vill ha bas-10-logaritmen för. |

## Loggregression: Korrelationskoefficient (tabell) {#concept_F3EB35016B754E74BE41766E46FDC246}

Returnerar korrelationskoefficienten *r* mellan två metriska kolumner (*metric_X* och *metric_Y*) för regressionsekvationen [!DNL Y = a ln(X) + b]. Den beräknas med CORREL-ekvationen.

```
CORREL.LOG(metric_X,metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mått som du vill korrelera med *metric_Y*. |
| *metric_Y* | Ett mått som du vill korrelera med *metric_X*. |

## Loggregression: Intercept (tabell) {#concept_75A3282EDF54417897063DC26D4FA363}

Returnerar spärren *b* som regressionen mellan två metriska kolumner med minsta kvadrat (*metric_X* och *metric_Y*) för regressionsekvationen [!DNL Y = a ln(X) + b]. Den beräknas med INTERCEPT-ekvationen.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som oberoende data. |
| *metric_Y* | Ett mätvärde som du vill ange som beroende data. |

## Loggregression: Förutsedd Y (rad) {#concept_5F3A9263BBB84E6098160A4DFB9E3607}

Beräknar de förväntade [!DNL y] värdena (metric_Y) med tanke på de kända [!DNL x] värdena (metric_X) med metoden &quot;minst fyrkanter&quot; för att beräkna raden för bästa passform baserat på [!DNL Y = a ln(X) + b]. Den beräknas med hjälp av ESTIMATE-ekvationen.

I regressionsanalys beräknar den här funktionen de förväntade [!DNL y]-värdena (*metric_Y*) med tanke på de kända [!DNL x]-värdena (*metric_X*) med hjälp av logaritmen för att beräkna raden som passar bäst för regressionsekvationen [!DNL Y = a ln(X) + b]. [!DNL a]-värdena motsvarar varje x-värde och [!DNL b] är ett konstant värde.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som oberoende data. |
| *metric_Y* | Ett mätvärde som du vill ange som beroende data. |

## Loggregression: Lutning (tabell) {#concept_B291EFBE121446A6B3B07B262BBD4EF2}

Returnerar lutningen *a* mellan två måttkolumner (*metric_X* och *metric_Y*) för regressionsekvationen [!DNL Y = a ln(X) + b]. Den beräknas med hjälp av SLOPE-ekvationen.

```
SLOPE.LOG(metric_A, metric_B)
```

| Argument | Beskrivning |
|---|---|
| *metric_A* | Ett mätvärde som du vill ange som oberoende data. |
| *metrisk_B* | Ett mätvärde som du vill ange som beroende data. |

## Naturlig logg {#concept_D3BE148A9B84412F8CA61734EB35FF9E}

Returnerar den naturliga logaritmen för ett tal. Naturliga logaritmer baseras på konstanten *e* (2.71828182845904). LN är inversen till EXP-funktionen.

```
LN(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Det positiva realtal som du vill ha den naturliga logaritmen för. |

## NOT {#concept_BD954C455A8148A3904A301EC4DC821E}

Returnerar 1 om talet är 0 eller returnerar 0 om det är ett annat tal.

```
NOT(logical)
```

| Argument | Beskrivning |
|---|---|
| *logisk* | Obligatoriskt. Ett värde eller uttryck som kan utvärderas till TRUE eller FALSE. |

Om du använder NOT måste du känna till om uttrycken (&lt;, >, =, &lt;> osv.) returnera 0- eller 1-värden.

## Inte lika med {#concept_EC010B7A9D2049099114A382D662FC16}

Returnerar alla objekt som inte innehåller den exakta matchningen av det angivna värdet.

## Eller (rad) {#concept_AF81A33A376C4849A4C14F3A380639D2}

Returnerar TRUE om något argument är TRUE, eller returnerar FALSE om alla argument är FALSE.

>[!NOTE]
>
>0 (noll) betyder False och alla andra värden är True.

```
OR(logical_test1,[logical_test2],...)
```

| Argument | Beskrivning |
|---|---|
| *logical_test1* | Obligatoriskt. Alla värden eller uttryck som kan utvärderas till TRUE eller FALSE. |
| *logical_test2* | Valfritt. Ytterligare villkor som du vill utvärdera som TRUE eller FALSE |

## Pi {#concept_41258789660D4A33B5FB86228F12ED9C}

Returnerar konstanten PI, 3,14159265358979, med 15 siffror.

```
PI()
```

Funktionen [!DNL PI]saknar argument.

## Strömregression: Korrelationskoefficient (tabell) {#concept_91EC2CFB5433494F9E0F4FDD66C63766}

Returnerar korrelationskoefficienten *r* mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mått som du vill korrelera med *metric_Y*. |
| *metric_Y* | Ett mått som du vill korrelera med *metric_X*. |

## Strömregression: Intercept (tabell) {#concept_7781C85597D64D578E19B212BDD1764F}

Returnerar spärren *b* mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som oberoende data. |
| *metric_Y* | Ett mätvärde som du vill ange som beroende data. |

## Strömregression: Förutsedd Y (rad) {#concept_CD652C0A921D4EFBA8F180CB8E486B18}

Beräknar de förväntade [!DNL y]-värdena ( [!DNL metric_Y]) med tanke på de kända [!DNL x]-värdena ( [!DNL metric_X]) med metoden &quot;minst fyrkanter&quot; för att beräkna raden som passar bäst för [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som oberoende data. |
| *metric_Y* | Ett mätvärde som du vill ange som beroende data. |

## Strömregression: Lutning (tabell) {#concept_5B9E71B989234694BEB5EEF29148766C}

Returnerar lutningen *a* mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som oberoende data. |
| *metric_Y* | Ett mätvärde som du vill ange som beroende data. |

## Kvadratisk regression: Korrelationskoefficient (tabell) {#concept_9C9101A456B541E69BA29FCEAC8CD917}

Returnerar korrelationskoefficienten, *r*, mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mått som du vill korrelera med *metric_Y*. |
| *metric_Y* | Ett mått som du vill korrelera med *metric_X*. |

## Kvadratisk regression: Intercept (tabell) {#concept_69DC0FD6D38C40E9876F1FD08EC0E4DE}

Returnerar spärren *b* mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som oberoende data. |
| *metric_Y* | Ett mätvärde som du vill ange som beroende data. |

## Kvadratisk regression: Förutsedd Y (rad) {#concept_2F1ED70B1BDE4664A61CC09D30C39CBB}

Beräknar de förväntade [!DNL y] värdena (metric_Y), med tanke på de kända [!DNL x] värdena (metric_X) med hjälp av metoden med minsta kvadrat för att beräkna raden för bästa passform med [!DNL Y=(a*X+b)]****.

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| Argument | Beskrivning |
|---|---|
| *metric_A* | Ett mätvärde som du vill ange som oberoende data. |
| *metrisk_B* | Ett mätvärde som du vill ange som beroende data. |

## Kvadratisk regression: Lutning (tabell) {#concept_0023321DA8E84E6D9BCB06883CA41645}

Returnerar lutningen *a* mellan två måttkolumner (*metric_X* och metric_Y) för [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som oberoende data. |
| *metric_Y* | Ett mätvärde som du vill ange som beroende data. |

## Ömsesidig regression: Korrelationskoefficient (tabell) {#concept_EBEC509A19164B8AB2DBDED62F4BA2A5}

Returnerar korrelationskoefficienten *r* mellan två måttkolumner (*metric_X)* och *metric_Y*) för [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mått som du vill korrelera med *metric_Y*. |
| *metric_Y* | Ett mått som du vill korrelera med *metric_X*. |

## Ömsesidig regression: Intercept (tabell) {#concept_2DA45B5C69F140EC987649D2C88F19B3}

Returnerar spärren *b* mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som oberoende data. |
| *metric_Y* | Ett mätvärde som du vill ange som beroende data. |

## Ömsesidig regression: Förutsedd Y (rad) {#concept_2CF4B8F417A84FE98050FE488E227DF8}

Beräknar de förväntade [!DNL y] värdena (metric_Y), med tanke på de kända [!DNL x]-värdena (metric_X) med hjälp av metoden med minst fyrkanter för att beräkna raden för bästa passning med [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som oberoende data. |
| *metric_Y* | Ett mätvärde som du vill ange som beroende data. |

## Ömsesidig regression: Lutning (tabell) {#concept_8A8B68C9728E42A6BFDC6BD5CBDCCEC5}

Returnerar lutningen *a* mellan två måttkolumner (*metric_X* och *metric_Y*) för [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beskrivning |
|---|---|
| *metric_X* | Ett mätvärde som du vill ange som oberoende data. |
| *metric_Y* | Ett mätvärde som du vill ange som beroende data. |

## Sinus (rad) {#concept_21C8C3AA835947A28B53A4E756A7451E}

Returnerar sinus för den angivna vinkeln. Om vinkeln är i grader multiplicerar du vinkeln med PI( )/180.

```
SIN(metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill ha sinus för. |

## T-poäng {#concept_80D2B4CED3D0426896B2412B4FC73BF7}

Alias för Z-poäng, dvs. avvikelsen från medelvärdet dividerat med standardavvikelsen

## T-test {#concept_A1F78F4A765348E38DBCAD2E8F638EB5}

Utför ett m-tailed t-test med t-score på kol och n frihetsgrader.

Signaturen är `t_test( x, n, m )`. Under anropet anropas bara `m*cdf_t(-abs(x),n)`. (Detta liknar z-test-funktionen som kör `m*cdf_z(-abs(x))`.

Här är `m` antalet sviter och `n` antalet frihetsgrader. Dessa ska vara tal (konstanta för hela rapporten, dvs. inte ändras rad för rad).

`X` är t-test-värdet och skulle ofta vara en formel (t.ex. zscore) som baseras på ett mätresultat och utvärderas på varje rad.

Returvärdet är sannolikheten att se provningsvärdet x med hänsyn till antalet frihetsgrader och antalet svansar.

**Exempel:**

1. Använd den för att hitta avvikelser:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Kombinera den med `if` om du vill ignorera mycket höga eller låga avhoppsfrekvenser och räkna besök på allt annat:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent {#concept_C25E00CB17054263AB0460D9EF94A700}

Returnerar tangenten för den angivna vinkeln. Om vinkeln är i grader multiplicerar du vinkeln med PI( )/180.

```
TAN (metric)
```

| Argument | Beskrivning |
|---|---|
| *mått* | Vinkeln i radianer som du vill ha tangenten för. |

## Z-poäng (rad) {#concept_96BEAC79476C49B899DB7E193A5E7ADD}

Returnerar Z-poäng, eller normal poäng, baserat på en normal fördelning. Z-värdet är antalet standardavvikelser som en observation ligger från medelvärdet. Ett Z-värde på 0 (noll) innebär att poängen är samma som medelvärdet. Ett Z-värde kan vara positivt eller negativt, vilket anger om det ligger över eller under medelvärdet och hur många standardavvikelser.

Ekvationen för Z-score är:

![](assets/z_score.png)

där [!DNL x] är råpoängen, är [!DNL μ] medelvärdet för populationen och [!DNL σ] standardavvikelsen för populationen.

>[!NOTE]
>
>[!DNL μ] (mu) och[!DNL σ] (sigma) beräknas automatiskt utifrån måttet.

Z-score (metrisk)

<table id="table_AEA3622A58F54EA495468A9402651E1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>mått</i> </td> 
   <td colname="col2"> <p> Returnerar värdet för dess första argument som inte är noll. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Z-test {#concept_2A4ADD6B3AEB4A2E8465F527FAFC4C23}

Utför ett n-tailed Z-test med Z-score på A.

Returnerar sannolikheten för att den aktuella raden kan ses av en slump i kolumnen.

>[!NOTE]
>
>Anta att värdena normalt fördelas.
