---
description: Med ett interdimensionellt flöde kan du undersöka användarsökvägar i olika dimensioner.
title: Intradimensionella flöden
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
feature: Visualiseringar
role: User, Admin
exl-id: f84917a4-2c07-48fb-9af3-d96c537da65c
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# Intradimensionella flöden

Med ett interdimensionellt flöde kan du undersöka användarsökvägar i olika dimensioner.

En dimensionsetikett högst upp i varje Flow-kolumn gör det mer intuitivt att använda flera dimensioner i en flödesvisualisering:

![](assets/flow.png)

Vi ska titta på två användningsfall: ett exempel på appanvändning och ett exempel på webbanvändning.

## Använd fall ett: app {#section_3D31D37B9C9F4134AE46C96291E41294}

Dimensionen [!UICONTROL Action Name] lades till i flödet, där det översta returnerade objektet var [!UICONTROL ItemAdded]:

![](assets/multi-dimensional-flow.png)

Om du vill utforska interaktionen mellan skärmar/sidor och åtgärder i den här appen kan du dra siddimensionen till flera platser, beroende på vad du vill utforska:

* Dra den till valfri ände av släppzonen (inuti den svarta trimmade rektangulära zonen som visas) för att **ersätta** det övre resultatet i ändarna:

   ![](assets/multi-dimensional-flow2.png) ![](assets/multi-dimensional-flow3.png)

* Dra den till det tomma utrymmet på slutet (lägg märke till den svarta parentesen) för att **lägga till i** visualiseringen:

   ![](assets/multi-dimensional-flow4.png)

Här är resultatet om du bestämmer dig för att ersätta ItemScaled-objektet i den högra kolumnen med Page-dimensionen. Det översta resultatet ändras nu till det översta resultatet för siddimensionen:

![](assets/multi-dimensional-flow5.png)

Nu kan ni se hur kunderna rör sig genom åtgärder och sidor. Du kan utforska flödet ytterligare genom att klicka på olika noder:

![](assets/multi-dimensional-flow6.png)

Detta är vad som händer om du lägger till en annan Action Name-dimension i slutet av visualiseringen:

![](assets/multi-dimensional-flow7.png)

Detta ger vissa djupgående insikter och möjlighet att ändra appen som du analyserar.

## Använd fall två: webb {#section_8D55983FA0C84926995270052AE01CD8}

Det här användningsexemplet visar hur ni kan analysera vilka kampanjer som leder till flest poster på en webbplats.

Dra Campaign Name-dimensionen till ett nytt flöde:

![](assets/multi-dimensional-flow8.png)

Nu vill jag se till vilka sidor dessa kampanjer genererar trafik, så jag drar siddimensionen åt höger om flödesresultaten för att lägga till ytterligare i visualiseringen:

![](assets/multi-dimensional-flow9.png)
