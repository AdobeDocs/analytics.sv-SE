---
description: Du kan inte kombinera klassificeringsregelbyggaren med underklassificeringar.
title: Underklassificeringar och regelbyggaren
feature: Classifications
exl-id: 745d6149-bcb1-48ad-abbe-63a9d009fa27
source-git-commit: e7346b11a7d3eb4c18ec02df6c8a07574e02a2b4
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 0%

---

# Underklassificeringar och regelbyggaren

Du kan kombinera klassificeringsregelbyggaren med underklassificeringar om du ser till att alla underklassificeringar har ett överordnat värde.

Genom att kombinera klassificeringsregelbyggaren med underklassificeringar kan klassificeringshanteringen förenklas och antalet regler som krävs minskas. Du kanske vill göra detta om spårningskoden består av koder som du vill klassificera separat.

Mer information om underklassificeringar finns i [Underklassificeringar](/help/components/classifications/c-sub-classifications.md).

## Exempel

Anta följande spårningskod:

`channel:broad_campaign:creative`

Med en klassificeringshierarki kan du tillämpa en klassificering på en klassificering (kallad *`sub-classification`*). Det innebär att du kan använda importören som en relationsdatabas med flera tabeller. En tabell mappar fullständiga spårningskoder till nycklar och en annan mappar dessa nycklar till andra tabeller.

![](assets/sub_class_table.png)

När du har den här strukturen på plats kan du använda [klassificeringsregelverktyget](/help/components/classifications/crb/classification-rule-builder.md) för att överföra små filer som bara uppdaterar uppslagstabellerna (de gröna och röda tabellerna i föregående bild). Sedan kan du använda regelbyggaren för att hålla huvudklassificeringstabellen uppdaterad.

I följande uppgift beskrivs hur du gör detta.

## Konfigurera underklassificeringar med regelverktyget{#task_2D9016D8B4E84DBDAF88555E5369546F}

Exempel på steg som beskriver hur du kan överföra underklassificeringar med regelbyggaren.

>[!NOTE]
>
>De här stegen beskriver hur du slutför det användningsfall som beskrivs i [Underklassificeringar och Regelbyggaren](/help/components/classifications/crb/sub-classification-rule-builder.md).

1. Skapa klassificeringar och underklassificeringar i [Klassificeringshanteraren](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html).

   Exempel:

   ![Steginformation](/help/admin/admin/assets/sub_class_create.png)

1. I [Klassificeringsregelbyggaren](/help/components/classifications/crb/classification-rule-builder.md) kan du klassificera underklassificeringsnyckeln från den ursprungliga spårningskoden.

   Du utför detta med ett reguljärt uttryck. I det här exemplet använder regeln för att fylla i *`Broad Campaign code`* det här reguljära uttrycket:

   | `#` | Regeltyp | Matcha | Ange klassificering | Till |
   |---|---|---|---|---|
   |   | Reguljärt uttryck | `[^\:]:([^\:]):([^\:]`) | Kampanjkod | `$1` |
   |   | Reguljärt uttryck | `[^\:]:([^\:]):([^\:]`) | Kreativ kod | `$2` |

   >[!NOTE]
   >
   >I nuläget fyller du inte i underklassificeringarna *`Campaign Type`* och *`Campaign Director`*.

1. Överför en klassificeringsfil som endast innehåller de underklassificeringar som anges.

   Se [Klassifikationer på flera nivåer](/help/components/classifications/c-sub-classifications.md).

   Exempel:

   | Nyckel | Kanal | Kampanjkod | &Kampanjkod;Hatt;Kampanjtyp | &Kampanjkod;Hatt;Campaign Director | ... |
   |---|---|---|---|---|---|
   | &#42; |  | 111 | Varumärke | Suzanne |  |
   | &#42; |  | 222 | Varumärke | Frank |  |

1. Om du vill underhålla uppslagstabellerna överför du en liten fil (som visas ovan).

   Du skulle till exempel överföra den här filen när en ny *`Broad Campaign code`* introduceras. Den här filen gäller för tidigare klassificerade värden. Om du skapar en ny underklassificering (till exempel *`Creative Theme`* som en underklassificering av *`Creative code`*) överför du bara underklassificeringsfilen, i stället för hela klassificeringsfilen.

   För rapportering av dessa underklassificeringar fungerar exakt som klassificeringar på den översta nivån. På så sätt minskar den handläggningsbörda som krävs för att använda dem.—>
