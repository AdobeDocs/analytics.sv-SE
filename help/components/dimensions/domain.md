---
title: Domän
description: Den organisation eller Internet-leverantör som besökaren använder för att få tillgång till internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 1%

---

# Domän

Dimensionen Domän rapporterar åtkomstpunkter som besökare använder för att få åtkomst till internet.

## Fyll den här dimensionen med data

Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att fastställa åtkomstpunktsdomänen. Flera metoder, bland annat omvänd DNS-sökning, används för att fastställa åtkomstpunktsdomänen. Den kräver ingen konfiguration och har ingen variabel att fylla i. Det fungerar som det ska med alla AppMeasurement-implementeringar.

## Dimensioner

Exempel på dimensionsobjekt inkluderar `comcast.net`, `rr.com`, `sbcglobal.net`och `amazonaws.com`. Observera att dessa domäner är åtkomstpunkter och inte nödvändigtvis den domän som representerar en Internet-leverantör eller organisation.

Dimension `None` innebär att ägaren av åtkomstpunktens IP-adress inte har angett någon domän.
