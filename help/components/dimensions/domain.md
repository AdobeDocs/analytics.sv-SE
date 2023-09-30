---
title: Domän
description: Den organisation eller Internet-leverantör som besökaren använder för att få tillgång till internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 1%

---

# Domän

Domänen [dimension](overview.md) rapporterar vilka åtkomstpunkter besökarna använder för att få tillgång till internet.

## Fyll den här dimensionen med data

Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att fastställa åtkomstpunktsdomänen. Flera metoder, bland annat omvänd DNS-sökning, används för att fastställa åtkomstpunktsdomänen. Den kräver ingen konfiguration och har ingen variabel att fylla i.

* För implementeringar av AppMeasurement fungerar den här dimensionen som standard.
* Aktivera för Web SDK-implementeringar [!UICONTROL Network Lookup] när [konfigurera ett datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Dimensioner

Exempel på dimensionsobjekt inkluderar `comcast.net`, `rr.com`, `sbcglobal.net`och `amazonaws.com`. Dessa domäner är åtkomstpunkter och inte nödvändigtvis den domän som representerar en Internet-leverantör eller organisation.

Dimension `None` innebär att ägaren av åtkomstpunktens IP-adress inte har angett någon domän.
