---
title: Schema för klassificeringsuppsättning
description: Visa och redigera schemat för en enskild klassificeringsuppsättning.
exl-id: 0fc12a0c-c1cf-4159-9d8b-492ebcaa8ea1
feature: Classifications
source-git-commit: d21903fe5683cadf2e235f5a1f911e2a62881c58
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# Schema

Visa aktuella konfigurerade klassificeringsdimensioner för den här klassificeringsuppsättningen.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > Klicka på önskat namn > **[!UICONTROL Schema]**

Följande knappar är tillgängliga:

<!--* **[!UICONTROL Add]**: Adds an empty row so that you can add a classification dimension to the schema.-->
* **[!UICONTROL Upload]**: Överför klassificeringsdata manuellt för en eller flera klassificeringsdimensioner. `JSON`, `CSV`, `TSV`och `TAB` filer stöds. När du överför en giltig fil visas en tabellförhandsvisning av data som ska klassificeras.
   * **[!UICONTROL File encoding]**: Välj rätt filkodning i den här listrutan. Giltiga alternativ är [!UICONTROL UTF-8] och [!UICONTROL Latin1].
   * **[!UICONTROL List delimiter]**: Välj rätt listavgränsare. Om du använder en hämtad fil eller mallfil måste du kontrollera att [!UICONTROL List delimiter] här matchar [!UICONTROL List delimiter] när filen hämtades.
   * **[!UICONTROL Apply]**: Spara överförda klassificeringsdata i klassificeringsuppsättningen.

  ![Överföring av klassificeringsuppsättning](../../assets/classification-set-upload.png)

* **[!UICONTROL Download]**: Hämta nyckelvärden och deras klassificeringskolumner.
   * **[!UICONTROL Rows]**: Det maximala antalet rader som ska inkluderas i den hämtade filen.
   * **[!UICONTROL Download rows received between]**: En datumväljare för kalender där du kan filtrera nyckelvärden efter när de visas i rapporter. Om ett nyckelvärde inte samlats in i det här datumintervallet visas det inte i den hämtade filen.
   * **[!UICONTROL Data returned]**: En nedrullningsbar lista där du kan filtrera nyckelvärden som ingår i den hämtade filen baserat på deras associerade klassificeringsdata.
      * **[!UICONTROL All classified values]**: Inkluderar rader där klassificeringsdata ingår i minst en kolumn.
      * **[!UICONTROL All unclassified values]**: Inkluderar rader där klassificeringsdata saknas i minst en kolumn.
   * **[!UICONTROL File format]**: En nedrullningsbar lista som anger i vilket filformat den hämtade filen finns. Alternativen inkluderar [!UICONTROL JSON], [!UICONTROL Comma separated values]och [!UICONTROL Excel tab separated values].
   * **[!UICONTROL File encoding]**: En nedrullningsbar lista som bestämmer filkodningen. Alternativen inkluderar [!UICONTROL UTF-8] och [!UICONTROL Latin1]. UTF-8 rekommenderas.

  ![Hämtning av klassificeringsuppsättning](../../assets/classification-set-download.png)

* **[!UICONTROL Template]**: Hämta en mallfil. Den här filen liknar [!UICONTROL Download] -knappen, förutom att den inte innehåller några klassificeringsdata eller nyckelvärden.
   * **[!UICONTROL File format]**: En nedrullningsbar lista som anger i vilket filformat mallfilen finns. Alternativen inkluderar [!UICONTROL Comma separated values]och [!UICONTROL Excel tab separated values].
   * **[!UICONTROL File encoding]**: En nedrullningsbar lista som bestämmer filkodningen. Alternativen inkluderar [!UICONTROL UTF-8] och [!UICONTROL Latin1]. UTF-8 rekommenderas.
   * **[!UICONTROL List delimiters]**: En nedrullningsbar lista som anger avgränsaren för klassificeringskolumner på varje rad.

  ![Mallen Klassificeringsuppsättning](../../assets/classification-set-template.png)

* **[!UICONTROL Job history]**: En genvägslänk som tar dig till [Jobbhanterare](../job-manager.md), visar endast jobb för den här klassificeringsuppsättningen.
* **[!UICONTROL Automate]**: Importera automatiskt data från externa lagringsplatser.
   * **[!UICONTROL Location account]**: En listruta med befintliga platskonton som din organisation har konfigurerat. Om din organisation inte redan har konfigurerat ett platskonto kan du konfigurera ett genom att välja [!UICONTROL **Skapa ett nytt konto**].

     Mer information om hur du konfigurerar platskontot finns i [Konfigurera molnimportkonton](/help/components/locations/configure-import-accounts.md).

   * **[!UICONTROL Location]**: En nedrullningsbar lista med befintliga platser som din organisation har konfigurerat. Om din organisation inte redan har konfigurerat en plats kan du konfigurera en genom att välja [!UICONTROL **Skapa en ny plats**].

     Mer information om hur du konfigurerar en plats finns i [Konfigurera platser för molnimport](/help/components/locations/configure-import-locations.md).

   * **[!UICONTROL Delimiter]**: Kolumnavgränsaren för överförda filer. Alternativen inkluderar [!UICONTROL Comma], [!UICONTROL Semicolon], [!UICONTROL Colon], [!UICONTROL Vertical bar], [!UICONTROL Space], [!UICONTROL Forward slash], [!UICONTROL Backward slash], [!UICONTROL Dash], eller [!UICONTROL Underscore].

   * **[!UICONTROL Encoding]**: En nedrullningsbar lista som bestämmer filkodningen. Alternativen inkluderar [!UICONTROL UTF-8] och [!UICONTROL Latin1]. UTF-8 rekommenderas.
