---
title: Anslutningstyp
description: Hur besökaren ansluter till internet.
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: 82d6137bc9229bbaa997c6856690bf76c20b755c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# Anslutningstyp

Dimensionen Anslutningstyp visar hur besökaren är ansluten till Internet. Den här dimensionen är användbar för att avgöra hur besökare ansluter till Internet för att surfa på din webbplats. Du kan använda den för att optimera webbplatsinnehållet baserat på besökarnas anslutningshastighet.

## Fyll den här dimensionen med data

Den här dimensionen använder en kombination av [`ct`-frågesträngen](/help/implement/validate/query-parameters.md) och serverlogiken i Adobe. Adobe använder följande regler för att fastställa sitt värde:

1. Om `ct`-frågesträngen är lika med `"modem"` anger du `"Modem"` för dimensionsobjektet. AppMeasurement samlar bara in dessa data i Internet Explorer-webbläsare som inte stöds, vilket gör detta dimensionsobjekt ovanligt.
1. Kontrollera träffens IP-adress och referera den till en uppslagstabell som är intern för Adobe. Om IP-adressen kommer från en mobiloperatör ställer du in dimensionsobjektet på `"Mobile Carrier"`.
1. Om `ct`-frågesträngen är lika med `"lan"` anger du `"LAN/Wifi"` för dimensionsobjektet.
1. Om träffen kommer från en [datakälla](/help/import/c-data-sources/datasrc-home.md) eller på annat sätt betraktas som en speciell typ av träff, ställer du in dimensionsobjektet på `"Not specified"`.
1. Om ingen av ovanstående regler uppfylls används standardvärdet `"LAN/Wifi"`.

## Dimensioner

Bland Dimensionerna finns `LAN/Wifi`, `Mobile Carrier`, `Modem` och `Not Specified`.

* **`LAN/Wifi`**: Besökaren är ansluten till internet via en fast linje eller Wi-Fi hotspot.
* **`Mobile Carrier`**: Besökaren är ansluten till Internet via ett mobiloperatör.
* **`Modem`**: Besökaren är ansluten till Internet via ett modem i en webbläsare som inte stöds.
* **`Not Specified`**: Träffen hade ingen anslutningstyp.
