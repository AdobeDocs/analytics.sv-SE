---
title: Så här konfigurerar du ett annonskonto i Advertising Analytics
description: Gör att du kan skapa nya annonskonton och mappa flera konton till flera rapportsviter.
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: 98c04c6553f6f18bb69a29ac2af0f622928b0b31
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 4%

---

# Konfigurera ett annonskonto

Adobe Analytics administratörer kan skapa nya annonskonton och mappa flera konton till flera rapportsviter (1:1, 1:Many, Many:Many).

Administratörer kan också [bevilja åtkomst till icke-administratörer](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) för att konfigurera annonskonton.

![](assets/aa_accounts.png)

1. I Adobe Analytics går du till **[!UICONTROL Admin]** > **[!UICONTROL Advertising Accounts]**.
1. (Endast första gången) Godkänn villkoren i slutanvändaravtalet.
1. Klicka på **[!UICONTROL + Add]**.
1. Dialogrutan [!UICONTROL New Search Engine Account] visas:

   ![](assets/aa_new_se_account.png)

1. Fyll i **[!UICONTROL Search Engine Settings]** enligt följande riktlinjer:

   <table id="table_B3BE66B7D4C54766B8FFD2C6DCD657AF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Inställning </th> 
      <th colname="col2" class="entry"> Beskrivning </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Typ </p> </td> 
      <td colname="col2"> <p>Du har två alternativ: Google AdWords och Microsoft Bing Ads. </p> <p>Obs! Yahoo Gemini absorberades av Microsoft Bing den 31 mars 2019. Detta innebär att annonskontoalternativet Yahoo Gemini inte längre är tillgängligt.  </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Kontonamn </p> </td> 
      <td colname="col2"> <p>Du kan ange det här kontonamnet till vilket namn som helst som passar dig. Det här är det egna namnet på kontot som ska visas i användargränssnittet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>OAuth-token </p> </td> 
      <td colname="col2"> <p>Obs!  OAuth är en öppen standard för åtkomstdelegering som ofta används som ett sätt att ge webbplatser eller program åtkomst till deras information på andra webbplatser, men utan att ge dem något lösenord. </p> <p>Obs!  Du kommer att märka att du dirigeras till en URL-adress från tredje part (efrontier.com). Adobe använder efrontier för att driva OAuth-autentiseringsprocessen för alla tre sökmotorer. </p> <p>Obs!  Om du använder Internet Explorer 11 (eller tidigare) kan du inte hämta Oauth-token för någon av de tre sökmotorerna. Använd i stället andra webbläsare. </p> <p>Om du klickar på <span class="uicontrol"> Retrieve Token</span> startas OAuth2-autentiseringsprocessen. Det innebär att du blir ombedd att logga in på ditt Google/Bing-sökkonto med dina inloggningsuppgifter. Beroende på vilken sökmotor du väljer är processen något annorlunda: </p>
      <ul id="ul_FC9B5612F6554495B04C357CB0AB72EB"> 
       <li id="li_CD54231BFF134F83B3B5B14B34A0E1D2">Google Adwords: Ange konto-ID för Google. </li> 
       <li id="li_89B9D54BAA914E5DB2959B193489582E">Microsoft Bing: Ange Bing-konto-ID och Bing-kund-ID. </li> 
       </ul> <p>Mer information om dessa ID finns i <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md"  > Hitta ditt konto-ID</a>. </p> <p>När du har loggat in visas OAuth-tokenfältet <code>Retrieved</code>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. I avsnittet **[!UICONTROL Tracking]** anger du information om hur sökmotordata spåras av din Adobe Analytics-implementering. Detta är ett nödvändigt steg för att utöka Adobe Analytics data med sökmotordata.
Fyll i **[!UICONTROL Tracking Settings]** enligt följande riktlinjer:

   | Inställning | Beskrivning |
   |--- |--- |
   | Typ | <ul><li>**Auto:** Låter Advertising Cloud Engine avgöra hur spårningsparametrarna läggs till i sökmotorns spårningsmallar/mål-URL:er. Detta är det enklaste sättet, men kanske inte ger den bästa integrerade datauppsättningen.<br>**Viktigt:** Om du vill konfigurera ett sökmotorkonto i Automatiskt läge ansvarar du för följande åtgärder:<br>- Parametern &quot;s_kwcid&quot; läggs till i kontospårningsmallarna eller URL:erna för landningssidan i det konto som läggs till. Den infogas i slutet av URL:en. Därför kan ytterligare åtgärder krävas från din sida om webbservern kräver ett visst nyckel=värde-par i slutet av URL:en ELLER en uppdatering som stöder ett nytt nyckel=värde-par i URL:en. **Obs!** Läs mer om huruvida du bör lägga till den här parametern i  [Content Security Policy](https://experienceleague.adobe.com/docs/id-service/using/reference/csp.html).<br>- Nyckelord kan dessutom infogas i landnings-URL:en som en del av värdet &quot;s_kwcid&quot;, så om de innehåller specialtecken eller symboler måste du bekräfta att webbservern kan hantera dessa tecken (ett exempel på ett vanligt specialtecken är &quot;+&quot; som används i nyckelorden &quot;Bred matchning ändrad&quot;).</li><li>**Manuell:** Gör att du kan hantera spårningsparametrarna som läggs till i sökmotorns spårningsmallar/mål-URL:er. [Se de här manuella spårningsexemplen för varje sökmotor](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md).</li></ul> |

1. I avsnittet **[!UICONTROL Mapping]** väljer du vilka rapportsviter som ska länkas till det här sökmotorkontot. Du måste ange minst en rapportserie innan du kan spara Advertising Account. Du kan mappa flera konton till flera rapportsviter (1:1, 1:Many, Many:Many). Observera att de data som AMO hämtar från sökmotorn helt enkelt kopieras till en mappad rapportsvit, så det finns ingen delning av data.

   >[!IMPORTANT]
   >
   >Endast rapportsviter som är mappade till en Experience Cloud-organisation kan väljas. Om du inte ser din rapportsserie läser du [Felsök Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   För **[!UICONTROL Mapping Settings]** följande riktlinjer:

   <table id="table_AF876DC40F97403882C0AA528BD204FF"> 
   <thead> 
   <tr> 
   <th colname="col1" class="entry"> Inställning </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
   <td colname="col1"> <p>Rapportsvitsmappning </p> </td> 
   <td colname="col2"> <p>Rapportsvitens mappning avgör vilket rapportpaket som länkas till det här sökmotorkontot. Med andra ord avgör den i vilken rapportssvit/vilka rapportsviter sökmotordata skickas. </p> </td>
   </tr> 
   </tbody> 
   </table>

1. Klicka på **[!UICONTROL Save]**.
1. När du har sparat en ansvarsfriskrivning visas en lista med undantag. Du ombeds bekräfta att du har läst och att du förstår det här avtalet. Klicka i kryssrutan och klicka sedan på **[!UICONTROL OK]**.

   Du dirigeras nu till Advertising Accounts [Management UI](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md), där ditt nya konto ska listas.

>[!NOTE]
>
>Du bör vänta minst 24 timmar innan sökmotordata börjar fylla i era Analytics-rapporter.
