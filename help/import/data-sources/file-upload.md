---
title: Överför datakällfil till Adobe
description: Processen att överföra en datakällfil till Adobe Analytics för förtäring.
exl-id: 64e3cd70-b511-4c4e-abd0-94eb36bc3519
feature: Data Sources
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 0%

---

# Överför datakällfil till Adobe

När du skickar en datakällfil till Adobe används ett vanligt autentiserat FTP-arbetsflöde. Du kan använda Utforskaren, Finder eller en dedikerad FTP-klient för att överföra önskade filer till Adobe FTP-platsen.

Leta reda på FTP-autentiseringsuppgifterna i dialogrutan [Datakällhanterare](manage.md). Varje datakälla har en länk till sin **[!UICONTROL FTP Info]**. Varje FTP-plats är avsedd för den specifika datakällan. du kan inte använda samma FTP-plats för flera datakällor.

Av säkerhetsskäl är FTP-platser utan aktivitet i över 30 dagar inaktiverade.

## The `.fin` fil

En viktig del av att lyckas med inhämtningen av en datakällfil är att en `.fin` -fil. Den här filen anger för Adobe att datafilen är klar för bearbetning. Om du överför en datakällfil utan en motsvarande `.fin` fil, Adobe bearbetar aldrig dessa data.

The `.fin` filen har följande egenskaper:

* Filen har en `.fin` tillägg. Kontrollera att operativsystemet tillåter dig att se och redigera filtyper.
* Filen är tom. Lagra inte data i `.fin` -fil.
* Filen har exakt samma namn som datakällfilen. Om du till exempel överför en datakällfil med namnet `example.txt`, `.fin` fil **måste** ha ett namn `example.fin`. Om de inte har samma namn bearbetar Adobe aldrig datakällfilen.

När både datakällfilen och `.fin` filen överförs till FTP-platsen, Adobe bearbetar filen. Överför inte `.fin` tills datakällfilen har överförts helt. Om `.fin` filen överförs för tidigt, Adobe hämtar och importerar den delvis överförda filen, vilket genererar möjliga fel.

## Behandlingsorder

Om du överför flera filer samtidigt till FTP-platsen, infogar Adobe dem i alfanumerisk ordning. Om din organisation kräver att filerna ska importeras i en viss ordning måste du se till att deras filnamn får ett alfanumeriskt namn.

## Bearbetningstid

För att filerna ska behandlas så snabbt som möjligt rekommenderar Adobe att du samlar in metadata på en rad per datum. Den här datakällfilen skulle till exempel bearbetas långsammare om den var giltig:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | | `1` | |
| `07/24/YYYY` | `red` | | | `1` |

Den här filen bearbetas snabbare och innehåller samma data:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `2` | `1` | `1` |
