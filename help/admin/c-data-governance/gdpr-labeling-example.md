---
description: 'null'
title: Exempel på etiketter
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
translation-type: tm+mt
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

---


# Exempel på etiketter

## Exempelträff

Anta att du har följande träffdata:

* Den första raden innehåller etiketterna för varje variabel.
* Den andra raden är namnet på variabeln. Om den har en ID-etikett innehåller den det tilldelade namnutrymmet inom parentes.
* Träffdata börjar på den tredje raden.

| Etiketter | I2<br>ID-<br>PERSONDEL-<br>PERSONACC-PERSON | I2<br>ID-<br>DEVICEDEL-<br>DEVICEACC-ALL | I2<br>DEL-<br>PERSONACC-PERSON | I2<br>DEL-<br>DEVICEDEL-<br>PERSONACC-ALL | I2<br>ID-<br>DEVICEDEL-<br>DEVICEACC-ALL |
|---|---|---|---|---|---|
| **Variabelnamn **<br>**(namnutrymme)** | **MyProp1 **<br>**(användare)** | **Besökar-ID **<br>**(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3 **<br>**(xyz)** |
| Träffdata | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | B |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## Exempel på åtkomstbegäran

Om jag skickar en åtkomstbegäran innehåller sammanfattningsfilen de värden som anges i tabellen nedan. En begäran kan bara returnera en enhetsfil, endast en personfil eller en av varje fil. Två sammanfattningsfiler returneras bara om ett person-ID används och expandIds är true.

| API-värden | API-värden | Returnerad filtyp | Data i <br>sammanfattningsåtkomstfil | Data i <br>sammanfattningsåtkomstfil | Data i <br>sammanfattningsåtkomstfil | Data i <br>sammanfattningsåtkomstfil | Data i <br>sammanfattningsåtkomstfil |
|--- |--- |--- |---|---|---|---|---|
| **Namnutrymme/ID** | **expandIDs** |  | **MyProp1** | **Besökar-ID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| AAID=77 | false | enhet | Variabeln finns inte | 77 | Variabeln finns inte | M, P | X, B |
| AAID=77 | true | enhet | Variabeln finns inte | 77 | Variabeln finns inte | M, P | X, B |
| user=Mary | false | person | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary | true | person | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary | true | enhet | finns inte | 77, 88 | finns inte | N, P | U, W |
| user=Mary AID=66 | true | person | Mary | 77, 88, 99 | A, B, C | M, N, O | X, Y, Z |
| user=Mary AID=66 | true | enhet | finns inte | 66, 77, 88 | finns inte | N, P | U, W, Z |
| xyz=X | false | enhet | finns inte | 55, 77 | finns inte | M, R | X |
| xyz=X | true | enhet | finns inte | 55, 77 | finns inte | M, P, R | B, X |

Observera att inställningen för expandID:n inte spelar någon roll för utdata när ett cookie-ID används.

## Ta bort exempelbegäran

Om en borttagningsbegäran använder API-värdena i den första raden i tabellen uppdateras träfftabellen så att den ser ut ungefär så här:

| AAID=77 expandID:s-<br>värdet spelar ingen roll | AAID=77 expandID:s-<br>värdet spelar ingen roll | AAID=77 expandID:s-<br>värdet spelar ingen roll | AAID=77 expandID:s-<br>värdet spelar ingen roll | AAID=77 expandID:s-<br>värdet spelar ingen roll |
|---|---|---|---|---|
| **MyProp1** | **STÖD** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Mary | 42 | A | Integritet-7398 | Integritet-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | Integritet-1866 | Integritet-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | B |

> [!NOTE] Endast celler på rader som innehåller AID = 77 och en DEL-DEVICE-etikett påverkas.

| user=<br>MaryexpandIDs=false | user=<br>MaryexpandIDs=false | user=<br>MaryexpandIDs=false | user=<br>MaryexpandIDs=false | user=<br>MaryexpandIDs=false |
|--- |---|---|---|---|
| **MyProp1** | **STÖD** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Integritet-0523 | 77 | Integritet-1866 | Integritet-3681 | X |
| Integritet-0523 | 88 | Integritet-2178 | Integritet-1975 | Y |
| Integritet-0523 | 99 | Integritet-9045 | Integritet-2864 | Z |
| John | 77 | D | P | B |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | B |

> [!NOTE] Endast celler på rader som innehåller user=Mary och etiketten DEL-PERSON påverkas. I praktiken är variabeln som innehåller A_ID antagligen en prop eller eVar och dess ersättningsvärde blir en sträng som börjar med &quot;Privacy-&quot;, följt av ett slumpmässigt tal (GUID), i stället för att ersätta det numeriska värdet med ett annat slumpmässigt numeriskt värde.

| user=<br>MaryexpandIDs=true | user=<br>MaryexpandIDs=true | user=<br>MaryexpandIDs=true | user=<br>MaryexpandIDs=true | user=<br>MaryexpandIDs=true |
|--- |---|---|---|---|
| **MyProp1** | **STÖD** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Integritet-5782 | 09 | Integritet-0859 | Integritet-8183 | Integritet-9152 |
| Integritet-5782 | 16 | Integritet-6104 | Integritet-2911 | Integritet-6821 |
| Integritet-5782 | 83 | Integritet-2714 | Integritet-0219 | Integritet-4395 |
| John | 09 | D | Integritet-8454 | Integritet-8216 |
| John | 16 | E | Integritet-2911 | Integritet-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | B |

Observera följande:

* Celler på rader som innehåller `user=Mary` och en `DEL-DEVICE` eller `DEL-PERSON` etikett påverkas, liksom celler med en `DEL-DEVICE` etikett på rader som innehåller ett Visitor-ID som finns på en rad som innehåller `user=Mary`.
* `MyEvar2` i den fjärde och femte raden uppdateras eftersom dessa rader innehåller samma ID-värden för besökare som på den första och andra raden, så ID-expansion inkluderar dem för borttagning på enhetsnivå.
* Värdena för `MyEvar2` i rad två och fem matchar både före och efter borttagningen, men efter borttagningen matchar inte längre värdet N som finns i den sista raden, eftersom raden inte uppdaterades som en del av borttagningsbegäran.
* `MyEvar3` beter sig på ett helt annat sätt än om ID-expandering saknas, eftersom ingen `ID-DEVICES` matchning gjordes utan ID-expansion. Nu `AAID` matchar på de första fem raderna.
