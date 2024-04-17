---
description: Konfigurera molnimportkontot och platsen där klassificeringsdata kan överföras
keywords: Analysis Workspace
title: Platshanteraren
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: 7b293c962428c7b8fac62a9f70ce62a0fe8f0cea
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# Platshanteraren

Med Platshanteraren kan du visa, skapa, redigera och ta bort konton och platser. De kan användas för något av följande ändamål:

* Exportera filer med [Dataflöden](/help/export/analytics-data-feed/create-feed.md)
* Exportera rapporter med [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importera scheman med [Klassificeringsuppsättningar](/help/components/classifications/sets/overview.md)

## Visa, filtrera och söka efter platser

Med Platshanteraren kan du visa alla platser som du har skapat. Systemadministratörer kan visa platser som skapats av alla användare.

1. Om du vill komma åt Platshanteraren i Adobe Analytics väljer du **[!UICONTROL Components]** > **[!UICONTROL Locations]**.

1. (Villkorligt) Om du är systemadministratör kan du aktivera [!UICONTROL **Visa platser för alla användare**] om du vill visa platser som har skapats av alla användare i organisationen. <!-- Maybe add a screenshot? This is new functionality -->

1. Filtrera eller sök i listan över platser:

   * **Filter:** Välj ikonen Filter om du vill filtrera listan över platser.

     Du kan filtrera platser efter **[!UICONTROL Location Type]**, **[!UICONTROL Account]**, eller **[!UICONTROL Created By]**.

     ![Platsfilter](assets/locations-filters.png)

   * **Sök:** I sökfältet börjar du skriva namnet på den plats du vill visa. Resultaten filtreras när du skriver. Följande kolumner genomsöks: **Platsnamn**, **Platstyp**, **Konto** och **Skapad av**.

1. (Valfritt) Om du har fler än 1 000 platser är det bara den första 1 000-skärmen som visas. Välj [!UICONTROL **Läs mer**] för att läsa in ytterligare 1 000 platser.

## Konfigurera kolumner i Platshanteraren

Följande kolumner är tillgängliga i Platshanteraren. Om du vill anpassa kolumnerna som visas i tabellen väljer du **Anpassa tabell** icon ![Anpassa tabellikon](assets/customize-table-icon.png).

* **[!UICONTROL Location name]**: Platsnamnet. Välj menyn med tre punkter bredvid ett platsnamn till antingen [redigera platsen](/help/components/locations/configure-import-locations.md) eller ta bort den.
* **[!UICONTROL Location type]**: Den kontotyp som är associerad med platsen.
* **[!UICONTROL Account]**: Det specifika konto som är associerat med platsen.
* **Program**: Den typ av program som platsen kan användas med (till exempel datafeeds, Data Warehouse eller Klassificeringsuppsättningar).
* **[!UICONTROL Last used]**: Det datum då platsen senast användes.
* **[!UICONTROL Created by]**: Den användare som skapade platsen.
* **[!UICONTROL Date created]**: Det datum då platsen skapades.

## Skapa och hantera platser

Du kan skapa, redigera och ta bort platser.

### Skapa en plats

Mer information om hur du skapar en plats finns i [Konfigurera platser för molnimport och -export](/help/components/locations/configure-import-locations.md).

<!-- Do I need to add some steps here about how to create a location and then assign that location to be used with DF, DW, or Classifications sets? Need to hear back from Ron and team whether we are including this functionality -->

### Redigera en plats

Mer information om hur du redigerar en plats finns i [Konfigurera platser för molnimport och -export](/help/components/locations/configure-import-locations.md).

### Ta bort en plats

>[!IMPORTANT]
>
>Om en plats tas bort kommer dataflödesfiler, Data Warehouse- eller klassificeringsscheman som är associerade med den borttagna platsen inte att fungera nästa gång de används.
>
>Om du tar bort en plats bör du [redigera dina dataflöden](/help/export/analytics-data-feed/create-feed.md), [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)och [Klassificeringsuppsättningar - scheman](/help/components/classifications/sets/manage/schema.md) för att använda en fungerande plats.

Så här tar du bort en plats:

1. Välj menyn med tre punkter i dialogrutan [!UICONTROL **Platsnamn**] kolumn för den plats som du vill ta bort.

1. Välj [!UICONTROL **Ta bort**].

## Redigera konton

1. Om du vill redigera konton i Platshanteraren i Adobe Analytics väljer du **[!UICONTROL Components]** > **[!UICONTROL Locations]** väljer du [!UICONTROL **Platskonton**] -fliken.

1. (Villkorligt) Om du är systemadministratör kan du aktivera [!UICONTROL **Visa konton för alla användare**] om du vill visa platser som har skapats av alla användare i organisationen. <!-- Maybe add a screenshot? This is new functionality -->


1. Välj [!UICONTROL **Visa detaljer**] på kontot som du vill redigera.

1. Gör önskade ändringar och välj sedan [!UICONTROL **Spara**].

## Visa kontonycklar

När du har skapat ett konto kan du visa alla associerade kontonycklar för det kontot. Du kan behöva visa den här informationen om du inte har slutfört konfigurationen av kontot med din molnleverantör när du [konfigurerade kontot från början](/help/components/locations/configure-import-accounts.md).

Så här visar du nycklar som är kopplade till ett exportkonto:

1. I Adobe Analytics: **[!UICONTROL Components]** > **[!UICONTROL Locations]** väljer du [!UICONTROL **Platskonton**] -fliken.

1. Markera ikonen med tre punkter på det konto som du vill redigera och välj sedan [!UICONTROL **Kontonycklar**].

## Ta bort konton

1. I Adobe Analytics: **[!UICONTROL Components]** > **[!UICONTROL Locations]** väljer du [!UICONTROL **Platskonton**] -fliken.

1. Markera ikonen med tre punkter på det konto som du vill redigera och välj sedan [!UICONTROL **Ta bort konto**]
