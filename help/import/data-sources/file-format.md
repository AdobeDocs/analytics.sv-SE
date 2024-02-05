---
title: Datakällfilformat
description: Generera en fil som kan användas i datakällor korrekt.
exl-id: 6632b970-e931-4272-a69b-c1130ad6475f
feature: Data Sources
role: Admin
source-git-commit: cc25fe304d9cab3db3fa2ddd306338ff3bb88a55
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 3%

---

# Datakällfilformat

Datakällfiler har följande egenskaper:

* Filen finns i `.txt` format.
* Kommenterade rader börjar med &#39;`#`och är valfria.
* Den första raden som inte är kommenterad innehåller filens rubriker.
* Det första värdet för varje rad är datumet som använder formatet `MM/DD/YYYY` eller `MM/DD/YYYY/HH/mm/SS`.
* Värden på alla rader, inklusive rubriker, är tabbavgränsade.
* Varje rad måste ha minst en dimension och ett mått.

## Kommentarer

Alla rader som börjar med &#39;`#`&#39; är en kommentar. När du hämtar en datakällmallfil är de två första raderna kommentarer.

* Den första kommentaren anger vilken typ av mall du har konfigurerat för datakällan, det användar-ID för backend-objektet som skapade datakällan samt datakällans-ID.
* Den andra kommentaren ger egna namn för vart och ett av de rubriker som finns i mallfilen.

Alla kommentarsrader ignoreras av Adobe när filen bearbetas, så du kan ta bort mallkommentarerna eller lägga till egna i hela filen. Endast hela rader kan kommenteras. Du kan inte kommentera i enskilda fält eller delar av rader.

## Sidhuvuden

När du överför datakällfiler krävs kolumnrubriker. De här kolumnrubrikerna är inte skiftlägeskänsliga, men det krävs blanksteg (t.ex. `eVar1` är en ogiltig rubrik, while `EVAR 1` är giltigt). Kolumnrubriker gäller för alla rapportsviter. Använd följande tabeller för att kontrollera att varje rubrik i datakällfilen är korrekt inställd.

>[!TIP]
>
>Du kan skapa en datakällfil från grunden om du tar med rätt rubriker i datakällfilen. Det finns ingen gräns för hur många rubriker du kan ta med i en enda fil. Varje rad kan dock bara innehålla maximalt 4 096 byte.

| Dimension | Datakällrubrik |
| --- | --- |
| [Kategori](/help/components/dimensions/category.md) | `Category` |
| [eVar1 - eVar250](/help/components/dimensions/evar.md) | `Evar 1` - `Evar 250` |
| [Marknadsföringskanal](/help/components/dimensions/marketing-channel.md) | `Marketing Channel` |
| [Information om marknadsföringskanal](/help/components/dimensions/marketing-detail.md) | `Marketing Channel Detail` |
| [Produkt](/help/components/dimensions/product.md) | `Product` |
| [Spårningskod](/help/components/dimensions/tracking-code.md) | `Tracking Code` |
| [Transaktions-ID](/help/implement/vars/page-vars/transactionid.md) | `transactionID` |
| [Postnummer](/help/components/dimensions/zip-code.md) | `Zip` |

{style="table-layout:auto"}

Dimensioner och mätvärden placeras i samma rubrikrad.

| Mått | Datakällrubrik |
| --- | --- |
| [Tillägg i kundvagn](/help/components/metrics/cart-additions.md) | `Cart Adds` |
| [Raderingar i kundvagn](/help/components/metrics/cart-removals.md) | `Cart Removes` |
| [Kundvagnsvisningar](/help/components/metrics/cart-views.md) | `Cart Views` |
| [Korgar](/help/components/metrics/carts.md) | `Cart Opens` |
| [Utcheckningar](/help/components/metrics/checkouts.md) | `Checkouts` |
| [Anpassade händelser](/help/components/metrics/custom-events.md) | `Event 1` - `Event 1000` |
| [Beställningar](/help/components/metrics/orders.md) | `Orders` |
| [Intäkter](/help/components/metrics/revenue.md) | `Price` |
| [Enheter](/help/components/metrics/units.md) | `Quantity` |

{style="table-layout:auto"}

Adobe stöder inte datakällor för andra mått eller mätvärden. Om variabler utöver vad som anges i tabellerna ovan är obligatoriska bör du använda [API för massdatainfogning](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) i stället.

## Datum

Det första värdet i varje rad **måste** vara datumet. Datumformatet måste ha något av följande format:

* **`MM/DD/YYYY/HH/mm/SS`**
* **`MM/DD/YYYY`**

Om du utelämnar timmar/minuter/sekunder anges tidsstämpeln automatiskt till 12 PM för den dagen.

En enda datakällfil har stöd för upp till 90 unika dagar. Om du vill inkludera mer än 90 unika dagar i en överföring delar du upp dina data i flera filer.

## Dimensions- och mätdata

Efterföljande värden efter datumet i varje rad innehåller de data som du vill överföra. Varje rad motsvarar den aktuella tidsstämpeln. Se till att samma antal flikar finns på varje rad. Kolumner kan vara i vilken ordning som helst. Kontrollera att data i varje rad justeras mot rubrikerna överst. Den maximala mängden data som en rad kan innehålla är 4 096 byte.

Dimensionen får inte innehålla semikolon (`;`). Rader som innehåller semikolon hoppas över.

## Nästa steg

[Filöverföring](file-upload.md): Lär dig processen att överföra en datakällfil för förtäring från Adobe.
