---
title: Felsöka inloggning på Adobe Analytics
description: Steg som ska utföras när du inte kan logga in på Adobe Analytics.
feature: Analytics Basics
exl-id: e670a043-c55b-4717-9b60-613ea4d04382
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 2%

---

# Felsöka inloggning på Adobe Analytics

Adobe Analytics använder flera autentiseringsmetoder för att logga in:

* Adobe ID via Experience Cloud
* ID för äldre analys
* Enkel inloggning

**Om du regelbundet kommer åt Analytics och slumpmässigt påträffar inloggningsproblem kan du lösa de flesta problem genom att rensa webbläsarens cookies och cache.**

Ibland kan tillgänglighetsproblem påverka inloggningsförmågan. Kontrollera [status.adobe.com](https://status.adobe.com) för alla öppna incidenter. I annat fall använder du rätt avsnitt beroende på organisationens autentiseringsmetod.

## Adobe ID

Felsöka problem med att logga in på Adobe Analytics med Experience Cloud.

1. Navigera till [experience.adobe.com](https://experience.adobe.com). Om du inte kan komma åt den här webbplatsen kanske din organisation inte tillåter den här domänen via din brandvägg. Samarbeta med IT-avdelningen i organisationen för att göra det möjligt. Se [IP-adresser och domäner som används i Adobe Experience Cloud](https://helpx.adobe.com/se/analytics/kb/adobe-ip-addresses.html) för att få information som kan lämnas till IT-avdelningen.

2. Autentisera med Adobe ID: Klicka **[!UICONTROL Sign In with an Adobe ID]**. Om du inte kan logga in kontrollerar du att din e-postadress är korrekt angiven. I annat fall klickar du på **[!UICONTROL Reset password]** och följ anvisningarna för att återställa ditt Adobe ID-lösenord.

3. Åtkomstanalys efter autentisering: Klicka på ikonen med nio rutnät i det övre högra hörnet och klicka sedan på Analytics (Analyser). Om du inte har det här alternativet, eller om det är nedtonat, kan du samarbeta med en produktadministratör i organisationen för att kontrollera att du har rätt behörighet för att få tillgång till Analytics.

## ID för äldre analys

En användare i organisationen kan få följande fel när de försöker logga in:

*Av säkerhetsskäl har det här kontot låsts på grund av för många misslyckade inloggningsförsök.*

Om problemet inte kan lösas genom att du rensar webbläsarens cookies/cache kan du kontakta en Analytics-administratör i organisationen för att återställa användarens lösenord.

>[!IMPORTANT]
>
>Följande steg för att återställa en användares lösenord gäller endast äldre ID:n för analys, inte Adobe ID. Om din organisation använder Adobe ID kan du hantera användarkonton på [adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Logga in på Adobe Analytics med ett konto som har administratörsbehörighet.
2. Navigera till **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]**.
3. Klicka på **[!UICONTROL Users]** klicka sedan på **[!UICONTROL Edit]** bredvid önskad användare.
4. Ändra lösenordet till valfritt värde och markera kryssrutan **[!UICONTROL Require user to change password on next login]**.
5. Informera användaren om det nya lösenordet.

## Enkel inloggning

Kontakta en administratör i organisationen för att lösa problem med enkel inloggning.

## Utgångna inloggningar

En användare i organisationen kan få följande fel när de försöker logga in:

*Fel: Inloggningen har upphört att gälla.*

Felet fungerar som det ska. Adobe Analytics ger administratörer möjlighet att ange ett datumintervall som ett användarkonto är giltigt. Om det aktuella datumet ligger utanför det giltiga datumintervallet för kontot kan de inte logga in. Samarbeta med en Analytics-administratör i organisationen för att utöka det giltiga datumintervallet för inloggningen. Adobe kundtjänst har inte behörighet att ändra giltiga inloggningsdatumintervall för användarkonton.

## Andra inloggningsproblem

Om inget av ovanstående steg fungerar, ska du fastställa bredden på inloggningsproblemet:

* Inträffar problemet i olika webbläsare eller i alla webbläsare?
* Inträffar problemet på en annan dator i nätverket eller på flera datorer?
* Försök att logga in med ett annat nätverk, till exempel en mobil dataanslutning, ett bibliotek eller ett hemnätverk. Finns problemet i olika nätverk?

Om problemet är isolerat i ditt nätverk kan du samarbeta med din organisations IT-avdelning för att lösa det. Kontakta Adobe kundtjänst om det inte är begränsat till ett enda nätverk.
