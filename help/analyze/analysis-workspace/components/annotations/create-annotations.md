---
title: Skapa anteckningar
description: Så här skapar du anteckningar i Workspace.
role: User, Admin
source-git-commit: 89cbecf109a8fa9a9fac1f1ed8ad198ffdd398d3
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---


# Skapa anteckningar

>[!NOTE]
>
>Den här funktionen är för närvarande i begränsad testning.

1. Du kan skapa anteckningar på fyra sätt:

   * Gå till [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Annotation]. Sidan Annotations Manager öppnas. Klicka [!UICONTROL Create New Annotation] och Annotation Builder öppnas.

   * Högerklicka på en punkt i en tabell eller ett linjediagram. Anteckningsverktyget öppnas.

   * Gå till [!UICONTROL Components] > [!UICONTROL Create annotation]. Anteckningsverktyget öppnas.

   * Använd den här snabbtangenten för att öppna Anteckningsverktyget:
      * (PC) `ctrl` `shift` + o
      * (Mac) `shift` + `command` + o

1. Fyll i Builder-elementen.

   ![](assets/ann-builder.png)

   | Element | Beskrivning |
   | --- | --- |
   | [!UICONTROL Title] | Namnge anteckningen, t.ex. &quot;Memorial Day&quot; |
   | [!UICONTROL Description] | (Valfritt) Ange en beskrivning för anteckningen, t.ex. &quot;Offentlig semester i USA&quot;. |
   | [!UICONTROL Tags] | (Valfritt) Ordna anteckningar genom att skapa eller använda en tagg. |
   | [!UICONTROL Applied date] | Välj det datum eller datumintervall som måste finnas för att anteckningen ska kunna visas. |
   | [!UICONTROL Color] | Använd en färg på anteckningen. Anteckningen visas i projektet med den valda färgen. Färg kan användas för att kategorisera anteckningar, t.ex. allmänna helgdagar, externa händelser, spårningsproblem. |
   | [!UICONTROL Scope] | (Valfritt) Dra och släpp mätvärdena som utlöser anteckningen. Dra och släpp sedan de dimensioner eller segment som fungerar som filter (d.v.s. som anteckningen ska vara synlig med). Om du inte anger ett omfång kommer anteckningen att gälla för alla dina data.<ul><li>**[!UICONTROL Any of these metrics are present]**: Dra och släpp upp till 10 mätvärden som utlöser den anteckning som ska visas.</li><li>**[!UICONTROL With all of these filters]**: Dra och släpp upp till 10 dimensioner eller segment som ska filtreras när anteckningen visas.</li></ul><p>Användningsexempel: En eVar har slutat samla in data för ett visst datumintervall. Dra eVar till **[!UICONTROL Any of these metrics are present]** -dialogrutan. Eller [!UICONTROL Visits] inga data rapporteras. Följ samma process. |
   | [!UICONTROL Apply to all report suites] | Som standard gäller anteckningen för den ursprungliga rapportsviten. Genom att markera den här rutan kan du göra så att anteckningen gäller för alla rapportsviter i företaget. |
   | [!UICONTROL Apply to all projects] | Som standard gäller anteckningen det aktuella projektet. Genom att markera den här rutan kan du göra så att anteckningen gäller för alla projekt som du äger. Observera att den här kryssrutan bara visas när du startar Anteckningsverktyget från Anteckningshanteraren. |

1. Klicka på [!UICONTROL Save].