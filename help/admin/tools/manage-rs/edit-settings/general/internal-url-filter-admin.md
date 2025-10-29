---
description: Interna URL-filter identifierar de referenser som du anser vara interna för din webbplats. De hjälper trafikkällor att fylla i data och hjälper till att filtrera intern trafik.
title: Interna URL-filter
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---


# Interna URL-filter

Med hjälp av interna URL-filter kan du identifiera de referenser som du anser vara interna för webbplatsen. De hjälper trafikkällor att fylla i data och hjälper till att filtrera intern trafik.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Internal URL Filters]**

En hänvisare, eller hänvisande sida, är vanligtvis den sida från vilken en besökare har angett webbplatsen. För att undvika att skevas kan du filtrera bort interna referenser. Dimensioner som är beroende av interna URL-filter är bland annat [Referent](/help/components/dimensions/referrer.md), [Refererande domän](/help/components/dimensions/referring-domain.md), [Marknadskanaler](/help/components/dimensions/marketing-channel.md) och andra trafikkällans dimensioner.

[Bearbetningsreglerna för marknadsföringskanaler](../marketing-channels/mc-proc-rules.md) anger [!UICONTROL Matches internal URL filters] som möjliga regelvillkor.

>[!IMPORTANT]
>
>Vissa rapportsviter har ett internt URL-filter med en punkt (`.`) konfigurerat som standard. När det här filtret finns klassificeras all trafik som intern. Referensrapporter fungerar inte förrän det här filtret har tagits bort och ersatts med en eller flera önskade interna domäner.

* Visa alla befintliga filter under avsnittet **[!UICONTROL Current Filters]**.
* Lägg till ett filter med textrutan under avsnittet **[!UICONTROL Add Filter]** och klicka sedan på **[!UICONTROL Add]**.

Filter använder logiken **contains** mot den fullständiga URL:en. Adobe rekommenderar att du utelämnar protokoll (`https://`) och underdomäner när du skapar filter, såvida inte trafik från separata underdomäner önskas som extern trafik.
