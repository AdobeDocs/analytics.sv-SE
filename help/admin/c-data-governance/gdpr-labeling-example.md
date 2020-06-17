---
description: 'null'
title: Exempel på etiketter
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Exempel på etiketter

## Exempel på träffdata

Anta att du har följande träffdata:

* Den första raden innehåller etiketterna för varje variabel.
* Den andra raden är namnet på variabeln. Om den har en ID-etikett innehåller den det tilldelade namnutrymmet inom parentes.
* Träffdata börjar på den tredje raden.

| Etiketter | I2<br>ID-PERSON<br>DEL-PERSON<br>ACC-PERSON | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL |
|---|---|---|---|---|---|
| **Variabelnamn**<br>**(namnutrymme)** | **MyProp1**<br>**(användare)** | **Besökar-ID**<br>**(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3**<br>**(xyz)** |
| Träffdata | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## Exempel på åtkomstbegäran

Om jag skickar en åtkomstbegäran innehåller sammanfattningsfilen de värden som anges i tabellen nedan. En begäran kan bara returnera en enhetsfil, endast en personfil eller en av varje fil. Två sammanfattningsfiler returneras bara om ett person-ID används och expandIds är Sant.

| API-värden | API-värden | Returnerad filtyp | Data i <br>sammanfattningsåtkomstfil | Data i <br>sammanfattningsåtkomstfil | Data i <br>sammanfattningsåtkomstfil | Data i <br>sammanfattningsåtkomstfil | Data i <br>sammanfattningsåtkomstfil |
|--- |--- |--- |---|---|---|---|---|
| **Namnutrymme/ID** | **expandIDs** |  | **MyProp1** | **Besökar-ID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| AAID=77 | falskt | enhet | Variabeln finns inte | 77 | Variabeln finns inte | M, P | X, W |
| AAID=77 | sant | enhet | Variabeln finns inte | 77 | Variabeln finns inte | M, P | X, W |
| användare=Mary | falskt | person | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| användare=Mary | sant | person | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| användare=Mary | sant | enhet | ej närvarande | 77, 88 | ej närvarande | N, P | U, W |
| användare=Mary AAID=66 | sant | person | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| användare=Mary AAID=66 | sant | enhet | ej närvarande | 66, 77, 88 | ej närvarande | N, P | U, W, Z |
| xyz=X | falskt | enhet | ej närvarande | 55, 77 | ej närvarande | M, R | X |
| xyz=X | sant | enhet | ej närvarande | 55, 77 | ej närvarande | M, P, R | W, X |

Observera att inställningen för expandID:n inte spelar någon roll för utdata när ett cookie-ID används.

## Exempel på borttagningsbegäran

Om en borttagningsbegäran använder API-värdena i den första raden i tabellen uppdateras träfftabellen så att den ser ut ungefär så här:

| AAID=77 expandIDs värdet<br>spelar ingen roll | AAID=77 expandIDs värdet<br>spelar ingen roll | AAID=77 expandIDs värdet<br>spelar ingen roll | AAID=77 expandIDs värdet<br>spelar ingen roll | AAID=77 expandIDs värdet<br>spelar ingen roll |
|---|---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Mary | 42 | A | Sekretess-7398 | Sekretess-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | Sekretess-1866 | Sekretess-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] Endast celler på rader som innehåller AAID = 77 och en DEL-DEVICE-etikett påverkas.

| användare=Mary<br>expandIDs=falskt | användare=Mary<br>expandIDs=falskt | användare=Mary<br>expandIDs=falskt | användare=Mary<br>expandIDs=falskt | användare=Mary<br>expandIDs=falskt |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Sekretess-0523 | 77 | Sekretess-1866 | Sekretess-3681 | X |
| Sekretess-0523 | 88 | Sekretess-2178 | Sekretess-1975 | Y |
| Sekretess-0523 | 99 | Sekretess-9045 | Sekretess-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] Endast celler på rader som innehåller användare=Mary och etiketten DEL-PERSON påverkas. I praktiken är variabeln som innehåller A_ID antagligen en prop eller eVar och dess ersättningsvärde blir en sträng som börjar med ”Sekretess-”, följt av ett slumpmässigt tal (GUID), snarare än att ersätta det numeriska värdet med ett annat slumpmässigt numeriskt värde.

| användare=Mary<br>expandIDs=sant | användare=Mary<br>expandIDs=sant | användare=Mary<br>expandIDs=sant | användare=Mary<br>expandIDs=sant | användare=Mary<br>expandIDs=sant |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Sekretess-5782 | 09 | Sekretess-0859 | Sekretess-8183 | Sekretess-9152 |
| Sekretess-5782 | 16 | Sekretess-6104 | Sekretess-2911 | Sekretess-6821 |
| Sekretess-5782 | 83 | Sekretess-2714 | Sekretess-0219 | Sekretess-4395 |
| John | 09 | D | Sekretess-8454 | Sekretess-8216 |
| John | 16 | E | Sekretess-2911 | Sekretess-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

Observera följande:

* Celler på rader som innehåller `user=Mary` och en `DEL-DEVICE`- eller `DEL-PERSON`-etikett påverkas, liksom celler med en `DEL-DEVICE`-etikett på rader som innehåller ett besökar-ID som finns på en rad som innehåller `user=Mary`.
* `MyEvar2` i den fjärde och femte raden uppdateras eftersom dessa rader innehåller samma ID-värden för besökare som på den första och andra raden, så ID-expansion inkluderar dem för borttagning på enhetsnivå.
* Värdena för `MyEvar2` på rad två och fem matchar både före och efter borttagningen, men efter borttagningen matchar inte längre värdet N som finns på den sista raden, eftersom raden inte uppdaterades som en del av borttagningsbegäran.
* `MyEvar3` beter sig på ett helt annorlunda än vad det gjorde utan ID-expansion, eftersom ingen `ID-DEVICES` matchade utan ID-expansion. Nu matchar `AAID` på de första fem raderna.
