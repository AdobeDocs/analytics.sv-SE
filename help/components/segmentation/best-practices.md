---
title: Bästa praxis för segmentering
description: Skapa optimala segment som returnerar data effektivt.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---


# Bästa praxis för segmentering

Komplexa segment behövs ofta för att få fram önskade data. Om komplexa segment är ineffektiva och används i en stor rapportserie tar det betydligt längre tid att köra rapporter. Tänk på följande när du skapar eller redigerar ett segment för att minimera komplexiteten.

## Använd endast operatorn&quot;Innehåller&quot; som en sista utväg

Operatorn&quot;Innehåller&quot; är en av de mest bearbetningsintensiva funktionerna i segmentering, eftersom den måste analysera hela innehållet i varje värde. Använd andra operatorer som &quot;Börjar med&quot; eller &quot;Slutar med&quot; om de önskade värdena finns i början eller slutet av en sträng.

Om en Contains-operator i ett segment returnerar ett stort antal resultat, kommer rapporten oftast att sluta fungera. Om du till exempel har skapat ett segment där `Referrer equals "."`söker segmentet igenom innehållet i alla värden. Du kan använda operatorn &#39;Exists&#39; i stället.

## Använd klassificeringar för att gruppera dimensionsobjekt

Om du har många segmentvillkor kan de snabbt försämra segmentets prestanda. Upprepas till exempel `Page equals X or Page equals Y or Page equals Z` med hundratals olika värden. I stället för att skriva ut dessa hundratals villkor klassificerar du alla önskade värden i ett segment och använder sedan det klassificerade värdet i ett segment.

1. Skapa en klassificering för variabeln som du arbetar med.
2. Hämta klassificeringsmallen och öppna den i det kalkylblad eller den textredigerare du vill använda.
3. Ge varje dimensionsartikel som du vill inkludera i ditt segment samma värde.
4. Använd klassificeringsimporteraren för att importera kalkylbladet tillbaka till Adobe Analytics
5. När klassificeringen är klar skapar du ett segment med det klassificerade värdet.

Den här metoden ökar prestandan drastiskt och erbjuder ett enkelt sätt att ändra segmentvillkoren. I stället för att redigera segmentet med olika värden kan du lägga till eller ta bort dimensionsobjekt från klassificeringen.
