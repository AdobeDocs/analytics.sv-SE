---
title: Jobbhanterare för klassificeringsuppsättning
description: Visa aktuella och slutförda klassificeringsjobb som genererats från klassificeringsuppsättningar.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
source-git-commit: 496b4891d447ed9dd091a6498a792146a2d5aceb
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 0%

---

# Jobbhanterare för klassificeringsuppsättning

Med jobbhanteraren för klassificeringsuppsättning kan du visa aktuella och slutförda klassificeringsjobb som genererats från klassificeringsuppsättningar. Du kan också använda det här gränssnittet för att hämta klassificeringsdata eller mallar för ett visst jobb, eller överföra ytterligare data till ett jobb.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Jobs]**

Du kan inte skapa jobb från det här gränssnittet. Skapa jobb genom att överföra data till en klassificeringsuppsättning (antingen manuellt eller via en konfigurerad extern plats), begära en hämtningsfil eller begära en mallfil.

## Filterklassificeringsuppsättningar

Vänster sida av jobbhanteraren för klassificeringsuppsättningen innehåller filterinställningar för att hitta det önskade jobbet. När du klickar på filterikonen växlas synligheten för filterinställningarna. Du kan filtrera klassificeringsuppsättningar efter **[!UICONTROL Classification set]**, **[!UICONTROL Completion time]**, **[!UICONTROL Status]**, **[!UICONTROL Job Type]**, eller **[!UICONTROL Source]**.

![Jobbfilter för klassificeringsuppsättning](../assets/classification-set-job-filters.png)

Ytterligare filteralternativ är tillgängliga ovanför kolumnerna för jobbhanteraren för klassificeringsuppsättningen:

* **[!UICONTROL Search by title]**: Sök efter jobb efter filnamn.
* **[!UICONTROL Load more]**: Jobbhanteraren för klassificeringsuppsättningen visar initialt upp till 1 000 jobb. Om det finns fler jobb klickar du på den här knappen för att läsa in 1 000 fler jobb.
* **Visa/dölj kolumner**: Växla synlighet för alla kolumner förutom [!UICONTROL Filename] och [!UICONTROL Completion time].

## Kolumner för jobbhanterare för klassificeringsuppsättning

Följande kolumner är tillgängliga i jobbhanteraren för klassificeringsuppsättningen:

* **[!UICONTROL Filename]**: Namnet på överförings- eller nedladdningsfilen.
* **[!UICONTROL Classification set]**: Namnet på den klassificeringsuppsättning som filen gäller för. Du kan klicka på klassificeringsuppsättningens namn för att nå klassificeringsuppsättningens namn [Inställningar](manage/settings.md).
* **[!UICONTROL Size]**: Filens storlek.
* **[!UICONTROL Status]**: Status för jobbet som bearbetar filen.
   * **[!UICONTROL Created]**: Jobbet skickades.
   * **[!UICONTROL Queued]**: Filen är klar att bearbetas och väntar på att en klassificeringsserver ska bearbeta filen.
   * **[!UICONTROL Validated]**: Filen är giltig och väntar på att bearbetas.
   * **[!UICONTROL Failed validation]**: Filen är felaktigt formaterad eller ogiltig på annat sätt. Filen bearbetas inte.
   * **[!UICONTROL Processing]**: Filen bearbetas aktivt av Adobe.
   * **[!UICONTROL Failed processing]**: Det gick inte att bearbeta filen.
   * **[!UICONTROL Complete]**: Bearbetningen är klar. Klassificeringsdata visas vid rapportering.
   * **[!UICONTROL Failed]**: Allmänt fel som inte är relaterat till validering eller bearbetning.
* **[!UICONTROL Job type]**: Typ av jobb.
* **[!UICONTROL Source]**: Jobbkällan.
* **[!UICONTROL File download]**: Gäller endast för nedladdningsjobb, t.ex. nedladdning av klassificeringsdata eller nedladdning av mallar. När nedladdningen är klar visas en nedladdningslänk i den här kolumnen.
* **[!UICONTROL Modified lines]**: Antalet ändrade rader.
* **[!UICONTROL Completed lines]**: Antalet slutförda rader.
* **[!UICONTROL Completion time]**: Datum och tid då jobbet slutfördes (eller misslyckades).
