---
title: Domän
description: Den organisation eller Internet-leverantör som besökaren använder för att få tillgång till internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 1%

---

# Domän

Domänen [dimension](overview.md) rapporterar de åtkomstpunkter som besökare använder för att få åtkomst till Internet.

## Fyll den här dimensionen med data

Adobe samarbetar med [Digital Element](https://www.digitalelement.com/) för att fastställa åtkomstpunktsdomänen. Flera metoder, bland annat omvänd DNS-sökning, används för att fastställa åtkomstpunktsdomänen. Den kräver ingen konfiguration och har ingen variabel att fylla i.

* För implementeringar av AppMeasurement fungerar den här dimensionen som standard.
* Aktivera [!UICONTROL Network Lookup] när [konfigurerar ett datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=sv-SE) för Web SDK-implementeringar.

## Dimensioner

Exempel på dimensionsobjekt är `comcast.net`, `rr.com`, `sbcglobal.net` och `amazonaws.com`. Dessa domäner är åtkomstpunkter och inte nödvändigtvis den domän som representerar en Internet-leverantör eller organisation.

Dimensionen `None` innebär att ägaren till åtkomstpunktens IP-adress inte har angett någon domän.
