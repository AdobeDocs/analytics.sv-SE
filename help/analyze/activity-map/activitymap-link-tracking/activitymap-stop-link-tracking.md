---
description: Steg för att stoppa länkspårning i Activity Map eller äldre ClickMap.
title: Stoppa länkspårning
uuid: e17fb7bd-d6ed-45c3-a006-9150d5718cff
feature: Activity Map
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 12%

---


# Stoppa länkspårning

Steg för att stoppa länkspårning i Activity Map eller äldre ClickMap.

<table id="table_1745199B3105467CBA26F50B3B1CCE99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Stoppa länkspårning i.. </th> 
   <th colname="col2" class="entry"> Gör det här.. </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> Ta bort följande innehåll från filen Appmeasurement.js: 
    <code>
     /*
     &nbsp;START&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;The&nbsp;following&nbsp;module&nbsp;enables&nbsp;Activity&nbsp;Map&nbsp;tracking&nbsp;in&nbsp;Adobe&nbsp;Analytics.&nbsp;Activity&nbsp;Map
     &nbsp;allows&nbsp;you&nbsp;to&nbsp;view&nbsp;data&nbsp;overlays&nbsp;on&nbsp;your&nbsp;links&nbsp;and&nbsp;content&nbsp;to&nbsp;understand&nbsp;how
     &nbsp;users&nbsp;engage&nbsp;with&nbsp;your&nbsp;web&nbsp;site.&nbsp;If&nbsp;you&nbsp;do&nbsp;not&nbsp;intend&nbsp;to&nbsp;use&nbsp;Activity&nbsp;Map,&nbsp;you
     &nbsp;can&nbsp;remove&nbsp;the&nbsp;following&nbsp;block&nbsp;of&nbsp;code&nbsp;from&nbsp;your&nbsp;AppMeasurement.js&nbsp;file.
     &nbsp;Additional&nbsp;documentation&nbsp;on&nbsp;how&nbsp;to&nbsp;configure&nbsp;Activity&nbsp;Map&nbsp;is&nbsp;available&nbsp;at:
     &nbsp;https://docs.adobe.com/content/help/en/analytics/analyze/activity-map/getting-started/get-started-admins/activitymap-enable.html
     */
     function&nbsp;AppMeasurement_Module_Activity&nbsp;Map(g){func
     ...
     /*&nbsp;END&nbsp;Activity&nbsp;Map&nbsp;MODULE&nbsp;*/
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClickMap (tidigare Visitor-ClickMap) </td> 
   <td colname="col2"> <p>Ställ in variabeln <a href="https://docs.adobe.com/content/help/en/analytics/implementation/vars/config-vars/configuration-variables.html"  > trackInlineStats</a> på false (detta är standardvärdet). Syntaxen är följande: 
     <code>
       s.trackInlineStats=false
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

