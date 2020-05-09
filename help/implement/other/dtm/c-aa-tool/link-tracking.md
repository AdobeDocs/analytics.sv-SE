---
description: Fältbeskrivningar i Dynamic Tag Management för länkspårning vid distribution av Analytics.
keywords: Dynamic Tag Management;link tracking;enable clickmap;track download links;download extensions;track outbound links;keep url parameters
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Länkspårning
uuid: 982b744b-5696-4c31-b1d1-410486b0eedd
translation-type: tm+mt
source-git-commit: 354785439a5920d8fc53d566fa9306c74e2504d2
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---


# Länkspårning

Fältbeskrivningar i Dynamic Tag Management för länkspårning vid distribution av Analytics.

**[!UICONTROL Property]** > ![Kugghjulsikon](assets/settings_gear.png) **[!UICONTROL Edit Tool]** > **[!UICONTROL Link Tracking]**

<table id="table_F23FB0B284E74B66A107B1D69D22A51C">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Element </th>
   <th colname="col2" class="entry"> Beskrivning </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Aktivera ClickMap </td>
   <td colname="col2"> <p>Avgör om klickmappningsdata för besökare samlas in. </p> <p>Se <a href="../../../vars/config-vars/trackinlinestats.md">trackInlinestatus</a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Spåra nedladdningslänkar </td>
   <td colname="col2"> <p>Spårar länkar till hämtningsbara filer på din plats. </p> <p>Se <a href="../../../vars/config-vars/trackdownloadlinks.md">trackDownloadLinks</a>.</p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Hämta tillägg </td> 
   <td colname="col2"> <p>Om webbplatsen innehåller länkar till filer med något av de angivna tilläggen, visas URL-adresserna för länkarna i rapporten. </p>Se <a href="../../../vars/config-vars/linkdownloadfiletypes.md">linkDownloadFileTypes</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Spåra utgående länkar </td>
   <td colname="col2"> <p>Avgör om en länk som klickas är en avslutningslänk. </p> <p>Se <a href="../../../vars/config-vars/trackexternallinks.md">trackExternalLinks</a>. </p> <p><b>Överväganden om ensidiga appar: </b>På grund av hur vissa SPA-webbplatser kodas kan en intern länk till en sida på SPA-webbplatsen se ut som om den är en utgående länk. </p> <p>Du kan använda någon av följande metoder för att spåra utgående länkar från SPA-platser: </p>
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9">
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>Om du inte vill spåra några utgående länkar från ditt SPA infogar du en post i avsnittet <span class="wintitle"> Spåra</span> aldrig. </p> <p>Till exempel <span class="filepath"> https://testsite.com/spa/#</span> </p> <p>Alla # länkar till den här värden ignoreras. Alla utgående länkar till andra värdar spåras, till exempel <span class="filepath"> https://www.google.com</span>. </p> </li>
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>Om det finns länkar som du vill spåra i ditt SPA använder du avsnittet <span class="wintitle"> Spåra alltid</span> . </p> <p>Om du till exempel har en <span class="filepath"> spa/#/about</span> -sida kan du placera "about" i <span class="wintitle"> Alltid Track</span> -avsnittet. </p> <p>Om-sidan är den enda utgående länken som spåras. Eventuella andra länkar på sidan (till exempel <span class="filepath"> https://www.google.com</span>) spåras inte. </p> </li>
    </ul> <p>Observera att dessa två alternativ utesluter varandra. </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> Behåll URL-parametrar </td>
   <td colname="col2"> <p>Bevarar frågesträngar. </p> <p>Se <a href="../../../vars/config-vars/linkleavequerystring.md">linkLeaveQueryString</a>. </p> </td>
  </tr>
 </tbody>
</table>
