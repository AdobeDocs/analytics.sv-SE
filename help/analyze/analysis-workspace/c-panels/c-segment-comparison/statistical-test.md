---
description: Lär dig hur statistiska tester används vid segmentjämförelse.
keywords: Analysis Workspace;Segment IQ
title: Statistiska tester som används vid segmentjämförelse
feature: Segmentation
role: User, Admin
exl-id: b1c235ca-2eab-48d2-bf11-e8a8c4067d03
source-git-commit: b4c1636bdc9d5be522b16f945a46beabf4f7a733
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 0%

---

# Statistiska tester som används vid segmentjämförelse

Var och en av de översta jämförelsetabellerna visar en differenspoäng. Poängen beräknas genom flera statistiska tester beroende på vilken jämförelse som görs. Oberoende av vilket test som används visas differensvärdet som ett värde mellan 0 och 1.

En poäng på 0 innebär att det inte finns någon skillnad mellan de två segmenten och en poäng på 1 innebär att det fanns en mycket stor skillnad mellan de två segmenten. Det finns två typer av statistiska tester som används för att generera dessa differensresultat:

* För tabellen **[!UICONTROL Top Metrics]** används ett Mann-Whitney U-test,
* För tabellen **[!UICONTROL Top Dimension Items]** och **[!UICONTROL Top Segments]** används en riskdifferensjämförelse.

## Poäng för största differensmått

I tabellen Top Metrics använder verktyget Segment Comparison Tool två exempel: Mann-Whitney U Test. Det här testet är ett likhetstest utan parametrar som används för att jämföra den endimensionella sannolikhetsfördelningen för varje mätvärde för varje givet segment. Skillnadspoängen i måtttabellen är en kombination av p-värdet från den beräknade U-statistiken (som representerar hur statiska skillnaderna mellan de två segmenten är fördelade över ett visst mått) och den relativa storleken på den observerade skillnaden. En stor differenspoäng (nära 1) innebär att det specifika måttet har en stor relativ skillnad samt en hög statistisk säkerhet för att segmenten är olika.

## Poster för de viktigaste dimensionerna och poäng för de vanligaste segmentskillnaderna

För att beräkna differenspoängen i tabellerna Top Dimension Items och Top Segment Difference används en relativ riskdifferentieringsalgoritm (som i riskförhållandet, men med en differens i stället för en kvot). En riskdifferens beräknas genom att subtrahera den kumulativa incidensen för en dimensionspost (eller överlappa med ett segment från segmenttabellen) för det ena segmentet från det andra. Ett poängvärde för stora skillnader (nära 1) innebär att en viss dimensionspost eller ett visst tertiärt segment var mycket framträdande i ett av de valda segmenten och inte i det andra.

>[!NOTE]
>
>I alla tre tabellerna baseras differensstatistiken på ett lämpligt urval besökare för att få processen att löpa så snabbt som möjligt samtidigt som den förblir statistiskt korrekt. Skillnaden baseras på ett prov, men resultaten i tabellen samplas inte. För att säkerställa statistisk signifikans förlitar sig varje statistiskt test på en dynamisk allokeringsalgoritm så att det mindre segmentet innehåller en samplingsstorlek som ger mindre än 3 % felmarginal. Om ett segment innehåller mycket få besökare (färre än 1 000) används alla tillgängliga data i stället för exempel för att beräkna poängen för differensen.
