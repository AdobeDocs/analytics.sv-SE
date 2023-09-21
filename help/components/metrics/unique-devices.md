---
title: Unika enheter
description: Antalet unika enheter.
feature: Metrics
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---

# Unika enheter

Unika enheter [mått](overview.md) är en [Enhetsövergripande analys](../cda/overview.md) mätvärden som räknar antalet unika oidentifierade enheter och unika virtuella enheter. Oidentifierade enheter är enheter som genererade anonyma träffar. Unika virtuella enheter är distinkta personer som identifieras per enhet.

## Hur det här måttet beräknas

För varje enhet, summera alla distinkta personer som är kopplade till den (inklusive anonyma om enheten innehåller icke-sammanfogade träffar).

Observera att det här måttet inte är lika med [Unika besökare](unique-visitors.md) i andra rapporteringsprogram än CDA. En enhet delas till exempel av tre olika konton. Om alla tre kontona besöker din webbplats i ett rapportfönster visas tre unika enheter i CDA i den resulterande rapporten. Samma data utanför CDA skulle visa 1 unik besökare.

## Exempel

1. Sally anländer till din webbplats på sin telefon via en annons, men är inte inloggad.
1. Sally vill göra ett köp, men vill helst göra det på familjens dator eftersom hon redan är inloggad där. På familjens dator gör hon ett köp.
1. Nästa dag kontrollerar hon sin beställning på telefonen och autentiserar den.
1. Bob&#39;s fru Alice, surfar på din sajt medan hon loggade in på sitt konto på familjens dator.
1. Bob&#39;s bror, Charles, bläddrar också till din webbplats medan han är inloggad på sitt konto på familjens dator.

![Antal unika enheter](/help/components/metrics/assets/Unique_Devices_Count.png)

Visa dessa data i en virtuell CDA-rapportsserie före [Spela upp](/help/components/cda/replay.md) oautentiserade träffar kan sammanfogas:

* **5 unika enheter**: 1 för oautentiserad Bob + 2 för Bob + 1 för Alice + 1 för Charles
* **4 [Folk](people.md)**: 1 [Oidentifierade personer](unidentified-people.md) + 3 [Identifierade personer](identified-people.md).
