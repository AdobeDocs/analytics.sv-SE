---
description: Steg som beskriver hur du överför datafiler via FTP.
subtopic: Classifications
title: FTP-import
topic: Admin tools
uuid: a914970d-ba02-4111-9dcf-06448f71b9f3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

Efter en första överföring i en rapportserie (för en viss variabel eller rapport) rekommenderar Adobe att du bara överför nya och uppdaterade rader i efterföljande importer. Rader som inte ändras ska utelämnas från framtida överföringar.

Varje nytt nyckelvärde som du överför räknas mot dina unika värden för den variabeln för månaden.

Om du har överskridit dina unika värden för månaden visas inte motsvarande klassificeringsdata för de unika värdena i rapporten. Du kan se dessa klassificeringar antingen i datalagret eller i ad hoc-analyser.

> [!NOTE] Den tid som krävs för att bearbeta en klassificeringsdatafil varierar beroende på filens storlek och det aktuella antalet filer som redan bearbetas av Adobes servrar. Bearbetningen av datafiler tar vanligtvis inte längre tid än 72 timmar.

Skapa ett FTP-konto innan du överför data via FTP. Mer information finns i [Skapa ett FTP-konto](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

## Importera klassificeringar via FTP {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

Steg som beskriver hur du använder ett FTP-konto för att importera klassificeringar till Adobe Analytics.

Mer information om hur du skapar ett FTP-konto finns i [Skapa ett FTP-konto](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Klicka **[!UICONTROL Import File]** och sedan på **[!UICONTROL FTP Import]**.
1. Klicka på bredvid det FTP-konto som du vill använda **[!UICONTROL View]**.
1. Använd FTP-åtkomstinformationen (värd, inloggning, lösenord) för att komma åt FTP-servern via en valfri FTP-klient.
1. Överför datafilen ( [!DNL .tab] eller [!DNL .txt]) till FTP-servern.
1. När du har överfört datafilen överför du en FIN-fil som anger att filen är klar att bearbetas.

   FIN-filen är en tom fil med samma namn som datafilen, med ett [!DNL .fin] filnamnstillägg. Om datafilen till exempel är [!DNL classdata1.tab]FIN-filens namn är [!DNL classdata1.fin].

Med jämna mellanrum hämtar Adobe överförda datafiler som har en associerad FIN-fil. Adobe importerar dem till de rapportsviter och datauppsättningar som anges i FTP-kontokonfigurationen.

## Skapa ett FTP-konto {#task_C019268E6C934C7C95F4326F42A22CCF}

Skapa ett FTP-konto innan du överför data via FTP. >

<!-- 

t_create_an_ftp_account.xml

 -->

Mer information om Adobes FTP-servrar finns i [FTP och sFTP](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/) .

1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Klicka **[!UICONTROL Import File]** och sedan på **[!UICONTROL FTP Import]**.
1. On the **[!UICONTROL Import File]** tab, click **[!UICONTROL Add New]**.
1. Ange information om FTP-kontot:

   | Element | Beskrivning |
   |---|---|
   | Namn | FTP-kontonamnet. |
   | Datauppsättning som ska klassificeras | I listrutan väljer du den datauppsättning (variabel för marknadsföringsrapport) som du vill klassificera. |
   | Välj rapportsviter | Välj de rapportsviter där du vill klassificera den markerade datauppsättningen. Om du vill välja flera rapportsviter måste klassificeringarna för var och en av de valda rapportsviterna vara identiska. |
   | Skriv över data i konflikter | Välj det här alternativet om du vill skriva över duplicerade data. Det här alternativet är användbart om du uppdaterar befintliga klassificeringar. Om du lägger till ytterligare klassificeringar rekommenderas inte det här alternativet. |
   | När importen är klar | Välj det här alternativet om du automatiskt vill exportera den uppdaterade datauppsättningen till samma FTP-konto när du har angett den e-postadress som ska ta emot meddelanden om det här FTP-kontot när importen är klar. |
   | Meddelandemottagare | Ange den e-postadress som ska ta emot meddelanden om det här FTP-kontot. |
   | Auktorisera | (Obligatoriskt) Adobe kan automatiskt importera alla datafiler som skickas till det nya FTP-kontot. |

1. Klicka på **[!UICONTROL Save]**.

När du har skapat ett FTP-konto kan du redigera eller ta bort det genom att klicka på lämplig länk bredvid det önskade FTP-kontot.
