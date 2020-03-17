---
description: Exempel som ger vägledning vid import av numeriska 2 klassificeringar.
subtopic: Classifications
title: Exempel
topic: Admin tools
uuid: 0553d07f-87c1-4372-90ce-7118a6393a01
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Exempel

Exempel som ger vägledning vid import av numeriska 2 klassificeringar.

<!-- 

c_example_1__rate.xml

 -->

I det här fallet skapade du klassificeringen för hanteraren och vill importera Januari-värdena: [!UICONTROL Classification Conversion]

| Nyckel | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` |  | `.2` |
| Product2 | Text2 | `Cost2_jan_var` |  | `.3` |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | omsättning | omsättning |
| 2010/01/01 - 2010/01/31 | omsättning | omsättning |

I januari 2001 stod Product1 för 20 % av intäkterna (se `~MyCost^~value~`nedan) och Product2 hade en kostnad på 30 % av intäkterna. Eftersom du importerar en ny rad `~MyCost^~id~` är den tom.

## Resultat {#section_E0569289C9B34C479C7D2CD9ECBF866E}

Ett exempel på utdata från rapporten visas här:

Punkt: Jan 2010

Rapport: Produkter

| Produkter | Intäkter | MinKostnad |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

<!-- 

c_example_2__rate.xml

 -->

| Nyckel | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product2 | Text2 | `Cost2_jan_var` | 2 | .3 |
| Product1 | Text1 | `Cost1_feb_var` |  | .15 |
| Product2 | Text2 | `Cost2_feb_var` |  | .25 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | omsättning | omsättning |
| 2010/01/01 - 2010/01/31 | omsättning | omsättning |
| 2010/02/01 - 2010/02/28 | omsättning | omsättning |
| 2010/02/01 - 2010/02/28 | omsättning | omsättning |

I februari minskade användarens kostnad för Produkt1 till 15 % av intäkterna och Produkt2 till 25 % av intäkterna.

## Resultat {#section_23DF5353AC1B478C88647F222703352C}

Ett exempel på utdata från rapporten visas här:

Punkt: Jan 2010

Rapport: Produkter

| Produkter | Intäkter | MinKostnad |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

Punkt: Feb 2010

Rapport: Produkter

| Produkter | Intäkter | MinKostnad |
|---|---|---|
| Product1 | $15,500.75 | $2325.11 |
| Product2 | $12,300.52 | $3075.13 |

Punkt: 1 januari 2010 - 28 februari 2010

Rapport: Produkter

| Produkter | Intäkter | MinKostnad |
|---|---|---|
| Product1 | $25,500.98 | $4325.16 |
| Product2 | $21,300.56 | $5,775.14 |

<!-- 

c_example_3__fixed.xml

 -->

Du importerar därför följande data:

| Nyckel | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_jan_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fast | ingen |
| 2010/03/01 - 2010/03/31 | fast | ingen |

## Resultat {#section_674B57ADB8284B878F9E670038C31464}

Ett exempel på utdata från rapporten visas här:

Punkt: Mars 2010

Rapport: Produkter

| Produkter | Intäkter | MinKostnad |
|---|---|---|
| Product1 | $11,023.75 | $3000.00 |
| Product2 | $8,000.12 | $2000.00 |

<!-- 

c_example_4__(advanced)_multiple_row_per_time_period.xml

 -->

I det här exemplet lägger du till en fraktkostnad på 500 USD för Product1 i januari och en fraktkostnad på 600 USD i februari.

| Nyckel | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product1 | Text1 | `Cost2_jan_fixed` |  | 500 |
| Product1 | Text1 | `Cost1_feb_var` | 2 | .15 |
| Product1 | Text1 | `Cost2_feb_fixed` |  | 600 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | omsättning | omsättning |
| 2010/01/01 - 2010/01/31 | fast | ingen |
| 2010/02/01 - 2010/01/31 | omsättning | omsättning |
| 2010/02/01 - 2010/01/31 | fast | ingen |

Raderna som tidigare importerades har ett ID som anger att de inte är nya kostnader.

## Resultat {#section_2096084176614B9AA60F97D5853CB9EA}

Ett exempel på utdata från rapporten visas här:

Punkt: Jan 2010

Rapport: Produkter

| Produkter | Intäkter | MinKostnad |
|---|---|---|
| Product1 | $10,000.23 | $2500.05 |

> [!NOTE] Den här funktionen är till för avancerade användare som vill approximera värden. Den resulterande informationen ska inte behandlas som exakta värden.

<!-- 

c_example_5__identical_rate_hinge.xml

 -->

Följande illustrerar detta exempel:

| Nyckel | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_var` |  | 1 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | order |

## Resultat {#section_39E24ECCC3B34C9AADC25572662750E5}

Ett exempel på utdata från rapporten visas här:

Punkt: Mars 2010

Rapport: Produkter per sida

| Produkter per sida | Beställningar | MinKostnad |
|---|---|---|
| Product1 | 1000 | $1000.00 |
| Hemsida | 600 | $600 |
| Kundvagn | 400 | $400 |

<!-- 

c_example_5__fixed_no_hinge.xml

 -->

| Nyckel | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fast | ingen |
| 2010/03/01 - 2010/03/31 | fast | ingen |

## Resultat {#section_7F5F5970077D4E14A5DC91495E23540D}

Ett exempel på utdata från rapporten visas här:

Punkt: Mars 2010

Rapport: Produkter per sida

| Produkter per sida | Beställningar | MinKostnad |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| Hemsida | 600 | 0 |
| Kundvagn | 400 | 0 |

<!-- 

c_example_7__fixed_hinge.xml

 -->

I det här fallet importerar du följande data:

| Nyckel | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fast | omsättning |
| 2010/03/01 - 2010/03/31 | fast | omsättning |

## Resultat {#section_5953BB6FD0CE4EF69D1D60B8B1203431}

Ett exempel på utdata från rapporten visas här:

Punkt: Mars 2010

Rapport: Produkter per sida

| Produkter per sida | Beställningar | MinKostnad |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| Hemsida | 600 | $1800.00 |
| Kundvagn | 400 | $1200.00 |

<!-- 

c_example_7_continued__different_rate_hinge.xml

 -->

I det här fallet importerar du följande fildata:

| Nyckel | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | Kostnad1_mar_fast |  | 3 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | omsättning |

## Resultat {#section_6E2604D9A3B0455585EFF0F80FF54127}

Ett exempel på utdata från rapporten visas här:

Punkt: Mars 2010

Rapport: Produkter per sida

| Produkter per sida | Beställningar | MinKostnad |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| Hemsida | 600 | $1,000.00 |
| Kundvagn | 400 | $2,000.00 |

