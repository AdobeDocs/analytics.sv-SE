---
title: Översikt över klassificeringsuppsättningar
description: Använd klassificeringsuppsättningar för att hantera klassificeringsdata.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---

# Översikt över klassificeringsuppsättningar

Klassificeringsuppsättningar har ett enda gränssnitt för att hantera klassificeringar och regler. I det här arbetsflödet kombineras begreppet att skapa klassificeringar i Rapportsvitens inställningar med begreppet Klassificeringsimporterare, vilket ger ett mer intuitivt gränssnitt för att skapa och hantera klassificeringsdata.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]**

Den serverdelsarkitektur som lanserats med klassificeringsuppsättningar innehåller flera viktiga förbättringar:

* Minskad bearbetningstid (72 timmar → 24 timmar)
* Möjligheten att använda användargränssnittet för klassificeringsuppsättningar
* Alternativet att använda klassificeringsdata i Adobe Experience Platform i framtiden via [Adobe Analytics källanslutning för klassificeringsdata](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)

Den serverdelsarkitektur som lanserats med klassificeringsuppsättningar innehåller också flera tydliga ändringar:

* När du använder webbläsaren eller automatiserad import, &#39;[!UICONTROL Overwrite on conflict]&#39; är alltid aktiverat.
* När du använder webbläsaren eller den automatiska importen stöds inte längre alternativet att exportera direkt efter importen. Export måste initieras separat.
* API:t för Analytics 2.0 `GetDimensions` slutpunkten returnerar nu strängidentifierare för klassificeringar i stället för numeriska identifierare. Numeriska identifierare kan fortfarande användas, men Adobe rekommenderar att du använder de nya strängidentifierarna där det är möjligt. Numeriska identifierare kan hämtas med `?expansion=hidden` frågesträngsparameter.

>[!IMPORTANT]
>
>Klassificeringsuppsättningens prestanda beror huvudsakligen på antalet unika nyckelvärden som innehåller data. Adobe rekommenderar att man är försiktig när man hanterar variabler som innehåller ett stort antal unika värden. Detta gäller särskilt när variabler från flera rapportsviter och dimensioner kombineras till en enda klassificeringsuppsättning.

Klassificeringsuppsättningar består av tre huvudområden:

* [**[!UICONTROL Classification sets manager]**](manage/set-manager.md): Skapa, redigera och ta bort klassificeringsuppsättningar.
* [**[!UICONTROL Classification set jobs manager]**](job-manager.md): Visa statusen för klassificeringsmängdsjobb och hämta exportfiler.
* [**[!UICONTROL Classification set consolidations]**](consolidations/manage.md): Kombinera flera klassificeringsuppsättningar till en enda klassificeringsuppsättning.
