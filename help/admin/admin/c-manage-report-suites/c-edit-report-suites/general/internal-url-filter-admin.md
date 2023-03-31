---
description: Interna URL-filter identifierar de referenser som du anser vara interna för din webbplats. De hjälper trafikkällor att fylla i data och hjälper till att filtrera intern trafik.
title: Interna URL-filter
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 2beb4cd38fc8b48e2b34468a4570f7168aeacb78
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 1%

---


# Interna URL-filter

Med hjälp av interna URL-filter kan du identifiera de referenser som du anser vara interna för webbplatsen. De hjälper trafikkällor att fylla i data och hjälper till att filtrera intern trafik.

En hänvisare, eller hänvisande sida, är vanligtvis den sida från vilken en besökare har angett webbplatsen. För att undvika att skevas kan du filtrera bort interna referenser. Rapporterna exkluderar filtrerade referenser från [Referenter](/help/components/dimensions/referrer.md) dimension, [Refererande domäner](/help/components/dimensions/referring-domain.md) dimension och andra mått för trafikkälla.

## Visa befintliga interna URL-filter

>[!NOTE]
>
>Vissa rapportsviter har ett internt URL-filter med en punkt (.) konfigureras som standard. När det här filtret finns klassificeras all trafik som intern. Referensrapporter fungerar inte förrän i perioden (.) filtret tas bort.

Så här kontrollerar du vilka interna URL-filter som har konfigurerats för en rapportserie: <!-- I don't see the period in my instance? Is the following information valid? "To avoid this, remove the rule listing a period (.) as a filter, and add your own site. The reason why a period is the default internal URL filter is to allow data to be collected in the Pages report. If hits do not match internal URL filters, all pages come up as Other. A period is always somewhere in the URL, which guarantees the Pages report is populated.")-->

1. Välj **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** för att få tillgång till Report Suite Manager.

1. Välj den rapportsvit där du vill kontrollera vilka interna URL-filter som har konfigurerats och välj sedan **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Internal URL Filters]**.

   Alla befintliga filter visas i [!UICONTROL **Aktuella filter**] -avsnitt.

## Lägga till ett internt URL-filter i en rapportserie

1. Välj **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** för att få tillgång till Report Suite Manager.

1. Välj den rapportsvit där du vill lägga till ett internt URL-filter och välj sedan **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Internal URL Filters]**.

1. I avsnittet Lägg till filter i fältet som visas börjar du skriva URL-adressen till sidan som du vill filtrera och väljer sedan [!UICONTROL **Lägg till**].

   URL:en som du har lagt till visas nu i [!UICONTROL **Aktuella filter**] -avsnitt.
