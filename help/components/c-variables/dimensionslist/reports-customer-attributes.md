---
description: Frågor och svar om Analytics för kundattribut och hur man kör kundattributrapporten.
solution: Experience Cloud,Analytics
title: Kundattribut
uuid: 94721265-ba23-45d5-8807-76f81b0b8a30
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Kundattribut

Frågor och svar om Analytics för kundattribut och hur man kör kundattributrapporten.

**[!UICONTROL Reports]** **[!UICONTROL > Visitor Profile]** > **[!UICONTROL Customer Attributes]**

Om du samlar in företagsdata i en CRM-databas (customer relationship management) kan du överföra data till en datakälla för kundattribut i Experience Cloud. När data har överförts kan du köra kundattributrapporten i Rapporter och analyser.

* [Kundattribut och rapporteringsstatistik i Analytics](/help/components/c-variables/dimensionslist/reports-customer-attributes.md#section_EF343662146B460A882D3DF772ADD86D)
* [Frågor och svar - Kundattribut i analyser](/help/components/c-variables/dimensionslist/reports-customer-attributes.md#section_E29641D1F3D649C1AC9EA5231921F038)

Mer information om hur du överför kundattributdata finns i [Kundattribut](https://marketing.adobe.com/resources/help/en_US/mcloud/attributes.html) i hjälpen för Experience Cloud.

## Kundattribut och rapporteringsstatistik i Analytics {#section_EF343662146B460A882D3DF772ADD86D}

När du har överfört kundattribut och validerat schemat (i Experience Cloud), skapas mätvärden baserat på de egna namn (som *`age`* eller *`gender`*) som du mappar till attributsträngar och heltal. Dessa värden visas i **[!UICONTROL Visitor Profile]** > **[!UICONTROL Customer Attributes]** rapporter.

Exempel:

**[!UICONTROL Visitor Profile]** > **[!UICONTROL Customer Attributes]** > **[!UICONTROL Age]**

![](assets/report_age.png)

**Exempel - Åldersmått**

Om du anger en sträng som *`age`* skapas följande mått och mått:

* Åldersdimension: Gör att du kan köra en rapport baserad på attributet Ålder.
* Åldersmått: Ett mätvärde som du kan lägga till i en rapport, t.ex. en unik besökarrapport.
* Antal åldersmått: Gör att du till exempel kan förstå om besökare har angett ett *`age`* värde i ett formulär.

Eftersom mätvärden är summor i en rapporttabell bör du [skapa ett beräknat mått](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) som anger medelåldern. Formeln för det här måttet är `Age / Count of Age`.

## Frågor och svar - Kundattribut i analyser {#section_E29641D1F3D649C1AC9EA5231921F038}

<table id="table_88631069013B408EBB0A810657662B36"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fråga </th> 
   <th colname="col2" class="entry"> Svar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Varför är det bättre att använda identitetstjänsten för att ange Kund-ID i stället för att fylla i Kund-ID i en prop eller eVar? </p> </td> 
   <td colname="col2"> <p>Att använda identitetstjänsten ger ett antal fördelar: </p> 
    <ul id="ul_5D3659604D43419F9CA5920B4F93728E"> 
     <li id="li_BA2EF0715C5A47EFAFA7191CFAD088A4">Om du inte ställer in kund-ID:t med identitetstjänsten är kundposterna bara tillgängliga för Adobe Analytics. Om du vill använda kundposterna för målgruppsanpassning i realtid måste du använda identitetstjänsten. </li> 
     <li id="li_228358684E474A298E39578D427BF932">Om du använder identitetstjänsten för att ange ett kund-ID minskar det tiden det tar att synkronisera ID:n med Experience Cloud. Om du placerar ditt kund-ID i en prop eller eVar skickas kundens ID:n till Experience Cloud via serversynkronisering som sker i grupp. Identitetstjänsten synkroniserar ditt kund-ID med Experience Cloud omedelbart. </li> 
     <li id="li_BCF28219E4014FCF9F747C3D8D270526"> Om du använder identitetstjänsten i stället för en prop eller eVar frigörs den propen eller eVar för annan användning. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Om jag redan lagrar ett kund-ID i en prop eller eVar, varför skulle jag använda den här nya funktionen i stället för att klassificera mitt prop eller eVar med CRM-attribut? </p> </td> 
   <td colname="col2"> <p>Props och eVars omfattas av begränsningar som överskrider Uniques. Med den här funktionen kan du hämta attributdata för ett obegränsat antal kund-ID:n. Om du använder metoden prop/eVar begränsas CRM-informationen till Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hur visas mina CRM-attribut i Adobe Analytics? </p> </td> 
   <td colname="col2"> <p>CRM-attributen visas i Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis, API:t för rapportering och Report Builder. Textattribut visas som rapporter/dimensioner. Numeriska attribut visas som både mått och mått. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kommer CRM-data att vara tillgängliga i datalagret och i dataflöden? </p> </td> 
   <td colname="col2"> <p>CRM-data är för närvarande inte tillgängliga i datalagret eller Analytics-dataflödet. </p> </td> 
  </tr> 
 </tbody> 
</table>

