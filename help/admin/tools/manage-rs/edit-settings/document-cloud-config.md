---
description: Du kan visa Document Cloud-data i Adobe Analytics
title: Konfigurera Document Cloud-rapportering
feature: Admin Tools
exl-id: eb58d011-c4b0-4c0c-9241-83b2bccc2c77
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 0%

---

# Konfigurera Document Cloud-rapportering

Du kan konfigurera PDF-specifika mått och mätvärden som ska vara tillgängliga i Adobe Analytics.

## Komponenter som läggs till när du aktiverar PDF-rapportering

När PDF rapportering är korrekt konfigurerad är följande mått och mätvärden tillgängliga i Adobe Analytics:

**Dimensioner:**

* PDF Search - term

* PDF zoomnivå

* PDF Action

* PDF sidnummer

* PDF Filnamn

**Mått:**

* PDF-vyer

* PDF sidvyer

* PDF Downloads

* PDF Search

* Använda PDF-bokmärken

* PDF Copy Text

* PDF Print

## Aktivera PDF-rapportering i Adobe Analytics

1. Gå till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **`<select report suite>`** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Document Cloud Management]** > [!UICONTROL **Document Cloud Reporting**].

1. Välj [!UICONTROL **Aktivera PDF-rapporter**] på Adobe Document Cloud-hanteringssidan.

1. Använd [Adobe Document Cloud Javascript SDK](https://www.adobe.io/apis/documentcloud/dcsdk.html) för att konfigurera Adobe Document Cloud att överföra data till Adobe Analytics.
