---
description: Genom att spåra och spela in besökarnas hänvisande webbplatser för varje besök kan ni avgöra hur besökarna fick reda på webbplatsen för varje besök.
title: Referenstyp
topic: Reports
uuid: 7f63d327-d223-4537-a722-4780aae05c2b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Referenstyp

Genom att spåra och spela in besökarnas hänvisande webbplatser för varje besök kan ni avgöra hur besökarna fick reda på webbplatsen för varje besök.

I listan nedan definieras de olika typerna av referenser:

**Andra webbplatser**: hänvisarna registreras när besökare klickar på en länk som finns på en sida på en annan webbplats (inte definierad som en del av din webbplats) och kommer till din webbplats.

**Sökmotorer**: Sökmotorreferenser registreras när besökare använder en sökmotor för att komma åt din webbplats. Det refererande värdet måste av Adobe betraktas som en sökmotor och kan inte vara en underdomän som inte betraktas som en sökmotor (t.ex. inte är en sökmotor eftersom den här domänen används för e-post). [!DNL mail.yahoo.com]

**[!UICONTROL Social networks]**: Det refererande värdet måste av Adobe betraktas som ett socialt nätverk. Se [Lista över sociala nätverk](https://helpx.adobe.com/analytics/kb/list-social-networks.html).

**E-post**: En refererande domän betraktas som en e-postrefererande domän när besökare klickar på en e-postmeddelandelänk som innehåller protokollet [!DNL imap://] eller [!DNL mail://] kommer till din webbplats. Allt som kommer från [!DNL https://mail.yahoo.com] räknas till exempel inte som e-postreferent eftersom protokollet är [!DNL https://]. E-post från Outlook rapporteras på raden Typed/Bookmarked, medan alla referenter med ett HTTP-protokoll där domänen är en känd sökmotor rapporteras på raden Sökmotor.

**Typat/bokmärkt**: referenter registreras när besökare skriver webbplatsens URL direkt i webbläsaren, eller om de öppnar webbplatsen genom att välja bokmärken. Mobilenheter rapporterar en typ av referent *`typed/bookmarked`* om det inte finns någon referent vid den första träffen av besöket.

**[!UICONTROL Inside Your Site]**: De här objekten är URL:er som är taggade med de interna URL-filtren. Dessa poster räknas inte som *`referrer instances`* men kan ses vid rapportering av andra mätvärden.

## Refererartyper efter gränssnitt {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Marknadsföringsrapporter och -analyser (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Ad hoc-analys </th> 
   <th colname="col4" class="entry"> Datalager </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Rapporterade referenstyper </td> 
   <td colname="col2"> 
    <ul id="ul_EFC8E81EC6DF4CC2AC0E290244FD5859"> 
     <li id="li_686FCAEB04054B9F8A7D2434E8C49F04">Andra webbplatser </li> 
     <li id="li_C232868230AA4A54958B524F3D8FDA35"> Sökmotorer </li> 
     <li id="li_A89BFD0468F74ED7822F64BE4A7332AE"> Social </li> 
     <li id="li_C824E6F7F6E748DD827A95B105ADBADD"> Typat/bokmärkt </li> 
    </ul> <p> Den här rapporten innehåller endast två fördefinierade mått: Instanser och unika besökare. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_FD81EB3C1BD949A39C5A9E9688D25271"> 
     <li id="li_6099E7E03F3843D484808258A332BBE9">Andra webbplatser </li> 
     <li id="li_5AABC02DA7964D578BF8404DA819245D"> Sökmotorer </li> 
     <li id="li_B18907AC7FA1429A893B57634EB7DC6F"> Social </li> 
     <li id="li_7674B67897994E1FA99BCD9B604BCB6E"> Typat/bokmärkt </li> 
    </ul> </td> 
   <td colname="col4"> 
    <ul id="ul_C37ADBEC31D04295BF5CDEA25DB5191A"> 
     <li id="li_81A642C96C674669BA00B2DACA534B8A">Andra webbplatser </li> 
     <li id="li_29B9DA9F2AAD46A69886D34D5E6E43D4"> Sökmotorer </li> 
     <li id="li_E381EEF111F248F99EE39600D616B7C2"> Social </li> 
     <li id="li_596377F4D3C248BEA5191EE2985A2B13"> Typat/bokmärkt </li> 
     <li id="li_A7A72D3D6B9A4CCFB43EDA77ABFDEDBC"> Inuti din webbplats </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Anteckningar {#section_B83A3571D64E4E7792712FAF740D7955}

* Referenten, typen av referent och referensdomän anges vid den första träffen av besöket, eller under ett besök när referenten är extern (om en besökare lämnar din webbplats använder till exempel en sökmotor och sedan återgår till din webbplats innan det första besöket upphör). Dessa värden ställs in samtidigt och kvarstår under hela besöket.
* Alla referenstyper visas inte i den här rapporten. Det innebär att webbplatsomfattande besök inte matchar besöken i den här rapporten.

## Rapporthistorik {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| Datum | Ändra |
|---|---|
| 1/16/2014 | Datalagret uppdaterades för att matcha logiken som används i marknadsföringsrapporter och analyser. Före detta datum kvarstod inte typen av referent vid besöket. |

