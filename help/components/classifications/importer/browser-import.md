---
description: Du kan importera (överföra) klassificeringsdata via webbläsaren. Den här metoden begränsar din överföring av klassificeringsdata till en enda rapportserie
subtopic: Classifications
title: Import via webbläsare
feature: Administratörsverktyg
uuid: 56dfbf4c-36e6-49f4-b5cb-8ab714432825
exl-id: 5bef1f6d-9b27-464d-8343-472f300a7437
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 4%

---

# Import via webbläsare

Du kan importera (överföra) klassificeringsdata via webbläsaren. Den här metoden begränsar din överföring av klassificeringsdata till en enda rapportserie

## Import via webbläsare {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

Du kan importera (överföra) klassificeringsdata via webbläsaren. Den här metoden begränsar din överföring av klassificeringsdata till en enda rapportserie

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**

## Import av klassificeringsläsare - fältbeskrivningar {#section_F628C47081DA4026A4D30E3D3454B1DA}

<table id="table_7FC7E510E7E74C2D9E8F316C5C6B66DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Välj Report Suite </td> 
   <td colname="col2"> <p>Rapportsviten där du vill importera klassificeringsdata. Importdatafilen måste matcha datauppsättningens format i rapportsviten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Datauppsättning som ska klassificeras </td> 
   <td colname="col2"> <p>Den datauppsättning som ska ta emot klassificeringarna. Listrutan innehåller alla rapporter i rapportsviterna som är konfigurerade för klassificeringar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Välj den fil som ska importeras </td> 
   <td colname="col2"> <p>Gör att du kan bläddra till den importdatafil som du vill överföra. </p> <p>Obs!  Storleksgränsen för överföring av filer är 1 MB. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Skriv över data i konflikter </td> 
   <td colname="col2"> <p>Skriver automatiskt över befintliga data som står i konflikt med importerade data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hämta klassificeringsfilen automatiskt när importen är klar </td> 
   <td colname="col2"> <p>Hämtar automatiskt en tabbavgränsad fil som representerar datauppsättningen med de nyligen överförda klassificeringsdata. Adobe genererar automatiskt den här filen åt dig om importen skapar unika ID:n eller om fel uppstår. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Importera klassificeringar via webbläsaren {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

<!-- 

t_upload_a_saint_data_file_via_web_browser.xml

 -->

1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Klicka på **[!UICONTROL Import File]**.
1. Konfigurera fälten **[!UICONTROL Browser Import]**.
1. Klicka på **[!UICONTROL Import File]**.
1. Titta på statusfönstret för att bearbeta meddelanden.
1. (Villkorligt) Om du valde **[!UICONTROL Automatically Download Classification File After Upload is Complete]** anger du var du vill spara den resulterande filen när bearbetningen är klar.
>Om importen lyckas visas omedelbart de ändringar som gjorts i en export. Dataändringar i rapporter tar dock upp till fyra timmar vid användning av en webbläsarimport och upp till 24 timmar vid användning av en FTP-import.
