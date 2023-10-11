---
title: Hantera anteckningar
description: Hantera anteckningar i Workspace.
role: User, Admin
feature: Annotations
exl-id: 37a538cc-9ea7-4cb1-8ee8-e8e474ad5b08
source-git-commit: 4f0bd39b64535be8ba55e97d65177f6ef291ef6c
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 0%

---

# Hantera anteckningar

The [!UICONTROL Annotations manager] visar alla anteckningar som du äger eller som har delats med dig. Projektspecifika anteckningar visas inte här. Du kan använda det här gränssnittet för att dela, filtrera, tagga, kopiera, ta bort och favoritanteckningar. Administratörer kan hantera och godkänna anteckningar.

**[!UICONTROL Components]** > **[!UICONTROL Annotations]**

## Annotations Manager-användargränssnitt

![](assets/annotation-mgr.png)

| Gränssnittselement | Beskrivning |
| --- | --- | 
| [!UICONTROL Title and Description] | Finns i Annotations Builder. Om du vill redigera titeln och beskrivningen klickar du på titellänken. Då återgår du till Anteckningsverktyget. |
| [!UICONTROL Report Suite] | Rapporten innehåller sviter som den här anteckningen gäller för. |
| [!UICONTROL Owner] | Anger vem som äger anteckningen. Som icke-administratör kan du bara se anteckningar som du äger eller de som delats med dig. |
| [!UICONTROL Applied Date Range] | Det datum eller datumintervall som den här anteckningen gäller för. |
| [!UICONTROL Shared with] | Visar hur många personer eller grupper som du har delat anteckningen med. Klicka för mer information. |
| [!UICONTROL Date Modified] | Visar datum och tid då anteckningen senast ändrades. |

{style="table-layout:auto"}

## Redigera anteckningar

Att redigera en anteckning innebär att du kan justera datumintervall, färger, omfång eller om det gäller alla rapportsviter eller projekt. Du kan redigera anteckningar på två sätt:

* Håll pekaren över anteckningen i ett linjediagram och klicka på pennikonen i pekaren.
* I [!UICONTROL Annotations Manager]klickar du på anteckningens titel.

Båda dessa alternativ ger dig tillbaka i [!UICONTROL Annotations Builder]. Där kan du göra nödvändiga justeringar och spara den nya versionen.

## Dela anteckningar

När du delar anteckningar eller arbetar med anteckningar som delats med dig bör du tänka på följande:

* Om du skapar ett projekt med endast projektanteckningar och sedan delar projektet med en annan användare, kan anteckningarna inte redigeras eller tas bort av någon som du delar projektet med.
* Om du sparar en anteckning och delar den direkt med en användare, kan han/hon bara redigera/ta bort anteckningen om han/hon har administratörsbehörighet.
* Om ett projekt delas med dig med en anteckning som bara innehåller ett projekt visas det bara i det projektet. Om anteckningen delas direkt med dig visas den i alla projekt där anteckningen kan visas.

## Anteckningar och tidszoner

Alla anteckningar skapas med en tidsstämpel, men inga timmar- eller tidszonsinformation. Vid rapporttillfället används alltid tidszonen för panelens rapportserie. En anteckning som skapats för juldagen inträffar till exempel den 25 december, oavsett vilken tidszon du befinner dig i.

## Andra anteckningsuppgifter

Med Annotations Manager kan administratörer redigera, lägga till, tagga, ta bort, byta namn på, godkänna, kopiera, exportera och filtrera anteckningar. Den är inte synlig för användare som inte är administratörer.

Ytterligare alternativ är tillgängliga när du väljer minst en anteckning:

| Uppgift | Beskrivning |
| --- | --- |
| [!UICONTROL Add] | Gå till Anteckningsverktyget där du kan skapa anteckningar. |
| [!UICONTROL Tag] | Alla användare kan skapa taggar för anteckningar och använda en eller flera taggar för en anteckning. Men du kan bara se taggar för anteckningar som du äger. |
| [!UICONTROL Delete] | Om du tar bort en anteckning tas den bort från alla projekt i organisationen. |
| [!UICONTROL Rename] | Om du ändrar namn på en anteckning ändras namnet i alla projekt som den används i. |
| [!UICONTROL Copy] | Skapar en distinkt kopia med sitt eget antecknings-ID, men med samma namn och definition. |
| [!UICONTROL Export to CSV] | Exportera anteckningsdefinitionen till en CSV-fil. |
| [!UICONTROL Filter] (vänster räl) | Filtrera efter taggar, rapportsvit, ägare och andra filter (Min, Godkänd, Favoriter, Delad med mig och Visa alla). |

{style="table-layout:auto"}
