---
title: AMO-ID
description: Adobe Media Optimizer ID, som används i Adobe Advertising-integreringar.
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 1%

---

# AMO-ID

**[!UICONTROL AMO ID]** är en samling sammanfogade identifierare som används i Adobe Advertising-integreringar. Värden som lagras i den här dimensionen ordnas automatiskt i olika, mer läsbara klassificeringsdimensioner för användning i analysrapporter. Dimensionen skapas automatiskt när [Analytics för Advertising](https://experienceleague.adobe.com/sv/docs/advertising/integrations/analytics/overview)-integreringen aktiveras.

## Fyll den här dimensionen med data

Den här dimensionen samlar in värden på flera sätt:

* För genomklickningstrafik samlas data in från frågesträngsparametern `s_kwcid` i [sid-URL](page-url.md), vanligtvis på den sida genom vilken reklamdriven trafik kommer in på webbplatsen.
* Genomklickningstrafik kan också hämtas när URL:en inte innehåller spårningskoder, men Adobe Advertising JavaScript upptäcker ett klick inom de föregående två minuterna.
* För genomskinlig trafik som stöds, kompletterar Adobe Advertising värdena på backend-objektet med ett extra ID (`SDID`).

## Dimension-objekt

Dimension-objekt innehåller AMO-ID:n, som också kallas `s_kwcid`-värden. Det exakta formatet beror på om trafiken kommer från DSP eller från Search, Social och Commerce. AMO-ID:n är mindre detaljerade än EF-ID:n och används främst för klassificeringar och förtäring av Adobe Advertising-värden i Analytics.

### DSP

```text
AC!{ad key}!{placement key}
```

* **`AC`**: Anger visningskanalen.
* **`ad key`**: Adobe Advertising-genererad alfanumerisk identifierare för annonsen.
* **`placement key`**: Adobe Advertising-genererad alfanumerisk identifierare för placeringen.

Exempelvärde:

```text
AC!iIMvXqlOa6Nia2lDvtgw!GrVv6o2oV2qQLjQiXLC7
```

### Söka, sociala medier och Commerce-annonser

ID:n för sökning, sociala medier och Commerce AMO börjar med `AL`, följt av annonsörens användar-ID, annonsnätverkets konto-ID och sedan nätverksspecifika identifierare. ID:n för delade annonskonton och nätverkskonton är:

* **`3`**: Google Ads
* **`10`**: Microsoft Advertising
* **`45`**: Meta
* **`86`**: Yahoo! Visa nätverk
* **`87`**: Naver
* **`88`**: Baidu
* **`90`**: Yandex
* **`94`**: Yahoo! Japan Ads
* **`105`**: Yahoo Native (utgått)
* **`106`**: Pinterest (borttagen)

#### Google Ads

Google Ads har två samhörande format. Nyare konton kan innehålla kampanj-ID och annonsgrupp-ID, som har stöd för kampanj- och annonsgruppsrapportering för Performance Max och utkast/experiment-kampanjer.

```text
AL!{user}!3!{creative}!{matchtype}!{placement}!{network}!{product partition}!{keyword}[!{campaign id}!{ad group id}]
```

* **`creative`**: Google Ads creative ID.
* **`matchtype`**: Nyckelordsmatchningstyp (`e` för exakt, `p` för fras, `b` för bred).
* **`placement`**: Domän där annonsen klickades.
* **`network`**: Nätverk där klickningen inträffade (`g` för Google-sökning, `s` för en sökpartner, `d` för visning).
* **`product partition`**: Produktgrupp-ID för produktannonser.
* **`keyword`**: Utlöser nyckelord på sökwebbplatser eller bästa matchande nyckelord på innehållswebbplatser.
* **`campaign id`**: Google Ads-kampanj-ID, om det finns.
* **`ad group id`**: Google Ads och grupp-ID, om sådana finns.

För dynamiska sökannonser fylls nyckelordsfältet i med det automatiska målet.

Exempel:

```text
AL!1234!3!569345525675!e!!g!!adobe express!15557590691!136734402131
```

#### Microsoft Advertising

```text
AL!{user}!10!{ad id}!!!!{keyword/order item id}!!{campaign id}!{ad group id}
```

* **`ad id`**: Microsoft Advertising Creative ID.
* **`keyword/order item id`**: Microsoft Advertising-nyckelords-ID.
* **`campaign id`**: Microsoft Advertising kampanj-ID.
* **`ad group id`**: Microsoft Advertising annonsgrupp-ID.

Äldre Microsoft-format kan fortfarande finnas för vissa konton som inte är migrerade.

Exempel:

```text
AL!1234!10!79577297926903!!!!79577437127536!!291647087!1273234845019564
```

#### Baidu

```text
AL!{user}!88!{creative}!{placement}!{keyword id}
```

* **`creative`**: Bajdu-kreativt ID.
* **`placement`**: Webbplats där annonsen klickades.
* **`keyword id`**: Nyckelords-ID för Baidu.

#### Yahoo! Japan Ads

```text
AL!{user}!94!{creative}!{matchtype}!{network}!{keyword}
```

* **`creative`**: Yahoo! Japan lägger till kreativt ID.
* **`matchtype`**: Nyckelordsmatchningstyp (`be` exact, `bp` phrase, `bb` wide).
* **`network`**: Nätverk där klickningen inträffade (`n` systemspecifik, `s` sökning).
* **`keyword`**: Nyckelordet utlöses.

#### Yandex

```text
AL!{user}!90!{ad id}!{source type}!!!{phrase id}
```

* **`ad id`**: Yandex creative ID.
* **`source type`**: Webbplatstyp som annonsen visades på (`b` search, `c` context/content, `ct` category).
* **`phrase id`**: Yandex-nyckelords-ID.

## Klassificeringar

När du aktiverar integreringen [Analytics for Advertising](https://experienceleague.adobe.com/sv/docs/advertising/integrations/analytics/overview) skapas följande klassificeringar automatiskt. Klassificeringsvärdena upprätthålls automatiskt av integreringen.

| Klassificering | Beskrivning | DSP | Sök,<br>socialt, &amp;<br>Commerce |
| --- | --- | :---: | :---: |
| **[!UICONTROL Account]** | Kontonamnet. | &check; | &check; |
| **[!UICONTROL Ad Display URL]** | Den URL som visas i annonsen. | | &check; |
| **[!UICONTROL Ad Description]** | Annonsbeskrivningen (DSP) eller annonstexten (Search, Social, &amp; Commerce). | &check; | &check; |
| **[!UICONTROL Ad Destination URL]** | Annonsens mål-URL. | | &check; |
| **[!UICONTROL Ad Group]** | Annonsgruppens namn. | | &check; |
| **[!UICONTROL Ad Platform]** | Marknadsföringens DSP-namn eller sökmotornamn. | &check; | &check; |
| **[!UICONTROL Ad Title]** | Annonstypen (DSP) eller annonsrubriken (Search, Social, &amp; Commerce). | &check; | &check; |
| **[!UICONTROL Ad Type]** | Annonstypen, till exempel `text`, `video`, `display` eller `native`. | &check; | &check; |
| **[!UICONTROL AdCloud Attribute 1]** -<br>**[!UICONTROL AdCloud Attribute 5]** | Platshållarklassificeringar är reserverade för framtida anpassade attribut. Används inte för närvarande. | | |
| **[!UICONTROL Campaign]** | Kampanjnamnet. | &check; | &check; |
| **[!UICONTROL Creative Experience Name]** | Namnet på den kreativa upplevelse som är kopplad till annonseringsinteraktionen, som representerar en grupp kreativa variationer som används vid testning eller personalisering. | &check; | |
| **[!UICONTROL Creative Branch Name]** | Namnet på grenen i en kreativ upplevelse som representerar en specifik variation eller bana i det kreativa experimentet. | &check; | |
| **[!UICONTROL Creative Branch ID]** | Unik identifierare som tilldelats en kreativ gren i en kreativ upplevelse. | &check; | |
| **[!UICONTROL Creative Name]** | Namnet på den specifika annonsresursen som har skickats till användaren. | &check; | |
| **[!UICONTROL Creative Variant Name]** | Namnet på den specifika varianten av ett kreativt verk som används inom en kreativ upplevelse eller gren. | &check; | |
| **[!UICONTROL Keyword]** | Nyckelordet. | | &check; |
| **[!UICONTROL Keyword Match Type]** | Nyckelordet och matchningstypen. | | &check; |
| **[!UICONTROL Landing Type]** | Anger om landningssidan var en genomsiktlig eller klickbar. | &check; | &check; |
| **[!UICONTROL Match Type]** | Sökmatchningstypen. | | &check; |
| **[!UICONTROL Network]** | RTB (DSP) eller annonsnätverksnamnet (Search, Social, &amp; Commerce). | &check; | &check; |
| **[!UICONTROL Optimization]** | Paketnamnet (DSP) eller portföljnamnet (Sök, Socialt och Commerce). | &check; | &check; |
| **[!UICONTROL Placement]** | Placeringsnamnet. | &check; | |
| **[!UICONTROL Product Target]** | Produktmålet för en produktlistad annons. | | &check; |
