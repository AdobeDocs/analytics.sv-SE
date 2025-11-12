---
description: Visar exempel på hur du kan etikettera data för träffdata, åtkomstbegäranden och borttagningsbegäranden
title: Exempel på etiketter
feature: Data Governance
role: Admin
exl-id: 9bea8636-c79c-4998-8952-7c66d31226e3
source-git-commit: 0b8b9d0067c183bfeb13816f942b3726ac66d08c
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 57%

---

# Exempel på etiketter

## Exempel på träffdata {#hit}

Anta att du har följande träffdata:

* Den första raden innehåller etiketterna för varje variabel.
* Den andra raden är namnet på variabeln. Om den har en ID-etikett innehåller den det tilldelade namnutrymmet inom parentes.
* Träffdata börjar på den tredje raden.

| Etiketter | I2 <br> ID-PERSON <br> DEL-PERSON <br> ACC-PERSON | I2 <br> ID-DEVICE <br> DEL-DEVICE <br> ACC-ALL | I2 <br> DEL-PERSON <br> ACC-PERSON | I2 <br> DEL-DEVICE <br> DEL-PERSON <br> ACC-ALL | I2 <br> ID-DEVICE <br> DEL-DEVICE <br> ACC-ALL |
|---|---|---|---|---|---|
| **Variabelnamn** <br> **(Namespace)** | **MyProp1** <br> **(användare)** | **Besökar-ID** <br> **(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3** <br> **(xyz)** |
| Träffdata | Mary | 77 | A | M | X |
| | Mary | 88 | B | N | Y |
| | Mary | 99 | C | O | Z |
| | John | 77 | D | P | W |
| | John | 88 | E | N | U |
| | John | 44 | F | Q | V |
| | John | 55 | G | R | X |
| | Alice | 66 | A | N | Z |

## Exempel på åtkomstbegäran {#access}

Om du skickar in en begäran om åtkomst får du två filer som du kan returnera till den registrerade. En fil är en CSV-fil som innehåller en rad för varje träff som tagits emot för den registrerade och en kolumn för varje variabel med lämplig åtkomstetikett. Den andra filen är en sammanfattande HTML-fil som listar varje variabel, följt av alla unika värden som har setts för variabeln för den registrerade och det antal gånger varje unikt värde har observerats.

Sammanfattningsfilen innehåller till exempel värdena som anges i tabellen nedan. En begäran kan bara returnera en enhetsfil, endast en personfil eller en av varje fil. Två sammanfattningsfiler returneras bara om ett person-ID används och `expandIds` är sant.

<table>
  <tr>
    <th colspan="2" style="text-align:center">API-värden</th>
    <th>Sammanfattning<br/>av filtyp<br/> returnerades</th>
    <th colspan="5" style="text-align:center">Data i sammanfattad åtkomstfil</th>
  </tr>
  <tr>
    <th>Namnutrymme/ID</th>
    <th>expandIDs</th>
    <th></th>
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
    <td>X, W</td>
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

Observera att inställningen för `expandIDs` inte spelar någon roll för utdata när ett cookie-ID används.

## Ta bort exempelbegäranden {#delete}

Om en borttagningsbegäran använder API-värdena i den första raden i tabellen uppdateras träfftabellen så att den ser ut ungefär så här:

<table>
  <tr>
    <th colspan="5" style="text-align:center">AAID=77 <br>(värdet expandIDs spelar ingen roll)</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>STÖD</th>
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
>Endast kolumner på rader som innehåller `AAID=77` och en `DEL-DEVICE`-etikett påverkas.

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary <br> expandIDs=false</th>
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
    <td>W</td>
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
>Endast cellkolumner på rader som innehåller `user=Mary` och en `DEL-PERSON`-etikett påverkas. I praktiken är variabeln som innehåller `A_ID` antagligen en propp eller en eVar. Dess ersättningsvärde skulle vara en sträng som börjar med `Privacy-`, följt av ett slumpmässigt tal (GUID), i stället för att ersätta det numeriska värdet med ett annat slumpmässigt numeriskt värde.

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary <br> expandIDs=true</th>
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

* Celler på rader som innehåller `user=Mary` och en `DEL-PERSON`-etikett påverkas.

