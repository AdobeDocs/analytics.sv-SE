---
description: Du kan visa data från Document Cloud i Adobe Analytics
title: Konfigurera rapportering för Document Cloud
feature: Admin Tools
source-git-commit: 01aa0959a7ddd8d5a29c838bdbc771435784c9e6
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 1%

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

**Mätvärden:**

* Vyer i PDF

* Sidvyer i PDF

* Nedladdningar för PDF

* PDF Search

* Bokmärken från PDF

* PDF Copy Text

* PDF Print

## Aktivera rapportering för PDF i Adobe Analytics

1. Gå till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **`<select report suite>`** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Document Cloud Management]** > [!UICONTROL **Document Cloud Reporting**].

1. På Adobe Document Cloud Management-sidan väljer du [!UICONTROL **Aktivera PDF-rapporter**].

1. Om du vill konfigurera Adobe Document Cloud att överföra data till Adobe Analytics använder du [Adobe Document Cloud Javascript SDK](https://www.adobe.io/apis/documentcloud/dcsdk.html).


