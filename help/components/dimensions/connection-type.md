---
title: Anslutningstyp
description: Hur besökaren ansluter till internet.
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# Anslutningstyp

Anslutningstypen [dimension](overview.md) visar hur besökaren är ansluten till Internet. Den här dimensionen är användbar för att avgöra hur besökare ansluter till Internet för att surfa på din webbplats. Du kan använda den för att optimera webbplatsinnehållet baserat på besökarnas anslutningshastighet.

## Fyll den här dimensionen med data

Den här dimensionen använder en kombination av [`ct`-frågesträngen ](/help/implement/validate/query-parameters.md) och serverlogiken i Adobe. Adobe använder följande regler för att fastställa sitt värde:

1. Om frågesträngen `ct` är lika med `"modem"` anger du dimensionsobjektet till `"Modem"`. AppMeasurementet samlar bara in dessa data i Internet Explorer-webbläsare som inte stöds, vilket gör det här dimensionsobjektet mindre vanligt.
1. Kontrollera träffens IP-adress och referera den till en uppslagstabell som är intern för Adobe. Om IP-adressen kommer från en mobiloperatör anger du dimensionsobjektet till `"Mobile Carrier"`.
1. Om frågesträngen `ct` är lika med `"lan"` anger du dimensionsobjektet till `"LAN/Wifi"`.
1. Om träffen kommer från en [datakälla](/help/import/data-sources/overview.md) eller på annat sätt betraktas som en speciell typ av träff anger du dimensionsobjektet till `"Not specified"`.
1. Om ingen av ovanstående regler uppfylls, används värdet `"LAN/Wifi"` som standard.

## Dimensioner

Bland Dimensionerna finns `LAN/Wifi`, `Mobile Carrier`, `Modem` och `Not Specified`.

* **`LAN/Wifi`**: Besökaren är ansluten till Internet via en aktiveringspunkt för en fast linje eller wifi.
* **`Mobile Carrier`**: Besökaren är ansluten till Internet via en mobiloperatör.
* **`Modem`**: Besökaren är ansluten till Internet via ett modem i en webbläsare som inte stöds.
* **`Not Specified`**: Träffen hade ingen anslutningstyp.
