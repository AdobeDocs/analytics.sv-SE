---
description: Lär dig mer om avvikelseidentifiering och hur det beräknas.
title: Hur avvikelseidentifiering används för att automatiskt hitta trender
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
feature: Report Builder
role: User, Admin
exl-id: 6e3881c8-3e1c-4df8-ba38-e8bc84cfc3d4
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# Avvikelseidentifiering{#anomaly-detection}

{{legacy-arb}}

Analysidentifiering använder statistisk modellering för att automatiskt hitta oväntade trender i dina data. Modellen analyserar mätvärden och fastställer en nedre gräns, övre gräns och förväntat värdeintervall. När en oväntad krökning eller släppning inträffar visas en varning i rapporten.

Exempel på avvikelser du kan undersöka är:

* Drastiska droppar i genomsnittligt ordervärde
* Inträffar i order med låg intäkt
* Taggar eller droppar i testregistreringar
* Droppar i landningssidvyer
* Spänn i videobufferthändelser
* Taggar i låga videobithastigheter

>[!NOTE]
>
>Avvikelseidentifiering är bara tillgängligt när du väljer daggranularitet.

<p class="head"> <b>Mätvärden för avvikelseidentifiering</b> </p>

Analysidentifiering lägger till nya mätvärden för varje mätvärde som du väljer, inklusive:

<table id="table_BF75FC874634498DB6632C12CBD8D533"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nedre gräns </td> 
   <td colname="col2"> <p>Lägre nivå för förutsägelseintervallet. Värden under den här nivån betraktas som onormala. </p> <p>Representerar 95-procentig konfidens av att värden kommer att ligga över denna nivå. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Förväntat </td> 
   <td colname="col2"> <p>Det förväntade värdet baserat på dataanalysen. Det här värdet är också mittpunkten mellan den övre och den nedre gränsen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Övre gräns </td> 
   <td colname="col2"> <p>Övre nivå för förutsägelseintervallet. Värden över denna nivå anses vara onormala. </p> <p>Representerar 95 % konfidensgrad av att värdena kommer att ligga under den här nivån. </p> </td> 
  </tr> 
 </tbody> 
</table>

Report builder använder dessa värden på valda mätvärden. Om du till exempel väljer ett mått för sidvisning och använder avvikelseidentifiering, används ett *`Page Views Lower Bound`*-mått.

**Hur avvikelseidentifiering beräknas**

Analysidentifiering använder en utbildningsperiod för att beräkna, lära sig och rapportera data för förutsägelseintervall per dag. Utbildningsperioden är en historisk period som identifierar vad som är normalt jämfört med onormalt och som tillämpar vad som har lärt sig under rapporteringsperioden. I marknadsföringsrapporter finns det utbildningstider på 30, 60 och 90. På Report Builder finns 30 dagar.

Utbildningsperioden är inte nödvändigtvis densamma som den valda rapporteringsperioden. I ett rapportdiagram visas datumintervallet som du anger i kalendern.

För att beräkna data jämförs den dagliga summan för varje mätvärde med utbildningsperioden med hjälp av följande algoritmer:

* Holt Winters Multiplicative (Triple Exponential Smoothing)
* Holt Winters Additive (Triple Exponential Smoothing)
* Innehåller trendkorrigering (dubbel exponentiell utjämning)

Varje algoritm används för att bestämma algoritmen med det minsta antalet fyrkantiga fel (SSE). Medelvärdet för absolut procentfel (MAPE) och aktuellt standardfel beräknas sedan för att säkerställa att modellen är statistiskt giltig.

Dessa algoritmer kan utökas för att ge prediktiva prognoser för mätvärden i framtida perioder.

Eftersom utbildningsperioden varierar beroende på början av rapporteringsperioden, kan du se skillnader i data som rapporterats för samma datum som en del av två olika tidsperioder.

Om du till exempel kör en rapport för 1-14 januari och sedan kör en rapport för 7-21 januari, kan du se olika förutsägelsedata för samma mätvärde mellan 7-14 januari i de två olika rapporterna. Detta beror på skillnaden i utbildningsperioder.

| Rapporteringsintervall | Utbildningsperiod |
|--- |--- |
| 1-14 januari | 27 november - 31 december |
| 7-21 januari | 4 december - 6 januari |
