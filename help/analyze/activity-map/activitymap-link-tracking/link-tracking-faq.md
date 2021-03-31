---
description: Frågor och svar om länkspårning i Activity Map.
title: Vanliga frågor om länkspårning
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 1%

---


# Vanliga frågor om länkspårning

Frågor och svar om länkspårning i Activity Map.

>[!CAUTION]
>
>Genom att aktivera spårning av Activity Map kan **du samla in data om personligt identifierbar information (PII).** Dessa data kan användas fristående eller tillsammans med annan information för att identifiera, kontakta eller hitta en person, eller för att identifiera en individ i sitt sammanhang.

Här är några kända fall där PII-data kan samlas in med Activity Map Tracking:

* `Mailto` länkar. En mailto-länk är en typ av HTML-länk som aktiverar standardklienten för e-post på datorn för att skicka ett e-postmeddelande.
* `User ID` länkar som kan visas i sidhuvudet/sidfoten på en webbplats när användaren har loggat in.
* För finansinstitut kan kontonumret visas som en länk. Om du klickar på den hämtas länktexten.
* Vårdwebbplatser kan också ha PII-data som visas som länkar. Om du klickar på de här länkarna samlas länktexten in, vilket innebär att PII-data samlas in.

<table id="table_0951EAC617344156BAE43000CCD838AF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>F: När inträffar länkspårning?</b> <p> </p> </td> 
   <td colname="col2"> S: Länk- och regionsidentifiering i Activity Map inträffar när användare klickar på en sida. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>F: Vad spåras som standard?</b> <p> </p> </td> 
   <td colname="col2"> S: Om en klickningshändelse inträffar för ett element måste elementet genomgå vissa kontroller för att avgöra om AppMeasurement kommer att behandla det som en länk. Detta är kontrollerna: 
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0"> 
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">Är det här en &lt;A&gt;- eller &lt;AREA&gt;-tagg med en HREF-egenskap? </li> 
     <li id="li_77828D24D54343E5B9A1FF7345221781">Finns det ett on-click-attribut som anger variabeln s_objectID? </li> 
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">Är detta en INPUT-tagg eller en SKICKA-knapp med ett värde eller en underordnad text? </li> 
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">Är detta en INPUT-tagg med typen IMAGE och en src-egenskap? </li> 
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">Är det här en &lt;Button&gt;? </li> 
    </ul> <p>Om svaret är <b>Ja</b> på någon av frågorna ovan behandlas elementet som en länk och spåras. </p> <p>Viktigt:  Button-taggar med attributet type="button" betraktas inte som länkar av AppMeasurement. Ta bort "type='button'" i knapptaggarna och lägg till role="button" eller submit="button" i stället. </p> <p>Viktigt: En ankartagg med en href som börjar med "#" betraktas som en intern målplats med AppMeasurement, inte som en länk (eftersom du inte lämnar sidan). Som standard spårar inte Activity Map dessa interna målplatser. Det spårar bara länkar som navigerar användaren till en ny sida.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>F: Hur spårar Activity Map andra visuella HTML-element?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5"> 
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b>Via  <code> s.tl() </code> funktionen</b> <p>Om klickningen inträffade via ett s.tl-anrop får Activity Map även den här click-händelsen och avgör om en linkName-strängvariabel hittades. Under s.tl-körningen anges detta linkName som Activity Map Link-ID. Elementet som klickades och som kom från anropet s.tl() kommer att användas för att avgöra regionen. Exempel: </p> <p> 
       <code>
         &lt;img&amp;nbsp;onclick="s.tl(true,'o','abc')"&amp;nbsp;src="someimageurl.png"/&gt; 
       </code> </p> </li> 
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b>Via  <code> s_objectID </code> variabeln</b> <p>Exempel: </p> <p> 
       <code>
         &lt;img&nbsp;onclick="s_objectID='abc';"&nbsp;src="someimageurl.png"/&gt; &lt;a&nbsp;href="some-url.html"&nbsp;onclick="s_objectID='abc';"&nbsp;&gt;Link&nbsp;Text&nbsp;Here&lt;/a&gt;
       </code> </p> <p>Viktigt:  Observera att ett avslutande semikolon (;) krävs när du använder s_objectID i Activity Map. </p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>F: Kan du ge mig några exempel på länkar som kommer att spåras?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA"> 
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0"> 
      <code>
        &lt;a&amp;nbsp;href="/home"&gt;Home&lt;/a&gt; 
      </code> </li> 
     <li id="li_76F3DB36ED734132A2386871E6EB4929"> 
      <code>
        &lt;input&amp;nbsp;type="submit"&amp;nbsp;value="Submit"/&gt; 
      </code> </li> 
     <li id="li_10CF9EDA224645169E7CDF74956DB98B"> 
      <code>
        &lt;input&amp;nbsp;type="image"&amp;nbsp;src="submit-button.png"/&gt; 
      </code> </li> 
     <li id="li_9FA171D7F49547E798DE21869F73A402"> 
      <code>
        &lt;p&nbsp;onclick="var&nbsp;s_objectID='custom&nbsp;link&nbsp;id';"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF"> 
      <code>
        &lt;div&nbsp;onclick="s.tl(true,'o','custom&nbsp;link&nbsp;id')"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/div&gt;
      </code> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>F: Kan du ge mig några exempel på länkar som INTE kommer att spåras?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547"> 
     <li id="li_99372060646B43EF94C13A9C682CE693">Orsak: Ankartaggen har ingen giltig href 
      <code>
        &lt;a&amp;nbsp;name="innerAnchor"&gt;Section&amp;nbsp;header&lt;/a&gt; 
      </code> </li> 
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">Orsak: Varken <code> s_ObjectID </code> eller <code> s.tl() </code> finns 
      <code>
        &lt;p&nbsp;onclick="showPanel('market&nbsp;rates')"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">Orsak: Varken <code> s_ObjectID </code> eller <code> s.tl() </code> finns 
      <code>
        &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="A"/&gt; &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="B"/&gt; &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="C"/&gt;
      </code> </li> 
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">Orsak: src-egenskapen saknar ett indataelement för formulär 
      <code>
        &lt;input&amp;nbsp;type="image"/&gt; 
      </code> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>
