---
description: 'Anpassa användaråtkomsten på detaljnivå: eVars, trafikrapporter, lösningsrapporter och kundvägsrapporter.'
keywords: grupper;behörigheter
subtopic: Users and groups
title: Anpassa dimensionsbehörigheter
feature: Admin Tools
uuid: aaf164ad-3863-4129-864e-39ec71c6a8eb
exl-id: 51c4193a-426e-46a0-8494-163b58588157
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 13%

---

# Anpassa dimensionsbehörigheter

>[!IMPORTANT]
>
>Användar- och produkthanteringen övergår till [Admin Console](https://helpx.adobe.com/se/enterprise/using/admin-console.html). Adobe meddelar dig när det är dags att migrera användare. När alla kunder har migrerat kommer hjälpinnehåll för **[!UICONTROL Analytics]** > **[!UICONTROL Admin Tools]** > **[!UICONTROL User Management]** att tas bort.

Anpassa användaråtkomsten på detaljnivå: eVars, trafikrapporter, lösningsrapporter och kundvägsrapporter.

**[!UICONTROL User Management]** >  **[!UICONTROL Groups]** >  **[!UICONTROL Report Access]** >  **[!UICONTROL Dimensions]** >  **[!UICONTROL Customize]**

>[!IMPORTANT]
>
>Vissa dimensioner är inte tillåtna just nu. Dessa mått är: Längd på mobilbokmärke. Mobilenhetsnummer; Mobil DRM. Mobila informationstjänster. Mobile Java VM; Dekoration av mobil e-post; Mobile Net-protokoll, Mobiloperativsystem. Mobilt tryck för att prata.
>
>Dessa dimensioner är tillgängliga för alla användare, oavsett andra behörigheter.

Inställningarna på den här sidan gäller för de rapportsviter som har valts på sidan [!UICONTROL Define User Groups].

![](assets/permissions-dimensions.png)

Läs mer om behörighetskategorin nedan.

* eVars 1-250 är individuellt tillåtna.
* Alla trafikrapporter är dimensioner.
* Video- och mobilrapporter är dimensioner samt andra rapporter om analyslösningar (Experience Manager, Advertising Cloud, Social och så vidare).
* Matchningsrapporter är tillgängliga om en användare har åtkomst till den överordnade dimensionen.
* Alla aktuella dimensioner och mått i anpassade grupper har automatiskt migrerats till de nya kategorierna. Om en befintlig grupp har mätvärden aktiverade får den som standard alla nya tillåtna mått (eVars och innehållsmedvetna) och mätvärden.
* Behörigheter för klassificeringsimporteraren (tidigare SAINT): Åtkomsten till klassificeringar bestäms av åtkomsten till variabeln [som klassificeringen baseras på.](https://docs.adobe.com/content/help/en/analytics/components/classifications/c-classifications.html)

Mer information finns i [Ändringar av användar- och gruppbehörighet](https://docs.adobe.com/content/help/en/analytics/admin/user-product-management/user-management/permissions-changes.html).

**Anpassa Dimensioner**

Följande objekt är dimensioner som du kan ge behörighet.

<table id="table_F37D74A1619A4560A5F5651E855DAF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivningar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/admin/admin/conversion-var-admin/conversion-var-admin.md"> eVars </a> </p> </td> 
   <td colname="col2"> <p>eVars 1-250 är individuellt tillåtna. eVars är anpassade konverteringsvariabler som du använder för att segmentera framgångsvärden för konverteringar i anpassade rapporter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/sv-SE/analytics/implementation/vars/page-vars/evar.html"> Props </a> </p> </td> 
   <td colname="col2"> <p>Props är anpassade trafikvariabler. </p> <p>Se <a href="https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/evar.html"> Traffic Props and conversion eVars </a> in Analytics Implementation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/page-variables.html"> Hierarki </a> </p> </td> 
   <td colname="col2"> <p> Variabeln hierarki (hierN) bestämmer platsen för en sida i platsens hierarki eller sidstruktur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/page-variables.html"> Listvar  </a> </p> </td> 
   <td colname="col2"> <p> Listvariabler liknar hur funktionen List Props tillåter flera värden inom samma bildbegäran. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> </td> 
   <td colname="col2"> <p>Avser standardmått (färdiga) i Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://helpx.adobe.com/support/experience-manager.html"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://helpx.adobe.com/support/advertising-cloud.html"> AMO  </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/sv-SE/analytics/analyze/activity-map/activity-map.html"> Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Rapporteringsdimensioner för Activity Map: Activity Map Page Activity Map Link Activity Map Activity Map Link by Region; Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/sv-SE/media-analytics/using/media-overview.html"> Mobil </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comscore </p> </td> 
   <td colname="col2"> <p>Den här partnerintegreringen är inte längre aktiv. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html"> Nielsen  </a> </p> </td> 
   <td colname="col2"> <p>Den här partnerintegreringen är inte längre aktiv. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Social </p> </td> 
   <td colname="col2"> <p>Används inte. </p> </td> 
  </tr> 
 </tbody> 
</table>
