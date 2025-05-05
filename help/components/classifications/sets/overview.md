---
title: Översikt över klassificeringsuppsättningar
description: Använd klassificeringsuppsättningar för att hantera klassificeringsdata.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%

---

# Översikt över klassificeringsuppsättningar

Klassificeringsuppsättningar har ett enda gränssnitt för att hantera klassificeringar och regler. I det här arbetsflödet kombineras begreppet att skapa klassificeringar i Rapportsvitens inställningar med begreppet Klassificeringsimporterare, vilket ger ett mer intuitivt gränssnitt för att skapa och hantera klassificeringsdata.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]**

Du måste vara produktadministratör eller tillhöra en produktprofil som innehåller behörighetsobjektet [!UICONTROL Report Suite Tools] > [!UICONTROL Classifications] för att kunna se det här menyobjektet. Observera att medan tidigare gränssnitt för klassificeringshantering finns under menyn [!UICONTROL Admin] finns Klassificeringsuppsättningar på menyn [!UICONTROL Components].

## Förbättringar

Den serverdelsarkitektur som lanserats med klassificeringsuppsättningar innehåller flera viktiga förbättringar:

* Minskad bearbetningstid (72 timmar → 24 timmar)
* Ett omdesignat användargränssnitt som hanterar klassificeringar
* Alternativet att använda klassificeringsdata i Adobe Experience Platform i framtiden via [Adobe Analytics-källkopplingen för klassificeringsdata](https://experienceleague.adobe.com/sv/docs/experience-platform/sources/connectors/adobe-applications/classifications)

Den serverdelsarkitektur som lanserats med klassificeringsuppsättningar innehåller också flera tydliga ändringar:

* [!UICONTROL Overwrite on conflict] är alltid aktiverat när webbläsaren eller den automatiska importen används.
* När du använder webbläsaren eller den automatiska importen stöds inte längre alternativet att exportera direkt efter importen. Export måste initieras separat.
* Slutpunkten för API:t `GetDimensions` för Analytics 2.0 returnerar nu strängidentifierare för klassificeringar i stället för numeriska identifierare. Numeriska identifierare kan fortfarande användas, men Adobe rekommenderar att du använder de nya strängidentifierarna där det är möjligt. Numeriska identifierare kan hämtas med frågesträngparametern `?expansion=hidden`.

>[!IMPORTANT]
>
>Klassificeringsuppsättningens prestanda beror huvudsakligen på antalet unika nyckelvärden som innehåller data. Adobe rekommenderar att man är försiktig när man hanterar variabler som innehåller ett stort antal unika värden. Detta gäller särskilt när variabler från flera rapportsviter och dimensioner kombineras till en enda klassificeringsuppsättning.

Klassificeringsuppsättningar består av tre huvudområden:

* [**[!UICONTROL Classification sets manager]**](manage/set-manager.md): Skapa, redigera och ta bort klassificeringsgrupper.
* [**[!UICONTROL Classification set jobs manager]**](job-manager.md): Visa statusen för klassificeringsmängdsjobb och hämta exportfiler.
* [**[!UICONTROL Classification set consolidations]**](consolidations/manage.md): Kombinera flera klassificeringsuppsättningar till en enda klassificeringsuppsättning.
