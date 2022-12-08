---
description: Fältbeskrivningar för rapportsvitens allmänna kontoinställningar i Admin.
title: Allmänna kontoinställningar
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
source-git-commit: 35e7c8bccb8524fa5e87cae223f0854956c7528a
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---

# Allmänna kontoinställningar

Fältbeskrivningar för en rapportsvits allmänna kontoinställningar i Admin.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**

De här inställningarna innehåller redigeringsalternativ för grundläggande rapportsvitsfunktioner, som namn och tidszon.

Här är en video om hur du konfigurerar allmänna kontoinställningar:

>[!VIDEO](https://video.tv.adobe.com/v/332330/?quality=12)

| Alternativ | Beskrivning |
|--- |--- |
| Platsrubrik | Identifierar din webbplats. Ge varje rapportsvit en unik webbplatsrubrik. |
| Bas-URL | Anger rapportsvitens huvudwebbplats. Bas-URL:en påverkar inte referentfiltrering. Använd [internt URL-filter](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) i stället. |
| Tidszon | Bestämmer datum och tid som är associerad med rapportdata.  Om du ändrar tidszonen för en live-rapportssvit skapas antingen en ökning eller en lucka i rapportdata. För att minimera påverkan rekommenderar Adobe att tidszoner ändras under icke-toppade timmar för att undvika skevningsdata.  Om du till exempel ändrar tidszonen för rapportsviten från Central till Stilla havet kl. 17:00 blir rapportsvitens aktuella tid 1:00. Eftersom rapporter redan har samlat in data under 1:00-timmen visar de en trafiktopp mellan 1:00 och 17:00.  Om du ändrar tidszonen för rapportsviten från central till öst kl. 17.00 blir rapportsvitens aktuella tid kl. 17.00. Rapporterna visar inga data mellan kl. 17.00 och 17.00 på dagen för tidsändringen. |
| Standardsida | Om [!UICONTROL Most Popular Pages] rapporten innehåller URL:er i stället för sidnamn. Den här inställningen förhindrar att flera URL:er representerar samma sida. URL:erna `https://example.com` och `https://example.com/index.html` är vanligtvis samma sida. Du kan ta bort standardfilnamn så att båda URL-adresserna visas som `https://example.com`.  Om inget anges tas följande filnamn bort från URL-adresserna: index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi och home.asp.  Om du vill inaktivera borttagning av filnamn helt och hållet anger du ett värde som aldrig finns i dina URL-adresser. |
| Ersätt den sista oktetten med IP-adresser med 0 | Borttagning av den sista oktetten görs innan bearbetningen av träffen görs, inklusive före IP-filtrering/uteslutning, innan du kontrollerar robotregler, innan sökningar efter geosegmentering osv. Den sista oktetten ersätts med 0, och reglerna för IP-undantag måste uppdateras för att matcha IP-adresser med en nolla på slutet. Matchande * ska matcha 0. IP-adressen 11.22.33.44 ändras till exempel till 11.22.33.0. Geosegmenteringsdata kommer inte att vara lika exakta som när hela IP-adressen används. Närmare bestämt kommer stadens exakthet att påverkas mer än precisionen i länder och regioner. Både batchregler och VISTA-regler påverkas eftersom hela IP-adressen inte är tillgänglig för dem. Dessutom påverkas alla bearbetningsregler som är IP-baserade, inklusive regler för marknadsföringskanaler och regler för bearbetning av rapportsviter, av den här inställningen. <br> **Anteckning**: Den här inställningen är aktiverad som standard för alla nya rapportsviter som skapas i London Data Center efter januari 2019, men bara om inställningarna för dessa rapportsviter kopieras från en mall som listas i Admin Console. Rapportsviter vars inställningar dupliceras från andra rapportsviter ärver alla inställningar från den valda rapportsviten. |
| IP-förvanskning | Ändrar IP-adresser till oidentifierbara strängar, vilket i huvudsak tar bort dem från datalagret i Adobe. När IP-förfalskning är aktiverat går de ursprungliga IP-adresserna förlorade permanent. <br> **Anteckning**: IP-adresserna är dolda överallt i Analytics, inklusive Data warehouse. IP-inställningen i Target styrs dock separat, så den här inställningen påverkar inte Target.<br> Om IP-förfalskning är aktiverat utförs all nödvändig bearbetning, inklusive IP-filtrering/uteslutning, robotregler och geosegmenteringssökningar innan IP-adressen döljs. Du behöver inte ändra någonting när du aktiverar IP-förfalskning.<ul><li>Kontrollerar **Handikappade** lämnar IP-adressen i data.</li><li>Kontrollerar **Felaktig IP-adress** ändrar IP till två kolon följt av ett hash-värde (t.ex. `::1932023538`).</li><li>Kontrollerar **Ta bort IP-adress** ersätter IP-adressen med `::X.X.X.X` i data, efter geosökning.</li></ul>**Anteckning**: Den här inställningen kan kräva ändringar i [robotregler](/help/admin/admin/bot-removal/bot-rules.md) eller [IP-undantag](/help/admin/admin/exclude-ip.md). |
| Lagring av transaktions-ID | Gör att du kan använda [Transaktions-ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md) datakällor. |
| Aktivera Data warehouse | Aktiverar användargränssnittet för Data warehouse under Analytics > Tools > Data warehouse. |
| Postalternativ | Gör att du kan ange postnumret i stället för att använda det som genereras av vår geo-IP-sökning. |
| Stöd för flerbytetecken | Stöd för flerbytetecken lagrar tecken i rapportsviten med UTF-8. Vid mottagande konverterar systemet data från webbsidans teckenuppsättning till teckenuppsättningen UTF-8, så att du kan använda vilket språk som helst i dina marknadsföringsrapporter. Kontakta din kontoansvarige eller kundtjänst om du vill ändra stödet för flerbytetecken för en befintlig rapportsvit. |
| Aktiverad | Anger om den här rapportsviten är aktiverad eller inte. |
| Basvaluta | Här kan du ange basen [valuta](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/currencycode.html) för den här rapportsviten. |
| Organisations-ID | Det ID som är associerat med ditt provisionerade Experience Cloud-företag. Detta ID är en alfanumerisk sträng med 24 tecken, följt av (och måste innehålla) @AdobeOrg. |