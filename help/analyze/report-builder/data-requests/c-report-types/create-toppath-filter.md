---
description: Beskriver hur du skapar sökvägsrapporter med fördefinierade filter.
title: Filtrera sökvägsrapporter genom att lägga till underordnade förfrågningar
feature: Report Builder
role: User, Admin
exl-id: 41aca5a4-7bda-4be5-ae93-a6d1dae6a554
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---

# Filtrera sökvägsrapporter genom att lägga till underordnade förfrågningar

Beskriver hur du skapar sökvägsrapporter med fördefinierade filter.

Marknadsföringsrapporter och -analyser erbjuder ett antal fristående rapporter som är de viktigaste sökvägsrapporterna med fördefinierade filter, som [!UICONTROL Next] och [!UICONTROL Previous Site Section] rapporter, bidrag och [!UICONTROL Exit Site Section] rapporter, och [!UICONTROL Single Site Section] rapport.

Report Builder erbjuder inte dessa som fristående rapporter, men du kan skapa dem via **[!UICONTROL Add dependent request]** > **[!UICONTROL Path]** snabbmenyer. Följande rapporter är tillgängliga:

* Bana > Sidutfall
* Sökväg > Sökväg till post
* Bana > Avsluta bana
* Bana > Nästa sida
* Path > Entry Path > next page
* Bana > Föregående sida
* Bana > Avsluta bana > Föregående sida
* Sökväg > Sökväg till posten > Som startsida
* Bana > Avsluta bana > Som avslutningssida

1. Markera flera rader i en befintlig begäran och högerklicka sedan **[!UICONTROL Add Dependent Request]** > **[!UICONTROL Path]**.

   (Observera att du måste markera minst tre rader om du vill att **[!UICONTROL Page Fallout]** menyalternativ.)

   ![](assets/dependen_request.png)

1. Välj t.ex. det fördefinierade filtret **[!UICONTROL Previous Page]**.

   Begärandeguiden visas med måttet Föregående sida markerat. 1. Fortsätt att förfina din begäran i Request Wizard och generera din begäran.
