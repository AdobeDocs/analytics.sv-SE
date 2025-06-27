---
title: Flera rapportsviter
description: Lär dig hur du arbetar med flera rapportsviter i ett Analysis Workspace-projekt.
feature: Workspace Basics
role: User, Admin
exl-id: 0429ddd9-935f-44ef-ae1e-97bb02e6e2df
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# Flera rapportsviter

Du kan skapa projekt i Analysis Workspace med data från mer än en rapportserie. Rapportsviterna väljs på panelnivå så att du kan välja olika rapportsviter för varje panel i samma Workspace-projekt.

Den här funktionen är användbar om du vill:

* Jämför data från två olika regioner och data finns i två olika rapportsviter. Du kan skapa tabeller och visualiseringar för att jämföra data sida vid sida.

* Bygg en kontrollpanel med mätvärden och visualiseringar för att rapportera till andra organisationer. Ni kan hämta data från olika rapportsviter till samma projekt.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Flera rapportsviter](https://video.tv.adobe.com/v/32843?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


## Tillämpa rapportsviten på alla paneler

Du kan använda en rapportserie för alla paneler samtidigt genom att högerklicka på ett panelhuvud och välja **[!UICONTROL Apply Report Suite to All Panels]**.

![](assets/apply-rs-all-panels.png)

## Aktiv panel

Den aktiva panelen känns igen av den ljusblå kanten runt den. Välj bara den panelen i en panel.

>[!TIP]
>
>Du kan dra och släppa till valfri panel som finns i samma rapportserie som den aktiva panelen. Genom att dra till en inaktiv panel i samma rapportserie aktiveras panelen.
>

## Arbeta med flera rapportsviter

![](assets/mrs-ui.png)

1. Skapa ett nytt projekt med 2 eller fler paneler i Workspace.

1. Dra och släpp komponenter (mått, dimensioner, segment, datumintervall) på panelen. Se till att panelerna har data och visualiseringar som är specifika för deras rapportserie.


   >[!NOTE]
   >
   >Ibland visas en banderoll när du läser in ett projekt (eller byter till en rapportsserie) där inte alla komponenter som ingår i projektet ingår i rapportsviten. De komponenter som saknas listas. Följ [de här instruktionerna](/help/admin/admin-console/permissions/product-profile.md) om du vill ange behörigheter för de mått/mått som krävs.
   >

   ![](assets/incompat-rs.png)

   Du har tre alternativ för att hantera den här inkompatibiliteten:
   * Aktivera nödvändiga mått/mätvärden
   * Ändra rapportsviten.
   * Fortsätt med vissa komponenter som saknas. Detta resulterar inte i några data för dessa komponenter och/eller tomma visualiseringar.

1. Ändra panelen till en annan rapportsserie och observera hur komponentetiketten (för närvarande aktiv rapportsvit) och listade komponenter uppdateras baserat på den nya rapportsviten.

1. Använd ett kortkommando (`shift`) när du drar för att omvandla en inaktiv panel till en aktiv panel.

1. (Valfritt) Du kan också gå till andra komponentbyggare i Analytics och se till att de nu visar en etikett för rapportsviten som anger

   * Var ett segment skapas: [Segmentbyggare](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=sv-SE).
   * Där ett beräknat mått skapas: [Beräknad metrisk byggare](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=sv-SE).
   * Var en avisering byggs: [Varningsbyggaren](https://experienceleague.adobe.com/docs/analytics/components/alerts/alert-builder.html?lang=sv-SE).
