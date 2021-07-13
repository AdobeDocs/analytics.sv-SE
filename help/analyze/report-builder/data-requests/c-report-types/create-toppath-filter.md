---
description: Beskriver hur du skapar sökvägsrapporter med fördefinierade filter.
title: Filtrera sökvägsrapporter genom att lägga till underordnade förfrågningar
uuid: dd1294f8-a26b-4254-a9f6-1365b2912adf
feature: Report Builder
role: User, Admin
exl-id: 41aca5a4-7bda-4be5-ae93-a6d1dae6a554
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 9%

---

# Filtrera sökvägsrapporter genom att lägga till underordnade förfrågningar

Beskriver hur du skapar sökvägsrapporter med fördefinierade filter.

Marknadsföringsrapporter och -analyser erbjuder ett antal fristående rapporter som är de viktigaste sökvägsrapporterna med fördefinierade filter, som [!UICONTROL Next]- och [!UICONTROL Previous Site Section]-rapporter, Entry- och [!UICONTROL Exit Site Section]-rapporter samt [!UICONTROL Single Site Section]-rapporter.

Report Builder erbjuder inte dessa som fristående rapporter, men du kan skapa dem via snabbmenyerna **[!UICONTROL Add dependent request]** > **[!UICONTROL Path]**. Följande rapporter är tillgängliga:

* Bana > Sidutfall
* Sökväg > Sökväg till post
* Bana > Avsluta bana
* Bana > Nästa sida
* Path > Entry Path > next page
* Bana > Föregående sida
* Bana > Avsluta bana > Föregående sida
* Sökväg > Sökväg till posten > Som startsida
* Bana > Avsluta bana > Som avslutningssida

1. Markera flera rader i en befintlig begäran och högerklicka sedan på **[!UICONTROL Add Dependent Request]** > **[!UICONTROL Path]**.

   (Observera att du måste markera minst tre rader om du vill se menyalternativet **[!UICONTROL Page Fallout]**.)

   ![](assets/dependen_request.png)

1. Välj det fördefinierade filtret, till exempel **[!UICONTROL Previous Page]**.

   Begärandeguiden visas med måttet Föregående sida markerat. 1. Fortsätt att förfina din begäran i Request Wizard och generera din begäran.
