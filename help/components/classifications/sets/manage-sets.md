---
title: Hantera klassificeringsuppsättningar
description: Hantera klassificeringsgrupper i Adobe Analytics.
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
source-git-commit: eb12185be8d6e2e6dc15df9da17ce34b5f6b9c80
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---

# Hantera klassificeringsuppsättningar

Du kan skapa, byta namn på, redigera, konsolidera, ta bort och tagga klassificeringsuppsättningar i hanteringsgränssnittet för klassificeringsuppsättningar. Du kan också filtrera och söka efter särskilda klassificeringsuppsättningar.

Så här hanterar du klassificeringsuppsättningar:

1. Välj **[!UICONTROL Components]** i Adobe Analytics övre menyrad och välj sedan **[!UICONTROL Classification sets]**.
1. I **[!UICONTROL Classification Sets]** väljer du fliken **[!UICONTROL Classification Sets]**.

## Klassificeringsuppsättningshanterare

Hanteraren **[!UICONTROL Classification Sets]** har följande gränssnittselement:

![Klassificeringsuppsättningshanteraren](assets/classification-sets-manage.png)


### Lista över klassificeringsuppsättningar

I listan **[!UICONTROL Classification Sets]** ➊ visas alla klassificeringsuppsättningar. Listan innehåller följande kolumner:

| Kolumn | Beskrivning |
|---|---|
| **[!UICONTROL Classification Set]** | Klassificeringsuppsättningens namn. Markera namnet för att [redigera klassificeringsmängden](create-set.md#edit-a-classification-set). |
| **[!UICONTROL Subscriptions]** | Antalet prenumerationer som klassificeringsmängden gäller för. |
| **[!UICONTROL Classifications]** | Antalet klassificeringsdimensioner som klassificeringsuppsättningen innehåller. |
| **[!UICONTROL Automated]** | Är klassificeringsuppsättningen konfigurerad att importera data från en molnplats automatiskt eller inte? Den här automatiseringen kan konfigureras som en del av schemat för [klassificeringsuppsättningar](manage/schema.md). |
| **[!UICONTROL Last modified]** | Tidsstämpeln för den senaste ändringen av klassificeringsuppsättningen. |

Om du vill ändra storlek på en kolumn i listan med klassificeringsuppsättningar kan du:

* Håll pekaren över kolumnavgränsaren och dra kolumnavgränsaren till önskad kolumnbredd.
* Välj ![SparrNed](/help/assets/icons/ChevronDown.svg) och välj **[!UICONTROL Resize column]**. Med en lodrät linje med storleksknappen kan du ändra storlek på kolumnen till det önskade med.

Sortera en kolumn i listan över klassificeringsuppsättningar

* Välj ![SparrNed](/help/assets/icons/ChevronDown.svg) och välj **[!UICONTROL Sort Ascending]** eller **[!UICONTROL Sort Descending]**. En pil ( ↑ ↓) visar vilken kolumn och hur kolumnen sorteras.

### Sökning och knappar

I området ➋ ovanför listan med klassificeringsuppsättningar kan du:

* Sök i ![Sök](/help/assets/icons/Search.svg) efter klassificeringsuppsättningar. Resultaten visas i listan med klassificeringsuppsättningar. Välj ![CrossSize200](/help/assets/icons/CrossSize200.svg) för att rensa sökningen.
* Ta bort alla filter som används i listan med klassificeringsuppsättningar. Välj ![CrossSize100](/help/assets/icons/CrossSize100.svg) om du vill ta bort ett filter.
* Välj ![MoreCircle](/help/assets/icons/MoreCircle.svg) om du vill läsa in ytterligare 1000 klassificeringsuppsättningar. Till att börja med visas klassificeringslistan upp till 1 000 klassificeringsuppsättningar.
* Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]** om du vill [skapa en ny klassificeringsuppsättning](create-set.md#create-a-classification-set).
* Definiera kolumnerna i klassificeringslistan. Välj ![Kolumninställning](/help/assets/icons/ColumnSetting.svg) och markera de kolumner som ska visas under **[!UICONTROL Customize table]** i dialogrutan **[!UICONTROL Select columns to show]**. Välj **[!UICONTROL Apply]** om du vill använda kolumninställningarna.


### Åtgärdsfält

När du väljer en eller flera klassificeringsuppsättningar i listan med klassificeringsuppsättningar visas ett blått åtgärdsfält ➌. Följande åtgärder är tillgängliga i åtgärdsfältet:

| Ikon | Åtgärd | Beskrivning |
|---|---|---|
| ![Redigera](/help/assets/icons/Edit.svg) | **[!UICONTROL Edit]** | [Redigera klassificeringsuppsättningen](create-set.md#edit-a-classification-set) i klassificeringsuppsättningsverktyget. |
| ![Byt namn](/help/assets/icons/Rename.svg) | **[!UICONTROL Rename]** | Byt namn på en klassificeringsuppsättning.<br/>I dialogrutan **[!UICONTROL Rename: _Klassificeringsuppsättning_]** anger du ett nytt namn och väljer **[!UICONTROL Rename]**. |
| ![Sammanfoga](/help/assets/icons/Merge.svg) | **[!UICONTROL Consolidate]** | [Konsolidera klassificeringsgrupper](/help/components/classifications/sets/consolidations/manage.md). |
| ![Ta bort](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Ta bort en klassificeringsgrupp.<br/>Klassificeringsuppsättningen **[!UICONTROL Delete _2?_Dialogrutan]**visas. Det går inte att ångra en borttagning av en klassificeringsuppsättning. Alla schemalagda projekt eller konsolideringar som använder den här klassificeringsuppsättningen fortsätter att använda definitionen för den här klassificeringsuppsättningen tills du sparar om de schemalagda projekten eller validerar de schemalagda konsolideringarna på nytt. Välj **[!UICONTROL Delete]**om du vill ta bort klassificeringsuppsättningen. |
| ![Etikett](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Tagga klassificeringsuppsättningen.<br/>I dialogrutan **[!UICONTROL Tag: _klassificeringsuppsättning_]** väljer du en eller flera taggar i listrutan **[!UICONTROL Tags]** för att lägga till taggar. Eller ange en eller flera nya taggar. Använd ![CrossSize100](/help/assets/icons/CrossSize100.svg) för att ta bort en tagg. <br/>Välj **[!UICONTROL Save]** om du vill spara taggarna. |


### Panelen Filter

Välj ![Filter](/help/assets/icons/Filter.svg) om du vill visa filterpanelen ➍ som du kan använda för att filtrera listan med klassificeringsuppsättningar. Du kan filtrera på:

* **[!UICONTROL Tags]**. Markera en eller flera taggar om du vill filtrera listan över klassificeringsuppsättningar för taggar.
* **[!UICONTROL Report Suite]**. Välj en eller flera rapportsviter om du vill filtrera listan över klassificeringsuppsättningar i rapportsviter.

Välj ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Hide filters]** om du vill dölja filterpanelen.

Observera att de filter som visas på filterpanelen återspeglar alternativen för de klassificeringsuppsättningar som är förinlästa.
