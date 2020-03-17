---
title: Konfigurera ett annonskonto
uuid: 4e37caa3-e4a5-43ad-97c0-12db62ad5283
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Konfigurera ett annonskonto

Adobe Analytics-administratörer kan skapa nya annonskonton och mappa flera konton till flera rapportsviter (1:1, 1:Many, Many:Many).

Administratörer kan också [bevilja icke-administratörer](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) åtkomst för att skapa annonskonton.

![](assets/aa_accounts.png)

1. Navigera till **[!UICONTROL Admin]** > **[!UICONTROL Advertising Accounts]** i Adobe Analytics.
1. (Endast första gången) Godkänn villkoren i slutanvändaravtalet.
1. Klicka på **[!UICONTROL + Add]**.
1. I [!UICONTROL New Search Engine Account] dialogrutan visas:

   ![](assets/aa_new_se_account.png)

1. Fyll i **[!UICONTROL Search Engine Settings]** följande riktlinjer:

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
      <td colname="col2"> <p>Obs!  OAuth är en öppen standard för åtkomstdelegering som ofta används som ett sätt att ge webbplatser eller program åtkomst till deras information på andra webbplatser, men utan att ge dem något lösenord. </p> <p>Obs!  Du kommer att märka att du dirigeras till en URL-adress från tredje part (efrontier.com). Adobe använder efrontier för att driva OAuth-autentiseringsprocessen för alla tre sökmotorer. </p> <p>Obs!  Om du använder Internet Explorer 11 (eller tidigare) kan du inte hämta Oauth-token för någon av de tre sökmotorerna. Använd andra webbläsare i stället. </p> <p>När du klickar på<span class="uicontrol"> Hämta token</span> startas OAuth2-autentiseringsprocessen. Det innebär att du blir ombedd att logga in på ditt Google/Bing-sökkonto med dina inloggningsuppgifter. Beroende på vilken sökmotor du väljer är processen något annorlunda: </p> 
        <ul id="ul_FC9B5612F6554495B04C357CB0AB72EB"> 
        <li id="li_CD54231BFF134F83B3B5B14B34A0E1D2">Google Adwords: Ange konto-ID för Google. </li> 
        <li id="li_89B9D54BAA914E5DB2959B193489582E">Microsoft Bing: Ange Bing-konto-ID och Bing-kund-ID. </li> 
        </ul> <p>Mer information om dessa ID finns i <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md"  > Hitta ditt konto-ID</a> . </p> <p>När du har loggat in visas OAuth-tokenfältet 
        <systemoutput>
          Hämtat
        </systemoutput>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. I **[!UICONTROL Tracking]** avsnittet anger du information om hur sökmotordata spåras av Adobe Analytics-implementeringen. Detta är ett nödvändigt steg för att utöka Adobe Analytics-data korrekt med sökmotordata.
Fyll i **[!UICONTROL Tracking Settings]** följande riktlinjer:

   <table id="table_1AB4E31456E84ABF8209B02058259C4D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Inställning </th> 
      <th colname="col2" class="entry"> Beskrivning </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Typ </p> </td> 
      <td colname="col2"> 
        <ul id="ul_1C5A0502A4984E57A08417A91CCD6FFE"> 
        <li id="li_5736E38286FF494ABDDC6E85281D7F2A"> <span class="uicontrol"> Auto</span>: Låter Advertising Cloud Engine avgöra hur spårningsparametrarna läggs till i sökmotorns spårningsmallar/mål-URL:er. Detta är det enklaste sättet, men kanske inte ger den bästa integrerade datauppsättningen. <p>Viktigt: Om du vill konfigurera ett sökmotorkonto i Automatiskt läge ansvarar du för följande åtgärder: 
          <ul id="ul_4FF9D1E3CC4E452BA339E0A725D29FEE"> 
            <li id="li_6F3A6D6259C0420CB7E6FD2C26A1B6E0">Parametern s_kwcid och värdet läggs till i kontospårningsmallarna eller URL:erna för landningssidan i det konto som läggs till. Den infogas i slutet av URL:en. Därför kan ytterligare åtgärder krävas från din sida om webbservern kräver ett visst nyckel=värde-par i slutet av URL:en ELLER en uppdatering som stöder ett nytt nyckel=värde-par i URL:en. </li> 
            <li id="li_A04D4AA31A934392808639E46C86573F">Nyckelord kan dessutom infogas i landnings-URL:en som en del av värdet "s_kwcid", så om de innehåller specialtecken eller symboler måste du kontrollera att webbservern kan hantera dessa tecken (ett exempel på ett vanligt specialtecken är "+" som används i nyckelorden "Bred matchning ändrad"). </li> 
          </ul> </p> </li> 
        <li id="li_EAA7A7CA1E584854A7EC1E43E13B63FE"><span class="uicontrol"> Manuell</span>: Gör att du kan hantera hur spårningsparametrarna läggs till i sökmotorns spårningsmallar/mål-URL:er. <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md"  > Se de här manuella spårningsexemplen för varje sökmotor</a>. </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. I **[!UICONTROL Mapping]** avsnittet väljer du vilka rapportsviter som ska länkas till det här sökmotorkontot. Du måste ange minst en rapportserie innan du kan spara Advertising Account. Du kan mappa flera konton till flera rapportsviter (1:1, 1:Many, Many:Many). Observera att de data som AMO hämtar från sökmotorn helt enkelt kopieras till en mappad rapportsvit, så det finns ingen delning av data.

   >[!IMPORTANT]
   >
   >Endast rapportsviter som har [mappats till en Experience Cloud-organisation](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html) kan väljas. Om du inte kan se din rapportsserie i listan, se [Felsök annonsanalys](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   I följande **[!UICONTROL Mapping Settings]** riktlinjer:

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
      <td colname="col2"> <p>Rapportsvitens mappning avgör vilket rapportpaket som länkas till det här sökmotorkontot. Med andra ord avgör den i vilken rapportssvit/vilka rapportsviter sökmotordata skickas. </p> <p>Om du inte ser din rapportsserie i listan kan du <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html"  > mappa din rapportsvit till en Experience Cloud-organisation</a> med det här verktyget. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Save]**.
1. När du har sparat en ansvarsfriskrivning visas en lista med undantag. Du ombeds bekräfta att du har läst och att du förstår det här avtalet. Klicka i kryssrutan och klicka sedan på **[!UICONTROL OK]**.

   Du kommer nu till gränssnittet för [kontohantering för annonsering](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md), där ditt nya konto ska listas.

> [!NOTE] Du bör vänta minst 24 timmar innan sökmotordata börjar fylla i era Analytics-rapporter.

