---
description: Innan du börjar skapa virtuella rapportsviter bör du tänka på några saker.
keywords: Virtual Report Suite
title: Skapa virtuella rapportsviter
feature: Rapporter och analyser - Grunderna och analyser
uuid: 022a6656-808e-4c92-b7ec-4d2a42e84fa8
exl-id: 5ff6ff1a-5b99-41cc-a3a7-928197ec9ef9
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 4%

---

# Skapa virtuella rapportsviter

Innan du börjar skapa virtuella rapportsviter bör du tänka på några saker.

* Användare som inte är administratörer kan inte se Virtual Report Suite Manager.
* Virtuella rapportsviter kan inte delas. Delning görs via grupper/behörigheter.
* I Virtual Report Suite Manager kan du bara se dina egna virtuella rapportsviter. Du måste klicka på &quot;visa alla&quot; för att se alla andras.

1. Navigera till **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]**.
1. Klicka på **[!UICONTROL Add +]**.

   ![](assets/new_vrs.png)

1. Fyll i fälten:

<table id="table_0F85B56480BB46CBA5BE236BBD70156D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Namn </td> 
   <td colname="col2"> <p>Namnet på den virtuella rapportsviten ärvs inte från den överordnade rapportsviten och ska vara distinkt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Beskrivning </td> 
   <td colname="col2"> <p>Lägg till en bra beskrivning för dina företagsanvändare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Taggar </td> 
   <td colname="col2"> <p>Du kan lägga till taggar för att ordna dina rapportsviter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupper </td> 
   <td colname="col2"> <p>Välj de behörighetsgrupper som du vill ska ha åtkomst till detta VRS. (Du kan också hantera gruppbehörigheter från <span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> Användarhantering</span> &gt; <span class="uicontrol"> Grupper</span></span>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Överordnad Report Suite </td> 
   <td colname="col2"> <p>Rapportsviten som den här virtuella rapportsviten ärver följande inställningar. De flesta tjänstenivåer och funktioner (till exempel eVar, bearbetningsregler, klassificeringar och så vidare) ärvs. Om du vill ändra de här ärvda inställningarna för ett VRS måste du redigera den överordnade rapportsviten (<span class="ignoretag"><span class="uicontrol"> Admin</span> &gt; <span class="uicontrol"> Rapportsviter</span></span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tidszon </td> 
   <td colname="col2"> <p>Det är valfritt att välja en tidszon. </p> <p>Om du väljer en tidszon sparas den tillsammans med VRS. Om du inte väljer någon tidszon används den överordnade rapportsvitens tidszon. </p> <p>När du redigerar ett VRS-system visas den tidszon som har sparats med VRS i den nedrullningsbara väljaren. Om VRS skapades innan tidszonsstödet lades till visas den överordnade rapportsvitens tidszon i den nedrullningsbara väljaren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Segment </td> 
   <td colname="col2"> <p>Du kan lägga till endast ett segment eller <a href="https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html"  > stacksegment</a>. </p> <p> <p>Obs!  När du staplar två segment förenas de med en AND-programsats. Detta kan inte ändras till en OR-sats. </p> </p> <p>När du försöker ta bort eller ändra ett segment som för närvarande används i en virtuell rapportserie visas en varning. </p> </td> 
  </tr> 
 </tbody> 
</table>
