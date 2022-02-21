---
title: Så här konfigurerar du ett annonskonto i Advertising Analytics
description: Gör att du kan skapa nya annonskonton och mappa flera konton till flera rapportsviter.
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 4%

---

# Konfigurera ett annonskonto

Adobe Analytics administratörer kan skapa nya annonskonton och mappa flera konton till flera rapportsviter (1:1, 1:Many, Many:Many).

Administratörer kan även [ge icke-administratörer åtkomst](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) för att skapa annonskonton.

![](assets/aa_accounts.png)

1. I Adobe Analytics navigerar du till **[!UICONTROL Admin]** > **[!UICONTROL Advertising Accounts]**.
1. (Endast första gången) Godkänn villkoren i slutanvändaravtalet.
1. Klicka på **[!UICONTROL + Add]**.
1. The [!UICONTROL New Search Engine Account] visas:

   ![](assets/aa_new_se_account.png)

1. Fyll i **[!UICONTROL Search Engine Settings]** följande riktlinjer:

   | Inställning | Beskrivning |
   | --- | --- |
   | Typ | Du har två alternativ: Google AdWords och Microsoft Bing Ads.  Obs! Yahoo Gemini absorberades av Microsoft Bing den 31 mars 2019. Detta innebär att annonskontoalternativet Yahoo Gemini inte längre är tillgängligt. |
   | Kontonamn | Du kan ange det här kontonamnet till vilket namn som helst som passar dig. Det här är det egna namnet på kontot som ska visas i användargränssnittet. |
   | OAuth-token | **Obs!**  OAuth är en öppen standard för åtkomstdelegering som ofta används som ett sätt att ge webbplatser eller program åtkomst till deras information på andra webbplatser, men utan att ge dem något lösenord. Du kommer att märka att du dirigeras till en URL-adress från tredje part (efrontier.com). Adobe använder efrontier för att driva OAuth-autentiseringsprocessen för alla tre sökmotorer. Om du använder Internet Explorer 11 (eller tidigare) kan du inte hämta Oauth-token för någon av de tre sökmotorerna. Använd i stället andra webbläsare.<p>Klicka **[!UICONTROL Retrieve Token]** startar OAuth2-autentiseringsprocessen. Du ombeds logga in på ditt Google/Bing-sökkonto med dina inloggningsuppgifter. Beroende på vilken sökmotor du väljer är processen något annorlunda: <ul><li>Google Adwords: Ange Google konto-ID</li><li>Microsoft Bing: Ange Bing-konto-ID och Bing-kund-ID.</li></ul>Se [Hitta ditt konto-ID](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md) för information om dessa ID:n. När du har loggat in kan du **[!UICONTROL OAuth Token]** fält visas **[!UICONTROL Retrieved]**. |

1. I **[!UICONTROL Tracking]** anger du information om hur sökmotordata spåras av din Adobe Analytics-implementering. Detta är ett nödvändigt steg för att utöka Adobe Analytics data med sökmotordata.
Fyll i **[!UICONTROL Tracking Settings]** följande riktlinjer:

   | Inställning | Beskrivning |
   | --- | --- |
   | Typ | <ul><li>**Auto:** Låter Advertising Cloud Engine avgöra hur spårningsparametrarna läggs till i sökmotorns spårningsmallar/mål-URL:er. Detta är det enklaste sättet, men kanske inte ger den bästa integrerade datauppsättningen.<br>**Viktigt:** Om du vill konfigurera ett sökmotorkonto i Automatiskt läge ansvarar du för följande åtgärder:<br>- Parametern s_kwcid och värdet läggs till i kontospårningsmallarna eller URL:erna för landningssidan i det konto som läggs till. Den infogas i slutet av URL:en. Därför kan ytterligare åtgärder krävas från din sida om webbservern kräver ett visst nyckel=värde-par i slutet av URL:en ELLER en uppdatering som stöder ett nytt nyckel=värde-par i URL:en. **Obs!** Läs mer om huruvida du bör lägga till den här parametern i [Skyddsprofil för innehåll](https://experienceleague.adobe.com/docs/id-service/using/reference/csp.html).<br>- Nyckelord kan dessutom infogas i landnings-URL:en som en del av värdet &quot;s_kwcid&quot;, så om de innehåller specialtecken eller symboler måste du bekräfta att webbservern kan hantera dessa tecken (ett exempel på ett vanligt specialtecken är &quot;+&quot; som används i nyckelorden &quot;Bred matchning ändrad&quot;).</li><li>**Manuell:** Gör att du kan hantera hur spårningsparametrarna läggs till i sökmotorns spårningsmallar/mål-URL:er. [Se de här manuella spårningsexemplen för varje sökmotor](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md).</li></ul> |

1. I **[!UICONTROL Mapping]** väljer du vilka rapportsviter som ska länkas till det här sökmotorkontot. Du måste ange minst en rapportserie innan du kan spara Advertising Account. Du kan mappa flera konton till flera rapportsviter (1:1, 1:Many, Many:Many). Observera att de data som AMO hämtar från sökmotorn helt enkelt kopieras till en mappad rapportsvit, så det finns ingen delning av data.

   >[!IMPORTANT]
   >
   >Endast rapportsviter som är mappade till en Experience Cloud-organisation kan väljas. Om du inte ser din rapportsvit som du har angett kan du läsa [Felsöka Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   För **[!UICONTROL Mapping Settings]** följande riktlinjer:

   | Inställning | Beskrivning |
   | --- | --- |
   | Rapportsvitsmappning | Rapportsvitens mappning avgör vilket rapportpaket som länkas till det här sökmotorkontot. Med andra ord avgör den i vilken rapportssvit/vilka rapportsviter sökmotordata skickas. |


1. Klicka på **[!UICONTROL Save]**.
1. När du har sparat en ansvarsfriskrivning visas en lista med undantag. Du ombeds bekräfta att du har läst och att du förstår det här avtalet. Klicka på kryssrutan och klicka sedan på **[!UICONTROL OK]**.

   Du dirigeras nu till Advertising Accounts [Hanteringsgränssnitt](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md), där ditt nyligen skapade konto ska visas.

>[!NOTE]
>
>Du bör vänta minst 24 timmar innan sökmotordata börjar fylla i era Analytics-rapporter.
