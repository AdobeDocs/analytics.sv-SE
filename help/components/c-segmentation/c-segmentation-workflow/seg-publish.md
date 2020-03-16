---
description: Gör att du kan använda segmentet för marknadsföringsaktivitet i målgruppsbiblioteket, målgruppshanteraren och Audience Manager.
title: Publicera segment till Experience Cloud
topic: Segments
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
translation-type: tm+mt
source-git-commit: 5c555bbea04bed68dd8b569ee2cdd7d25092bb7a

---


# Publicera segment till Experience Cloud

Genom att publicera ett segment i Experience Cloud kan ni använda segmentet för marknadsföringsaktiviteter i [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], [!DNL Advertising Cloud]och [!DNL Campaign]. Nyligen har uppdateringarna optimerat publiceringsarbetsflödet avsevärt. Tidigare tog det ca 48 timmar att publicera ett användbart segment.

Bearbetningen kan nu ta upp till 8 timmar, men beroende på annan trafik och segmentstorleken kan bearbetningen gå ännu snabbare. (För närvarande finns det dock inget sätt att informera dig om när segmentet är tillgängligt, så du måste kontrollera manuellt.) Vi har också ökat det maximala antalet publicerbara segment till 75 (från 20). Du kan visa publicerade segment i Komponenter > Segment.

> [!NOTE] Adobe Campaign (Classic och Standard) uppför sig annorlunda på så sätt att det får ytterligare 24 timmars fördröjning utöver 8-timmars fördröjning.


## Förutsättningar

* Se till att rapportsviten som du sparar det här segmentet i är [aktiverad för Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). Annars kan du inte publicera det på Experience Cloud.
* Se till att du arbetar i en rapportsserie som är [kopplad till din Experience Cloud-organisation](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).
* Se till att din organisation använder Experience Cloud ID:n.
* Innan du kan publicera segment måste din administratör tilldela [!UICONTROL Segment Publishing] behörigheten till en produktprofil i [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)och lägga till dig i produktprofilen.


## Överväganden

* **Report Suite-begränsningar**: Du kan publicera upp till 75 segment per rapportserie. Den här gränsen gäller. Om du redan har 75 segment publicerade kan du inte publicera några ytterligare segment förrän du avpublicerar tillräckligt många segment för att komma under tröskelvärdet på 75 segment.
* **Medlemskapsbegränsningar**: Målgrupper som delas med [!DNL Experience Cloud] Analytics får inte överstiga 20 miljoner unika medlemmar.
* **Dataintegritet**: Publiken filtreras inte baserat på besökarens autentiseringstillstånd. Om en besökare kan bläddra på webbplatsen i icke-autentiserade och autentiserade lägen, kan åtgärder som utförs när en besökare inte är autentiserad ändå göra att besökaren inkluderas i en målgrupp. Granska [sekretessen](https://www.adobe.com/privacy/experience-cloud.html) för Adobe Experience Cloud för att förstå de fullständiga integritetspåföljderna av målgruppsdelning.
* Om du vill diskutera **skillnaderna mellan segment i[!DNL Adobe Analytics]och[!DNL Audience Manager]**i går[du hit](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

## Tidslinje för segmentpublicering

| Vad finns tillgängliga? | När det är tillgängligt | Var den finns |
|---|---|---|
| Metadata (segmenttitel och definition) | Omedelbart efter publicering | [!DNL Audience Manager], [!UICONTROL Experience Cloud Audience Library], [!DNL Target] |
| Användbart segment med medlemskap | ~ 8 timmar efter publicering | Visningsprogram för besökarprofiler i [!DNL Audience Manager] |
| Fackens- och medlemskapspopulation | Inom 24-48 timmar | [!DNL Audience Manager] |

## Publicera segment i [!UICONTROL Segment Builder]

1. Navigera till **[!UICONTROL Analytics > Workspace > Components > Segments]> +**
1. Skapa ett segment i [!UICONTROL Segment Builder].
1. Ange en rubrik och en beskrivning för segmentet - annars kan du inte spara det.
1. Kontrollera **[!UICONTROL Publish this segment to the Experience Cloud (for *rapportsviten *)]**.

![](assets/publish-ec.png)

>[!IMPORTANT]
>
>Se till att du använder&quot;Besökare med Experience Cloud ID&quot; när du tittar på förhandsvisningar av segment i Analytics i stället för den totala förhandsgranskningen av segmentet&quot;unika besökare&quot; när du jämför Adobe Analytics-nummer med Audience Manager-nummer:
>
>![](assets/seg-vis-ecid.png)

| Element | Beskrivning |
|---|---|
| **[!UICONTROL Publish this segment to the Experience Cloud (for *<report suite>*)]** | När det här alternativet är aktiverat delas segmentets namn och definition (dvs. gränssnittets målgrupp så ofta som den används i annonsplattformar) direkt med Experience Cloud, medan segmentmedlemskapet utvärderas och delas var fjärde timme. <br> När den målgruppen är kopplad till en aktivitet i [!DNL Target]till exempel [!DNL Analytics] börjar skicka ID:n för besökare som är kvalificerade för Experience Cloud och [!DNL Target] målgruppen. Då börjar målgruppsnamnet och motsvarande data visas på sidan för Experience Cloud-målgrupper. </br> |
| **[!UICONTROL Audience Creation Window]** | Den tidsram du väljer används för att skapa målgruppen baserat på rullande kalenderinformation. Exempel:&quot;De senaste 30 dagarna&quot; (standard) innehåller besökare som har kvalificerat sig för målgruppen under de senaste 30 dagarna från dagens datum (INTE från det ursprungliga datumet när segmentet skapades). |
| **[!UICONTROL Create in Audience Library]** | Segmenten som du skapar och publicerar kan göras tillgängliga utan fördröjning i Experience Cloud Audience Library. De är inte beroende av Analytics-uppdateringar. Dessa segment räknas inte av mot din gräns på 75 publicerade segment. |
| **[!UICONTROL x of 75 Published]** | Visar antalet segment som du har publicerat till Experience Cloud. Klicka på länken för att visa en lista över publicerade segment och deras associerade rapportsvit och ägare. |
| **[!UICONTROL Save]** | Sparar det här segmentet. |

## Avpublicera eller ta bort segment

Om du vill ta bort ett segment som har publicerats i Experience Cloud måste du först avpublicera det. Om du vill avpublicera ett segment **avmarkerar** du bara kryssrutan som du använde för att publicera det.

> [!NOTE] Du **kan inte** avpublicera ett segment som används av någon av följande Adobe-lösningar: [!DNL Analytics] (in [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (för [!DNL Core Service] &amp; [!DNL Audience Manager] kunder) och alla andra externa partner (för [!DNL Audience Manager] kunder). Du **kan** avpublicera ett segment som används av [!DNL Target].

## Visa segmentpubliceringsstatus i [!UICONTROL Segment Manager]

1. Navigera till [!UICONTROL Analytics > Components > Segments].
1. Lägg märke till den nya [!UICONTROL Published] kolumnen. Ja/Nej avser om segmentet har publicerats till Experience Cloud eller inte.

![](assets/publish-status.png)

## Hämta [!DNL Audience Manager] UID

Det finns två sätt att hämta det AAM UUID som är kopplat till webbläsaren:

* Adobe Experience Cloud Debugger
* Internt utvecklarverktyg i webbläsare (t.ex. Chrome Developer Tools)

Följande skärmbilder visar hur du hämtar AAM UUID i webbläsaren och använder det i Audience Manager Visitor Profile Viewer för att validera trait &amp; segment-medlemskap.

**Metod 1: Använd Adobe Experience CLoud Debugger**

1. Hämta och installera [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) i Chrome Web Store.
1. Starta felsökaren när du läser in en sida.
1. Bläddra till avsnittet Audience Manager och hitta AAM UUID som angetts på den aktuella webbläsarsidan (`50814298273775797762943354787774730612` i exemplet nedan)

![](assets/debugger.jpg)

**Metod 2: Använd Chrome Developer Tools (eller andra verktyg för webbläsarutveckling)**

1. Starta Chrome Developer Tools innan du läser in en sida
1. Läs in sidan och kontrollera Program > Cookies. AAM UUID ska anges i cookie-filen från tredje part ([adobe.demdex.net](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) i exemplet nedan). Fältdemonstrationen är AAM UUID-setet i webbläsaren (`50814298273775797762943354787774730612` i exemplet nedan).

![Verktyg för Chrome Developer](assets/ggogle-uuid.png)

## Använd Audience Manager [!UICONTROL Visitor Profile Viewer]

AAM UUID i webbläsaren används som standard när den [!UICONTROL Visitor Profile Viewer] läses in. Om du verifierar trait-implementeringar för andra användare anger du ett UUID i fältet UUID och klickar på [!UICONTROL Refresh]. Mer information finns i [Visitor Profile Viewer](https://marketing.adobe.com/resources/help/en_US/aam/t_visitor_profile_viewer.html) .

![](assets/aam-vpv.png)

## Visa segmentegenskaperna i [!DNL Audience Manager]

I AAM utvärderas listan över besökare med ECID för ett visst segment i direktuppspelning när Analytics delar segment med Experience Cloud.

1. In [!DNL Audience Manager], gå till [!UICONTROL Audience Data > Traits > Analytics Traits]. Du ser en mapp för varje Analytics-rapportssvit som mappas till din Experience Cloud-organisation. Dessa mappar (för Traits, Segments och Data Sources) skapas när huvudtjänsten Profiles and Audiences/People initieras eller etableras.
1. Välj mapp för den rapportserie i vilken du tidigare skapade det segment som du vill dela med [!DNL Audience Manager]. Du ser segmentet/målgruppen som du skapade. När du delar ett segment inträffar två saker i [!DNL Audience Manager]:
* Ett drag skapas först utan data. Cirka. 8 timmar efter att segmentet publicerats i [!DNL Analytics]kommer listan över ECID:n att introduceras och delas med [!DNL Audience Manager] och andra Experience Cloud-lösningar.

![](assets/aam-traits.png)

* Ett entraitetssegment skapas. Den använder den datakälla som är associerad med rapportsviten där du publicerade segmentet.
* Utgångsdatumet för trait är nu 16 dagar (tidigare två dagar).

## Visa segmentet i [!DNL Adobe Target]

Kryssrutan [!UICONTROL Publish this segment to the Experience Cloud] när segmenten skapas i Adobe Analytics gör att segmentet är tillgängligt i Adobe Target egna målgruppsbibliotek. Ett segment som skapats i Analytics eller Audience Manager kan användas för aktiviteter i Target. Ni kan till exempel skapa kampanjaktiviteter baserat på analysstatistik och målgruppssegment som skapats i Analytics.
], click [!UICONTROL Audiences].
1. På [!UICONTROL Audiences] sidan kan du hitta målgruppen som kommer från [!DNL Experience Cloud]. Dessa målgrupper är tillgängliga för användning i [!DNL Target] aktiviteter.

