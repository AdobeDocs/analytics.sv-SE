---
description: Du kan visa data från Document Cloud i Adobe Analytics
title: Konfigurera rapportering för Document Cloud
feature: Admin Tools
exl-id: eb58d011-c4b0-4c0c-9241-83b2bccc2c77
source-git-commit: bdd9473b0ac3bd77ffeff53a095876e21ca2f4d4
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 0%

---

# Konfigurera rapportering för Document Cloud

Du kan konfigurera PDF-specifika mått och mätvärden som ska vara tillgängliga i Adobe Analytics.

## Komponenter som läggs till när du aktiverar PDF-rapportering

När rapportering från PDF är korrekt konfigurerad är följande mått och mått tillgängliga i Adobe Analytics:

**Dimensioner:**

* Sökord för PDF

* PDF zoomnivå

* PDF Action

* PDF Page Number

* PDF filnamn

**Mått:**

* Vyer i PDF

* Sidvyer i PDF

* Nedladdningar för PDF

* PDF Search

* Bokmärken från PDF används

* PDF Copy Text

* PDF Print

## Aktivera rapportering för PDF i Adobe Analytics

1. Gå till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **`<select report suite>`** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Document Cloud Management]** > [!UICONTROL **Document Cloud Reporting**].

1. På Adobe Document Cloud Management-sidan väljer du [!UICONTROL **Enable PDF Reports**].

1. Använd [Adobe Document Cloud Javascript SDK](https://www.adobe.io/apis/documentcloud/dcsdk.html) om du vill konfigurera Adobe Document Cloud att överföra data till Adobe Analytics.
