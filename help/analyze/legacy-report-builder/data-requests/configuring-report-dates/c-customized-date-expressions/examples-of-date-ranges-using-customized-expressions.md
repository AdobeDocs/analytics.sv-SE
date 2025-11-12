---
description: Exempel, anteckningar och syntaxanteckningar om hur du använder datumintervall i anpassade uttryck.
title: Exempel på datumintervall med anpassade uttryck
uuid: 3f46816d-9eee-4b2d-83be-bf1c9fb97fcf
feature: Report Builder
role: User, Admin
exl-id: d936dd4e-d330-4ed9-a979-3273397d7d92
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 1%

---

# Exempel på datumintervall med anpassade uttryck

{{legacy-arb}}

Exempel, anteckningar och syntaxanteckningar om hur du använder datumintervall i anpassade uttryck.

I tabellen antas dagens datum vara måndag, 10 november 2011, med den gregorianska kalendern.

| Exempel | Datumintervall | Anpassa uttryck | Rapportens datumintervall |
|---|---|---|---|
|  | | **Från** | **Till** |
| 1 | För två veckor sedan | `cw-2w  \| cw-1w-1d` | 26 okt till 1 nov |
| 2 | De första 3 dagarna i den femte månaden i det senaste året | `cy-1y+4m  \| cy-1y+4m+2d` | 1 maj-3 maj 2010 |
| 3 | En hel vecka med början för 4 veckor sedan | `cw-4w  \| cw-3w-1d` | 12 okt till 18 okt |
| 4 | Senaste veckan föregående år | `cw-53w  \| cw-52w-1d` | 9 nov 2010-9 nov |
| 5 | En månad med början för 2 månader sedan | `cm-2m  \| cm-1m-1d` | 1 sept till 30 sept |
| 6 | För 12 månader sedan föregående år | `cm-12m  \| cm-11m-1d` | 1 nov till 30 nov 2010 |

## Kommentarer till exempel {#section_37801B0D6D364ABAA8DCE3A4C0123B2C}

**Exempel 1**

Om det idag är måndag den 10 november 2011 tar du det aktuella datumet och subtraherar en vecka för att få fram den sista fullständiga veckan i oktober.

**Exempel 2**

Lägg till fyra månader i början av året (januari) för att hämta månaden maj; lägg till två dagar till den första dagen i månaden för att få den tredje dagen i månaden.

## Syntaxanteckningar {#section_555D6563B2D94FA3BDD801DC0B8C289D}

Du kan skapa anpassade uttryck som täcker de flesta datumintervall genom att länka två termer till en operator. En term är en kombination av en heltalsmultiplikator och en periodförkortning. Ett exempel på en term är 18d. Ett exempel på en operator är +.

* Tomt utrymme tillåts inte mellan operatorer och termer.
* Använd endast dessa förkortningar: cd cw cm cq cy d w m q y
* Det bästa sättet är att använda samma datumreferens i startdatumet och i slutdatumet: cd, cd eller cw, cw eller cy, cy. Blandningsdatumreferenser kan leda till ogiltiga datum vid vissa tidpunkter på året.
* Giltiga multiplar av förkortningarna d w m q y formas med heltal ( 1 2 3 ... ) som är föregås av förkortningen, t.ex. 53d 3w 5q 9m 2y
* Tal som inte är heltal tillåts inte.
* Lägg inte till förkortningen med bara noll. 0w tillåts till exempel inte.
* Följande operatorer används för att sammanfoga förkortningar: + -
* Eftersom datumintervall måste beräknas i förhållande till den aktuella perioden börjar alltid den första termen i ett uttryck med c.
