---
description: Var och en av de översta jämförelsetabellerna visar ett differensresultat som beräknas genom flera statistiska tester beroende på vilken jämförelse som görs. Oberoende av vilket test som används visas dock differenspoängen som ett värde mellan 0 och 1.
keywords: Analysis Workspace;Segmentanalys
title: Statistiska tester som används vid segmentjämförelse
feature: Rapporter och analysgrunder
uuid: c3f52470-5bfc-4e6b-8638-1c142b08d013
role: Business Practitioner, Administrator
exl-id: b1c235ca-2eab-48d2-bf11-e8a8c4067d03
translation-type: tm+mt
source-git-commit: cddf2a76ca36914f133379959b7cbb5246bdd695
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 2%

---

# Statistiska tester som används vid segmentjämförelse

Var och en av de översta jämförelsetabellerna visar ett differensresultat som beräknas genom flera statistiska tester beroende på vilken jämförelse som görs. Oberoende av vilket test som används visas dock differenspoängen som ett värde mellan 0 och 1.

En poäng på 0 betyder att det inte finns någon skillnad mellan de två segmenten och en poäng på 1 betyder att det fanns en mycket stor skillnad mellan de två segmenten. Det finns två typer av statistiska tester som används för att generera dessa differensresultat: I tabellen Top Metrics används ett Mann-Whitney U-test, och i tabellen Top Dimension Items and Top Segments används en riskdifferensjämförelse.

## Högsta måttdifferenspoäng {#section_5E8047464EB945C78543B25F8F30F17A}

I tabellen Top Metrics (Övre mått) använder segmentjämförelseverktyget två exempel: Mann-Whitney U Test, som inte är ett parametriskt likhetstest som används för att jämföra den endimensionella sannolikhetsfördelningen för varje mätvärde för varje givet segment. Skillnadspoängen i måtttabellen är en kombination av p-värdet från den beräknade U-statistiken (som representerar hur statiska skillnaderna mellan de två segmenten är fördelade över ett visst mått) och den relativa storleken på den observerade skillnaden. En stor differenspoäng (nära 1) innebär att det specifika måttet har en stor relativ skillnad samt en hög statistisk säkerhet för att segmenten är olika.

## Poster för övre dimensioner och poäng för skillnaden mellan övre segment {#section_8073ADA6053B44C9A23FDC5ED4AF2AC4}

För att beräkna differenspoängen i tabellerna Poster i översta Dimensionen och Differens i översta segment används en relativ riskdifferensalgoritm (som liknar riskkvot, men som använder en skillnad snarare än en proportion). En riskdifferens beräknas genom att subtrahera den kumulativa incidensen för en dimensionspost (eller överlappa med ett segment från segmenttabellen) för det ena segmentet från det andra. Ett poängvärde för stora skillnader (nära 1) innebär att den specifika dimensionsposten eller det eftergymnasiala segmentet var mycket framträdande i ett av de valda segmenten och inte i det andra.

>[!NOTE]
>
>I alla tre tabellerna baseras differensstatistiken på ett lämpligt urval besökare för att få processen att löpa så snabbt som möjligt samtidigt som den förblir statistiskt korrekt. Differenspoängen baseras på ett prov, men resultaten i tabellen samplas inte. För att säkerställa statistisk signifikans förlitar sig varje statistiskt test på en dynamisk allokeringsalgoritm så att det mindre segmentet innehåller en samplingsstorlek som ger mindre än 3 % felmarginal. Om ett segment innehåller mycket få besökare (färre än 1 000) använder vi alla tillgängliga data och tar inte prov på att beräkna poängen.
