---
description: Vanliga frågor om användning av Adobe Analytics Server Call
title: Vanliga frågor om användning av serversamtal
uuid: 43340481-2e49-446b-bec7-86fcadeb4233
exl-id: a660542c-9389-4608-bc25-49831c21ceb7
source-git-commit: 9186c8d61368074cbf1df6e63bd8d3136adf0f57
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# Vanliga frågor om användning av serversamtal

| Fråga | Svar |
|--- |--- |
| F: Jag är Analytics Admin. Varför visas ingen [!UICONTROL Server Call Usage]-länk under administrationsavsnittet för mitt inloggningsföretag? | S: Du kan välja vilket av dina inloggningsföretag som ska visa länken för [!UICONTROL Server Call Usage] under avsnittet Admin. Om du inte ser den kontaktar du kundtjänst för att aktivera den. |
| F: Är [!UICONTROL Server Call Usage] en funktion som endast är för administratörer? | S: Nej. Precis som för funktionen [!UICONTROL Billing] som [!UICONTROL Server Call Usage] ersätter kan du tilldela en icke-administratör behörighet att komma åt den här länken. |
| F: Är [!UICONTROL Server Call Usage]- och åtagandeinformationen specifik för ett inloggningsföretag? | S: Nej. De användnings- och åtagandeuppgifter som visas gäller alla dina inloggningsföretag som regleras av ditt Adobe Analytics-avtal. |
| F: På fliken [!UICONTROL Report Suite Usage] kan jag se förbrukning i flera rapportsviter som inte är tillgängliga för rapportering under det aktuella inloggningsföretaget. Är det en bugg? | S: Nej. Precis som din [!UICONTROL Server Call Usage] och dina bindningsuppgifter omfattar rapportsviterna alla inloggningsföretag som du har implementerat enligt ditt Analytics-avtal. |
| F: Är användningsperioden alltid densamma som för mitt Analytics-kontrakt eller min faktureringscykel? | S: Nej. Användningsperioden är den tid som ditt abonnemang på servern gäller och kan skilja sig från din kontraktstid eller faktureringscykel. Ditt årskontrakt kan till exempel ge dig rätt till en miljard serversamtal per månad. I så fall blir ditt åtagande en miljard serversamtal och din användningsperiod en månad. |
| F: Mitt kontrakt innehåller ett åtagande för Video Heart Beats, men jag ser dem inte under [!UICONTROL Server Call Usage]. Ska jag kontakta kundtjänst? | S: Konsumtions- och bindningsinformation för videohjärtslag ingår inte i [!UICONTROL Server Call Usage]. |
| F: Mitt kontrakt innehåller inte någon bestämmelse för sekundära serversamtal, men jag kan fortfarande se dem under flikarna [!UICONTROL Current Usage] och [!UICONTROL Report Suite Usage]. Är det här ett fel? | S: Nej. Även om ditt avtal inte uttryckligen tillhandahåller sekundära serversamtal kan du ändå få dem om du skickar in Analytics-data till fler än en av rapportsviterna. Du kan antingen gå igenom implementeringen igen för att vara säker på att du inte skickar in sådana samtal eller kontakta din Account Manager för att uppdatera ditt kontrakt så att det innehåller en bestämmelse om att sådana samtal ska skickas. |
| F: Mitt kontrakt innehåller inte någon bestämmelse för sekundära serversamtal, men jag kan fortfarande se dem under flikarna [!UICONTROL Current Usage] och [!UICONTROL Report Suite Usage]. Betyder det att jag kommer att börja få överdrift? | S: Om du skulle börja få en överbelastning när du skickar in sekundära serversamtal utan att bli tilldelad för dem beror på ditt avtal. I vissa fall kan förbrukning av sekundära serversamtal räknas av mot ditt åtagande för primära serversamtal, vilket innebär att de tas bort snabbare än du förväntade dig. I andra fall kan du faktureras för sekundära serversamtal även om du inte har förbrukat alla dina primära serversamtal. Se ditt kontrakt eller kontakta din kontoansvarige för att bekräfta. |
| F: Mitt kontrakt/min användningsperiod började precis och jag får redan varningar om att mitt andra serversamtal överskred mitt åtagande. Är det här ett fel och kommer jag att börja faktureras för overages? | S: Nej. Det kan innebära att du förbrukar sekundära serversamtal utan att dessa uttryckligen läggs in i ditt Adobe Analytics-kontrakt. Det är bara för att säkerställa att du är medveten om detta och för att vid behov kunna vidta korrigerande åtgärder. Se även Frågor och svar 8 ovan. |
| F: Jag skapade inga [!UICONTROL Server Call Usage]-varningar, men jag får flera sådana varningar, allt med samma innehåll. Är det här ett fel? | S: Nej. Standardvarningar utlöses för alla inloggningsföretag som har länken [!UICONTROL Server Call Usage] aktiverad under avsnittet [!UICONTROL Admin]. Varningarna innehåller namnet på det företag som utlöste varningen. Som administratör kan du inaktivera och/eller ta bort dessa aviseringar för att undvika dubbletter, ta bort dig själv från listan över mottagare eller låta kundtjänst inaktivera länken [!UICONTROL Server Call Usage] för specifika företag. |
