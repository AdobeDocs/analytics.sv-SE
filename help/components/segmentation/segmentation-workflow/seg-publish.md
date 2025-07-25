---
description: Lär dig hur du publicerar segment för marknadsföringsaktiviteter i Audience Library, Target och Audience Manager.
title: Publicera segment
feature: Segmentation
exl-id: 0215f896-d3f8-42cc-ac8d-8a94b009927b
source-git-commit: c44bffa45ab8ed29ea28b91b2b3dc51811ab25fe
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 0%

---

# Publicera segment {#publish-segments}

>[!CONTEXTUALHELP]
>id="components_segments_publishing"
>title="Experience Cloud"
>abstract="Ni kan publicera målgruppen i målgruppsbiblioteket där målgruppen kan användas för marknadsföringsaktiviteter i Target och andra Experience Cloud-lösningar."

>[!CONTEXTUALHELP]
>id="components_segments_audiencelibrary"
>title="Målgruppsbibliotek"
>abstract="Segment som har skapats i målgruppsbiblioteket är tillgängliga direkt och är inte beroende av Analytics-uppdateringar."


Du kan publicera ett Adobe Analytics-segment till Experience Cloud. Du kan alltså använda segmentet för marknadsföringsaktivitet i [!DNL Audience Manager] och i andra aktiveringskanaler, inklusive [!DNL Advertising Cloud], [!DNL Target] och [!DNL Campaign].

Ni kan publicera Analytics-segment till Experience Cloud på mindre än 8 timmar. Använd dessa segment för att aktivera målgrupper i Audience Manager för alla destinationer i efterföljande led.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Publicera segment](https://video.tv.adobe.com/v/32842?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Adobe Campaign (Classic och Standard) beter sig annorlunda genom att det får ytterligare 24 timmars fördröjning utöver 8-timmars fördröjning.

## Förutsättningar

* Kontrollera att rapportsviten som du sparar det här segmentet i är [aktiverad för Experience Cloud](https://experienceleague.adobe.com/sv/docs/analytics/components/segmentation/segmentation-workflow/seg-publish). Annars kan du inte publicera den på Experience Cloud.
* Se till att din organisation använder Experience Cloud ID:n.
* Innan du kan publicera segment måste din administratör tilldela [!UICONTROL Segment Publishing]-behörigheten till en produktprofil i [Admin Console](https://experienceleague.adobe.com/sv/docs/core-services/interface/administration/admin-tool-experience-cloud) och lägga till dig i produktprofilen.

## Överväganden

* **Report Suite-begränsningar**: Du kan publicera upp till 75 segment per rapportserie. Den här gränsen gäller. Om du redan har 75 segment publicerade kan du inte publicera några ytterligare segment förrän du avpublicerar tillräckligt många segment för att komma under tröskelvärdet på 75 segment.
* **Medlemskapsgränser**: Publiker som delas med [!DNL Experience Cloud] från Adobe Analytics får inte överstiga 20 miljoner unika medlemmar.
* **Dataintegritet**: Målgrupperna filtreras inte baserat på autentiseringstillståndet för en besökare. En besökare kan kanske bläddra på webbplatsen i icke-autentiserade och autentiserade lägen. Åtgärder som utförs när en besökare inte är autentiserad kan ändå göra att en besökare inkluderas i en målgrupp. Granska [Adobe Experience Cloud sekretess](https://www.adobe.com/privacy/experience-cloud.html) om du vill veta mer om målgruppsdelningens konsekvenser för integriteten.
* En diskussion om **skillnaderna mellan segment i [!DNL Adobe Analytics] och[!DNL Audience Manager]** finns i [Förstå segment i Analytics och Audience Manager](https://experienceleague.adobe.com/sv/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments).

## Tidslinje för segmentpublicering

| Vad finns tillgängliga? | När det är tillgängligt | Var den finns |
|---|---|---|
| Metadata (segmenttitel och definition) | Omedelbart efter publicering | [!DNL Audience Manager], [!UICONTROL Experience Cloud Audience Library], [!DNL Target] |
| Användbart segment med medlemskap | ~ 8 timmar efter publicering | Visningsprogram för besökarprofiler i [!DNL Audience Manager] |
| Fackens- och medlemskapspopulation | Inom 24-48 timmar | [!DNL Audience Manager] |

>[!NOTE]
>En gång i veckan synkroniseras alla data helt för att ta hänsyn till eventuella deltavärden eller avvikelser som inte fångats in under den föregående veckan.

## Publicera segment i [!UICONTROL Segment builder]

1. I Adobe Analytics går du till **[!UICONTROL Components]** > **[!UICONTROL Segments]**
1. Välj **[!UICONTROL Add]** om du vill skapa ett nytt segment.
   ![Publicera Experience Cloud](assets/publish-ec.png)
1. Ange en rubrik och en beskrivning för segmentet. Dessa fält är obligatoriska innan du kan spara segmentet.
1. I avsnittet **[!UICONTROL Experience Cloud publishing]** väljer du alternativet **[!UICONTROL Publish this segment to the Experience Cloud (for *rapportsviten *)]**.

   >[!IMPORTANT]
   >
   >Kontrollera att du övervakar **[!UICONTROL Visitors with Experience Cloud ID]** i **[!UICONTROL Data Preview]** i stället för **[!UICONTROL Unique Visitors]** när du jämför Adobe Analytics-nummer med Audience Manager-nummer.
   >

| Element | Beskrivning |
|---|---|
| **[!UICONTROL Publish this segment to the Experience Cloud (for *rapportserie *)]** | När det här alternativet är aktiverat delas segmenttiteln och definitionen med Experience Cloud omedelbart, medan segmentmedlemskapet utvärderas och delas var fjärde timme. <br> När den målgruppen är associerad med en aktivitet i [!DNL Target], till exempel, börjar [!DNL Analytics] skicka ID:n för besökare som är kvalificerade för den Experience Cloud och [!DNL Target] målgruppen. Då börjar målgruppsnamnet och motsvarande data visas på sidan [!DNL Audience Library] i Experience Cloud. </br> |
| **[!UICONTROL Audience Creation Window]** | Den tidsram du väljer används för att skapa målgruppen baserat på rullande kalenderinformation. **[!UICONTROL Last 30 days]** (standard) innehåller till exempel besökare som har kvalificerat sig för målgruppen under de senaste 30 dagarna från dagens datum (INTE från det ursprungliga datumet när segmentet skapades). |
| **[!UICONTROL Create in Audience Library]** | Segmenten som du skapar och publicerar kan göras tillgängliga utan fördröjning på sidan [!DNL Audience Library] i Experience Cloud. De är inte beroende av Analytics-uppdateringar. Dessa segment räknas inte av mot din gräns på 75 publicerade segment. |
| **[!UICONTROL x of 75 Published]** | Antalet segment som du har publicerat till Experience Cloud. Klicka på länken för att visa en lista över publicerade segment och deras associerade rapportsvit och ägare. |
| **[!UICONTROL Save]** | Sparar detta segment. |

## Avpublicera eller ta bort segment

>[!CAUTION]
>
>Om du vill ta bort ett segment som har publicerats till Experience Cloud måste du först avpublicera segmentet. Om du vill avpublicera ett segment avmarkerar du bara **[!UICONTROL Publish this segment to the Experience Cloud (for *rapportsviten *)]**.


>[!NOTE]
>
>Du **kan inte** avpublicera ett segment som för närvarande används av någon av följande Adobe-lösningar: [!DNL Analytics] (i [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (för [!DNL Core Service]- och [!DNL Audience Manager]-kunder) och alla andra externa partner (för [!DNL Audience Manager]-kunder). Du **kan** avpublicera ett segment som används av [!DNL Target].

## Visa segmentens publiceringsstatus

Det högsta antalet publicerbara Adobe Analytics-segment är 75.

Så här visar du publicerade segment:

1. Gå till **[!UICONTROL Components]** > **[!UICONTROL Segments]** i Adobe Analytics.

1. Visa kolumnen **[!UICONTROL Published]**. **[!UICONTROL Yes]** i den här kolumnen anger att segmentet publiceras till Experience Cloud. **[!UICONTROL No]** anger att segmentet inte har publicerats.

## Hämta UUID:t [!DNL Audience Manager]

Det finns två sätt att hämta det Adobe Audience Manager UUID som är kopplat till webbläsaren:

* Adobe Experience Cloud Debugger
* Inbyggt utvecklarverktyg i webbläsare (t.ex. Chrome Developer Tools)

Följande skärmbilder visar hur du hämtar Adobe Audience Manager UUID i webbläsaren och använder det i Audience Manager Visitor Profile Viewer för att validera trait &amp; segment-medlemskap.

### Metod 1: Använd Adobe Experience Cloud Debugger

1. Hämta och installera [Adobe Experience Cloud Debugger](/help/implement/validate/debugger.md) i Chrome Web Store.
1. Starta felsökaren när du läser in en sida.
1. Bläddra till avsnittet Audience Manager och hitta Adobe Audience Manager UUID som finns på den aktuella webbläsarsidan
(`35721780439475290181087231320657663953` i exemplet nedan)

   ![Felsökning](assets/aepdebugger.png)

### Metod 2: Använda Chrome Developer Tools (eller andra verktyg för webbläsarutvecklare)

1. Starta Chrome Developer Tools innan du läser in en sida
1. Läs in sidan och kontrollera Program > Cookies. Adobe Audience Manager UUID ska anges i tredjepartsprodukten
Demdex cookie ([adobe.demdex.net](https://experienceleague.adobe.com/sv/docs/audience-manager/user-guide/reference/demdex-calls) i exemplet nedan). Fältdemonstrationen är Adobe Audience Manager UUID-uppsättningen
i webbläsaren (`35721780439475290181087231320657663953` i exemplet nedan).

   ![Chrome Developer Tools](assets/devtools.png)

## Använd Audience Manager [!UICONTROL Visitor Profile Viewer]

Adobe Audience Manager UUID i webbläsaren är som standard när [!UICONTROL Visitor Profile Viewer] läses in. Om du verifierar trait-implementeringar för andra användare anger du ett UUID i UUID-fältet och klickar på [!UICONTROL Refresh]. Mer information finns i [Visitor Profile Viewer](https://experienceleague.adobe.com/sv/docs/audience-manager/user-guide/features/visitor-profile-viewer).

## Visa segmentegenskaperna i [!DNL Audience Manager]

I Adobe Audience Manager utvärderas listan över besökare med ECID för ett visst segment medan Analytics delar segment med Experience Cloud.

1. Gå till [!DNL Audience Manager] > **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** i **[!UICONTROL Analytics Traits]**. Du ser en mapp för varje Analytics-rapportssvit som mappas till din Experience Cloud-organisation. Dessa mappar (för Traits, Segments och Data Sources) skapas när huvudtjänsten Profiles and Audiences/People initieras eller etableras.
1. Välj mappen för den rapportserie i vilken du tidigare skapade det segment som du vill dela med [!DNL Audience Manager]. Du ser segmentet/målgruppen som du skapade. När du delar ett segment inträffar två saker i [!DNL Audience Manager]:
   * Ett drag skapas först utan data. Cirka. 8 timmar efter att segmentet har publicerats i [!DNL Analytics], kommer listan över ECID:n att introduceras och delas med [!DNL Audience Manager] och andra Experience Cloud-lösningar.

     ![Målgruppshanterarens egenskaper](assets/aam-traits.png)

   * Ett entraitetssegment skapas. Den använder den datakälla som är associerad med rapportsviten där du publicerade segmentet.
   * Utgångsdatumet för trait är nu 16 dagar (tidigare två dagar).

## Visa segmentet i [!DNL Adobe Target]

**[!UICONTROL Publish this segment to the Experience Cloud]** tillåter att segmentet är tillgängligt i Adobe Target anpassade målgruppsbibliotek. Ett segment som skapats i Analytics eller Audience Manager kan användas för aktiviteter i Target. Ni kan till exempel skapa kampanjaktiviteter baserat på analysstatistik och målgruppssegment som skapats i Analytics.

I Adobe Target:

1. Välj **[!UICONTROL Audiences]**.
1. På sidan **[!UICONTROL Audiences]** letar du reda på målgruppen som kommer från [!DNL Experience Cloud]. Dessa målgrupper är tillgängliga för användning i [!DNL Target]-aktiviteter.

   ![Målgrupper](assets/target-audiences.png)
