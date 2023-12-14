---
title: Borttagning av ojämnheter i Adobe Analytics
description: Så här tar du bort objekt i Adobe Analytics
feature: Bot Removal
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
source-git-commit: 59d4ade5e16fdd8c9cea266b7c352ce2057381d9
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 0%

---

# Borttagning av ojämnheter i Adobe Analytics

Adobe Analytics har flera alternativ för att ta bort robottrafik från rapportering:

## Använd punktregler

Både standardfiltreringsmetoder och anpassade robotfiltreringsmetoder stöds i **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**:

| Regeltyp | Beskrivning |
|--- |--- |
| Standard IAB-robotregler | Markera **[!UICONTROL Enable IAB Bot Filtering Rules]** använder [IAB](https://www.iab.com/) (International Advertising Bureau&#39;s) International Spiders &amp; Bots List för att ta bort robottrafiken. De flesta kunder väljer det här alternativet till ett minimum. |
| Anpassade robotregler | Du kan definiera och lägga till anpassade robotregler baserat på användaragenter, IP-adresser eller IP-intervall. |

Mer information finns i [Förstå och konfigurera robotregler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

## Använd [!UICONTROL websiteBot] plugin-program för att identifiera robotar

The [!UICONTROL websiteBot] Med plugin-programmet kan du dynamiskt identifiera om besökarna på stationära datorer är favoriter. Ni kan använda dessa data för att öka noggrannheten i alla typer av rapporter, vilket ger er ett bättre sätt att mäta legitim webbplatstrafik.

Denna plug-in utför två kontroller:

* Först avgörs om enheten är en stationär eller mobil enhet som använder variabeln navigator.UserAgent. Mobila enheter ignoreras.
* Om det är en stationär enhet läggs en händelseavlyssnare till för musrörelser.

Mer information finns i [Adobe Analytics Implementeringshandbok](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/websitebot.html).

## Använda en kombination av Adobe-verktyg

Eftersom botar dessutom morfar snabbt erbjuder Adobe flera andra kraftfulla funktioner som, när de kombineras korrekt och regelbundet, kan bidra till att avlägsna dessa fiender för datakvalitet. Dessa funktioner är: Experience Cloud ID-tjänst, segmentering, Data Warehouse, kundattribut och virtuella rapportsviter. Här är en översikt över hur du kan använda dessa verktyg.

### Steg 1: Skicka Experience Cloud-ID:t till ett nytt deklarerat ID

Börja med att skapa ett nytt deklarerat ID i [Bastjänst för människor](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html). Skicka besökarens Experience Cloud-ID till detta nya deklarerade ID, som kan göras snabbt och enkelt med [taggar i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html). Låt oss använda namnet &quot;ECID&quot; för det deklarerade ID:t.

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-cust-attr-setup.png)

Så här kan detta ID hämtas via dataelement. Fyll i ditt Experience Cloud OrgID i dataelementet korrekt.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

När dataelementet är konfigurerat följer du [dessa instruktioner](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html) för att skicka deklarerade ID:n till ECID-verktyget med hjälp av taggar i Adobe Experience Platform.

### Steg 2: Använd segmentering för att identifiera bottnar

Nu när besökarens ECID skickas till ett deklarerat ID kan du använda [segmentering i Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html) för att identifiera besökare som beter sig som botar. Boten definieras ofta av deras beteende: enstaka besök, ovanliga användaragenter, okänd information om enhet/webbläsare, inga hänvisare, nya besökare, ovanliga landningssidor osv. Använd kraften i Workspace-detaljgranskning och segmentering för att identifiera de robotar som har undgått IAB-filtrering och era regler för rapportrutins robotar. Här är till exempel en skärmbild av ett segment som du kan använda:

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-filter-seg1.png)

### Steg 3: Exportera alla [!DNL Experience Cloud IDs] från segmentet via Data Warehouse

Nu när du har identifierat bottarna med hjälp av segment är nästa steg att använda Data Warehouse för att extrahera alla Experience Cloud-ID:n som är kopplade till det här segmentet. På den här skärmbilden visas hur du ska konfigurera [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) begäran:

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-dwh-3.png)

Kom ihåg att använda Experience Cloud Visitor-ID som dimension och tillämpa segmentet &#39;Bts&#39;.

### Steg 4: Skicka tillbaka den här listan till Adobe som kundattribut

När Datan Warehouse har kommit fram har du en lista över ECID som måste filtreras från historiska data. Kopiera och klistra in dessa ECID:n i en tom .CSV-fil med bara två kolumner, ECID och Bot Flag.

* **ECID**: Kontrollera att den här kolumnrubriken matchar namnet som du gav det nya deklarerade ID:t ovan.
* **Punktflagga**: Lägg till &#39;Bot Flag&#39; som en schemdimension för kundattribut.

Använd den här .CSV-filen som import av kundattribut och prenumerera sedan dina rapportsviter på kundattributet enligt beskrivningen i den här [blogginlägg](https://blog.adobe.com/en/publish/2016/10/20/link-digital-behavior-customers).

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-csv-4.png)

### Steg 5: Skapa ett segment som utnyttjar det nya kundattributet

När datauppsättningen har bearbetats och integrerats i Analysis Workspace kan du skapa ett segment till som utnyttjar den nya kundattributsdimensionen &quot;Bot Flag&quot; och en [!UICONTROL Exclude] container:

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-filter-seg2.png)

### Steg 6: Använd det här segmentet som filter för den virtuella rapportsviten

Skapa slutligen en [Virtuell rapportsvit](/help/components/vrs/vrs-about.md) som använder det här segmentet för att filtrera bort de identifierade bottarna:

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-vrs.png)

Den här nysegmenterade virtuella rapportsviten kommer nu att resultera i en renare datamängd med identifierade botar borttagna.

### Steg 7: Upprepa steg 2, 3 och 4 regelbundet

Ställ in minst en månatlig påminnelse för att identifiera och filtrera nya robotar, kanske före en vanlig schemalagd analys.
