---
title: Överför datakällfil till Adobe
description: Processen att överföra en datakällfil till Adobe Analytics för förtäring.
exl-id: 64e3cd70-b511-4c4e-abd0-94eb36bc3519
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 0%

---

# Överför datakällfil till Adobe

När du skickar en datakällfil till Adobe används ett vanligt autentiserat FTP-arbetsflöde. Du kan använda Utforskaren, Finder eller en dedikerad FTP-klient för att överföra önskade filer till Adobe FTP-platsen.

Leta reda på FTP-autentiseringsuppgifterna i [hanteraren för datakällor](manage.md). Varje datakälla har en länk till dess **[!UICONTROL FTP Info]**. Varje FTP-plats är dedikerad till den specifika datakällan. Du kan inte använda samma FTP-plats för flera datakällor.

Av säkerhetsskäl är FTP-platser utan aktivitet i över 30 dagar inaktiverade.

## Filen `.fin`

En viktig del av att det går att hämta en datakällfil är att en `.fin`-fil inkluderas. Den här filen anger för Adobe att datafilen är klar för bearbetning. Om du överför en datakällfil utan någon motsvarande `.fin`-fil bearbetar Adobe aldrig dessa data.

Filen `.fin` har följande egenskaper:

* Filen har tillägget `.fin`. Se till att ditt operativsystem tillåter dig att se och redigera filtyper.
* Filen är tom. Lagra inte data i filen `.fin`.
* Filen har exakt samma namn som datakällfilen. Om du till exempel överför en datakällfil med namnet `example.txt` måste `.fin` file **&#x200B;**&#x200B;ha namnet `example.fin`. Om de inte har samma namn bearbetar Adobe aldrig datakällfilen.

När både datakällfilen och filen `.fin` har överförts till FTP-platsen bearbetar Adobe filen. Överför inte filen `.fin` förrän datakällfilen har överförts helt. Om filen `.fin` överförs för tidigt, hämtar och importerar Adobe den delvis överförda filen, vilket genererar eventuella fel.

## Bearbetningsorder

Om du överför flera filer samtidigt till FTP-platsen, infogar Adobe dem i alfanumerisk ordning. Om din organisation kräver att filerna ska importeras i en viss ordning måste du se till att deras filnamn får ett alfanumeriskt namn.

## Bearbetningstid

För att filerna ska behandlas så snabbt som möjligt rekommenderar Adobe att du samlar in metadata på en enda rad per datum. Den här datakällfilen skulle till exempel bearbetas långsammare om den var giltig:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | | `1` | |
| `07/24/YYYY` | `red` | | | `1` |

Den här filen bearbetas snabbare, som innehåller samma data:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `2` | `1` | `1` |
