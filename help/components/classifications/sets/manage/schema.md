---
title: Schema för klassificeringsuppsättning
description: Lär dig hur du visar och redigerar schemat för en enskild klassificeringsuppsättning.
exl-id: 4a7c5bfe-ff2b-4380-af46-435801d73c1e
feature: Classifications
source-git-commit: cfa8335008548254786e46dfe634229edad5bd54
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 0%

---

# Schema för klassificeringsuppsättning

Schemat är den lista med klassificeringar som du vill tillämpa på de nyckeldimensioner som du har definierat för klassificeringsuppsättningen. Om du t.ex. har definierat produkten som nyckeldimension och det här fältet innehåller en produkt-SKU, använder du schemat för att lägga till klassificeringar som produktnamn, produktfärg, produktstorlek med mera.

Så här redigerar du schemat för en klassificeringsuppsättning:


1. Välj **[!UICONTROL Components]** i Adobe Analytics övre menyrad och välj sedan **[!UICONTROL Classification sets]**.
1. I **[!UICONTROL Classification Sets]** väljer du fliken **[!UICONTROL Classification Sets]**.
1. I hanteraren för **[!UICONTROL Classifications Sets]** väljer du den klassificeringsgrupp som du vill redigera schemat för.
1. Välj fliken **[!UICONTROL Classification Set: _i dialogrutan_]** klassificeringsuppsättningsnamn **[!UICONTROL Schema]**. Fliken består av följande gränssnittselement:

   ![Klassificeringsuppsättningar - schema](assets/classification-sets-schema.png)

   * [Klassificeringslista](#classification-list)
   * [Sök](#search)
   * [Åtgärder](#actions)
   * [Åtgärdsfält](#action-bar)

## Klassificeringslista

Listan med klassificeringar har följande kolumner:

| Kolumn | Beskrivning |
|---|---|
| **[!UICONTROL Classification Name]** | Namnet som du angav för klassificeringen. |
| **[!UICONTROL Identity Name]** | Det härledda namnet av systemet för klassificeringen. Det här namnet är ett skrivskyddat värde och du kan använda identitetsnamnet |
| **[!UICONTROL Classified By]** | Om det används, en länk till den uppslagsklassificeringsuppsättning som används för att klassificera den här klassificeringen. |


## Sök

Du kan snabbt söka i ![Sök](/help/assets/icons/Search.svg) efter en eller flera klassificeringar. Använd ![CrossSize100](/help/assets/icons/CrossSize100.svg) för att rensa sökningen.

## Åtgärder

Följande åtgärder är tillgängliga som knappar högst upp i klassificeringslistan:

| Ikon | Åtgärd | Beskrivning |
|---|---|---|
| ![Lägg till](/help/assets/icons/Add.svg) | **[!UICONTROL Add]** | [Lägg till en klassificering](#add) i listan. |
| ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) | **[!UICONTROL Upload]** | [Överför en JSON-, CSV-, TSV- eller TAB-fil](#upload). |
| ![Hämta](/help/assets/icons/Download.svg) | **[!UICONTROL Download]** | [Hämta klassificeringsdata](#download). |
| ![Dokumentfragment](/help/assets/icons/DocumentFragment.svg) | **[!UICONTROL Template]** | [Hämta en mall](#template) för klassificeringsdata. |
| ![Historik](/help/assets/icons/History.svg) | **[!UICONTROL Job History]** | Visa jobbhanteraren [&#x200B; för klassificeringsuppsättningen, filtrerad för den valda klassificeringsuppsättningen.](/help/components/classifications/sets/job-manager.md) |
| ![Kugghjul](/help/assets/icons/Gear.svg) | **[!UICONTROL Automate]** | [Automatisera inmatningen av klassificeringsdata](#automate) med hjälp av en molnplats. |


### Lägg till

Om du vill lägga till en ny klassificering väljer du ![Lägg till](/help/assets/icons/Add.svg) **[!UICONTROL Add]**.

![Klassificeringsuppsättningar - Lägg till klassificering i schema](assets/classification-sets-schema-add-classification.png)

Ange **[!UICONTROL Add a new classification for _och välj_]** i dialogrutan **[!UICONTROL Classification Name]** klassificeringsuppsättningsnamn **[!UICONTROL Add]**. Klassificeringen läggs till i listan.



### Överför

Om du vill importera klassificeringsdata till schemat för en klassificering väljer du ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) **[!UICONTROL Upload]**.


![Klassificeringsuppsättningar - Schema överför en fil](assets/classification-sets-schema-upload-file.png)

1. I dialogrutan **[!UICONTROL Add new classifications]**:

   * Dra en fil som innehåller klassificeringsdata och släpp filen på **[!UICONTROL Drag and drop here]**.
   * Välj **[!UICONTROL Browse]** och välj en fil på datorn eller i nätverket.

   En **[!UICONTROL Schema Preview]** av filens innehåll visas. I förhandsgranskningen visas kolumnerna med data från filen. Om du vill ändra storlek på en kolumn väljer du ![SparrronDownSize300](/help/assets/icons2/ChevronDownSize300.svg) och väljer **[!UICONTROL Resize column]**. Ett handtag som gör att du kan ändra storlek på kolumnen visas.

   När ingen klassificering har definierats i klassificeringsuppsättningen för en kolumn visas en varning ![Alert](/help/assets/icons/Alert.svg). Varningen förklarar att det inte finns någon klassificering i den befintliga klassificeringsschemamängden och att den skapas vid importen.

1. Välj **[!UICONTROL Overwrite data on conflict?]** om du vill skriva över aktuella klassificeringsdata med de nya importerade. Exempel:

   | | Nyckel | Aktuell färg | Importera fil | Ny produktfärg |
   |---|---|---|---|---|
   | ![SelectBox](/help/assets/icons/SelectBox.svg) **[!UICONTROL Overwrite data on conflict?]** | 1234 | grön | blå | blå |
   | ![Fyrkant](/help/assets/icons2/Square.svg) **[!UICONTROL Overwrite data on conflict?]** | 1234 | grön | blå | grön |

1. Välj **[!UICONTROL Apply]**. En varning visas om det inte finns några kolumner som klassificeringar i den befintliga schemamängden. Dessa kolumner läggs till som nya klassificeringar när du bekräftar överföringen.

   ![Klassificeringsuppsättning - Överför klassificeringsvarning](assets/classification-sets-schema-upload-file-preview-alert.png)

   Välj **[!UICONTROL Confirm Upload]** för att bekräfta överföringen. Välj **[!UICONTROL Cancel Upload]** om du vill avbryta överföringen.


### Ladda ned

Om du vill hämta klassificeringsdata väljer du ![Hämta](/help/assets/icons/Download.svg) **[!UICONTROL Download]**.

![Klassificeringsuppsättningar - Schema hämtar klassificeringsdata](assets/classification-sets-schema-download-file.png)

I dialogrutan **[!UICONTROL Download data for _klassificeringsuppsättningsnamn_]**:

1. Ange antalet **[!UICONTROL Rows]** som du vill hämta. Till exempel: `10000`.
1. Ange start- och slutdata för **[!UICONTROL Download Rows Received Between]** om du vill välja den period som du vill hämta rader med klassificeringsdata för. Du kan också använda ![Kalender](/help/assets/icons/Calendar.svg) om du vill använda en kalender-popup för att markera perioden.
1. Välj ett alternativ från **[!UICONTROL Data Returned]** om du vill välja vilka data som ska returneras.

   * **[!UICONTROL All values]** returnerar alla värden för aktuella klassificeringsdata.
   * **[!UICONTROL Any columns empty]** returnerar en kolumn med nyckelvärden för befintliga klassificeringsdata. Och kolumner utan värde för klassificeringsdata som saknar värden.
   * **[!UICONTROL All columns empty]** returnerar en nyckelkolumn med värden för befintliga klassificeringsdata. Och kolumner utan värde för klassificeringsdata.
1. Om du vill välja [filformat](/help/components/classifications/sets/data-files.md#general-file-requirements) för de hämtade klassificeringsdata väljer du ett alternativ i listrutan **[!UICONTROL File Format]** . Alternativ:

   * **[!UICONTROL JSON]**.
   * **[!UICONTROL Comma separated values]** (CSV).
   * **[!UICONTROL Excel tab separated values]** (TSV eller TAB).

1. Om du vill välja [filkodning](/help/components/classifications/sets/data-files.md#general-file-requirements) när filen hämtas väljer du ett alternativ i listrutan Filkodning. Alternativ:

   * **[!UICONTROL UTF-8]**.
   * **[!UICONTROL Latin-1]**.


1. Välj **[!UICONTROL Download]** om du vill hämta klassificeringsdata. Du hittar den hämtade filen i webbläsarens standardkatalog för hämtning, och filen heter <code><i>Klassificeringsuppsättning</i>.<i>json</i>|<i>csv</i>|<i>tsv</i></code>. Om filen redan finns, sekvensnummer <code>(<i>x</i>)</code> läggs till i filnamnet.<br/>Om du har angett alternativ som inte returnerar några data visas en **[!UICONTROL Notice]**-dialogruta där du kan ange alternativ för datumintervall och returnerade data.


### Mall

Om du vill hämta en mall för klassificeringsdata väljer du ![DocumentFragment](/help/assets/icons/DocumentFragment.svg) **[!UICONTROL Template]**.

![Schema för klassificeringsuppsättningar - Hämta mall](assets/classification-sets-schema-download-template.png)

I dialogrutan **[!UICONTROL Download template for _klassificeringsuppsättningsnamn_]**:

1. Om du vill välja [filformat](/help/components/classifications/sets/data-files.md#general-file-requirements) för de hämtade klassificeringsdata väljer du ett alternativ i listrutan **[!UICONTROL File Format]** . Alternativ:

   * **[!UICONTROL Comma separated values]**.
   * **[!UICONTROL Excel tab separated values]**.

1. Om du vill välja [filkodning](/help/components/classifications/sets/data-files.md#general-file-requirements) när filen hämtas väljer du ett alternativ i listrutan Filkodning. Alternativ:

   * **[!UICONTROL UTF-8]**.
   * **[!UICONTROL Latin-1]**.

1. Välj **[!UICONTROL Download]** om du vill hämta klassificeringsdatamallen. Du hittar den hämtade filen i webbläsarens standardkatalog för hämtning och den heter <code><i>Klassificeringsuppsättning</i>.<i>csv</i>|<i>tsv</i></code>. Om filen redan finns, sekvensnummer <code>(<i>x</i>)</code> läggs till i filnamnet.


### Automatisera {#automate}


>[!CONTEXTUALHELP]
>id="classificationsets_schema_automate_locationaccount"
>title="Platskonto"
>abstract="Lista över platskonton för kontotyper som stöder import av klassificeringsdata. Välj **[!UICONTROL New account]** om du vill skapa ett nytt platskonto."
>additional-url="https://experienceleague.adobe.com/docs/analytics/components/locations/configure-import-accounts.html?lang=sv-SE" text="Konfigurera molnimport- och exportkonton"


>[!CONTEXTUALHELP]
>id="classificationsets_schema_automate_location"
>title="Plats"
>abstract="Lista över platser på det valda platskontot som stöder import av klassificeringsdata. Välj **[!UICONTROL New location]** om du vill skapa en ny plats."
>additional-url="https://experienceleague.adobe.com/docs/analytics/components/locations/configure-import-locations.html?lang=sv-SE" text="Konfigurera platser för molnimport och -export"


Om du vill automatisera intaget av klassificering väljer du ![Kugghjul](/help/assets/icons/Gear.svg) **[!UICONTROL Automate]**.

![Schema för klassificeringsuppsättningar - Automatisera](assets/classification-sets-schema-automate.png)

I dialogrutan **[!UICONTROL Associate / Update Ingest Location for _klassificeringsuppsättningsnamn_]**:

1. Välj en molnplats genom att välja ett alternativ från **[!UICONTROL Location Account]**. Endast [platskonton för kontotyper som stöds som tillåter import av klassificeringsdata](https://experienceleague.adobe.com/sv/docs/analytics/components/locations/configure-import-accounts) visas. Välj **[!UICONTROL New account]** om du vill skapa ett nytt konto.
1. Välj en plats genom att välja ett alternativ från **[!UICONTROL Location]**. Endast platserna för valda kontotyper för import av klassificeringsdata visas. Välj **[!UICONTROL New location]** om du vill skapa en ny plats.

   >[!IMPORTANT]
   >
   >Platsen som du skapar eller väljer bör innehålla en **[!UICONTROL Prefix]** (mapp) i **[!UICONTROL Bucket]** som värd för klassificeringsdatafilerna. En mapp med namnet `files`. De flesta molnplatser fungerar inte med värdfiler som finns i roten av en bucket.
   >

1. Om du vill välja en avgränsare väljer du ett alternativ i listrutan **[!UICONTROL List delimiter]**. Alternativen är:
   * **[!UICONTROL Comma ,]**
   * **[!UICONTROL Semicolon ;]**
   * **[!UICONTROL Colon :]**
   * **[!UICONTROL Vertical bar |]**
   * **[!UICONTROL Space]**
   * **[!UICONTROL Tab]**
1. Om du vill välja [filkodningen](/help/components/classifications/sets/data-files.md#general-file-requirements) när filen hämtas väljer du ett alternativ i listrutan **[!UICONTROL File Encoding]** . Alternativ:

   * **[!UICONTROL UTF-8]**.
   * **[!UICONTROL Latin-1]**.

1. Om du vill meddela användare om slutförandet av importen anger du e-postadresser, avgränsade med kommatecken, för **[!UICONTROL Email(s) to notify when ingest jobs completes (comma separated)]**.
1. Välj **[!UICONTROL Validate]**. Anslutningen till molnplatsen verifieras.
1. Om valideringen lyckas visas ett popup-meddelande som visar ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Location validation successful. Connection to cloud storage verified.]**<br/>Välj **[!UICONTROL Save]**&#x200B;om du har skapat anslutningen till molnanslutningen. Annars väljer du **[!UICONTROL Update]**. Eller välj **[!UICONTROL Cancel]**&#x200B;om du vill avbryta konfigurationen av molnplatsen.

När du överför filer till molnplatsen identifieras filen och skickas som ett importjobb inom 15 minuter. Resultatet av det importjobbet rapporteras i jobbhanteraren [för klassificeringar](/help/components/classifications/sets/job-manager.md). Om du har lagts till i listan över användare för att meddela att importen har slutförts, får du även e-postmeddelanden.

Exempel:

![Klassificeringsuppsättningar - e-post för jobbvalidering](assets/job-failed-validation.png){width="400"}


## Åtgärdsfält

Åtgärdsfältet visar åtgärder som är tillgängliga för den valda klassificeringen. Tillgängliga alternativ är:

| Ikon | Åtgärd | Beskrivning |
|---|---|---|
| ![Bläddra](/help/assets/icons/Browse.svg) | **[!UICONTROL Add Lookup]** | Lägg till en klassificeringsuppsättning som en sökning (underklassificering).<br/>I tabellen **[!UICONTROL Attach lookup]**: <ol><li>Välj en uppslagsklassificering i listrutan **[!UICONTROL Classification Name]**.</li><li>Välj **[!UICONTROL Add]**.</li></ol>Uppslagsklassificeringen läggs till i klassificeringen och listas i kolumnen **[!UICONTROL Classified by]** med hjälp av det interna ID:t. |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | **[!UICONTROL Remove Lookup]** | Ta bort en klassificeringsuppsättning som en sökning. Om du vill ta bort sökningen permanent från klassificeringen väljer du **[!UICONTROL Remove _i bekräftelsedialogrutan för _klassificeringsuppsättningen_ från_]** klassificeringen **[!UICONTROL Delete]**. |
| ![Byt namn](/help/assets/icons/Rename.svg) | **[!UICONTROL Rename]** | Byt namn på **[!UICONTROL Classification Name]** för en klassificering. I dialogrutan **[!UICONTROL Rename: _klassificeringsnamn_]** anger du ett nytt namn och väljer **[!UICONTROL Rename]**. |
| ![Ta bort](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Ta bort en klassificering. Dialogrutan **[!UICONTROL Delete _Klassificeringsnamn_]** visas. Välj **[!UICONTROL Delete]** om du vill ta bort klassificeringen. |
