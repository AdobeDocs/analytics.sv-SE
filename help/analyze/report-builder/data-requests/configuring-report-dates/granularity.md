---
description: I begärandeguiden, steg 1, kan du använda en detaljnivå för databegäran. Granularitet anger den nivå av tidsbaserad detalj som ingår i rapporten.
title: Kornighet
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
feature: Report Builder
role: User, Admin
exl-id: 96c3b93a-9adf-4993-b6fc-9146ee5be4bd
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 1%

---

# Kornighet

I Request Wizard: Steg 1 kan du använda en nivå av granularitet för databegäran. Granularitet anger den nivå av tidsbaserad detalj som ingår i rapporten.

Giltiga värden är Hour, Day, Week, Month, Quarter, Year och Aggregated.

## Hur Report Builder hanterar granularitet

Anta att du väljer ett datumintervall för en månad med [!UICONTROL Month] granularitet. Förfrågningar visar summor för måttet baserat på exakt en månads data. Om datumintervallet för din begäran sträcker sig över en fjärdedel visar rapporten tre siffror: en för varje månadsenhet, eller del därav. Om det är den 18 mars i dag returnerar det sista kvartalet en siffra för 1 januari-31 januari, en annan för 1 februari-28 februari och en sista siffra för 1 mars-17 mars.
