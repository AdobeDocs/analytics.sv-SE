---
title: Importera mått för betald sökning
description: Steg för att konfigurera Adobe Analytics att spåra dina betalda sökvärden (t.ex. Google AdWords, MSN, Yahoo osv.) med datakällor.
translation-type: tm+mt
source-git-commit: 81592ab80942b802fff3df62d2cd44b1e376aff8
workflow-type: tm+mt
source-wordcount: '1106'
ht-degree: 2%

---


# Importera [!UICONTROL Paid Search] mätvärden med [!UICONTROL Data Sources]

För många marknadsföringsorganisationer är betalsökningar ett av de mest värdefulla och tillförlitliga sätten att både &#x200B; nya kunder och behålla befintliga. Tack vare funktionerna i Adobe Analytics är det enkelt att importera avancerade sökdata från digitala annonsplattformar som Google AdWords. [!UICONTROL Data Sources] Ni kan integrera den med resten av era marknadsföringsdata, tillsammans med beteendedata på plats och kundattributdata, för att ni ska få bättre insikter i er organisations betalda sökinsatser.

De här stegen visar hur du konfigurerar en integrering med AdWords för att importera nyckelordsdata samt mätvärden som visningar, klick, kostnad per klick med mera.

Stegen beskriver hur du konfigurerar en engångsimport av Pay-Per-Click-data. tillåter dock [!UICONTROL Data Sources] kontinuerlig import av data med det filformat som beskrivs här. Beroende på vilken sökplattform du använder kan du eventuellt schemalägga periodiska exporter (varje dag, månad, osv.), konfigurera automatiska processer för att omvandla dessa exporter till det filformat som Adobe Analytics kräver, och överföra dessa filer till Adobe Analytics för betald sökintegreringsrapportering.

## Förutsättningar

* Du har implementerat betalsökningsidentifiering.
* Du hämtar spårningskoddata.
* Du har unika spårningskoder för varje annonsgrupp.

## Konfigurera [!UICONTROL Success Events]

Vårt första steg är att förbereda Adobe Analytics för mätningarna. För att kunna göra detta måste du konfigurera några lyckade händelser.

[!UICONTROL Success events] är åtgärder som kan spåras. Du bestämmer vad en [!UICONTROL success event] är. Vi vill kunna spåra [!UICONTROL paid search] mätvärden [!UICONTROL success events] runt [!UICONTROL clicks], [!UICONTROL impressions]och aktivera [!UICONTROL total cost][!UICONTROL tracking codes].

1. Gå till **[!UICONTROL Adobe Analytics > Admin > Report Suites]**.
1. Välja en rapportsvit.
1. Klicka på **[!UICONTROL Edit Settings > Conversion > Success Events]**.

   ![Success Events](assets/success-events.png)

1. Under Anpassade lyckade händelser använder du **[!UICONTROL Add New]** för att skapa tre anpassade lyckade händelser: [!UICONTROL Clicks] (Räknare), [!UICONTROL Impressions] (Räknare) och [!UICONTROL Total Cost] (Valuta).

   ![Ny händelse](assets/new-success-events.png)

1. Klicka på Spara.
Du bör få ett meddelande om att dina spara har godkänts.
1. Navigera till **[!UICONTROL Admin > Report Suites > Edit Settings > Conversion > Conversion Variables]**.
1. Aktivera spårningskoder genom att markera kryssrutan bredvid **[!UICONTROL Tracking Code]** under **[!UICONTROL Campaign > Campaign Variable]**.

   ![Kampanjvariabel](assets/campaign-variable.png)

## Ställ in datakällor

[!UICONTROL Data Sources] kan du dela data som inte är klickbara med Adobe Analytics. I det här fallet använder vi Adobe Analytics för att spåra betalda sökvärden. Vi använder spårningskoden som nyckel för att knyta samman de två datamängderna - betalda sökvärden och Adobe Analytics-statistik.

1. Navigera till **[!UICONTROL Adobe Analytics > Admin > Data Sources]**.
1. Klicka på **[!UICONTROL Create]** fliken för att börja aktivera nya datakällor.
1. Under **[!UICONTROL Select Category]** väljer du **[!UICONTROL Ad Campaign]**.

   ![Datakällor](assets/data-sources.png)

1. Under **[!UICONTROL Select Type]** väljer du **[!UICONTROL Generic Pay-Per-Click Service]**.
1. Klicka på **[!UICONTROL Activate]**.
Följande [!UICONTROL Data Source Activation Wizard] visas:

   ![Aktiveringsguiden](assets/ds-activation-wizard.png)

1. Klicka på **[!UICONTROL Next]** och ge datakällan ett namn. Det här namnet visas i Data Source Manager.
1. Acceptera serviceavtalet och klicka på **[!UICONTROL Next]**.
1. Välj tre standardmått: [!UICONTROL Impressions]och [!UICONTROL Clicks] klicka [!UICONTROL Total Cost] på **[!UICONTROL Next]**.
1. Mappa nu den här nya datakällan till anpassade händelser som vi skapade i [Konfigurera lyckade händelser](/help/admin/admin/c-success-events/t-success-events.md).

   ![Mappning](assets/data-source-mapping.png)

1. Välj datamåttMarkera rutan bredvid Spårningskoder och klicka på **[!UICONTROL Next]**.
1. Dimensioner för kartdata.
Mappa den importerade datamängden (attributet) till det Adobe Analytics-attribut som du vill lagra den i. Detta kan vara en standarddimension eller en eVar. När du har klickat **[!UICONTROL Next]** visas de resulterande mappningarna i sammanfattningen:

   ![Sammanfattning](assets/data-source-summary.png)

1. Klicka på **[!UICONTROL Save]**.
1. Klicka **[!UICONTROL Download]** för att hämta mallfilen för den här datakällan.
Filnamnet motsvarar den typ av datakälla som du ursprungligen angav, i det här fallet&quot;Allmän mall för betala per klick-tjänst.txt&quot;.
1. Öppna mallen i textredigeraren.
Filen är redan ifylld med mått och dimensioner samt deras mappningar.

## Exportera PPC-data och överföra dem till Analytics

Steg som liknar de här för Google Adwords, MSN, Yahoo och andra PPC-konton.

### Exportera data

1. Logga in på ditt PPC-konto och skapa en ny rapport eller export.
Kontrollera att exporten innehåller följande fält: datum, mål-URL (landningssida), avtryck, klick och kostnad. Exporten kan innehålla andra fält, men du tar bort dem enligt stegen nedan.
1. Om det är möjligt sparar du rapporten som en `.csv` eller tabbavgränsad fil. Detta gör det enklare att arbeta med i följande steg.
1. Öppna filen i Microsoft Excel.

### Redigera filen i Microsoft Excel

1. I Microsoft Excel tar du bort alla kolumner utom de som nämns ovan.
1. Ta bort eventuella extra rader överst.
1. Så här isolerar du spårningskoderna från mål-URL:erna:
a. Kopiera och klistra in data från alla kolumner.
b. Klicka **[!UICONTROL Data > Text to Columns]**.
c. Kontrollera att det **[!UICONTROL Delimited]** är markerat i steg 1 i guiden och klicka på **[!UICONTROL Next]**.
d. I steg 2 i guiden anger du avgränsaren beroende på hur du har skapat dina URL-adresser (antingen ? eller &amp;) och klicka **[!UICONTROL Next]**.
e. Förhandsgranska data i steg 3 i guiden och kontrollera att en av kolumnerna är &quot;trackingcodename=trackingcode&quot;. Om du har ytterligare variabler upprepar du de här stegen (med &amp; som avgränsare).
f. Ta bort alla kolumner utom spårningskoder, visningar, klickningar och kostnader. Lägg till en ny kolumn med namnet Datum och ordna kolumnerna i följande ordning: Datum: Spårningskod: Impressions: Klicka: Kostnad.
1. Lägg till dessa data i mallen som du hämtade under Konfigurera datakällor ovan.
Nu kan du överföra filen.

### Överför filen till Adobe Analytics via FTP

Gå tillbaka till guiden Datakälla för instruktioner och överför filen via FTP:

![Överför FTP](assets/upload-ftp.png)

## Skapa beräknade värden

Det kan vara praktiskt att lägga till beräknade värden när man ska fatta beslut per klick.

Du kan till exempel lägga till följande [beräknade mått](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=en#calculated-metrics):

| Namn | Formel | Mätningstyp | Beskrivning |
| --- | --- | --- | --- |
| Sidvisningar per besök | Sidvyer/besök | Numeriskt | När det används på en webbplatsnivå: visar det genomsnittliga antalet sidor per besök. När det används i rapporten Populäraste sidor: visar det genomsnittliga antalet gånger en viss sida visats per besök. |
| Genomsnittligt ordervärde | Intäkter/order | Valuta | Visar genomsnittlig intäkt per order. |
| Intäkter per besök | Intäkter/besök | Valuta | Visar genomsnittlig intäkt per besök. |
| Genomklickningshastighet (CTR) | Klick/Impressions | Numeriskt | Mät förhållandet mellan klick och visningar för en online- eller e-postmarknadsföringskampanj. |
| Vinst | Intäkter - kostnad | Valuta | Visar intäkterna från en kampanj minus kostnaden. |
| Resultat per intryck (PPI) | (Intäkter - kostnad)/Impression | Valuta | Visar hur mycket intäkter som genererades varje gång en annons visades, balanserat med kostnaden. |
| Avkastning på annonskostnad (ROAS) | Försäljningsbelopp/annonsutgift | Valuta | (ROI) Representerar de dollar som tjänats in på motsvarande annonsering. |

## Konfigurera och köra rapporter

Det sista steget är att lägga till datakällmått och beräknade värden i Tracking Code-rapporten och fördjupa er i en kampanj för att få en omedelbar bild av hur varje annonsgrupp fungerar.

1. I **[!UICONTROL Adobe Analytics > Reports]** väljer du den rapportserie som du har importerat datakällor till.
1. Navigera till **[!UICONTROL Reports > Campaigns > Tracking Code > Tracking Code]**.
1. Välj datumintervall.
1. Klicka på **[!UICONTROL Metrics > Add]** och lägg till dina datakällmått (klicka, Impressions, Total Cost) i listan med standardmått.
1. Gör samma sak för alla beräknade värden som du har lagt till. Rapporten uppdateras när du lägger till mätvärden.