---
title: Unika enheter
description: Antalet unika enheter.
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: db88bd439c036e97cca641f31f4fc3101a368636
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---

# Unika enheter

Mätvärdet för &#39;Unika enheter&#39; är en [enhetsanalys](../cda/overview.md) som räknar antalet unika oidentifierade enheter och unika virtuella enheter. Oidentifierade enheter är enheter som genererade anonyma träffar. Unika virtuella enheter är distinkta personer som identifieras per enhet.

## Hur det här måttet beräknas

För varje enhet, summera alla distinkta personer som är kopplade till den (inklusive anonyma om enheten innehåller icke-sammanfogade träffar).

Observera att det här måttet inte är lika med [Unika besökare](unique-visitors.md) i andra rapporteringsprogram än CDA. En enhet delas till exempel av tre olika konton. Om alla tre kontona besöker din webbplats i ett rapportfönster visas tre unika enheter i CDA i den resulterande rapporten. Samma data utanför CDA skulle visa 1 unik besökare.

## Exempel

1. Bob kommer till din webbplats på sin telefon via en annons, men är inte inloggad.
1. Bob vill köpa något, men föredrar att göra det på familjens dator eftersom han redan är inloggad där. På familjens dator gör han ett köp.
1. Dagen därpå kontrollerar han sin order på sin telefon och autentiserar den.
1. Bob&#39;s fru Alice, surfar på din webbplats medan hon loggade in på sitt konto på familjens dator.
1. Bob&#39;s bror, Charles, bläddrar också till din webbplats medan han är inloggad på sitt konto på familjens dator.

![Antal unika enheter](/help/components/metrics/assets/Unique_Devices_Count.png)

Om du visar dessa data i en virtuell CDA-rapportsserie före [Replay](/help/components/cda/replay.md) sammanfogar oautentiserade träffar kan följande visas:

* **5 unika enheter**: 1 för oautentiserad Bob + 2 för Bob + 1 för Alice + 1 för Charles
* **4  [Personer](people.md)**: 1  [Identifierade personer](unidentified-people.md) + 3  [Identifierade personer](identified-people.md).
