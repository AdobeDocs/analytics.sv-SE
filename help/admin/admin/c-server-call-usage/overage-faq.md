---
description: Vanliga frågor om användning av Adobe Analytics Server Call
title: Vanliga frågor om användning av serversamtal
feature: Server Call Usage
exl-id: a660542c-9389-4608-bc25-49831c21ceb7
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 0%

---

# Vanliga frågor om användning av serversamtal

| Fråga | Svar |
|--- |--- |
| F: Jag är Analytics Admin. Varför ser jag inte [!UICONTROL Server Call Usage] under Admin-avsnittet för mitt inloggningsföretag? | S: Du kan välja vilket av dina inloggningsföretag som ska visa länken för [!UICONTROL Server Call Usage] under avsnittet Admin. Om du inte ser den kontaktar du kundtjänst för att aktivera den. |
| F: Är [!UICONTROL Server Call Usage] en funktion som endast är tillgänglig för administratörer? | S: Nej. Precis som [!UICONTROL Billing] funktion som [!UICONTROL Server Call Usage] ersätter kan du tilldela en annan användare behörighet att komma åt länken. |
| F: Är [!UICONTROL Server Call Usage] och information om ett specifikt inloggningsföretag? | S: Nej. De användnings- och åtagandeuppgifter som visas gäller alla dina inloggningsföretag som regleras av ditt Adobe Analytics-avtal. |
| F: Under [!UICONTROL Report Suite Usage] Jag kan se förbrukning i alla rapportsviter som inte är tillgängliga för rapportering under det aktuella inloggningsföretaget. Är det en bugg? | S: Nej. Precis som dina [!UICONTROL Server Call Usage] och information om åtaganden omfattar rapportsviterna alla inloggningsföretag som du har implementerat enligt ditt Analytics-avtal. |
| F: Är användningsperioden alltid densamma som för mitt Analytics-kontrakt eller min faktureringscykel? | S: Nej. Användningsperioden är den tid som ditt abonnemang på servern gäller och kan skilja sig från din kontraktstid eller faktureringscykel. Ditt årskontrakt kan till exempel ge dig rätt till en miljard serversamtal per månad. I så fall blir ditt åtagande en miljard serversamtal och din användningsperiod en månad. |
| F: Mitt kontrakt innehåller ett åtagande för Video Heart Beats, men jag ser dem inte under [!UICONTROL Server Call Usage]. Ska jag kontakta kundtjänst? | S: Konsumtions- och åtagandeinformation för videohjärtslag ingår inte i [!UICONTROL Server Call Usage]. |
| F: Mitt kontrakt innehåller inte någon bestämmelse om sekundära serversamtal, men jag ser dem fortfarande under [!UICONTROL Current Usage] och [!UICONTROL Report Suite Usage] -tabbar. Är det här ett fel? | S: Nej. Även om ditt avtal inte uttryckligen tillhandahåller sekundära serversamtal kan du ändå få dem om du skickar in Analytics-data till fler än en av rapportsviterna. Du kan antingen gå igenom implementeringen igen för att se till att du inte skickar in sådana samtal eller kontakta ditt kontoteam på Adobe för att uppdatera ditt avtal så att det innehåller en bestämmelse om att sådana samtal ska skickas. |
| F: Mitt kontrakt innehåller inte någon bestämmelse om sekundära serversamtal, men jag ser dem fortfarande under [!UICONTROL Current Usage] och [!UICONTROL Report Suite Usage] -tabbar. Betyder det att jag kommer att börja få överdrift? | S: Om du skulle börja få en överbelastning när du skickar in sekundära serversamtal utan att bli tilldelad för dem beror på ditt avtal. I vissa fall kan förbrukning av sekundära serversamtal räknas av mot ditt åtagande för primära serversamtal, vilket innebär att de tas bort snabbare än du förväntade dig. I andra fall kan du faktureras för sekundära serversamtal även om du inte har förbrukat alla dina primära serversamtal. Se ditt kontrakt eller kontakta ditt kontoteam på Adobe för att bekräfta. |
| F: Mitt kontrakt/min användningsperiod började precis och jag får redan varningar om att mitt andra serversamtal överskred mitt åtagande. Är det här ett fel och kommer jag att börja faktureras för overages? | S: Nej. Det kan innebära att du förbrukar sekundära serversamtal utan att dessa uttryckligen läggs in i ditt Adobe Analytics-kontrakt. Det är bara för att säkerställa att du är medveten om detta och för att vid behov kunna vidta korrigerande åtgärder. Se även Frågor och svar 8 ovan. |
| F: Jag skapade inga [!UICONTROL Server Call Usage] varningar, men jag får flera sådana varningar, allt med samma innehåll. Är det här ett fel? | S: Nej. Standardvarningar utlöses för alla inloggningsföretag som har [!UICONTROL Server Call Usage] länk aktiverad under [!UICONTROL Admin] -avsnitt. Varningarna innehåller namnet på det företag som utlöste varningen. Som administratör kan du inaktivera och/eller ta bort dessa varningar för att undvika dubbletter, ta bort dig själv från listan över mottagare eller låta Kundtjänst inaktivera [!UICONTROL Server Call Usage] länk för specifika företag. |
