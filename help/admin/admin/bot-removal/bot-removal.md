---
title: Borttagning av bot i Adobe Analytics
description: 3 sätt att ta bort botar i Adobe Analytics
translation-type: tm+mt
source-git-commit: e1cbdf87140b915dccbb8f64694797bb903d8ab8

---


# Borttagning av bot i Adobe Analytics

I Adobe Analytics finns det flera alternativ för att ta bort robottrafik från rapporter:

## Använd punktregler

Både standardfiltermetoder och anpassade robotfiltermetoder stöds i **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**:

| Regeltyp | Beskrivning |
|--- |--- |
| Standard IAB-robotregler | När du väljer **[!UICONTROL Enable IAB Bot Filtering Rules]** används [IAB:s](https://www.iab.com/) (International Advertising Bureau&#39;s) International Spiders &amp; Bots List för att ta bort robottrafiken. De flesta kunder väljer det här alternativet till ett minimum. |
| Anpassade robotregler | Du kan definiera och lägga till anpassade robotregler baserat på användaragenter, IP-adresser eller IP-intervall. |

Mer information finns i Översikt över [PUNKTSregler](/help/admin/admin/bot-removal/bot-rules.md).

## Använda en kombination av Adobe-verktyg

Eftersom botar dessutom morfar snabbt erbjuder Adobe flera andra kraftfulla funktioner som, när de kombineras korrekt och regelbundet, kan bidra till att avlägsna dessa fiender för datakvalitet. De här funktionerna är: Experience Cloud ID-tjänst, segmentering, datalager, kundattribut och virtuella rapportsviter. Här får du en översikt över hur du kan utnyttja dessa verktyg.

### Steg 1: Överför besökarnas Experience Cloud-ID till ett nytt deklarerat ID

Till att börja med vill du skapa ett nytt deklarerat ID i [People Core Service](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html). Du måste skicka besökarens Experience Cloud-ID till det nya deklarerade ID:t, vilket kan göras snabbt och enkelt med [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html). Låt oss använda namnet &quot;ECID&quot; för det deklarerade ID:t.

![](assets/bot-cust-attr-setup.png)

Så här kan detta ID hämtas via dataelement. Se till att du fyller i ditt Experience Cloud OrgID i dataelementet korrekt.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

När detta dataelement har konfigurerats följer du [dessa anvisningar](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) för att skicka deklarerade ID:n till ECID-verktyget i Launch.

### Steg 2: Använd segmentering för att identifiera objekt

Nu när besökarens ECID skickas till ett deklarerat ID kan du använda [segmentering i Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) för att identifiera besökare som beter sig som robotar. Boter definieras ofta av sitt beteende: Enskilda besök, ovanliga användaragenter, okänd information om enhet/webbläsare, inga hänvisningar, nya besökare, ovanliga landningssidor osv. Använd kraften i Workspace-detaljgranskning och segmentering för att identifiera de robotar som har undgått IAB-filtrering och era regler för rapportrutins robotar. Här är till exempel en skärmbild av ett segment som du kan använda:

![](assets/bot-filter-seg1.png)

### Steg 3: Exportera alla [!DNL Experience Cloud IDs] från segmentet via datalagret

Nu när du har identifierat robotarna med hjälp av segment är nästa steg att utnyttja Data Warehouse för att extrahera alla Experience Cloud-ID:n som är kopplade till det här segmentet. Så här ställer du in din begäran om [datalager](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) :

![](assets/bot-dwh-3.png)

Kom ihåg att använda Experience Cloud Visitor ID som din dimension och att använda Bots-segmentet.

### Steg 4: Skicka tillbaka listan till Adobe som kundattribut

När datalagerrapporten kommer har du en lista över ECID:n som måste filtreras från historiska data. Kopiera och klistra in dessa ECID:n i en tom .CSV-fil med bara två kolumner, ECID och Bot Flag.

* **ECID**: Kontrollera att den här kolumnrubriken matchar namnet som du gav det nya deklarerade ID:t ovan.
* **Punktflagga**: Lägg till detta som en schemamodell för kundattribut.

Använd den här .CSV-filen som import av kundattribut och prenumerera sedan dina rapportsviter på kundattributet enligt beskrivningen i det här [blogginlägget](https://theblog.adobe.com/link-digital-behavior-customers).

![](assets/bot-csv-4.png)

### Steg 5: Skapa ett segment som utnyttjar det nya kundattributet

När datauppsättningen har bearbetats och integrerats i Analysis Workspace kan du skapa ytterligare ett segment som utnyttjar din nya&quot;Bot Flag&quot;-kundattributdimension och en [!UICONTROL Exclude] behållare:

![](assets/bot-filter-seg2.png)

### Steg 6: Använd det här segmentet som Virtual Report Suite-filter

Slutligen bör du skapa en [Virtual Report Suite](/help/components/vrs/vrs-about.md) som utnyttjar det här segmentet för att filtrera bort de identifierade delarna:

![](assets/bot-vrs.png)

Den här nysegmenterade virtuella rapportsviten kommer nu att resultera i en betydligt renare uppsättning data, med de identifierade robotarna helt borttagna.

### Steg 7: Upprepa steg 2, 3 och 4 regelbundet

Ställ in minst en månatlig påminnelse för att identifiera och filtrera nya robotar, kanske före regelbundna schemalagda analyser.
