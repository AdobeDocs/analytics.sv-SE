---
title: Översikt över klassificeringsuppsättningar
description: Använd Klassificeringsuppsättningar för att hantera klassificeringsdata.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
source-git-commit: 4824170ae2465f3fa04ee588d9571e1cc73d11fc
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 0%

---

# Översikt över klassificeringsuppsättningar

Klassificeringsuppsättningar har ett enda gränssnitt för att hantera klassificeringar och regler. I det här arbetsflödet kombineras begreppet att skapa klassificeringar i Report Suite-inställningar med begreppet Klassificeringsimporterare, vilket ger ett mer intuitivt gränssnitt för att skapa och hantera klassificeringsdata.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]**

>[!NOTE]
>
>Klassificeringsuppsättningar är tillgängliga för alla kunder som har sina rapportsviter migrerade till den nya klassificeringsarkitekturen. Kontakta Adobe kundtjänst eller din kontoansvarige om du vill ha mer information.

Den serverdelsarkitektur som lanserades med Klassificeringsuppsättningar innehåller flera viktiga förbättringar:

* Betydande minskning av bearbetningstiden (72 timmar → 24 timmar)
* Möjligheten att använda användargränssnittet för klassificeringsuppsättningar
* Alternativet att använda klassificeringsdata i Adobe Experience Platform i framtiden via [Adobe Analytics källanslutning för klassificeringsdata](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)

Den serverdelsarkitektur som lanserades med Klassificeringsuppsättningar innehåller också flera tydliga ändringar:

* Vid användning av webbläsarimport, &#39;[!UICONTROL Overwrite on conflict]&#39; är alltid aktiverat.
* När du använder webbläsarimporten stöds inte längre alternativet att exportera direkt efter importen. Export måste initieras separat.
* API:t för Analytics 2.0 `GetDimensions` slutpunkten returnerar nu strängidentifierare för klassificeringar i stället för numeriska identifierare. Numeriska identifierare kan fortfarande användas, men Adobe rekommenderar att du använder de nya strängidentifierarna där det är möjligt. Numeriska identifierare kan hämtas med `?expansion=hidden` frågesträngsparameter.


Klassificeringsuppsättningar består av två huvudområden:

* [**[!UICONTROL Classification Sets Manager]**](set-manager.md): Skapa, redigera och ta bort klassificeringsuppsättningar.
* [**[!UICONTROL Classification Set Jobs Manager]**](job-manager.md): Visa status för jobb för klassificeringsuppsättning och hämta exportfiler.
