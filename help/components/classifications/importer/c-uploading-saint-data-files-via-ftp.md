---
description: Så här överför du datafiler via FTP.
title: FTP-import
feature: Classifications
exl-id: 3e93b35c-6f65-4a93-887d-d94e4d359bdc
source-git-commit: 5edf3e6684b3572616f76db3f7c3bf0cf58ed408
workflow-type: tm+mt
source-wordcount: '712'
ht-degree: 1%

---

# FTP-import

Steg som beskriver hur du överför datafiler via FTP.

## FTP-import {#concept_2F965BE873254546A61FB755F25299FD}

Steg som beskriver hur du överför datafiler via FTP.

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

Följande rekommenderade gränsvärden är viktiga:

* Många små filer tar längre tid att bearbeta än ett fåtal stora filer. Detta beror på mängden köer och prioritering som krävs för de mindre jobben.
* Dela upp stora filer i 50 MB-segment. Detta är inte nödvändigt, men rekommenderas eftersom det ger bättre synlighet i bakänden. Om fel inträffar medan vi bearbetar ditt jobb kommer jobbet att startas om; stora filer resulterar i stora mängder arbete som behöver göras om i det här scenariot.

Den första konfigurationen fyller i klassificeringsdatabasen med en stor uppsättning ursprungliga data, eller omstrukturerar klassificeringarna i stället för att klassificera om några rader eller lägga till rader.

Efter en inledande överföring i en rapportserie (för en viss variabel eller rapport) rekommenderar Adobe att du bara överför nya och uppdaterade rader i efterföljande importer. Rader som inte ändras ska utelämnas från framtida överföringar.

Varje nytt nyckelvärde som du överför räknas mot dina unika värden för den variabeln för månaden.

Om du har överskridit dina unika värden för månaden visas inte motsvarande klassificeringsdata för de unika värdena i rapporten. Du kan se klassificeringarna i Data warehouse.

>[!NOTE]
>
>Den tid som krävs för att bearbeta en klassificeringsdatafil varierar beroende på filens storlek och det aktuella antalet filer som redan bearbetas av Adobe-servrar. Bearbetningen av datafiler tar vanligtvis inte längre tid än 72 timmar.

Skapa ett FTP-konto innan du överför data via FTP. Mer information finns i [Skapa ett FTP-konto](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

## Importera klassificeringar via FTP {#task_132C36830B69418B8C929E39838EF01D}

Steg som beskriver hur du använder ett FTP-konto för att importera klassificeringar till Adobe Analytics.

Mer information om hur du skapar ett FTP-konto finns i [Skapa ett FTP-konto](/help/components/classifications/importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Klicka **[!UICONTROL Import File]** och sedan klicka **[!UICONTROL FTP Import]**.
1. Bredvid det FTP-konto som du vill använda klickar du på **[!UICONTROL View]**.
1. Använd FTP-åtkomstinformationen (värd, inloggning, lösenord) för att komma åt FTP-servern via en valfri FTP-klient.
1. Överför datafilen ( [!DNL .tab] eller [!DNL .txt]) till FTP-servern.
1. När du har överfört datafilen överför du en FIN-fil som anger att filen är klar att bearbetas.

   FIN-filen är en tom fil som har samma namn som datafilen, med en [!DNL .fin] filnamnstillägg. Om datafilen till exempel är [!DNL classdata1.tab], FIN-filnamnet är [!DNL classdata1.fin].

Med jämna mellanrum hämtar Adobe överförda datafiler som har en associerad FIN-fil. Adobe importerar dem till de rapportsviter och datauppsättningar som anges i FTP-kontokonfigurationen.

När Adobe Analytics har läst och bearbetat filer som överförts till FTP-mappen tas filerna bort automatiskt.

## Skapa ett FTP-konto {#task_C019268E6C934C7C95F4326F42A22CCF}

Skapa ett FTP-konto innan du överför data via FTP. >

Se [FTP och sFTP](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/ftp-overview.html) om du vill ha mer information om FTP-servrar i Adobe.

1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Klicka **[!UICONTROL Import File]** och sedan klicka **[!UICONTROL FTP Import]**.
1. På **[!UICONTROL Import File]** flik, klicka **[!UICONTROL Add New]**.
1. Ange information om FTP-kontot:

   | Element | Beskrivning |
   |---|---|
   | Namn | FTP-kontonamnet. |
   | Datauppsättning som ska klassificeras | I listrutan väljer du den datauppsättning (variabel för marknadsföringsrapport) som du vill klassificera. |
   | Välj rapportsviter | Välj de rapportsviter där du vill klassificera den markerade datauppsättningen. Om du vill välja flera rapportsviter måste klassificeringarna för var och en av de valda rapportsviterna vara identiska. |
   | Skriv över data i konflikter | Välj det här alternativet om du vill skriva över duplicerade data. Det här alternativet är användbart om du uppdaterar befintliga klassificeringar. Om du lägger till ytterligare klassificeringar rekommenderas inte det här alternativet. |
   | När importen är klar | Välj det här alternativet om du automatiskt vill exportera den uppdaterade datauppsättningen till samma FTP-konto när du har angett den e-postadress som ska ta emot meddelanden om det här FTP-kontot när importen är klar. |
   | Meddelandemottagare | Ange den e-postadress som ska ta emot meddelanden om det här FTP-kontot. |
   | Auktorisera | (Obligatoriskt) Adobe tillåts att automatiskt importera alla datafiler som skickas till det nya FTP-kontot. |

1. Klicka på **[!UICONTROL Save]**.

När du har skapat ett FTP-konto kan du redigera eller ta bort det genom att klicka på lämplig länk bredvid det önskade FTP-kontot.

>[!NOTE]
>
>Meddelanden skickas inte om en import inte medför några ändringar i en klassificering. Ett e-postmeddelande skickas bara om det lyckas och leder till ändringar i en klassificering.
