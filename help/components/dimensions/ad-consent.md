---
title: Godkännande av annonsplattform
description: Se konfigurationen för annonsmedgivande för tredjeparts annonsleverantörer.
feature: Dimensions
source-git-commit: 043f2c2b2e3e50570e2f0367680274a1f2670492
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# Godkännande av annonsplattform

Ad Platform-medgivande [dimension](overview.md) visar om samtycke samlas in för att skicka data till tredjepartsleverantörer av annonser, som Google, Meta och andra.

För närvarande används den här dimensionen endast för Google. På grund av EU:s sekretessbestämmelser, Digital Markets Act (DMA), kräver Google att data som skickas till deras servrar och som samlas in i Europa måste ange om samtycke samlas in. Vissa Analytics-kunder skickar händelsedata via Adobe Advertising som konverteringshändelser till Google.

I framtiden kan den här dimensionen användas som stöd för kodning av ytterligare medgivandeinformation för andra tredjepartsleverantörer av annonser.

## Fyll den här dimensionen med data

Den här dimensionen samlar in data från följande [Sammanhangsdatavariabler](/help/implement/vars/page-vars/contextdata.md)

* `contextData.['adConsent']`

Du fyller i kontextdatavariabeln med relevanta värden för Google medgivandefält

* `ad_user_data` (första tecknet) och
* `ad_personalization` (andra tecknet).

Se [Godkännande i API-referensen för Google Ads](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent) för mer information.

Möjliga värden för dessa fält kan vara:

| Värde | ad_user_data | ad_personalization |
|:-:|---|---|
| `Y` | Ge Google samtycke för annonsanvändardata. | Ge Google samtycke för annonspersonalisering. |
| `N` | Neka Google samtycke för annonsanvändardata. | Google ger sitt uttryckliga medgivande för personalisering av annonser. |
| `U` | Ospecificerad. | Ospecificerad. |

Exemplet nedan ger Google samtycke för annonsanvändardata men inte för annonspersonalisering:

```
contextData.['adConsent'] = "YN..."
```

Tecken efter det första och andra tecknet ignoreras.

## Använd data

Du kan använda insamlade data för annonsgodkännande:

* Dataflöden: data om annonsmedgivande är tillgängliga med `dataprivacydmaconsent` [kolumn](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).
* Data Warehouse-rapporter: data om annonsmedgivande finns tillgängliga med **[!UICONTROL Ad Platform Consent]** dimension.

Organisationen bestämmer logiken för att implementera den här kontextdatavariabeln. Värdet finns inte kvar efter den träff det är aktiverat, så du måste ange kontextdatavariabeln på varje sida.

När du skickar annonsdata från Adobe Analytics via Adobe Advertising som konverteringsevenemang till Google, konsultera Adobe Advertising-teamet för att få hjälp med integreringen.

Mer information finns i [Sekretessrapportering](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md).
