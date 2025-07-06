---
title: Bästa praxis
description: Lär dig några av de bästa metoderna för segmentering.
feature: Segmentation
exl-id: 4115a804-5063-430a-b9d3-2b64b26ca4d8
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# Bästa praxis för segmentering

Komplexa segment behövs ofta för att få fram önskade data. Om komplexa segment är ineffektiva och används i en stor rapportserie tar det betydligt längre tid att köra rapporter. Tänk på följande när du skapar eller redigerar ett segment för att minimera komplexiteten.

## Använd bara operatorn `Contains` som sista utväg

Operatorn [**[!UICONTROL Contains]**](/help/components/segmentation/seg-reference/seg-operators.md) är en av de mest bearbetningsintensiva funktionerna i segmentering, eftersom operatorn måste analysera hela innehållet i varje värde. Använd andra operatorer som **[!UICONTROL Starts with]**eller **[!UICONTROL Ends with]**om de önskade värdena finns i början eller slutet av en sträng.

Om en **[!UICONTROL Contains]**-operator i ett segment returnerar ett stort antal resultat, kommer rapporten oftast att sluta fungera. Om du till exempel har skapat ett segment där **[!UICONTROL Referrer]** **[!UICONTROL equals]** `"."` genomsöks innehållet i alla värden. Använd operatorn **[!UICONTROL Exists]** i stället.

## Använd klassificeringar för att gruppera dimensionsobjekt

Om du har många segmentvillkor kan de snabbt försämra segmentets prestanda. Exempel: **[!UICONTROL Page]** **[!UICONTROL equals]** `X` **[!UICONTROL OR]** **[!UICONTROL Page]** **[!UICONTROL equals]** `Y` **[!UICONTROL OR]** **[!UICONTROL Page]** **[!UICONTROL equals]** `Z` repeterat med hundratals olika värden. I stället för att skriva ut dessa hundratals villkor klassificerar du alla önskade värden i ett segment och använder sedan det klassificerade värdet i ett segment.

1. Skapa en klassificering för variabeln som du arbetar med.
2. Ladda ned klassificeringsmallen och öppna den i det kalkylblad eller den textredigerare du vill använda.
3. Ge varje dimensionsartikel som du vill inkludera i ditt segment samma värde.
4. Använd klassificeringsimporteraren för att importera kalkylbladet tillbaka till Adobe Analytics
5. När klassificeringen är klar skapar du ett segment med det klassificerade värdet.

Den här metoden ökar prestandan drastiskt och erbjuder ett enkelt sätt att ändra segmentvillkoren. I stället för att redigera segmentet med olika värden kan du lägga till eller ta bort dimensionsobjekt från klassificeringen.
