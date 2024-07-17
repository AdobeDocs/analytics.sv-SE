---
description: Så här överför du datafiler via FTP.
title: FTP-import
feature: Classifications
exl-id: 3e93b35c-6f65-4a93-887d-d94e4d359bdc
source-git-commit: 95767d10f63e20d5943fa95be3f2fe8f88e67e97
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 0%

---

# FTP-import

>[!IMPORTANT]
>
>Vi rekommenderar inte längre att du använder FTP för import enligt beskrivningen på den här sidan.
>
>FTP rekommenderas inte eftersom det är en okrypterad metod för att dela filer, vilket innebär att alla kan fånga upp filinnehållet samt användarnamnet och lösenordet som används för kontot.
>
>Konfigurera i stället ett molnkonto enligt beskrivningen i [Konfigurera molnimport- och exportkonton](/help/components/locations/configure-import-accounts.md).

Steg som beskriver hur du överför datafiler via FTP.

## FTP-import {#concept_2F965BE873254546A61FB755F25299FD}

Så här överför du datafiler via FTP:

1. **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

Följande rekommenderade gränser är viktiga.

>[!IMPORTANT]
>
>För många små filer eller enstaka stora filer kan ge onödig processorbelastning på bearbetningsservrar. Adobe rekommenderar att du delar upp stora filer i 50 MB-bitar och kombinerar små filer.

Den första konfigurationen fyller i klassificeringsdatabasen med en stor uppsättning ursprungliga data, eller omstrukturerar klassificeringarna i stället för att klassificera om några rader eller lägga till rader.

Efter en inledande överföring i en rapportserie (för en viss variabel eller rapport) rekommenderar Adobe att du bara överför nya och uppdaterade rader i efterföljande importer. Rader som inte ändras ska utelämnas från framtida överföringar.

Varje nytt nyckelvärde som du överför räknas mot dina unika värden för den variabeln för månaden.

Om du har överskridit dina unika värden för månaden visas inte motsvarande klassificeringsdata för de unika värdena i rapporten. Dessa klassificeringar visas i Data Warehouse.

>[!NOTE]
>
>Den tid som krävs för att bearbeta en klassificeringsdatafil varierar beroende på filens storlek och det aktuella antalet filer som redan bearbetas av Adobe-servrar. Bearbetningen av datafiler tar vanligtvis inte längre tid än 72 timmar.

## Skapa ett FTP-konto

Skapa ett FTP-konto innan du överför data via FTP. >

Mer information om FTP-servrar i Adobe finns i [FTP och sFTP](/help/export/ftp-and-sftp/ftp-overview.md).

1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Klicka på **[!UICONTROL Import File]** och sedan på **[!UICONTROL FTP Import]**.
1. Klicka på **[!UICONTROL Add New]** på fliken **[!UICONTROL Import File]**.
1. Ange information om FTP-kontot:

   | Element | Beskrivning |
   |---|---|
   | **Namn** | FTP-kontonamnet. |
   | **Datauppsättning som ska klassificeras** | I listrutan väljer du den datauppsättning (variabel för marknadsföringsrapport) som du vill klassificera. |
   | **Välj rapportsviter** | Välj de rapportsviter där du vill klassificera den markerade datauppsättningen. Om du vill välja flera rapportsviter måste klassificeringarna för var och en av de valda rapportsviterna vara identiska. |
   | **Skriv över data i konflikter** | Välj det här alternativet om du vill skriva över duplicerade data. Det här alternativet är användbart om du uppdaterar befintliga klassificeringar. Om du använder den [senaste klassificeringsarkitekturen](../sets/overview.md) är den här inställningen alltid aktiverad. |
   | **När importen är klar** | Välj det här alternativet om du automatiskt vill exportera den uppdaterade datauppsättningen till samma FTP-konto när du har angett den e-postadress som ska ta emot meddelanden om det här FTP-kontot när importen är klar. Om du använder den [senaste klassificeringsarkitekturen](../sets/overview.md) är det här alternativet inte tillgängligt. |
   | **Meddelandemottagare** | Ange den e-postadress som ska ta emot meddelanden om det här FTP-kontot. |
   | **Auktorisera** | (Obligatoriskt) Adobe tillåts att automatiskt importera alla datafiler som skickas till det nya FTP-kontot. |

1. Klicka på **[!UICONTROL Save]**.

När du har skapat ett FTP-konto kan du redigera eller ta bort det genom att klicka på lämplig länk bredvid det önskade FTP-kontot.

>[!NOTE]
>
>Meddelanden skickas inte om en import inte medför några ändringar i en klassificering. Ett e-postmeddelande skickas bara om det lyckas och leder till ändringar i en klassificering.

## Importera klassificeringar via FTP

Du kan använda ett FTP-konto för att importera klassificeringar till Adobe Analytics.

Så här importerar du klassificeringar via FTP:

1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Klicka på **[!UICONTROL Import File]** och sedan på **[!UICONTROL FTP Import]**.
1. Klicka på **[!UICONTROL View]** bredvid det FTP-konto som du vill använda.
1. Använd FTP-åtkomstinformationen (värd, inloggning, lösenord) för att komma åt FTP-servern via en valfri FTP-klient.
1. Överför datafilen ( `.tab` eller `.txt`) till FTP-servern.
1. När du har överfört datafilen överför du en FIN-fil som anger att filen är klar att bearbetas.

   FIN-filen är en tom fil med samma namn som datafilen, med filnamnstillägget `.fin`. Om din datafil till exempel är `classdata1.tab` är FIN-filnamnet `classdata1.fin`.

Med jämna mellanrum hämtar Adobe överförda datafiler som har en associerad FIN-fil. Adobe importerar dem till de rapportsviter och datauppsättningar som anges i FTP-kontokonfigurationen.

När Adobe Analytics har läst och bearbetat filer som överförts till FTP-mappen tas filerna automatiskt bort från FTP-platsen.
