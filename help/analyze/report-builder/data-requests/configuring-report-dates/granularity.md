---
description: I begärandeguiden, steg 1, kan du använda en detaljnivå för databegäran. Granularitet anger den nivå av tidsbaserad detalj som ingår i rapporten.
title: Kornighet
topic: Report builder
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Kornighet

I Request Wizard: Steg 1 kan du använda en nivå av granularitet för databegäran. Granularitet anger den nivå av tidsbaserad detalj som ingår i rapporten.

Giltiga värden är Hour, Day, Week, Month, Quarter, Year och Aggregated.

## Hur Report Builder bearbetar kornighet

Anta att du väljer ett datumintervall för en månad med [!UICONTROL Month] granularitet. Förfrågningar visar summor för måttet baserat på exakt en månads data. Om datumintervallet för din begäran sträcker sig över en fjärdedel visar rapporten tre siffror: en för varje månadsenhet, eller del därav. Om det är den 18 mars i dag returnerar det sista kvartalet en siffra för 1 januari-31 januari, en annan för 1 februari-28 februari och en sista siffra för 1 mars-17 mars.
