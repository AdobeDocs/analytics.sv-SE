---
description: Fältbeskrivningar för rapportsvitens allmänna kontoinställningar i Admin.
title: Allmänna kontoinställningar
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 0%

---

# Allmänna kontoinställningar

Fältbeskrivningar för en rapportsvits allmänna kontoinställningar i Admin.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL General Account Settings]**

De här inställningarna innehåller redigeringsalternativ för grundläggande rapportsvitsfunktioner, som namn och tidszon.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Konfigurera allmänna kontoinställningar](https://video.tv.adobe.com/v/332330/?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]

| Alternativ | Beskrivning |
|--- |--- |
| Platsrubrik | Identifierar din webbplats. Ge varje rapportsvit en unik webbplatsrubrik. |
| Bas-URL | Anger rapportsvitens huvudwebbplats. Bas-URL:en påverkar inte referentfiltrering. Använd [interna URL-filter](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) i stället. |
| Tidszon | Bestämmer datum och tid som är associerad med rapportdata.  Om du ändrar tidszonen för en live-rapportssvit skapas antingen en ökning eller en lucka i rapportdata. För att minimera påverkan rekommenderar Adobe att tidszoner ändras under icke-toppade timmar för att undvika skevningsdata.  Om du till exempel ändrar tidszonen för rapportsviten från Central till Stilla havet kl. 17:00 blir rapportsvitens aktuella tid 1:00. Eftersom rapporter redan har samlat in data under 1:00-timmen visar de en trafiktopp mellan 1:00 och 17:00.  Om du ändrar tidszonen för rapportsviten från central till öst kl. 17.00 blir rapportsvitens aktuella tid kl. 17.00. Rapporterna visar inga data mellan kl. 17.00 och 17.00 på dagen för tidsändringen. |
| Standardsida | Om din [!UICONTROL Most Popular Pages]-rapport innehåller URL:er i stället för sidnamn förhindrar den här inställningen att flera URL:er representerar samma sida. URL:erna `https://example.com` och `https://example.com/index.html` är till exempel vanligtvis samma sida. Du kan ta bort standardfilnamn så att båda URL-adresserna visas som `https://example.com`.  Om du inte anger något namn tas följande filnamn bort från URL:erna: index.htm, index.html, index.cgi, index.asp, default.htm, default.html, default.cgi, default.asp, home.htm, home.html, home.cgi och home.asp.  Om du vill inaktivera borttagning av filnamn helt och hållet anger du ett värde som aldrig finns i dina URL-adresser. |
| Ersätt den sista oktetten med IP-adresser med 0 | När det här alternativet är aktiverat ersätts den sista oktetten med IP-adresser med noll. Detta inträffar innan georelaterade rapporter fylls i och kan därför påverka noggrannheten i dessa rapporter. |
| IP-förvanskning | Ändrar IP-adresser till oidentifierbara strängar, vilket i huvudsak tar bort dem från datalagret i Adobe. När IP-förfalskning är aktiverat går de ursprungliga IP-adresserna förlorade permanent. <br> **Obs!** IP-adresserna är dolda överallt i Analytics, inklusive Data Warehouse. IP-inställningen i Target styrs dock separat, så den här inställningen påverkar inte Target.<br> Om IP-förfalskning är aktiverat utförs all nödvändig bearbetning, inklusive IP-filtrering/uteslutning, robotregler och geosegmenteringssökningar innan IP-adressen döljs. Du behöver inte ändra någonting när du aktiverar IP-förfalskning.<ul><li>Om du kontrollerar **Inaktiverad** lämnas IP-adressen i data.</li><li>Om du markerar **Obfuschera IP-adress** ändras IP-adressen till två kolon följt av ett hash-värde (t.ex. `::1932023538`).</li><li>Om du markerar **Ta bort IP-adress** ersätts IP-adressen med `::X.X.X.X` i data, efter geosökning.</li></ul>**Obs!**: Den här inställningen kan kräva ändringar av anpassade [robotregler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) eller [IP-undantag](/help/admin/admin/exclude-ip.md).<br> **Obs!** Data som samlas in med Web SDK kan ha IP-förfalskning på Edge Network via [dataströmskonfiguration](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=sv-SE#@advanced-options). Om IP-förfalskning tillämpas på Edge Network är den redan obuserad när den når Analytics. Detta missförstånd påverkar robotregler och geosökningar. |
| Lagring av transaktions-ID | Gör att du kan använda datakällor för [Transaktions-ID](/help/import/data-sources/transactionid.md). |
| Aktivera Data Warehouse | Aktiverar användargränssnittet för Data Warehouse under Analytics (Analyser) > Tools (Verktyg) > Data Warehouse. |
| Postalternativ | Gör att du kan ange postnumret i stället för att använda det som genereras av vår geo-IP-sökning. |
| Stöd för flerbytetecken | Stöd för flerbytetecken lagrar tecken i rapportsviten med UTF-8. Vid mottagande konverterar systemet data från webbsidans teckenuppsättning till teckenuppsättningen UTF-8, så att du kan använda vilket språk som helst i dina marknadsföringsrapporter. Kontakta kontoteamet eller kundtjänst på Adobe för att ändra stödet för flerbytetecken för en befintlig rapportsvit. |
| Aktiverad | Anger om den här rapportsviten är aktiverad eller inte. |
| Basvaluta | Här kan du ange bas [valuta](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/currencycode.html?lang=sv-SE) för den här rapportsviten. |
| Organisations-ID | Det ID som är associerat med ditt provisionerade Experience Cloud-företag. Detta ID är en alfanumerisk sträng med 24 tecken, följt av (och måste innehålla) @AdobeOrg. |
