---
title: Domän
description: Den organisation eller Internet-leverantör som besökaren använder för att få tillgång till internet.
translation-type: tm+mt
source-git-commit: c2d371cee2821360ab87240b1a81695798af4f9f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 1%

---


# Domän

Dimensionen Domän rapporterar åtkomstpunkter som besökare använder för att få åtkomst till internet.

## Fyll den här dimensionen med data

Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att fastställa åtkomstpunktens domän. Flera metoder, bland annat omvänd DNS-sökning, används för att fastställa åtkomstpunktsdomänen. Den kräver ingen konfiguration och har ingen variabel att fylla i. Det fungerar som det ska med alla AppMeasurement-implementeringar.

## Dimensioner

Exempel på dimensionsobjekt är `comcast.net`, `rr.com`, `sbcglobal.net`och `amazonaws.com`. Observera att dessa domäner är åtkomstpunkter och inte nödvändigtvis den domän som representerar en Internet-leverantör eller organisation.

Dimensionens värden `None` innebär att ägaren till åtkomstpunktens IP-adress inte har angett någon domän.
