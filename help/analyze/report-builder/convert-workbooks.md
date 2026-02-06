---
title: Konvertera dina gamla Report Builder-arbetsböcker
description: Lär dig hur du konverterar dina gamla Report Builder-baserade arbetsböcker till nya Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 504cce24babdd8aefa5f819433139671904f2e1e
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 0%

---

# Konvertera äldre Report Builder-arbetsböcker

Som en del av övergången till en ny Report Builder-funktion kan du snabbt konvertera dina nuvarande gamla Report Builder-baserade arbetsböcker (äldre arbetsböcker) till den nya Report Builder [datablocks](create-a-data-block.md) -funktionen.

>[!IMPORTANT]
>
>Duplicera varje arbetsbok och byt namn på en version innan du konverterar den äldre arbetsboken. Det ser till att du alltid har en kopia av den ursprungliga arbetsboken om du behöver den.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Konvertera arbetsböcker](https://video.tv.adobe.com/v/3434957?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Om du vill konvertera äldre arbetsböcker måste du först [konfigurera nya Report Builder](/help/analyze/report-builder/report-builder-setup.md).


## Öppna en äldre arbetsbok

Om du vill öppna en äldre arbetsbok kan du:

* Öppna en schemalagd äldre arbetsbok från fliken **[!UICONTROL Schedule]** i [Report Builder-hubben](report-builder-hub.md). Detta är den metod som rekommenderas för schemalagda äldre arbetsböcker. Du får alternativet att använda schemat som är associerat med den äldre arbetsboken så snart du [schemalägger den konverterade äldre arbetsboken](#schedule-a-converted-legacy-workbook).

   1. Öppna Excel och välj ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** i menyfliksområdet i Excel.

   1. Välj **[!UICONTROL Login]** och logga in på Report Builder.

   1. Välj **[!UICONTROL Schedule]** i [Report Builder-hubben](report-builder-hub.md).
   1. Välj fliken **[!UICONTROL Legacy]**. På fliken visas de gamla schemalagda arbetsböckerna som baseras på Report Builder.

      ![Äldre arbetsböcker](assets/upgrade-legacy-schedule.png)

   1. Välj ![SelectBox](/help/assets/icons/SelectBox.svg) för den schemalagda arbetsbok som du vill konvertera från listan och välj ![Hämta](/help/assets/icons/Download.svg). Arbetsboken hämtas och öppnas i ett nytt fönster i Excel. Du kan nu [konvertera den gamla Report Builder-arbetsboken](#convert-a--workbook).


* Öppna en äldre arbetsbok direkt från den lokala datorn eller nätverket. När du använder den här metoden erbjuds du inte att använda det schema som kan vara kopplat till den äldre arbetsboken. <br/>När den äldre arbetsboken är öppen i Excel:

   1. Välj ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** i menyfliksområdet i Excel.
   1. Välj **[!UICONTROL Login]** och logga in på Report Builder.
   1. [konvertera sedan den äldre arbetsboken](#convert-a-workbook).


## Konvertera en äldre arbetsbok

Så här konverterar du din gamla arbetsbok:

1. När du har öppnat en äldre arbetsbok upptäcker den nya Report Builder om arbetsboken innehåller [äldre Report Builder](/help/analyze/legacy-report-builder/home.md)-begäranden.

   ![fråga om arbetsbok för uppgradering](assets/upgrade-workbook.png){zoomable="yes"}

1. Om en eller flera tidigare begäranden hittas klickar du på **[!UICONTROL Upgrade]** i dialogrutan **[!UICONTROL Upgrade workbook]** för att uppgradera arbetsboken.

   >[!NOTE]
   >
   >Du måste uppgradera varje begäran separat. Massuppgradering stöds inte.


1. En **[!UICONTROL Warning]**-dialogruta visas som varnar dig om ändringar i arbetsboken om du uppgraderar. Du uppmanas också att skapa en säkerhetskopia av din gamla arbetsbok innan du fortsätter.

   ![uppgraderingsvarning](assets/upgrade-warning.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Proceed]** om du vill fortsätta med uppgraderingen.

   Om uppgraderingen lyckas visas ett meddelande om **[!UICONTROL The workbook upgrade is now completed]**.

   ![Uppgraderingen har slutförts](assets/upgrade-complete.png)

   * Välj **[!UICONTROL Close]** om du vill stänga meddelandet och fortsätta arbeta i arbetsboken med uppdaterade begäranden för nya Report Builder.

   * Välj **[!UICONTROL Download upgrade report]** om du vill hämta och öppna en ny Excel-arbetsbok som visar resultatet av uppgraderingen. Se ett exempel nedan.

     ![Excel Report Builder - arbetsbok för uppgraderingsrapport](assets/upgrade-report.png)

Du kan nu [hantera datablocken](/help/analyze/report-builder/manage-reportbuilder.md) i arbetsboken. Dessa datablock är resultatet av uppgraderingen och ersätter dina tidigare förfrågningar från Report Builder.


## Schemalägg en konverterad äldre arbetsbok

Du kan använda schemainformationen från den äldre arbetsboken som du har hämtat och öppnat från fliken **[!UICONTROL Schedule]** i Report Builder-hubben. Det här alternativet är inte tillgängligt för äldre arbetsböcker med schemainformation som du öppnar från den lokala datorn eller nätverket.

1. Så här schemalägger du en konverterad äldre arbetsbok med ett äldre schema:

   * Välj **[!UICONTROL Send workbook]** från Report Builder-navet, eller
   * Välj **[!UICONTROL Schedule workbook]** på fliken **[!UICONTROL Workbooks]** som finns på fliken **[!UICONTROL Schedules]** i Report Builder.

1. Du kan använda schemainformationen från den äldre arbetsboken som standardinställningar för scheman.

   ![Migrera äldre arbetsboksschema](assets/upgrade-legacy-schedule-convert.png)

   * Välj **[!UICONTROL Use]** om du vill använda äldre schemadetaljer. Schemainformationen är förifylld i gränssnittet [Skicka arbetsbok](schedule-reportbuilder.md#schedule-a-workbook).
   * Välj **[!UICONTROL Don't use]** om du inte vill använda äldre schemainformation.
   * Välj **[!UICONTROL Cancel]** om du vill avbryta.

   Välj **[!UICONTROL Remove legacy metadata from future use]** om du inte vill använda äldre schemainformation för den här arbetsboken i framtiden.


## Äldre Report Builder-funktioner stöds inte {#unsupported}

Vissa äldre Report Builder-funktioner är inte längre tillgängliga i nya Report Builder

* Realtidsbegäranden.

* Rapportering av sökväg/bortfall.

* FTP-alternativ för schemalagda rapporter.

* Besökarstatistik. Följande mått konverteras till *unika besökare*, även om rapportresultatet kanske inte är en exakt matchning: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` och `visitorsyearly`. Den här konverteringen gäller även för `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` och `mobilevisitorsyearly`.
