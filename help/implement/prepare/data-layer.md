---
title: Skapa ett datalager
description: Lär dig vad ett datalager är i Analytics-implementeringen och hur det kan användas för att mappa variabler i Adobe Analytics.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
source-git-commit: 571192e27972f2bc15912481f9a578427e1c1cfb
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 2%

---

# Skapa ett datalager

Ett datalager är ett ramverk av JavaScript-objekt på din webbplats som innehåller de variabelvärden som används i din Analytics-implementering. Det ger bättre kontroll och enklare underhåll när du tilldelar värden till analysvariabler.

## Förutsättningar

[Skapa ett dokument för lösningsdesign](solution-design.md) - Det är viktigt för er organisation att följa spårningskraven. Se till att du är förberedd på ett lösningsdesigndokument innan du kontaktar utvecklingsteamen i organisationen.

## Arbetsflöde

Implementering av Adobe Analytics med ett datalager följer vanligtvis dessa steg:

1. **Samarbeta med webbplatsens utvecklingsteam för att implementera ett datalager**: Webbplatsutvecklingsteamet ansvarar i första hand för att se till att datalagret fylls med korrekta värden. Granska den här sidan med ditt utvecklingsteam för att se till att förväntningarna är desamma i olika team.

   >[!NOTE]
   >
   >Följande Adobe rekommenderade datalagerspecifikationer är valfria. Om du redan har ett datalager, eller på annat sätt väljer att inte följa Adobe specifikationer, måste du se till att din organisation anpassar sig efter vilken specifikation som ska följas.

1. **Validera datalagret med en webbläsarkonsol**: När ett datalager har skapats kan du validera att det fungerar med hjälp av en webbläsares utvecklarkonsol. Du kan öppna utvecklarkonsolen i de flesta webbläsare med `F12` nyckel. Ett exempel på variabelvärde skulle vara `adobeDataLayer.page.title`.
1. **Använd Adobe Experience Platform Data Collection för att mappa datalager-objekt till dataelement**: Det här steget varierar beroende på organisationens implementeringsmetod:
   * **Om du använder Web SDK**: Mappa önskade datalagerobjekt till önskade XDM-fält i Adobe Experience Platform Edge. Se [Variabelmappning för analyser](../aep-edge/variable-mapping.md) för att fastställa den önskade datalagermappningen.
   * **Om Analytics-tillägget används**: Skapa dataelement under Taggar i Adobe Experience Platform Data Collection och tilldela dem till önskade datalager-objekt. Tilldela sedan varje dataelement till rätt Analytics-variabel i Analytics-tillägget.

## Specifikationer

Adobe rekommenderar att du använder [Adobe-klientdatalager](https://github.com/adobe/adobe-client-data-layer/wiki) för nya eller omstrukturerade implementeringar.

Din organisation kan använda andra datalagerspecifikationer, som [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf)eller en annan anpassad specifikation helt och hållet. Det viktigaste är att anpassa sig till ett konsekvent datalager som uppfyller organisationens behov.

Datalager är utökningsbara. om du har särskilda krav för organisationen, kan du inkludera objekt i datalagret för att tillgodose dessa behov.

## Ange datalagervärden

Datalager genererar vanligtvis serversidan och refererar till samma objekt som används för att skapa webbplatsinnehållet. Upprätta webbplatsens datalager baserat på spårningskrav som anges i organisationens [konstruktionsdokument](solution-design.md).

## Nästa steg

[Mappa datalagerobjekt till dataelement](../launch/layer-to-elements.md): Använd webbplatsens datalager i Adobe Experience Platform.
