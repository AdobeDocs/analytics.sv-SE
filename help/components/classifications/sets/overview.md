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

Du måste vara produktadministratör eller tillhöra en produktprofil som innehåller behörighetsobjektet [!UICONTROL Report Suite Tools] > [!UICONTROL Classifications] om du vill visa det här menyalternativet. Observera att tidigare gränssnitt för klassificeringshantering finns under [!UICONTROL Admin] menyn, klassificeringsuppsättningar finns under [!UICONTROL Components] -menyn.

## Förbättringar

Den serverdelsarkitektur som lanserats med klassificeringsuppsättningar innehåller flera viktiga förbättringar:

* Minskad bearbetningstid (72 timmar → 24 timmar)
* Ett omdesignat användargränssnitt som hanterar klassificeringar
* Alternativet att använda klassificeringsdata i Adobe Experience Platform i framtiden via [Adobe Analytics källanslutning för klassificeringsdata](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/classifications)

Den serverdelsarkitektur som lanserats med klassificeringsuppsättningar innehåller också flera tydliga ändringar:

* När du använder webbläsaren eller automatiserad import, &#39;[!UICONTROL Overwrite on conflict]&#39; är alltid aktiverat.
* När du använder webbläsaren eller den automatiska importen stöds inte längre alternativet att exportera direkt efter importen. Export måste initieras separat.
* API:t för Analytics 2.0 `GetDimensions` slutpunkten returnerar nu strängidentifierare för klassificeringar i stället för numeriska identifierare. Numeriska identifierare kan fortfarande användas, men Adobe rekommenderar att du använder de nya strängidentifierarna där det är möjligt. Numeriska identifierare kan hämtas med `?expansion=hidden` frågesträngparameter.

>[!IMPORTANT]
>
>Klassificeringsuppsättningens prestanda beror huvudsakligen på antalet unika nyckelvärden som innehåller data. Adobe rekommenderar att man är försiktig när man hanterar variabler som innehåller ett stort antal unika värden. Detta gäller särskilt när variabler från flera rapportsviter och dimensioner kombineras till en enda klassificeringsuppsättning.

Klassificeringsuppsättningar består av tre huvudområden:

* [**[!UICONTROL Classification sets manager]**](manage/set-manager.md): Skapa, redigera och ta bort klassificeringsgrupper.
* [**[!UICONTROL Classification set jobs manager]**](job-manager.md): Visa status för klassificeringsuppsättningsjobb och hämta exportfiler.
* [**[!UICONTROL Classification set consolidations]**](consolidations/manage.md): Kombinera flera klassificeringsuppsättningar till en enda klassificeringsuppsättning.
