---
title: Så här skapar du ett Advertising-konto i Advertising Analytics
description: I den här artikeln beskrivs hur du skapar nya annonskonton och mappar flera konton till flera rapportsviter.
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: 6bedfb9b1333a442bf17cf71dad1e0883b97fd45
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 3%

---

# Konfigurera ett Advertising-konto

Adobe Analytics-administratörer kan skapa nya annonskonton och mappa flera konton till flera rapportsviter (1: 1, 1: Många, många: många).

Administratörer kan också [bevilja åtkomst till icke-administratörer](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) för att konfigurera annonskonton.

<!--
![](assets/aa_accounts.png)
-->

1. I Adobe Analytics går du till **[!UICONTROL Admin]** > **[!UICONTROL Advertising Accounts]**.
1. (Endast första gången) Godkänn villkoren i slutanvändaravtalet.
1. Välj **[!UICONTROL + Add]**.
1. Dialogrutan [!UICONTROL New search engine setting] visas.

   ![](assets/aa-new-se-account.png)

1. Fyll i **[!UICONTROL search engine Settings]** enligt följande riktlinjer:

   | Inställning | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Type]** | Du har två alternativ: **[!UICONTROL Google Adwords]** och **[!UICONTROL Bing Ads]**. Obs! Yahoo Gemini absorberades av Microsoft den 31 mars 2019. Detta innebär att annonskontoalternativet Yahoo Gemini inte längre är tillgängligt. |
   | Kontonamn | Du kan ange det här kontonamnet till vilket namn som helst som passar dig.  Kontonamnet är det egna namnet på kontot som visas i användargränssnittet. |
   | OAuth-token | **Obs!**: OAuth är en öppen standard för åtkomstdelegering som ofta används som ett sätt att ge webbplatser eller program åtkomst till information på webbplatser, men utan att ange lösenord. Du ser att du dirigeras till en URL för tredje part (efrontier.com). Adobe använder Adobe Media Optimizer för att driva OAuth-autentiseringsprocessen för alla tre sökmotorer. Om du använder Internet Explorer 11 (eller tidigare) kan du inte hämta Oauth-token för någon av de tre sökmotorerna. Använd i stället andra webbläsare.<p>Välj **[!UICONTROL Retrieve Token]** om du vill starta OAuth2-autentiseringsprocessen. Du ombeds logga in på ditt sökkonto för Google Ads eller Microsoft Advertising med dina inloggningsuppgifter. Beroende på vilket du väljer är processen något annorlunda: <ul><li>Google Ads: Ange konto-ID för Google</li><li>Microsoft Advertising: Ange ditt konto-ID och ID för hanterarkonto.</li></ul>Mer information om dessa ID finns i [Leta upp ditt konto-ID](aa-locate-account-id.md). När du har loggat in visas **[!UICONTROL OAuth Token]**-fältet **[!UICONTROL Retrieved]**. |

1. I avsnittet **[!UICONTROL Tracking]** anger du information om hur du spårar data med din Adobe Analytics-implementering. Spårning är ett nödvändigt steg för att utöka Adobe Analytics data korrekt med sökmotordata.
Fyll i **[!UICONTROL Tracking Settings]** enligt följande riktlinjer:

   | Inställning | Beskrivning |
   | --- | --- |
   | Typ | <ul><li>**Auto**: Låter Advertising Cloud Engine avgöra hur spårningsparametrarna läggs till i spårningsmallarna/mål-URL:erna. [!UICONTROL Auto Type Tracking] är det enklaste sättet, men kanske inte resulterar i den bästa integrerade datauppsättningen.<br>**Viktigt!** Om du vill konfigurera ett sökmotorkonto med [!UICONTROL Auto Type Tracking] måste du utföra följande åtgärder:<ul><li>Parametern `s_kwcid` och värdet läggs till i kontospårningsmallarna eller URL:erna för landningssidan i det konto som läggs till. Parametern och värdet infogas i slutet av URL:en. Ytterligare åtgärder kan krävas om webbservern kräver ett visst `key=value`-par i slutet av URL:en. Eller så krävs en uppdatering som stöder nya `key=value`-par i URL:en. **Obs!**: Lär dig mer om huruvida du bör lägga till den här parametern i din [skyddsprofil för innehåll](https://experienceleague.adobe.com/sv/docs/id-service/using/reference/csp).</li><li>Dessutom kan nyckelord infogas i landnings-URL:en som en del av värdet `s_kwcid`. Om nyckelorden innehåller specialtecken eller symboler måste du bekräfta att webbservern kan hantera dessa tecken. Ett exempel på ett vanligt specialtecken är `+`, som används i nyckelorden&quot;Bred matchning ändrad&quot;.</li></ul></li><li>**Manuell**: Här kan du hantera hur spårningsparametrarna läggs till i sökmotorns spårningsmallar/mål-URL:er. [Se de här manuella spårningsexemplen för varje sökmotor](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md).</li></ul> |

1. Välj **[!UICONTROL Save]**.
1. En ansvarsfriskrivning visar en lista över kavattar. Bekräfta att du har läst och att du förstår det här avtalet. Markera kryssrutan och välj sedan **[!UICONTROL OK]**.

   Du dirigeras nu till [hanteringsgränssnittet](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md) för Advertising-konton, där ditt nyskapade konto ska listas.

>[!NOTE]
>
>Du bör vänta minst 24 timmar innan sökmotordata börjar fylla i era Analytics-rapporter.
