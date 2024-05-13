---
title: Så här konfigurerar du ett annonskonto i Advertising Analytics
description: I den här artikeln beskrivs hur du skapar nya annonskonton och mappar flera konton till flera rapportsviter.
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: c53b533a1d037ab3ed811bcc0960418f037a708f
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 3%

---

# Konfigurera ett annonskonto

Adobe Analytics-administratörer kan skapa nya annonskonton och mappa flera konton till flera rapportsviter (1: 1, 1: Många, många: många).

Administratörer kan även [ge icke-administratörer åtkomst](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) för att skapa annonskonton.

<!--
![](assets/aa_accounts.png)
-->

1. I Adobe Analytics navigerar du till **[!UICONTROL Admin]** > **[!UICONTROL Advertising Accounts]**.
1. (Endast första gången) Godkänn villkoren i slutanvändaravtalet.
1. Välj **[!UICONTROL + Add]**.
1. The [!UICONTROL New search engine setting] visas:

   ![](assets/aa-new-se-account.png)

1. Fyll i **[!UICONTROL search engine Settings]** följande riktlinjer:

   | Inställning | Beskrivning |
   | --- | --- |
   | **[!UICONTROL Type]** | Du har två alternativ: **[!UICONTROL Google Adwords]** och **[!UICONTROL Bing Ads]**.  Obs! Yahoo Gemini absorberades av Microsoft Bing den 31 mars 2019. Detta innebär att annonskontoalternativet Yahoo Gemini inte längre är tillgängligt. |
   | Kontonamn | Du kan ange det här kontonamnet till vilket namn som helst som passar dig.  Kontonamnet är det egna namnet på kontot som visas i användargränssnittet. |
   | OAuth-token | **Anteckning**: OAuth är en öppen standard för åtkomstdelegering som ofta används som ett sätt att ge webbplatser eller program åtkomst till information på webbplatser, men utan att ange lösenord. Du ser att du dirigeras till en URL för tredje part (efrontier.com). Adobe använder Adobe Media Optimizer för att driva OAuth-autentiseringsprocessen för alla tre sökmotorer. Om du använder Internet Explorer 11 (eller tidigare) kan du inte hämta Oauth-token för någon av de tre sökmotorerna. Använd i stället andra webbläsare.<p>Välj **[!UICONTROL Retrieve Token]** för att starta OAuth2-autentiseringsprocessen. Du ombeds logga in på ditt Google/Bing-sökkonto med dina inloggningsuppgifter. Beroende på vilket du väljer är processen något annorlunda: <ul><li>Google Adwords: Ange konto-ID för Google</li><li>Microsoft Bing: Ange Bing-konto-ID och Bing-kund-ID.</li></ul>Se [Hitta ditt konto-ID](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md) för information om dessa ID:n. När du har loggat in kan du **[!UICONTROL OAuth Token]** fält visas **[!UICONTROL Retrieved]**. |

1. I **[!UICONTROL Tracking]** ger du information om hur du spårar data med hjälp av din Adobe Analytics-implementering. Spårning är ett nödvändigt steg för att utöka Adobe Analytics data korrekt med sökmotordata.
Fyll i **[!UICONTROL Tracking Settings]** följande riktlinjer:

   | Inställning | Beskrivning |
   | --- | --- |
   | Typ | <ul><li>**Auto**: Låter Advertising Cloud Engine avgöra hur spårningsparametrarna läggs till i spårningsmallarna/mål-URL:erna. [!UICONTROL Auto Type Tracking] är det enklaste sättet, men kanske inte ger den bästa integrerade datauppsättningen.<br>**Viktigt:** Konfigurera ett sökmotorkonto med [!UICONTROL Auto Type Tracking]är du ansvarig för följande åtgärder:<ul><li>The `s_kwcid` parameter och värde läggs till i kontospårningsmallarna eller URL:er för landningssidan i det konto som läggs till. Parametern och värdet infogas i slutet av URL:en. Ytterligare åtgärder kan behövas om webbservern kräver en viss `key=value` i slutet av URL:en. Eller en uppdatering med stöd för nya `key=value` måste anges i URL:en. **Anteckning**: Läs mer om huruvida du bör lägga till den här parametern i [Skyddsprincip för innehåll](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp).</li><li>Dessutom kan nyckelord infogas i landnings-URL:en som en del av `s_kwcid` värde. Om nyckelorden innehåller specialtecken eller symboler måste du bekräfta att webbservern kan hantera dessa tecken. Ett exempel på ett vanligt specialtecken är `+`, som används i nyckelorden&quot;Bred Match Modified&quot;.</li></ul></li><li>**Manuell**: Används för att hantera hur spårningsparametrarna läggs till i sökmotorns spårningsmallar/mål-URL:er. [Se dessa manuella spårningsexempel för varje sökmotor](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md).</li></ul> |

1. I **[!UICONTROL Mapping]** väljer du en eller flera rapportsviter att länka till det här sökmotorkontot. Du måste ange minst en rapportserie innan du kan spara Advertising Account. Du kan mappa flera konton till flera rapportsviter (1: 1, 1: Många, Många: Många). Observera att de data som Adobe Media Optimizer hämtar från sökmotorn helt enkelt kopieras till alla mappade rapportsviter, så det finns ingen delning av data.

   >[!IMPORTANT]
   >
   >Endast rapportsviter som är mappade till en Experience Cloud-organisation kan väljas. Om du inte ser din rapportsvit som du har angett kan du läsa [Felsöka Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   För **[!UICONTROL Mapping Settings]** följande riktlinjer:

   | Inställning | Beskrivning |
   | --- | --- |
   | Rapportsvitsmappning | Rapportsvitens mappning avgör vilket rapportpaket som länkas till det här sökmotorkontot. Med andra ord avgör den i vilken rapportssvit/vilka rapportsviter sökmotordata skickas. |


1. Välj **[!UICONTROL Save]**.
1. En ansvarsfriskrivning visar en lista över kavattar. Bekräfta att du har läst och att du förstår det här avtalet. Markera kryssrutan och välj sedan **[!UICONTROL OK]**.

   Du dirigeras nu till Advertising Accounts [Hanteringsgränssnitt](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md), där ditt nyligen skapade konto ska listas.

>[!NOTE]
>
>Du bör vänta minst 24 timmar innan sökmotordata börjar fylla i era Analytics-rapporter.
