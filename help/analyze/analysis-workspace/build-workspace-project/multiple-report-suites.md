---
title: Flera rapportsviter
description: Lär dig hur och varför du skapar projekt i Workspace med flera rapportsviter
feature: Grundläggande om arbetsytan
role: User, Admin
exl-id: 0429ddd9-935f-44ef-ae1e-97bb02e6e2df
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 0%

---

# Flera rapportsviter

Nu kan du skapa projekt i Analysis Workspace med data från mer än en rapportserie. Rapportsviterna väljs nu på panelnivå så att du kan välja olika rapportsviter för varje panel i samma Workspace-projekt.

Den här funktionen är användbar om du t.ex. vill

* Jämför data från två olika regioner och data finns i två olika rapportsviter. Du kan skapa tabeller och visualiseringar för att jämföra data sida vid sida.

* Bygg en kontrollpanel med mätvärden och visualiseringar för att rapportera till andra organisationer. Nu kan ni hämta data från olika rapportsviter till samma projekt.

## Tillämpa rapportsviten på alla paneler

Du kan använda en rapportserie för alla paneler samtidigt genom att högerklicka på ett panelhuvud och välja **[!UICONTROL Apply Report Suite to All Panels]**.

![](assets/apply-rs-all-panels.png)

## Aktiv panel

Vi introducerar begreppet&quot;aktiv panel&quot; jämfört med&quot;inaktiv panel&quot; med den här funktionen. Den aktiva panelen känns igen av den ljusblå kanten runt den. Om du klickar inuti en panel blir panelen den aktiva panelen.

>[!IMPORTANT]
>Du kan dra och släppa till valfri panel som finns i samma rapportserie som den aktiva panelen. Genom att dra till en inaktiv panel i samma rapportserie aktiveras panelen.

| Uppgift | Aktiv panel | Inaktiv panel |
|---|---|---|
| Byt rapportsvit | Ja | Nej |
| Dra och släppa komponenter | Ja | Ja, för alla paneler som finns i samma rapportsserie som den aktiva panelen. |
| Dra och släpp visualiseringar | Ja | Ja, för alla paneler som finns i samma rapportsserie som den aktiva panelen. |

## Arbeta med flera rapportsviter

![](assets/mrs-ui.png)

1. Skapa ett nytt projekt med 2 eller fler paneler i Workspace.

1. Dra och släpp komponenter (mått, dimensioner, segment, datumintervall) på panelen. Se till att panelerna har data och visualiseringar som är specifika för deras rapportserie.


   >[!NOTE]
   >Ibland visas en banderoll när ett projekt läses in (eller när du växlar till en rapportsvit) där inte alla komponenter som ingår i projektet ingår i rapportsviten. De komponenter som saknas listas. Följ [de här instruktionerna](/help/admin/admin-console/permissions/product-profile.md) för att ange behörigheter för de mått/mått som krävs.

   ![](assets/incompat-rs.png)

   Du har tre alternativ för att hantera den här inkompatibiliteten:
   * Aktivera nödvändiga mått/mått
   * Ändra rapportsviten.
   * Fortsätt med vissa komponenter som saknas. Detta resulterar inte i några data för dessa komponenter och/eller tomma visualiseringar.

1. Ändra panelen till en annan rapportsserie och observera hur komponentetiketten (för närvarande aktiv rapportsvit) och listade komponenter uppdateras baserat på den nya rapportsviten.

1. Använd ett kortkommando (`shift`) när du drar för att omvandla en inaktiv panel till en aktiv panel.

1. (Valfritt) Du kan också gå till andra komponentbyggare i Analytics och se till att de nu visar en etikett för rapportsviten som anger

   * Var ett segment ska skapas: [Segmentbyggare](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html).
   * Där ett beräknat mätvärde skapas: [Beräknad metrisk byggare](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html).
   * Var en varning ska skapas: [Varningsbyggaren](https://experienceleague.adobe.com/docs/analytics/components/alerts/alert-builder.html).
