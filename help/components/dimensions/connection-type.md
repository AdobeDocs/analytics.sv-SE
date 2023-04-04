---
title: Anslutningstyp
description: Hur besökaren ansluter till internet.
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: ac3748826d9907cc68076ad39e865f39ea903cf2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Anslutningstyp

Dimensionen Anslutningstyp visar hur besökaren är ansluten till Internet. Den här dimensionen är användbar för att avgöra hur besökare ansluter till Internet för att surfa på din webbplats. Du kan använda den för att optimera webbplatsinnehållet baserat på besökarnas anslutningshastighet.

## Fyll den här dimensionen med data

Den här dimensionen använder en kombination av [`ct` frågesträng](/help/implement/validate/query-parameters.md) och serverlogik på Adobe. Adobe använder följande regler för att fastställa sitt värde:

1. Om `ct` frågesträng är lika med `"modem"`, ange dimensionsobjektet till `"Modem"`. AppMeasurement samlar bara in dessa data i Internet Explorer-webbläsare som inte stöds, vilket gör detta dimensionsobjekt ovanligt.
1. Kontrollera träffens IP-adress och referera den till en uppslagstabell som är intern för Adobe. Om IP-adressen kommer från en mobiloperatör anger du dimensionsposten till `"Mobile Carrier"`.
1. Om `ct` frågesträng är lika med `"lan"`, ange dimensionsobjektet till `"LAN/Wifi"`.
1. Om träffen kommer från en [Datakälla](/help/import/data-sources/overview.md) eller på annat sätt betraktas som en särskild typ av träff, ställ in dimensionsobjektet på `"Not specified"`.
1. Om ingen av ovanstående regler uppfylls används standardvärdet för `"LAN/Wifi"`.

## Dimensioner

Dimensionerna innehåller `LAN/Wifi`, `Mobile Carrier`, `Modem`och `Not Specified`.

* **`LAN/Wifi`**: Besökaren är ansluten till internet via en fast linje eller Wi-Fi hotspot.
* **`Mobile Carrier`**: Besökaren är ansluten till Internet via ett mobiloperatör.
* **`Modem`**: Besökaren är ansluten till Internet via ett modem i en webbläsare som inte stöds.
* **`Not Specified`**: Träffen hade ingen anslutningstyp.
