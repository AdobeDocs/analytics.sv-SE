---
description: Fältbeskrivningar i Dynamic Tag Management för referenser och kampanjalternativ när Dynamic Tag Management distribueras i Adobe Analytics.
keywords: Dynamic Tag Management;referrers;campaigns;referrer override;campaign variable;query param
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Referenter och kampanjer
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# Referenter och kampanjer

Fältbeskrivningar i [!UICONTROL Dynamic Tag Management] för referenser och kampanjalternativ vid distribution [!UICONTROL Dynamic Tag Management] i Adobe [!DNL Analytics].

**[!UICONTROL  *`Property`*]** > ![Kugghjulsikon](assets/settings_gear.png) **[!UICONTROL Edit Tool]** > **[!UICONTROL Referrers & Campaigns]**

<table id="table_09AE3BFF0F12442F9C19CD96451F93E4">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Element </th>
   <th colname="col2" class="entry"> Beskrivning </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Åsidosätt referent </td>
   <td colname="col2"> <p>Åsidosätter det värde som anges i variabeln <span class="varname"> s.reference</span> , som vanligtvis fylls i av den som har angett i webbläsaren. </p> <p>Se <a href="../../../vars/page-vars/referrer.md">hänvisare</a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Campaign </td>
   <td colname="col2"> <p>En variabel som identifierar marknadsföringskampanjer som används för att visa besökare på er webbplats. Värdet för kampanjen hämtas vanligtvis från en frågesträngsparameter. </p> <p>Se <a href="../../../vars/page-vars/campaign.md">kampanj</a>. </p> </td>
  </tr>
 </tbody>
</table>

Använd DTM-gränssnittet för att välja om du vill använda en frågesträng eller ett värde (som kan hämtas från ett dataelement):

![Frågeparameter](assets/dtm-queryparam.png)

Du kan antingen ange frågesträngen direkt i gränssnittet eller referera till ett separat dataelement om du har andra sätt att spåra en kampanj.
