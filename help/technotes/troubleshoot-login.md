---
title: Felsöka inloggning på Adobe Analytics
description: Steg som ska utföras när du inte kan logga in på Adobe Analytics.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---


# Felsöka inloggning på Adobe Analytics

Adobe Analytics använder flera autentiseringsmetoder för att logga in:

* Adobe ID via Experience Cloud
* ID för äldre analys
* Enkel inloggning

**Om du regelbundet kommer åt Analytics och slumpmässigt påträffar inloggningsproblem kan du lösa de flesta problem genom att rensa webbläsarens cookies och cache.**

Ibland kan tillgänglighetsproblem påverka inloggningsförmågan. Kontrollera [status.adobe.com](https://status.adobe.com) om det finns några öppna incidenter. I annat fall använder du rätt avsnitt beroende på organisationens autentiseringsmetod.

## Adobe ID

Felsöka problem med att logga in på Adobe Analytics med Experience Cloud.

1. Navigera till [experience.adobe.com](https://experience.adobe.com). Om du inte kan komma åt den här webbplatsen kanske din organisation inte tillåter den här domänen via din brandvägg. Samarbeta med IT-avdelningen i organisationen för att göra det möjligt. Se [IP-adresser och domäner som används i Adobe Experience Cloud](https://helpx.adobe.com/se/analytics/kb/adobe-ip-addresses.html) för att få användbar information att ge IT-avdelningen.

2. Autentisera med Adobe ID: Klicka **[!UICONTROL Sign In with an Adobe ID]**. Om du inte kan logga in kontrollerar du att din e-postadress är korrekt angiven. Annars klickar du på **[!UICONTROL Reset password]** och följer anvisningarna för att återställa ditt Adobe ID-lösenord.

3. Åtkomstanalys efter autentisering: Klicka på ikonen med nio rutnät i det övre högra hörnet och klicka sedan på Analytics (Analyser). Om du inte har det här alternativet, eller om det är nedtonat, kan du samarbeta med en produktadministratör i organisationen för att kontrollera att du har rätt behörighet för att få tillgång till Analytics.

## ID för äldre analys

Det händer att en användare i organisationen får följande felmeddelande när han/hon loggar in:

*Av säkerhetsskäl har det här kontot låsts på grund av för många misslyckade inloggningsförsök.*

Om problemet inte kan lösas genom att du rensar webbläsarens cookies/cache kan du kontakta en Analytics-administratör i organisationen för att återställa användarens lösenord.

>[!IMPORTANT]
>
>Följande steg för att återställa en användares lösenord gäller endast äldre ID:n för analys, inte Adobe ID. Om din organisation använder Adobe ID kan du hantera användarkonton på [adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Logga in på Adobe Analytics med ett konto som har administratörsbehörighet.
2. Navigera till **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
3. Klicka på **[!UICONTROL Users]** fliken och klicka sedan **[!UICONTROL Edit]** bredvid önskad användare.
4. Ändra lösenordet till valfritt värde och markera kryssrutan **[!UICONTROL Require user to change password on next login]**.
5. Informera användaren om det nya lösenordet.

## Enkel inloggning

Kontakta en administratör i organisationen för att lösa problem med enkel inloggning.

## Andra inloggningsproblem

Om inget av ovanstående steg fungerar, ska du fastställa bredden på inloggningsproblemet:

* Inträffar problemet i olika webbläsare eller i alla webbläsare?
* Inträffar problemet på en annan dator i nätverket eller på flera datorer?
* Försök att logga in med ett annat nätverk, till exempel en mobil dataanslutning, ett bibliotek eller ett hemnätverk. Finns problemet i olika nätverk?

Om problemet är isolerat i ditt nätverk kan du samarbeta med din organisations IT-avdelning för att lösa det. Kontakta Adobe kundtjänst om det inte är begränsat till ett enda nätverk.
