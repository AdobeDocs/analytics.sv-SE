---
description: Fältbeskrivningar för rapportsvitens allmänna kontoinställningar i Admin.
title: Allmänna kontoinställningar
topic: Admin tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
translation-type: tm+mt
source-git-commit: fde56828eafad8b7668a854170cd9ee3a8c7ed6b

---


# Allmänna kontoinställningar

Fältbeskrivningar för en rapportsvits allmänna kontoinställningar i Admin.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**

De här inställningarna innehåller redigeringsalternativ för grundläggande rapportsvitsfunktioner, som namn och tidszon.

| Alternativ | Beskrivning |
|--- |--- |
| Platsrubrik | Identifierar din webbplats. Ge varje rapportsvit en unik webbplatsrubrik. |
| Bas-URL | Anger rapportsvitens huvudwebbplats. Bas-URL:en påverkar inte referentfiltrering. Använd [interna URL-filter](/help/admin/admin/internal-url-filter-admin.md) i stället. |
| Tidszon | Bestämmer datum och tid som är associerad med rapportdata.  Om du ändrar tidszonen för en live-rapportssvit skapas antingen en ökning eller en lucka i rapportdata. För att minimera påverkan rekommenderar Adobe att du ändrar tidszoner under icke-topp-timmar för att undvika skevning av data.  Om du t.ex. ändrar tidszonen för rapportsviten från Central till Stilla havet kl. 17.00 blir rapportsvitens aktuella tid 1:00. Eftersom rapporter redan har samlat in data under 1:00-timmen visar de en trafiktopp mellan 1:00 och 17:00.  Om du ändrar tidszonen för rapportsviten från central till öst kl. 17.00 blir rapportsvitens aktuella tid kl. 17.00. Rapporterna visar inga data mellan kl. 17.00 och 17.00 på dagen för tidsändringen. |
| Standardsida | Om din [!UICONTROL Most Popular Pages] rapport innehåller URL-adresser i stället för sidnamn, förhindrar den här inställningen att flera URL-adresser representerar samma sida. URL:erna `https://mysite.com` och `https://mysite.com/index.html` är till exempel vanligtvis samma sida. Du kan ta bort standardfilnamn så att båda URL-adresserna visas som `https://mysite.com`.  Om inget anges tas följande filnamn bort från URL-adresserna:  index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi och home.asp.  Om du vill inaktivera borttagning av filnamn helt och hållet anger du ett värde som aldrig finns i dina URL-adresser. |
| Ersätt den sista oktetten med IP-adresser med 0 | Den senaste oktetten tas bort före IP-filtrering. Den sista oktetten ersätts med 0, och reglerna för IP-undantag måste uppdateras för att matcha IP-adresser med en nolla på slutet. Matchande * ska matcha 0. Om du markerar det här alternativet ändras IP-adressen innan den bearbetas. IP-adressen 134.123.567.780 ändras till exempel till 134.123.567.0. Geosegmenteringsdata kommer inte att vara lika exakta som när hela IP-adressen används. Närmare bestämt kommer stadens exakthet att påverkas mer än precisionen i länder och regioner. Både batchregler och VISTA-regler påverkas eftersom hela IP-adressen inte är tillgänglig för dem. Dessutom påverkas alla bearbetningsregler som är IP-baserade, inklusive regler för marknadsföringskanaler och regler för bearbetning av rapportsviter, av den här inställningen.<br>**Obs **: Den här inställningen är aktiverad som standard för alla nya rapportsviter som skapas i London Data Center efter januari 2019, men bara om inställningarna för dessa rapportsviter kopieras från en mall som listas i Admin Console. Rapportsviter vars inställningar dupliceras från andra rapportsviter ärver alla inställningar från den valda rapportsviten. |
| IP-förvanskning | Konverterar IP-adresser till oidentifierbara strängar, vilket i huvudsak tar bort dem från Adobes datalager. När IP-förfalskning är aktiverat går de ursprungliga IP-adresserna förlorade permanent.<br>**Obs **: IP-adresserna är dolda överallt i Analytics, inklusive Data Warehouse. IP-inställningen i Target styrs dock separat, så den här inställningen påverkar inte Target.<br>Om IP-förfalskning är aktiverat inträffar IP-uteslutning innan IP-adressen döljs, så kunderna behöver inte ändra någonting när de aktiverar IP-förfalskning.<br>Om du kontrollerar** Inaktiverad **lämnas IP-adressen i data.<br>Om du kontrollerar** inkompatibel IP-adress **ändras IP-adressen till ett hash-värde (t.ex. 234abc6493872038).<br>Om du markerar** Ta bort IP-adress **ersätts IP-adressen med x.x.x.x i data efter geosökning.<br>**Obs**: Den här inställningen kan kräva ändringar av anpassade [robotregler](/help/admin/admin/bot-removal/bot-rules.md) eller [IP-undantag](/help/admin/admin/exclude-ip.md). |
| Lagring av transaktions-ID | Gör att du kan använda datakällor för [transaktions-ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md) . |
| Aktivera ad hoc-analys | Anger om rapportsviten i fråga visas som en tillgänglig rapportsvit i Ad Hoc Analysis. Använd den här inställningen för att begränsa vilka rapportsviter som visas som ett alternativ för Ad Hoc-analys. Du kan till exempel inaktivera Ad Hoc-analys för utveckling och QA-rapportsviter. |
| Aktivera datalager | Aktiverar gränssnittet för datalagret under Analytics > Tools > Data Warehouse. |
