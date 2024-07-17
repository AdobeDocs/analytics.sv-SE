---
title: Skapa ett datalager
description: Lär dig vad ett datalager är i er Analytics-implementering och hur det kan användas för att mappa variabler i Adobe Analytics.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
source-git-commit: 5ef8ba686a13f8b4ab592c0b48a9c074b0477fcf
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 0%

---

# Skapa ett datalager

Ett datalager är ett ramverk av JavaScript-objekt på din webbplats som innehåller de variabelvärden som används i din Analytics-implementering. Det ger bättre kontroll och enklare underhåll när du tilldelar värden till analysvariabler.

## Förutsättningar

[Skapa ett lösningsdesigndokument](solution-design.md) - Det är viktigt för din organisation att anpassa sig efter spårningskrav. Se till att du är förberedd på ett lösningsdesigndokument innan du kontaktar utvecklingsteamen i organisationen.

## Arbetsflöde

Implementering av Adobe Analytics med ett datalager följer vanligtvis dessa steg:

1. **Arbeta med webbplatsutvecklingsteamet för att implementera ett datalager**: Webbplatsutvecklingsteamet ansvarar främst för att datalagretobjektet fylls med korrekta värden. Granska den här sidan med ditt utvecklingsteam för att se till att förväntningarna är desamma i olika team.

   >[!NOTE]
   >
   >Följande Adobe rekommenderade datalagerspecifikationer är valfria. Om du redan har ett datalager, eller på annat sätt väljer att inte följa Adobe specifikationer, måste du se till att din organisation anpassar sig efter vilken specifikation som ska följas.

1. **Verifiera datalagret med en webbläsarkonsol**: När ett datalager har skapats kan du validera att det fungerar med valfri webbläsares utvecklarkonsol. Du kan öppna utvecklarkonsolen i de flesta webbläsare med tangenten `F12`. Ett exempelvariabelvärde skulle vara `adobeDataLayer.page.title`.
1. **Använd Adobe Experience Platform Data Collection för att mappa datalager-objekt till dataelement**: Det här steget varierar beroende på organisationens implementeringsmetod:
   * **Om du använder Web SDK**: Mappa önskade datalagretobjekt till önskade XDM-fält i Adobe Experience Platform Edge. Se [Analysera XDM-variabelmappning](../aep-edge/xdm-var-mapping.md) för att ta reda på vilken datalagermappning du vill använda.
   * **Om du använder Analytics-tillägget**: Skapa dataelement under Taggar i Adobe Experience Platform Data Collection och tilldela dem till önskade datalager-objekt. Tilldela sedan varje dataelement till rätt Analytics-variabel i Analytics-tillägget.

## Specifikationer

Adobe rekommenderar att du använder [Adobe Client Data Layer](https://github.com/adobe/adobe-client-data-layer/wiki) för nya eller omstrukturerade implementeringar.

Din organisation kan använda andra datalagerspecifikationer, som [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf), eller en annan anpassad specifikation helt och hållet. Det viktigaste är att anpassa sig till ett konsekvent datalager som uppfyller organisationens behov.

Datalager är utökningsbara. Om du har särskilda krav för organisationen kan du inkludera objekt i datalagret för att tillgodose dessa behov.

## Ange datalagervärden

Datalager genererar vanligtvis serversidan och refererar till samma objekt som används för att skapa webbplatsinnehållet. Upprätta webbplatsens datalager baserat på spårningskrav som anges i organisationens [lösningsdesigndokument](solution-design.md).

## Nästa steg

[Mappa datalagerobjekt till dataelement](../launch/layer-to-elements.md): Använd datalagret för din plats i Adobe Experience Platform.
