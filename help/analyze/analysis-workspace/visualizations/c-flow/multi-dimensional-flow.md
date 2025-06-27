---
description: Förstå hur ett interdimensionellt flöde låter dig undersöka användarbanor i olika dimensioner.
title: Mellandimensionella flöden
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
feature: Visualizations
role: User, Admin
exl-id: f84917a4-2c07-48fb-9af3-d96c537da65c
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 0%

---

# Flerdimensionella flöden

Med ett interdimensionellt flöde kan du undersöka användarsökvägar i olika dimensioner.

>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Interdimensionella flöden](https://video.tv.adobe.com/v/24041?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

Den här artikeln visar hur du använder det här flödet för två användningsområden: interaktioner och händelser för mobilappar och hur kampanjer leder till webbbesök.

## Interaktioner och händelser för mobilappar

Dimensionen [!UICONTROL Screen Name] används i det här exempelflödet för att se hur användare använder de olika skärmarna (scenerna) i appen. Den översta skärmen som returneras är **[!UICONTROL luma: content: ios: en: home]**, som är appens startsida:

![Ett flöde som visar det tillagda objektet.](assets/flowapp.png)

Om du vill utforska interaktionen mellan skärmar och händelsetyper (som att lägga till i kundvagn, inköp med mera) i den här appen drar och släpper du dimensionen **[!UICONTROL Event Types]**:

* Ovanför alla tillgängliga steg i flödet för att ersätta dimensionen:

  ![Ett flöde som visar siddimensionen som har dragits till flera områden.](assets/flowapp-replace.png)

* Utanför den aktuella flödesvisualiseringen lägger du till dimensionen:

  ![Ett flöde som visar siddimensionen som dras till det tomma utrymmet i slutet.](assets/flowapp-add.png)

Flödesvisualiseringen nedan visar resultatet av att lägga till dimensionen **[!UICONTROL Event Types]**. Visualiseringen ger insikter om hur mobilappsanvändare förflyttar sig mellan olika skärmar i appen innan de lägger till produkter i en kundvagn, stänger appen, presenteras ett erbjudande med mera.

![En fLow som visar siddimensionens resultat högst upp i listan.](assets/flowapp-result.png)

## Hur kampanjer lockar webbbesök

Ni vill analysera vilka kampanjer som leder till besök på webbplatsen. Du skapar en flödesvisualisering med **[!UICONTROL Campaign Name]** som dimension

![Namndimension för webbkampanj för flöde](assets/flowweb.png)

Du ersätter den sista **[!UICONTROL Campaign Name]**-dimensionen med dimensionen **[!UICONTROL Formatted Page Name]** och lägger till ytterligare en **[!UICONTROL Formatted Page Name]**-dimension i slutet av flödesvisualiseringen.

![Flöda webbkampanjnamn och webbsidesdimension](assets/flowweb-replace.png)

Du kan hålla muspekaren över något av flödena för att se mer information. Till exempel vilka kampanjer som har resulterat i en kundvagnsutcheckning.

![Flöda webbkampanjens namn och hovring över webbsidans dimension](assets/flowweb-hover.png)
