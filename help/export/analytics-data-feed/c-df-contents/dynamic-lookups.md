---
title: Dynamiska sökningar
description: Lär dig mer om vad dynamiska sökningar är och hur du aktiverar dem. Innefattar bärare, mobilattribut och operativsystemstyper.
source-git-commit: b6084fc34165ea602fce616e13b3adfcd7bdfdbd
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Dynamiska sökningar

Med dynamiska sökningar kan du ta emot ytterligare sökfiler i din datafeed som annars inte är tillgänglig. Med den här inställningen kan följande uppslagstabeller skickas med varje dataflödesfil:

* **Transportföretagets namn**: Tillhandahåller ytterligare kontext för `carrier` kolumn. Filnamnet som ingår är `carrier.tsv`.
* **Mobilattribut**: Tillhandahåller ytterligare kontext för `mobile_id` -kolumn, inklusive alla funktioner som spåras för varje mobil enhet. Filnamnet som ingår är `mobile_attributes.tsv`.
* **Operativsystemtyp**: Anger en alternativ kontext för `os` kolumn. Båda `operating_systems.tsv` och `operating_system_type.tsv` använder `os` kolumn som tangent, men bara `operating_system_type.tsv` är en dynamisk sökning.

## Aktivera dynamiska sökningar

Om du vill få de uppslagsfiler som nämns måste du uppfylla följande krav:

* Nyckelkolumnen måste inkluderas i dataflödet.
   * För `carrier.tsv`måste du ta med `carrier`.
   * För `mobile_attributes.tsv`måste du ta med `mobile_id`.
   * För `operating_system_type.tsv`måste du ta med `os`.
* Följande kolumner måste vara **exkluderad**. Om någon av dessa kolumner ingår i dataflödet inkluderas inte de extra uppslagstabellerna.
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

När din datafeed uppfyller kraven för kolumninkludering och exkludering kontaktar du kundtjänst med ID:t för datafeed och begäran om att aktivera dynamiska sökningar.

## Referens för sökhuvud

Kolumnrubrikerna för de här sökfilerna ändras inte över tid, så rubrikerna tas inte med i varje dataflödesfil. Använd de här kolumnrubrikerna som referens eller hämta deras respektive rubriker `.tsv` -fil.

+++**Transportföretagets namn**
Hämta [bärare_huvuden.tsv](assets/carrier_headers.tsv) eller referera till rubrikerna nedan.

`carrier`
`Carrier Name`
+++

+++**Mobilattribut**
Hämta [mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv) eller referera till rubrikerna nedan.

`mobile_id`
`Manufacturer`
`Device`
`Device Type`
`Operating System`
`Diagonal Screen Size`
`Screen Height`
`Screen Width`
`Cookie Support`
`Color Depth`
`MP3 Audio Support`
`AAC Audio Support`
`AMR Audio Support`
`Midi Monophonic Audio Support`
`Midi Polyphonic Audio Support`
`QCELP Audio Support`
`GIF87 Image Support`
`GIF89a Image Support`
`PNG Image Support`
`JPG Image Support`
`3GPP Video Support`
`MPEG4 Video Support`
`3GPP2 Video Support`
`WMV Video Support`
`MPEG4 Part 2 Video Support`
`Stream MP4 AAC LC Video Support`
`Stream 3GP H264 Level 10b Video Support`
`Stream 3GP AAC LC Video Support`
`3GP AAC LC Video Support`
`Stream MP4 H264 Level 11 Video Support`
`Stream MP4 H264 Level 13 Video Support`
`Stream 3GP H264 Level 12 Video Support`
`Stream 3GP H264 Level 11 Video Support`
`Stream 3GP H264 Level 10 Video Support`
`Stream 3GP H264 Level 13 Video Support`
`3GP AMR NB Video Support`
`3GP AMR WB Video Support`
`MP4 H264 Level 11 Video Support`
`3GP H263 Video Support`
`MP4 H264 Level 13 Video Support`
`Stream 3GP H263 Video Support`
`Stream 3GP AMR WB Video Support`
`3GP H264 Level 10b Video Support`
`MP4 ACC LC Video Support`
`Stream 3GP AMR NB Video Support`
`3GP H264 Level 10 Video Support`
`3GP H264 Level 13 Video Support`
`3GP H264 Level 11 Video Support`
`3GP H264 Level 12 Video Support`
`Stream HTTP Live Streaming Video Support`
+++

+++**Operativsystemtyp**
Hämta [operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv) eller referera till rubrikerna nedan.

`os`
`Operating System Type`
+++