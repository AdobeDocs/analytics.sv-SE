---
description: Läs mer om Report Builder Frågor och svar.
title: Vanliga frågor om Report Builder
feature: Report Builder
role: User, Admin
exl-id: 86604d39-2965-45a5-98ab-3ee4adcb7f97
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 0%

---

# REPORT BUILDER FAQ

{{legacy-arb}}

Frågor och svar om Report Builder.

## Kan jag använda funktionen `TODAY()` eller `DATERANGE()` i arbetsböcker? {#today}

[`TODAY()`-funktionen ](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) i Excel returnerar den aktuella dagen. [`DATEVALUE()`-funktionen ](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) konverterar en datumsträng till ett serievärde. Adobe rekommenderar att du inte använder dessa funktioner som en del av Report Builder schemalagda begäranden, men är till stor hjälp för många funktioner i Excel. Adobe kundtjänst stöder inte felsökningsförfrågningar med någon av dessa funktioner.

Schemalagda rapporter bearbetas på servrar som troligen inte delar tidszoner som rapportsviten. De `TODAY()` som en användare förväntar sig och de `TODAY()` som bearbetningsservern använder kan ofta vara olika. Det datum som används baseras dessutom på när bearbetningen startar. Om många rapporter körs samtidigt kan datumet ändras mellan den tidpunkt då det begärs och den tidpunkt då bearbetningen startar på grund av förseningar. Problemet uppstår om den schemalagda tiden är nära midnatt.

Schemalagda rapporter bearbetas även på servrar som troligtvis inte har samma datumsyntax. `7/1/YYYY` kan till exempel hänvisa till 1 juli eller 7 januari beroende på ditt land eller din region. Om du använder funktionen `DATEVALUE()` på det här datumet kan serievärdena variera beroende på vilken dator som kör den.

Adobe rekommenderar att du använder datumintervall i Report Builder-begäranden som ett alternativ till de här Excel-funktionerna. Välj **[!UICONTROL Preset Dates]** i listrutan på den första sidan i begärandeguiden och välj sedan **[!UICONTROL Today]** eller ett annat önskat datumintervall under Vanligt använda datum. Den här inställningen används vid körningen av rapportsviten och inte vid tidpunkten för serverbearbetningen av begäran.

## Hur stora och komplexa kan jag göra mina arbetsböcker? {#complexity}

Report Builder stöder arbetsböcker upp till följande begränsningar:

* **1000 förfrågningar**: En enskild arbetsbok kan innehålla upp till 1000 dataförfrågningar. Om du har rapporter eller projekt som kräver mer än 1 000 förfrågningar rekommenderar Adobe att du delar upp dem i flera arbetsböcker.
* **20K-begäranden per timme per företag**: Report Builder använder API:t för analysrapportering för att hämta data. Varje enskild begäran använder ett API-anrop när den skapas eller uppdateras. Om din organisation samlar in fler än 20 000 API-anrop inom en given timme måste du vänta tills nästa timme för att hämta data igen.
* **4-timmars bearbetningstid**: Schemalagd rapporterar timeout efter bearbetning i mer än 4 timmar. Om arbetsboken innehåller många komplexa begäranden som använder stora datauppsättningar kan den schemalagda rapporten misslyckas.

## Hur vet jag om jag har tillgång till Report Builder? {#access}

Du måste beviljas Report Builder-åtkomst av din Adobe Analytics-administratör. Admin ställer in produktprofiler i [Adobe Admin Console](/help/admin/admin-console/home.md). Be din administratör att ge dig åtkomst.
