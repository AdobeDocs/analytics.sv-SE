---
description: Distribuera Adobe Analytics med dynamisk tagghantering genom att skapa Adobe Analytics-verktyget och konfigurera sidkoden antingen automatiskt eller manuellt. Den automatiska metoden rekommenderas för de flesta användare.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;analytics tool;property;tool type;tool name;configuration method;analytics premium;evars;events
title: Lägg till Adobe Analytics-verktyg
topic: Developer and implementation
uuid: 1c54331e-de03-4f44-8002-a19723c585b0
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 8%

---


# Lägg till Adobe Analytics-verktyg

Distribuera Adobe Analytics med dynamisk tagghantering genom att skapa Adobe Analytics-verktyget och konfigurera sidkoden antingen automatiskt eller manuellt. Den automatiska metoden rekommenderas för de flesta användare.

>[!NOTE]
>
>För förbättrad besöksspårning rekommenderar vi att du aktiverar [identitetstjänsten](https://docs.adobe.com/content/help/sv-SE/id-service/using/home.html).

## Add an Adobe Analytics Tool {#section_D5066B21581B4F7F811AD0027BF44EA5}

1. Klicka på  **[!UICONTROL  *`Web Property Name`*]** > **[!UICONTROL Overview]** > **[!UICONTROL Add a Tool]** > **[!UICONTROL Adobe Analytics]** .

   ![](assets/dtm-add-analytics-tool.png)

1. Fyll i fälten:

<table id="table_1CFB53FE72E74CCB8CAA5D4E3873D286"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Verktygstyp </p> </td> 
   <td colname="col2">Typ av verktyg, t.ex. <span class="keyword"> Adobe Analytics</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Verktygsnamn </p> </td> 
   <td colname="col2">Ett beskrivande namn för det här verktyget. Det här namnet visas på fliken <span class="wintitle"> Översikt</span> under <span class="wintitle"> Installerade verktyg</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p>Konfigurationsmetod </p> </td> 
   <td colname="col2"> <p> <b>Automatiskt</b> (rekommenderas): Använd dynamisk tagghantering för att hantera konfigurationen. Med den här metoden kan <span class="keyword"> Adobe Analytics</span> -rapportsviter synkroniseras automatiskt via ett <span class="keyword"> Experience Cloud</span> -inloggnings- eller Web Services-ID och AppMeasurement-koden hanteras. </p> <p>När kontona har anslutits hämtar Dynamic Tag Management <span class="keyword"> Adobe Analytics</span> -rapportsvitens ID:n och namn till verktygskonfigurationsgränssnittet, vilket ger snabbare driftsättning med mindre risk för användarfel. </p> <p> <p>Obs! Du måste välja alternativet <span class="wintitle"> Automatisk</span> om du är <span class="keyword"> Adobe Analytics Premium</span> -kund. </p> </p> <p>Fyll i fälten som är specifika för automatisk konfiguration: </p> 
    <ul id="ul_8D9797B01E444B9C85B862A9F96B447C"> 
     <li id="li_0AC84C1F37B24C658F2178E50ECCC4B0"> <p> <b>Experience Cloud</b>: (Standard) Använder enkel inloggning <span class="keyword"> Experience Cloud</span> . Ange ditt Experience Cloud-ID och lösenord. </p> </li> 
     <li id="li_6C80468835D04CC09F4AEC46D1300310"> <p><b>Webbtjänster</b>: Ange ditt användarnamn och din delade hemlighet för webbtjänster. </p> <p>Delade hemliga autentiseringsuppgifter finns i <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Företagsinställningar</span> &gt; <a href="https://docs.adobe.com/content/help/en/analytics/admin/company-settings/web-services-admin.html"> Webbtjänster</a>. </p> <p>Utvecklare kan få hjälp med att hämta inloggningsuppgifter för Web Services genom att gå till <a href="https://marketing.adobe.com/developer/en_US/get-started/enterprise-api/c-get-web-service-access-to-the-enterprise-api"> Få webbtjänståtkomst till Enterprise API</a> . </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Manuell</b>: Hantera AppMeasurement-koden manuellt. You can download the <span class="keyword"> Analytics</span><span class="keyword"> AppMeasurement</span> code from <span class="ignoretag"><span class="uicontrol"> Admin Tools</span> &gt; <span class="uicontrol"> Code Manager</span></span>. </p> <p>Klicka på <a href="https://docs.adobe.com/content/help/en/analytics/implementation/js/migrate-from-hcode.html"> JavaScript (nytt)</a> om du vill ha information om hur du hämtar koden lokalt för att kopiera och klistra in den i fältet <span class="wintitle"> Redigera kod</span> i <a href="/help/implement/other/dtm/c-aa-tool/library-management.md"> Bibliotekshantering</a>. </p> <p>Fyll i fälten som är specifika för en manuell konfiguration: </p> 
    <ul id="ul_CFB6CE78AEB743EF8B47BAAC42E2DB0A"> 
     <li id="li_5B7046CD95AB416F8C113B381A264D91"> <p><b>Produktionskonto-ID: </b>(Obligatoriskt) Ditt produktionskonto för datainsamling. För Analytics är det här ditt rapportsvits-ID. Med Dynamic Tag Management installeras automatiskt rätt konto i produktions- och mellanlagringsmiljön. </p> </li> 
     <li id="li_14E840FD79A0451BABEDD15DC0584768"> <p><b>ID för mellanlagringskonto: </b>(Obligatoriskt) Används i utvecklings- eller testmiljön. För Analytics är det här ditt rapportsvits-ID. Ett mellanlagringskonto håller testdata åtskilda från produktionen. </p> </li> 
     <li id="li_69E6C6A41F5240E1ABE8ABE0B9D151FC"> <p><b>Spårningsserver: </b>Ange information för spårningsservern. </p> <p>Variablerna <span class="wintitle"> Tracking Server</span> och <span class="wintitle"> SSL Tracking Server</span> används för cookie-implementering från första part för att ange den domän där bildbegäran och cookie-filen skrivs. Mer information finns i artikeln <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html"> Correct Fyll i trackingServer och trackingServerSecure Variable</a> . </p> </li> 
     <li id="li_1A7271C68205428F8CA5548A96CACBEC"> <p><b>SSL-spårningsserver: </b>Ange information för SSL-spårningsservern. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. Klicka **[!UICONTROL Create Tool]** för att skapa verktyget och visa det för redigering.

   Verktyg visas på [!UICONTROL Overview] fliken, under [!UICONTROL Installed Tools].

1. (Villkorligt) Konfigurera verktyget ytterligare efter behov genom att följa instruktionerna i länkarna nedan ( [!UICONTROL General], [!UICONTROL Library Management], [!UICONTROL Global Variables], [!UICONTROL Pageviews & Content], [!UICONTROL Link Tracking], [!UICONTROL Referrers & Campaigns], [!UICONTROL Cookies]och [!UICONTROL Customize Page Code]).

Mer information om det här verktyget finns i [Vanliga frågor om Adobe Analytics-verktyget](/help/implement/faq.md) .

## Redigera ett befintligt Adobe Analytics-verktyg {#section_148B16AF429B4949B06238D90635B726}

Du kan redigera ett befintligt Adobe Analytics-verktyg om du vill ändra dess konfigurationsinställningar.

1. Klicka på ![](assets/settings_gear.png) ikonen bredvid ett installerat verktyg på [!UICONTROL Overview] fliken.
1. Redigera fälten efter behov.

   Följande tabell innehåller endast de element som skiljer sig från de element som är tillgängliga när du skapar ett Analytics-verktyg, enligt beskrivningen ovan. Du kan dock ändra vilket element som helst på sidan enligt beskrivningen i båda tabellerna.

<table id="table_2B60CD109CFF4839AB7F91D61125EDFF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Aktivera automatisk konfiguration </p> </td> 
   <td colname="col2"> <p>Obs! Om du aktiverar den här inställningen ändras en manuellt konfigurerad implementering till den automatiska konfigurationsmetoden som beskrivs i <span class="term"> Konfigurationsmetod</span>. </p> <p>Med det här alternativet kan Dynamic Tag Management automatiskt hämta konfigurationen för ditt <span class="keyword"> Adobe Analytics</span> -konto. </p> <p>Den senaste tillgängliga AppMeasurement-koden används och uppgraderingsmeddelanden visas när nya versioner blir tillgängliga. Du kan även återställa tidigare AppMeasurement-versioner om det behövs, t.ex. av kompatibilitetsskäl. Upp till fem tidigare versioner visas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uppdatera autentiseringsuppgifter </p> </td> 
   <td colname="col2"> <p>Uppdatera till exempel API för att uppdatera rapportsviter som är kopplade till en användare. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Villkorligt) Konfigurera verktyget ytterligare efter behov genom att följa instruktionerna i länkarna nedan ( [!UICONTROL General], [!UICONTROL Library Management], [!UICONTROL Global Variables], [!UICONTROL Pageviews & Content], [!UICONTROL Link Tracking], [!UICONTROL Referrers & Campaigns], [!UICONTROL Cookies]och [!UICONTROL Customize Page Code]).
1. Klicka på **[!UICONTROL Save Changes]**.
