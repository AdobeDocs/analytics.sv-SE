---
title: Schema för klassificeringsuppsättning
description: Visa och redigera schemat för en enskild klassificeringsgrupp.
exl-id: 4a7c5bfe-ff2b-4380-af46-435801d73c1e
feature: Classifications
source-git-commit: de12253f6db798f49d0cae34bf9cb6b7a3de17db
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---

# Schema

Visa aktuella konfigurerade klassificeringsdimensioner för den här klassificeringsuppsättningen.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > Klicka på önskat namn på klassificeringsmängden > **[!UICONTROL Schema]**

![klassificeringsuppsättningens schema-UI](../../assets/classification-set-schema.png)

Följande knappar är tillgängliga:

<!--* **[!UICONTROL Add]**: Adds an empty row so that you can add a classification dimension to the schema.-->
* **[!UICONTROL Upload]**: Överför klassificeringsdata manuellt för en eller flera klassificeringsdimensioner. `JSON`-, `CSV`-, `TSV`- och `TAB`-filer stöds. När du överför en giltig fil visas en tabellförhandsvisning av data som ska klassificeras.
   * **[!UICONTROL File encoding]**: Välj rätt filkodning med den här listrutan. Giltiga alternativ är [!UICONTROL UTF-8] och [!UICONTROL Latin1].
   * **[!UICONTROL List delimiter]**: Välj rätt listavgränsare. Om du använder en hämtad fil eller mallfil måste du se till att [!UICONTROL List delimiter] här matchar [!UICONTROL List delimiter] när filen hämtades.
   * **[!UICONTROL Apply]**: Spara överförda klassificeringsdata i klassificeringsuppsättningen.

  ![Överföring av klassificeringsuppsättning](../../assets/classification-set-upload.png)

* **[!UICONTROL Download]**: Hämta nyckelvärden och deras klassificeringskolumner.
   * **[!UICONTROL Rows]**: Det maximala antalet rader som ska inkluderas i hämtningsfilen.
   * **[!UICONTROL Download rows received between]**: En datumväljare i kalendern där du kan filtrera nyckelvärden efter när de visas i rapporter. Om ett nyckelvärde inte samlats in i det här datumintervallet visas det inte i den hämtade filen.
   * **[!UICONTROL Data returned]**: En nedrullningsbar lista där du kan filtrera nyckelvärden som ingår i den hämtade filen baserat på deras associerade klassificeringsdata.
      * **[!UICONTROL All classified values]**: Inkluderar rader där klassificeringsdata ingår i minst en kolumn.
      * **[!UICONTROL All unclassified values]**: Inkluderar rader där klassificeringsdata saknas i minst en kolumn.
   * **[!UICONTROL File format]**: En nedrullningsbar lista som avgör i vilket filformat den hämtade filen finns. Alternativen är [!UICONTROL JSON], [!UICONTROL Comma separated values] och [!UICONTROL Excel tab separated values].
   * **[!UICONTROL File encoding]**: En nedrullningsbar lista som avgör filkodningen. Alternativen är [!UICONTROL UTF-8] och [!UICONTROL Latin1]. UTF-8 rekommenderas.

  ![Hämtning av klassificeringsuppsättning](../../assets/classification-set-download.png)

* **[!UICONTROL Template]**: Hämta en mallfil. Den här filen liknar knappen [!UICONTROL Download], förutom att den inte innehåller några klassificeringsdata eller nyckelvärden.
   * **[!UICONTROL File format]**: En nedrullningsbar lista som avgör vilket filformat mallfilen finns i. Alternativen är [!UICONTROL Comma separated values] och [!UICONTROL Excel tab separated values].
   * **[!UICONTROL File encoding]**: En nedrullningsbar lista som avgör filkodningen. Alternativen är [!UICONTROL UTF-8] och [!UICONTROL Latin1]. UTF-8 rekommenderas.
   * **[!UICONTROL List delimiters]**: En nedrullningsbar lista som anger avgränsaren för klassificeringskolumner på varje rad.

  ![Mallen för klassificeringsuppsättning](../../assets/classification-set-template.png)

* **[!UICONTROL Job history]**: En genvägslänk som tar dig till [Jobbhanteraren](../job-manager.md) och endast visar jobb för den här klassificeringsuppsättningen.
* **[!UICONTROL Automate]**: Importerar automatiskt data från externa lagringsplatser.
   * **[!UICONTROL Location account]**: En listruta med befintliga platskonton som din organisation har konfigurerat. Om din organisation inte redan har konfigurerat ett platskonto kan du konfigurera ett genom att välja [!UICONTROL **Skapa ett nytt konto**].

     Mer information om hur du konfigurerar platskontot finns i [Konfigurera molnimport- och exportkonton](/help/components/locations/configure-import-accounts.md).

   * **[!UICONTROL Location]**: En nedrullningsbar lista med befintliga platser som din organisation har konfigurerat. Om din organisation inte redan har konfigurerat en plats kan du konfigurera en genom att välja [!UICONTROL **Skapa en ny plats**].

     Mer information om hur du konfigurerar en plats finns i [Konfigurera molnimport och exportplatser](/help/components/locations/configure-import-locations.md).

   * **[!UICONTROL Delimiter]**: Kolumnavgränsaren för överförda filer. Alternativen är [!UICONTROL Comma], [!UICONTROL Semicolon], [!UICONTROL Colon], [!UICONTROL Vertical bar], [!UICONTROL Space], [!UICONTROL Forward slash], [!UICONTROL Backward slash], [!UICONTROL Dash] eller [!UICONTROL Underscore].

   * **[!UICONTROL Encoding]**: En nedrullningsbar lista som avgör filkodningen. Alternativen är [!UICONTROL UTF-8] och [!UICONTROL Latin1]. UTF-8 rekommenderas.
