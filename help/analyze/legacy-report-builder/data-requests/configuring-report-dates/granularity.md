---
description: I begärandeguiden, steg 1, kan du använda en detaljnivå för databegäran. Granularitet anger den nivå av tidsbaserad detalj som ingår i rapporten.
title: Kornighet
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
feature: Report Builder
role: User, Admin
exl-id: 96c3b93a-9adf-4993-b6fc-9146ee5be4bd
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 1%

---

# Kornighet

I begärandeguiden: Steg 1 kan du använda en nivå av granularitet för databegäran. Granularitet anger den nivå av tidsbaserad detalj som ingår i rapporten.

Giltiga värden är Hour, Day, Week, Month, Quarter, Year och Aggregated.

## Så här bearbetar Report Builder granularitet

Anta att du väljer ett datumintervall för en månad med [!UICONTROL Month] granularitet. Förfrågningar visar summor för måttet baserat på exakt en månads data. Om datumintervallet för din begäran sträcker sig över en fjärdedel visar rapporten tre siffror: en för varje månadsenhet eller en del av den. Om det är den 18 mars i dag returnerar det sista kvartalet en siffra för januari 1-31, en annan för februari 1-28 och en sista siffra för mars 1-31.
