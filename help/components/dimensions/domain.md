---
title: Domän
description: Den organisation eller Internet-leverantör som besökaren använder för att få tillgång till internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 1%

---

# Domän

Domänen [dimension](overview.md) rapporterar åtkomstpunkter som besökare använder för att få tillgång till internet.

## Fyll den här dimensionen med data

Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att fastställa åtkomstpunktsdomänen. Flera metoder, bland annat omvänd DNS-sökning, används för att fastställa åtkomstpunktsdomänen. Den kräver ingen konfiguration och har ingen variabel att fylla i. Det fungerar som det ska med alla implementeringar av AppMeasurement.

## Dimensioner

Exempel på dimensionsobjekt inkluderar `comcast.net`, `rr.com`, `sbcglobal.net`och `amazonaws.com`. Observera att dessa domäner är åtkomstpunkter och inte nödvändigtvis den domän som representerar en Internet-leverantör eller organisation.

Dimension `None` innebär att ägaren av åtkomstpunktens IP-adress inte har angett någon domän.
