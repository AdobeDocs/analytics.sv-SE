---
title: Sena träffar
description: Lär dig hur dataflöden hanterar sena träffar.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
source-git-commit: 4d0007d1a23a81f0d5ba60541b4f7b9ac7b00ace
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# Sena träffar {#late-arriving-hits}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_late_hits"
>title="Tillåt sena träffar"
>abstract="Välj det här alternativet om du vill inkludera data som har tagits emot efter att datafeedjobbet har slutfört databearbetningen inom den angivna rapporteringsfrekvensen (vanligtvis dagligen eller timvis). När det här alternativet är aktiverat tittar dataflödet varje gång data bearbetas i de senaste träffar som inträffat och grupperar dem i nästa dataflödesfil som skickas."

<!-- markdownlint-enable MD034 -->

## Förstå sena träffar

Historiska data kan komma när ett datafeedjobb har avslutat bearbetningen för en viss timme eller dag, till exempel genom tidsstämplade träffar eller datakällor.

När en dataström normalt bearbetar data, tittar den bara på data i sitt rapportfönster (vanligtvis den senaste timmen eller dagen). Om data kommer efter att en feed har bearbetat det rapportfönstret, inkluderas dessa data aldrig i någon datafeed.

När sena träffar är aktiverade ändras bearbetningsmetoden så att den inkluderar dessa data. Varje gång en datafeed bearbetar data tittar den på eventuella sena träffar som har kommit fram och grupperar dem i nästa datafeedfil som skickas.

## Aktivera sena träffar

Innan du aktiverar alternativet att tillåta sena träffar för en datafeed bör du tänka på följande:

* Data för olika dagar visas ofta i dataflöden när sena träffar är aktiverade. Se till att den plattform du använder för att importera dataflöden kan innehålla data från olika dagar inom samma fil.
* Om en dataflödesfil bearbetas på nytt inkluderas de träffar som togs med i originalfilen i den bearbetade filen när bearbetningen görs inom de första fem dagarna. Efter 5 dagar inkluderas inte sena träffar i den bearbetade filen.

Du kan aktivera sena träffar när du skapar eller redigerar en datafeed genom att aktivera alternativet **[!UICONTROL Allow late-arriving hits]** enligt beskrivningen i [Skapa en datafeed](/help/export/analytics-data-feed/create-feed.md).
