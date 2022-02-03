---
title: Skapa anteckningar
description: Så här skapar du anteckningar i Workspace.
role: User, Admin
source-git-commit: 6b5fd4e25056d7efbf3119a4d55d2e0a7897965f
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 0%

---


# Skapa anteckningar

>[!NOTE]
>
>Den här funktionen är för närvarande i begränsad testning.

1. Du kan skapa anteckningar på fyra sätt:

   * Gå till [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Annotation]. Sidan Annotations Manager öppnas. Klicka [!UICONTROL Create New Annotation] och Annotation Builder öppnas.

   * Högerklicka på en punkt i en tabell eller ett linjediagram. Anteckningsverktyget öppnas. Observera att som standard visas anteckningar som skapats på det här sättet bara i det projekt där de skapades. Men du kan göra dem tillgängliga för alla projekt.

   * Gå till [!UICONTROL Components] > [!UICONTROL Create annotation]. Anteckningsverktyget öppnas.

   * Använd den här snabbtangenten för att öppna Anteckningsverktyget:
      * (PC) `ctrl` `shift` + o
      * (Mac) `shift` + `command` + o

1. Fyll i elementen i Anteckningsverktyget.

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
   | [!UICONTROL Apply to all projects] | Som standard gäller anteckningen det aktuella projektet. Genom att markera den här rutan kan du göra så att anteckningen gäller för alla projekt som du äger. Observera att den här kryssrutan bara visas när du startar Anteckningsverktyget från Anteckningsverktyget? |

1. Klicka på [!UICONTROL Save].

## Skapa anteckningar från en [!UICONTROL Line] diagram

1. Från en [!UICONTROL Line] välj en dip eller en spik i [!UICONTROL Line] och högerklicka på det. En popup som anropas **[!UICONTROL Annotate selection]** visas.

   ![](assets/annotate-line.png)

1. Klicka på **[!UICONTROL Annotate selection]**. Anteckningsverktyget öppnas.

>[!NOTE]
>
>Observera anteckningen som endast gäller för projektet. Markera kryssrutan om du vill att anteckningen ska vara tillgänglig för alla dina projekt.

1. Fyll i uppgifterna enligt ovan. Observera att datumet/datumen och eventuella mätvärden osv. redan har fyllts i.

## Skapa en anteckning inifrån en frihandsritabell

1. Fortsätt som för ett linjediagram, men högerklicka på en rad i tabellen som behöver kommenteras.

1. Välj **[!UICONTROL Create annotation from selection]**.

   ![](assets/annotate-table.png)

1. Fyll i uppgifterna enligt ovan. Observera att datumet/datumen och eventuella mätvärden osv. redan har fyllts i.

