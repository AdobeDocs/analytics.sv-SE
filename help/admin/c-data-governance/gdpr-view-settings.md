---
description: Dialogrutan Datastyrning i Administratörsverktyg ger en översikt över vilka rapportsviter som har konfigurerats för datastyrning, om de har mappats till en Experience Cloud-organisation och om det finns en policy om datalagring för den här rapportsviten.
title: Visa/hantera inställningar för datastyrning i rapportsviten
uuid: f3b83e8e-00af-4a60-a5de-29b5c43f6788
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 98%

---

# Visa/hantera inställningar för datastyrning i rapportsviten

Dialogrutan Datastyrning i Administratörsverktyg ger en översikt över vilka rapportsviter som har konfigurerats för datastyrning, om de har mappats till en Experience Cloud-organisation och om det finns en policy om datalagring för den här rapportsviten.

1. Logga in på Adobe Experience Cloud.
1. Navigera till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Data Governance]**.

   Du ser alla rapportsviter som ingår i ditt inloggningsföretag:

   ![](assets/privacy_setup_an.png)

<table id="table_448292730FF0475E9DCB731882F9A29B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Inställning </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Rapportsviter </p> </td> 
   <td colname="col2"> <p>På den första raden visas rapportsvitens egna namn. Den andra raden innehåller rapportsvitens interna namn. Om du kan ange etiketter för en rapportsvit blir den första raden en klickbar länk som tar dig till etikettsidan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Organisationsmappning </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EF8F613B0C5E42D19DB60BD0C89C114B"> 
     <li id="li_B35EE88555F547EFBF55ADE9D0C9EC3B"><b>Mappad</b>: Den här rapportsviten har redan mappats till samma Experience Cloud-organisation som det Analytics-inloggningsföretag du är inloggad på. Endast rapportsviter som har den här inställningen kan etiketteras. </li> 
     <li id="li_4E800BF80CFF477BAA091EF272D9071C"><b>Mappa rapportsvit</b>: Om du klickar på den här länken kan du <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/report-suite-mapping.html"> mappa en rapportsvit </a> till en Experience Cloud-organisation. <p>Det innebär att du omdirigeras till sidan Experience Cloud-organisation – Administratör för mappning av rapportsvit där du måste hitta rapportsviten och tilldela den till rätt organisation. Sedan går du tillbaka till det här användargränssnittet för datastyrning. </p> </li> 
     <li id="li_FF825A65D089487BBF5FCB0D74D41CD7"><b>Mappad till en annan organisation</b>: En annan Experience Cloud-organisation har redan mappat den här rapportsviten till sin organisation. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Policy för datalagring </p> </td> 
   <td colname="col2"> <p>Implementeringen av datasekretess i Analytics kräver att du har en policy för datalagring. </p> <p>Den här inställningen visar om: </p> 
    <ul> 
     <li>det finns en policy för datalagring för den här rapportsviten, och </li> 
     <li>Hur länge Adobe lagrar data innan de raderas. Standardperioden för datalagring är 25 månader. </li> 
    </ul> <p>Obs! Adobe Analytics kan inte hjälpa dig med att behandla begäranden till API:n för datasekretess, d.v.s. behandla de begäranden om åtkomst eller borttagning som du mottar från dina slutanvändare, om datalagringsperioden inte har ställts in. Kontakta din Customer Success Manager för att ange din datalagringsperiod. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Grupper </p> </td> 
   <td colname="col2"> <p>Grupperingsfunktionen är för närvarande inte implementerad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vänster sidofält </p> </td> 
   <td colname="col2"> <p>Klicka på kanalikonen för att öppna eller stänga sidorutan. </p> <p>I avsnittet Organisationsmappning visas antalet rapportsviter som tillhör de beskrivna kategorierna. </p> <p>Avsnittet för Policy för datalagring visar varje unik policy för datalagring som finns för din organisation och antalet rapportsviter som har tilldelats den lagringspolicyn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exportera till CSV </p> </td> 
   <td colname="col2"> <p>Om du markerar kryssrutan bredvid en eller flera rapportsviter visas alternativet <span class="uicontrol"> Exportera till CSV </span>. Med det här alternativet kan du hämta en CSV-fil som innehåller alla aktuella etikettdefinitioner för alla variabler för alla valda rapportsviter. </p> <p>Vi rekommenderar att ditt juridiska team granskar dina etikettval och det här alternativet underlättar den här granskningen. I stället för att behöva utföra granskningen när du är inloggad i användargränssnittet för datastyrning kan du dela .CSV-filen med dem. </p> <p><img placement="break"  src="assets/export_csv.png" width="300px" id="image_5FE821B2D07B402D8E0F6FE53D6FC52E" /> </p> </td> 
  </tr> 
 </tbody> 
</table>
