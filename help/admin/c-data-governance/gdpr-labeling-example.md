---
description: Visar exempel på hur du kan etikettera data för träffdata, åtkomstbegäranden och borttagningsbegäranden
title: Exempel på etiketter
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
exl-id: 9bea8636-c79c-4998-8952-7c66d31226e3
source-git-commit: 3ff221b8715ecde6923310b6818904c697a2b003
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 84%

---

# Exempel på etiketter

## Exempel på träffdata

Anta att du har följande träffdata:

* Den första raden innehåller etiketterna för varje variabel.
* Den andra raden är namnet på variabeln. Om den har en ID-etikett innehåller den det tilldelade namnutrymmet inom parentes.
* Träffdata börjar på den tredje raden.

| Etiketter | I2<br>ID-PERSON<br>DEL-PERSON<br>ACC-PERSON | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL |
|---|---|---|---|---|---|
| **Variabelnamn** <br> **(Namespace)** | **MyProp1** <br> **(användare)** | **Besökar-ID** <br> **(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3** <br> **(xyz)** |
| Träffdata | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## Exempel på åtkomstbegäran

Om jag skickar en åtkomstbegäran innehåller den sammanfattande filen de värden som anges i tabellen nedan. En begäran kan bara returnera en enhetsfil, endast en personfil eller en av varje fil. Två sammanfattningsfiler returneras bara om ett person-ID används och expandIds är Sant.

<table>
  <tr>
    <th colspan="2" style="text-align:center">API-värden</th>
    <th rowspan="2">Returnerad<br>filtyp</th>
    <th colspan="5" style="text-align:center">Data i sammanfattningsåtkomstfil</th>
  </tr>
  <tr>
    <th>Namnutrymme/ID</th>
    <th>expandIDs</th>
    <th>MyProp1</th>
    <th>Besökar-ID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>AAID=77</td>
    <td>falskt</td>
    <td>enhet</td>
    <td>ej närvarande</td>
    <td>77</td>
    <td>ej närvarande</td>
    <td>M, P</td>
    <td>X, W</td>
  </tr>
  <tr>
    <td>AAID=77</td>
    <td>sant</td>
    <td>enhet</td>
    <td>ej närvarande</td>
    <td>77</td>
    <td>ej närvarande</td>
    <td>M, P</td>
    <td>X, B</td>
  </tr>
  <tr>
    <td>användare=Mary</td>
    <td>falskt</td>
    <td>person</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A, B, C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td rowspan="2">användare=Mary</td>
    <td rowspan="2">sant</td>
    <td>person</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A, B, C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td>enhet</td>
    <td>ej närvarande</td>
    <td>77, 88</td>
    <td>A, B, C</td>
    <td>N, P</td>
    <td>U, W</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary<br>AID=66</td>
    <td rowspan="2">sant</td>
    <td>person</td>
    <td>Mary</td>
    <td>77, 88, 99</td>
    <td>A, B, C</td>
    <td>M, N, O</td>
    <td>X, Y, Z</td>
  </tr>
  <tr>
    <td>enhet</td>
    <td>ej närvarande</td>
    <td>66, 77, 88</td>
    <td>A, B, C</td>
    <td>N, P</td>
    <td>U, W, Z</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>falskt</td>
    <td>enhet</td>
    <td>ej närvarande</td>
    <td>55, 77</td>
    <td>ej närvarande</td>
    <td>M, R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>sant</td>
    <td>enhet</td>
    <td>ej närvarande</td>
    <td>55, 77</td>
    <td>ej närvarande</td>
    <td>M, P, R</td>
    <td>W, X</td>
  </tr>
</table>

Observera att inställningen för expandID:n inte spelar någon roll för utdata när ett cookie-ID används.

## Ta bort exempelbegäranden

Om en borttagningsbegäran använder API-värdena i den första raden i tabellen uppdateras träfftabellen så att den ser ut ungefär så här:

<table>
  <tr>
    <th colspan="5" style="text-align:center">AAID=77 <br>(expandIDs-värdet spelar ingen roll)</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Mary</td>
    <td>42</td>
    <td>A</td>
    <td>Sekretess-7398</td>
    <td>Sekretess-9152</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>88</td>
    <td>B</td>
    <td>N</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>99</td>
    <td>C</td>
    <td>O</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>42</td>
    <td>D</td>
    <td>Sekretess-1866</td>
    <td>Sekretess-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>N</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
>Endast celler på rader som innehåller AAID = 77 och en DEL-DEVICE-etikett påverkas.

<table>
  <tr>
    <th colspan="5" style="text-align:center">användare=Mary<br>expandIDs=falskt</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>STÖD</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Sekretess-0523</td>
    <td>77</td>
    <td>Sekretess-1866</td>
    <td>Sekretess-3681</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Sekretess-0523</td>
    <td>88</td>
    <td>Sekretess-2178</td>
    <td>Sekretess-1975</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Sekretess-0523</td>
    <td>99</td>
    <td>Sekretess-9045</td>
    <td>Sekretess-2864</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>77</td>
    <td>D</td>
    <td>P</td>
    <td>B</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>N</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
>Endast celler på rader som innehåller användare=Mary och etiketten DEL-PERSON påverkas. I praktiken är variabeln som innehåller A_ID antagligen en prop eller eVar och dess ersättningsvärde blir en sträng som börjar med ”Sekretess-”, följt av ett slumpmässigt tal (GUID), snarare än att ersätta det numeriska värdet med ett annat slumpmässigt numeriskt värde.

<table>
  <tr>
    <th colspan="5" style="text-align:center">användare=Mary<br>expandIDs=sant</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>STÖD</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Sekretess-5782</td>
    <td>09</td>
    <td>Sekretess-0859</td>
    <td>Sekretess-8183</td>
    <td>Sekretess-9152</td>
  </tr>
  <tr>
    <td>Sekretess-5782</td>
    <td>16</td>
    <td>Sekretess-6104</td>
    <td>Sekretess-2911</td>
    <td>Sekretess-6821</td>
  </tr>
  <tr>
    <td>Sekretess-5782</td>
    <td>83</td>
    <td>Sekretess-2714</td>
    <td>Sekretess-0219</td>
    <td>Sekretess-4395</td>
  </tr>
  <tr>
    <td>John</td>
    <td>09</td>
    <td>D</td>
    <td>Sekretess-8454</td>
    <td>Sekretess-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>16</td>
    <td>E</td>
    <td>Sekretess-2911</td>
    <td>Sekretess-2930</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

Observera följande:

* Celler på rader som innehåller `user=Mary` och en `DEL-DEVICE`- eller `DEL-PERSON`-etikett påverkas, och celler med en `DEL-DEVICE`-etikett på rader som innehåller ett Visitor ID (AID) som finns på en rad som innehåller `user=Mary`.
* Inställningen expandIDs utökas inte till anropet för att inkludera värden som finns i MyEvar3, som har en ID-DEVICE-etikett, när `user=Mary`. Expanderings-ID:n utökas endast så att de inkluderar besökar-ID:n (AAID:n i det här exemplet, men även ECID:n) på rader där `user=Mary`.
* `MyEvar2` i den fjärde och femte raden uppdateras eftersom dessa rader innehåller samma ID-värden för besökare som på den första och andra raden, så ID-expansion inkluderar dem för borttagning på enhetsnivå.
* Värdena för `MyEvar2` på rad två och fem matchar både före och efter borttagningen, men efter borttagningen matchar inte längre värdet N som finns på den sista raden, eftersom raden inte uppdaterades som en del av borttagningsbegäran.
* `MyEvar3` beter sig på ett helt annorlunda än vad det gjorde utan ID-expansion, eftersom ingen `ID-DEVICES` matchade utan ID-expansion. Nu matchar `AAID` på de första fem raderna.
