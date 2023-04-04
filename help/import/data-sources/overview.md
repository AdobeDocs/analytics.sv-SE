---
title: Översikt över datakällor
description: Importera data till Adobe Analytics med externa filer.
source-git-commit: e32a7c85e2f0629c04bcd7ed0fa80ec1593bb6e8
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Översikt över datakällor

Med Adobe Analytics datakällor kan du importera ytterligare online- eller offlinedata för rapportering. De är värdefulla för att förstå aspekter av verksamheten utanför er webbplats och hur de interagerar med er webbplats. Det allmänna arbetsflödet för att använda datakällor består av följande steg:

1. Din organisation samlar in data från andra källor. Exemplen omfattar data före klickning, callcenter-data eller information om transaktioner som har inträffat utanför platsen.
1. Data formateras på ett sätt som Adobe Analytics förstår med en tabbavgränsad textfil.
1. Du överför textfilen till en FTP-plats som Adobe tillhandahåller tillsammans med ett medföljande `.fin` -fil.
1. Adobe importerar textfilen och visar den informationen tillsammans med mått och mätvärden som samlats in på webbplatsen.

Det finns två allmänna typer av datakällor som Adobe erbjuder. Alla datakällmallar är baserade på en av dessa två typer:

* **Sammanfattningsdatakälla**: Ett enkelt sätt att importera högnivådata i Adobe Analytics. Du anger tidsstämpeln, variabelvärdet och tillhörande mått. Dessa mätvärden för varje dimensionsobjekt ökas sedan i enlighet med detta. Det är värdefullt om du vill se data offline och online sida vid sida. Däremot länkas inte online- och offlinedata tillsammans.
* **Datakälla för transaktions-ID**: Om en träff som skickas av AppMeasurement och en datakällrad innehåller matchande transaktions-ID:n, läggs dimensionen och måttvärdena i datakällan till i den träffen.

**Datakällor med fullständig bearbetning** inte längre erbjuds som datakälltyp från och med den 25 mars 2021. Se [Meddelande om att produkten är slut](full-processing-eol.md) för mer information.

Adobe erbjuder också [API för datakällor](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), som gör att du kan skapa datakällor och överföra data utan att använda produktgränssnittet eller en FTP-plats.

## Nästa steg

[Komma igång med datakällor](getting-started.md): Ladda upp en enkel datakälla till en utvecklingsrapportsserie.
