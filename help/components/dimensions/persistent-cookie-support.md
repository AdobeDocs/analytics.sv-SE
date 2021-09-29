---
title: Stöd för permanenta cookies
description: Avgör om besökaren kan stödja beständiga cookies.
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
source-git-commit: 82d6137bc9229bbaa997c6856690bf76c20b755c
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Stöd för permanenta cookies

Dimensionen &quot;Beständigt stöd för cookies&quot; visar om träffen använde en besökaridentifierare som härstammar från en beständig källa. Den vanligaste beständiga källan är från en cookie, men kan även använda mobilrubriker och andra källor.

## Fyll den här dimensionen med data

Adobe bestämmer värdet för den här dimensionsserversidan baserat på källan för träffens identifierare. Det finns inget sätt att ställa in den direkt. Det fungerar som det ska för alla implementeringar.

## Dimensioner

* **`Enabled`**: Träffens besökaridentifierare kommer från en källa som vanligtvis består. De vanligaste exemplen är `aid`, `fid` eller `mid` frågesträngsparametrar, eftersom de hämtar sina värden från en cookie.
* **`Disabled`**: Träffens besökaridentifierare kom från en källa som Adobe inte känner igen som beständig, till exempel IP + användaragentsträng. Detta dimensionsobjekt inkluderar även anpassade besökar-ID:n som använder variabeln [`visitorID`](/help/implement/vars/config-vars/visitorid.md).

## Skillnad mellan &#39;Stöd för cookies&#39; och &#39;Stöd för beständig cookie&#39;

* **Cookie-stöd**: AppMeasurement försöker ange en allmän cookie. Dimensionsobjektet baseras på om cookien har angetts.
* **Stöd** för permanenta cookies: Dimensionsobjektet baseras på om träffens identifierare härstammar från en beständig källa, till exempel en cookie.
