---
title: Konvertera dina gamla Report Builder-arbetsböcker till databaser
description: Beskriver hur du konverterar dina gamla förfrågningar till databaser
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 0%

---

# Konvertera gamla arbetsböcker från Report Builder till databaser

Som en del av övergången till en ny Report Builder-teknik kan du snabbt konvertera dina nuvarande gamla arbetsböcker till Javascript-baserade arbetsböcker.

>[!IMPORTANT]
>
>Duplicera varje arbetsbok och byt namn på en version innan du konverterar den. På så sätt har du fortfarande en kopia av den ursprungliga arbetsboken om du behöver den.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Konvertera arbetsböcker](https://video.tv.adobe.com/v/3446186?quality=12&learn=on&captions=swe){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]



1. Konfigurera den nya Report Builder genom att [följa dessa instruktioner](/help/analyze/report-builder/report-builder-setup.md).

1. Öppna Excel och klicka på Adobe Report Builder-ikonen längst upp till höger.

1. Klicka på **[!UICONTROL Login]** och logga in på Report Builder.

1. Tillägget Report Builder identifierar om arbetsboken innehåller [äldre Report Builder](/help/analyze/legacy-report-builder/home.md)-begäranden.

   ![fråga om arbetsbok för uppgradering](assets/upgrade_workbook.png)

1. Om en eller flera tidigare begäranden hittas klickar du på **[!UICONTROL Upgrade]** för att uppgradera en arbetsbok.

   >[!NOTE]
   >
   >Du måste uppgradera varje begäran separat. Massuppgradering stöds inte.


1. Det visas en varning som meddelar dig om ändringar i arbetsboken om du uppgraderar. Du uppmanas också att skapa en säkerhetskopia av din gamla arbetsbok innan du fortsätter.

   ![uppgraderingsvarning](assets/upgrade_warning.png)

1. Klicka på **[!UICONTROL Proceed]** om du vill fortsätta med uppgraderingen.

   Om uppgraderingen lyckas visas följande meddelande:

   ![Uppgraderingen har slutförts](assets/upgrade_complete.png)

1. (Valfritt) Klicka på **[!UICONTROL Download upgrade report]**. Den här rapporten innehåller statusen för varje datablock som har uppgraderats.

Du kan nu [hantera datablocket](/help/analyze/report-builder/manage-reportbuilder.md).


## Äldre Report Builder-funktioner som inte stöds i nya Report Builder {#unsupported}

När funktionen för äldre Report Builder jämförs med det nya tillägget Report Builder är vissa funktioner inte längre tillgängliga:

- Förfrågningar i realtid

- Sökväg-/bortfallsrapportering

- FTP-alternativ för schemalagda rapporter

- Besökarstatistik. Följande mått konverteras till&quot;unika besökare&quot;, även om rapportresultatet kanske inte är en exakt matchning: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` och `visitorsyearly`. Detta gäller även `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` och `mobilevisitorsyearly`.

## Schemalägg en konverterad arbetsbok {#schedule}

Se [Schemalägg en konverterad arbetsbok](/help/analyze/report-builder/schedule-reportbuilder.md) i schemaläggningsartikeln.