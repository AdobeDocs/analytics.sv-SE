---
description: Inkonsekventa data kan orsaka stora problem. Lär dig hur du identifierar statistiska avvikelser med avvikelsedetekteringstekniker från Adobe. Kom igång idag.
title: Statistiska tekniker som används för avvikelseidentifiering
feature: AI Tools
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---


# Statistiska tekniker som används för avvikelseidentifiering

Analysupptäckt i Analysis Workspace använder en rad avancerade statistiska tekniker för att avgöra om en observation bör anses onormal eller inte.

Beroende på vilket datum som använts i rapporten används tre olika statistiska metoder - särskilt för att upptäcka avvikelser per timme, dag, vecka/månad. Varje statistisk metod beskrivs nedan.

## Analysidentifiering för daglig granularitet {#section_758ACA3C0A6B4D399563ECABFB8316FA}

För dagliga granularitetsrapporter anser algoritmen att flera viktiga faktorer är viktiga för att få bästa möjliga resultat. För det första avgör algoritmen vilken typ av modell som ska användas baserat på tillgängliga data som vi väljer mellan en av två klasser - en tidsseriebaserad modell eller en avbrottsdetekteringsmodell (kallas funktionell filtrering).

Urvalet av tidsseriemodell baseras på följande kombinationer för typ av fel, trend och säsongsberoende (ETS) enligt beskrivningen i [Hyndman et al. (2008)](https://www.springer.com/us/book/9783540719168). Algoritmen försöker i synnerhet med följande kombinationer:

1. ANA (additivt fel, ingen trend, additiv säsongsvariation)
1. AAA (additivt fel, additiv trend, additiv säsongsvariation)
1. MNM (multiplikativt fel, ingen trend, multiplikativ säsongsvariation)
1. MNA (multiplikativt fel, ingen trend, additiv säsongsvariation)
1. AAN (additivt fel, additiv trend, ingen säsongsvariation)

Algoritmen testar lämpligheten hos vart och ett av dessa genom att välja det som har det bästa genomsnittliga absoluta procentfelet (MAPE). Om MAPE för modellen med bästa tidsserie är större än 15 % används emellertid funktionell filtrering. Vanligtvis är data med hög repetitionsgrad (t.ex. vecka över vecka eller månad över månad) bäst lämpade för en tidsseriemodell.

Efter modellval justerar algoritmen sedan resultaten baserat på helger och årstidsberoende. För helger kontrollerar algoritmen om någon av följande helger finns i datumintervallet för rapportering:

* Minnesdag
* Juli 4
* Thanksgiving
* Black Friday
* Cyber Monday
* 24-26 december
* Januari 1
* 31 december

Dessa helgdagar valdes ut baserat på omfattande statistisk analys av många kunddatapunkter för att identifiera helger som matchar flest kundtrender. Även om listan inte är fullständig för alla kunder eller affärscykler, fann vi att användningen av dessa helger avsevärt förbättrade algoritmens prestanda totalt för nästan alla kunders dataset.

När modellen har valts och helger har identifierats i rapportdatumintervallet utförs algoritmen på följande sätt:

1. Konstruera avvikelsens referensperiod - detta omfattar upp till 35 dagar före rapporteringsdatumintervallet och ett matchande datumintervall från ett år före (redovisning för skottdagar vid behov och inklusive eventuella helgdagar som kan ha inträffat på en annan kalenderdag föregående år).
1. Testa om helgdagar under den aktuella perioden (exklusive föregående år) är onormala baserat på de senaste uppgifterna.
1. Om semestern i det aktuella datumintervallet är onormal justerar du det förväntade värdet och konfidensintervallet för den aktuella semestern med hänsyn till föregående års semester (med hänsyn till två dagar före och efter). Korrigeringen för den aktuella ledigheten baseras på det lägsta genomsnittliga absoluta procentfelet för:

   1. Additiva effekter
   1. Multiplicerande effekter
   1. YoY-differens

Lägg märke till den dramatiska förbättringen av juldagen och nyårsdagen i följande exempel:

![](assets/anomaly_statistics.png)

## Analysidentifiering för timgranularitet {#section_014C9E9209AF43F8A03D5D46E3B3AEE7}

Timdata bygger på samma algoritm för tidsserier som den dagliga granularitetsalgoritmen gör. Den är dock starkt beroende av två trendmönster: 24-timmarscykeln samt veckodagscykeln. För att fånga upp dessa två säsongseffekter konstruerar timalgoritmen två separata modeller för en helg och en veckodag med samma metod som beskrivs ovan.

Utbildningsfönstren för timtrender är beroende av ett 336-timmars uppslagsfönster.

## Analysidentifiering för vecko- och månadsgranulariteter {#section_5D421576BFBC4B24A58DFCC0A6407545}

Trender för varje vecka och månad visar inte samma trender för varje vecka eller varje dag som finns på en daglig eller timbaserad noggrannhet, vilket innebär att en sådan separat algoritm används. För varje vecka och varje månad används en metod med tvåstegsidentifiering som kallas GESD-test (Generalized Extreme Studentized Deviate). I detta test beaktas det maximala antalet förväntade avvikelser i kombination med den justerade boxrumsmetoden (en icke-parametrisk metod för oulier-upptäckt) för att fastställa det maximala antalet avvikande värden. De två stegen är:

1. Justerad box-plot-funktion: Den här funktionen avgör det maximala antalet avvikelser som anges av indata.
1. GESD-funktion: Tillämpas på indata med utdata från steg 1.

Avvikelseprocessen för semester och YY-årstidsavvikelsen tar sedan bort förra årets data från årets data och itererar sedan på uppgifterna igen med tvåstegsprocessen ovan för att kontrollera att avvikelserna är säsongsrelaterade. Var och en av dessa datumgranulariteter använder en 15-periodsökning inklusive det valda datumintervallet för rapportering (antingen 15 månader eller 15 veckor) och ett motsvarande datumintervall för 1 år sedan för utbildning.
