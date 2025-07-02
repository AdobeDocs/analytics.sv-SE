---
description: Lär dig hur du skapar varningar i Analysis Workspace.
title: Skapa aviseringar
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 24dd47e995523aedba1385ee8882af5e11c7b128
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 0%

---

# Skapa aviseringar {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Tidsgranularitet"
>abstract="Tidsgranularitet avser hur ofta varningen kontrolleras."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>Det går bara att använda aviseringar med avvikelseidentifiering (kallas även _Intelligent Alerts_) för organisationer med ett Adobe Analytics Prime- eller Ultimate-paket.

Med varningar i Adobe Analytics kan du meddelas baserat på ändrade procentsatser eller specifika datapunkter. Beroende på ditt Adobe Analytics-paket kan du även använda varningar som utlöses baserat på avvikelsetrösklar. Varningar om användning av serversamtal är en annan typ av varning som bara är tillgänglig för Analytics-administratörer. Dessa varningar meddelar dig om risken för eller förekomsten av en överbelastning i serversamtalsförbrukning och åtagandedata. Mer information finns i [Varningar om användning av serversamtal](/help/admin/admin/c-server-call-usage/scu-alerts.md).

Mer detaljerad information om aviseringar finns i [Översikt över aviseringar](intellligent-alerts.md).

Så här skapar du en varning:

1. Använd något av följande sätt för att skapa en varning.:

   * Öppna ett projekt i Analysis Workspace och välj sedan **[!UICONTROL Components]** > **[!UICONTROL Create alert]**.
   * Öppna ett projekt i Analysis Workspace och använd sedan följande kortkommando: ***cmd + shift + a*** (macOS) eller ***ctrl + shift + a*** (Windows).
   * Öppna ett projekt i Analysis Workspace, markera ett eller flera linjeobjekt i en frihandstabell, högerklicka och välj **[!UICONTROL Create alert from selection]**. Den här åtgärden fyller i [varningsverktyget](alert-builder.md) i förväg för att skapa en avisering med rätt mått och filter.
   * Skapa en avisering [från aviseringshanteraren](/help/components/c-alerts/alert-manager.md#create-alerts).

   Varningsbyggaren visas. Gränssnittet är välbekant med gränssnittet för att skapa segment eller beräknade värden i Analytics.



## Varningsverktyg

Gränssnittet i Alert Builder liknar det gränssnitt du använder för att skapa segment eller beräknade värden i Customer Journey Analytics:

![Gränssnitt för varningsverktyget](assets/alert-builder.png)

Ange följande information i varningsverktyget för en avisering:

| Element | Beskrivning |
|---------|----------|
| **[!UICONTROL Title]** | Ange ett namn för aviseringen. Varningsnamnet kan innehålla rapportens namn eller måttets tröskelvärde. |
| **[!UICONTROL Description (optional)]** | Ange en beskrivning för aviseringen. |
| **[!UICONTROL Time granularity]** | Välj hur ofta du vill att måttet ska kontrolleras: Varje dag, Varje vecka eller Varje månad.<p> |
| **[!UICONTROL Recipients]** | Ange var aviseringen kan skickas. En avisering kan skickas till en Analytics-användare, en Analytics-grupp, en raw-e-postadress eller till ett telefonnummer.<p><b>Viktigt</b>: Telefonnumret måste föregås av en `+` och en [landskod](https://countrycode.org/).</p><p>Ett exempel på e-postmeddelandet som en användare får:</p><p>![Varningsmeddelande](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Expiration date]** | Ange det datum och den tidpunkt då du vill att aviseringen ska förfalla. |
| **[!UICONTROL Delay]** | Den tid som krävs innan data är fullständiga och tillgängliga för att rapporteras i Customer Journey Analytics varierar beroende på organisation, vanligtvis mellan 3 och 9 timmar efter datahändelsetiden. För att varningarna ska vara korrekta måste händelsedata för ett givet händelseintervall vara fullständiga, vilket innebär att Adobe inte längre tar emot några händelsedata för det angivna händelseintervallet.<p>Om du vill ta hänsyn till den här fördröjningen av inmatningstiden har aviseringar en standardfördröjning på 9 timmar innan de skickas.</p><p>Du kan justera standardfördröjningen på 9 timmar till valfri plats mellan 0 och 24 timmar. Om du minskar fördröjningen till under 9 timmar kan det dock innebära att du rapporterar ofullständiga data, vilket leder till felaktig varningsinformation.</p><p>Tänk på följande när du minskar fördröjningstiden:</p><ul><li>**Förstå datatillgänglighet jämfört med datainsamling**: Alla batchdata importeras endast till en Experience Platform-datauppsättning efter en period på 3 till 9 timmar. För att varningarna ska vara korrekta måste datainmatningen vara fullständig, med alla batchdata tillgängliga i datauppsättningen.</li><li>**Bestäm hur lång tid det tar för dina data att bli fullständiga och tillgängliga i datauppsättningen**: Dataöverföringstiderna skiljer sig åt i olika organisationer. Se till att fördröjningen som du väljer för varningsleverans är samma eller mindre frekvent än den tid det tar för batchdata att vara tillgängliga i plattformsdatauppsättningen <!--add link? -->.</li><p>**Tips!** Det mest korrekta sättet att veta hur lång tid det tar för alla batchdata att slutföras och hämtas till plattformsdatauppsättningen är att rådfråga datateknikerna i organisationen.</p><p>Du kan också få en allmän uppfattning om hur lång tid det tar för batchleveransen i din organisation att vara tillgänglig i Experience Platform datamängd. Skapa följande friformstabell i Analysis Workspace:</p><ol><li>I en frihandstabell i Analysis Workspace lägger du till måtten [!UICONTROL **Händelser**] och [!UICONTROL **Dag**] .</li><li>Dela upp dimensionen [!UICONTROL **Dag**] med en [!UICONTROL **Timmar**]-dimension.<p>Timmar som inte har några data visas som 0.</p></li></ol><li>**Ta hänsyn till fel i dina beräkningar**: Om du minskar standardfördröjningstiden konfigurerar du fördröjningen i minst en timme längre än den tid det tar för organisationen att få en fullständig dataöverföring. Om det till exempel finns en 3-timmars fördröjning innan dataimporten är klar bör du ange fördröjningen till 4 timmar.</li> |
| **[!UICONTROL Send an alert when]** | [!UICONTROL **Någon av dessa mätvärden utlöser**]: Dra och släpp mätvärden (inklusive beräknade värden) här för att skapa utlösare för aviseringen.<p>Ett **&quot;inkompatibla komponenter&quot;**-meddelande visas om inte alla mått, dimensioner eller segment i aviseringen är kompatibla med den datavyn som är vald.</p><p>Fastställ tröskelvärdet som måttet måste överskrida innan en avisering anges. Du kan ange ett tröskelvärde och sedan något av följande villkor:</p><ul><li>avvikelse finns</li><li>avvikelsen är större än förväntat</li><li>avvikelsen är under förväntad</li><li>är över eller lika med</li><li>är under eller lika med</li><li>ändras med</li><li>Du kan ange ett tröskelvärde på 90 %, 95 %, 99 %, 99,75 % och 99,9 %.</li></ul><p>[!UICONTROL **Med alla dessa filter**]: Dra och släpp segment eller dimensioner för att lägga till filter i aviseringen. Om du till exempel lägger till segmentet *Endast mobila enheter* innebär det att regeln bara aktiveras för mobila enheter. Du kan lägga till ytterligare filter med en AND-programsats. Du kan lägga till OCH- eller OR-regler genom att klicka på kugghjulsikonen.</p><p>Se [Varningar - användningsfall](alerts-use-cases.md) använder till exempel fall.</p> |
| **[!UICONTROL Preview]** | Den interaktiva förhandsvisningen visar hur ofta, ungefär, en varning utlöses baserat på tidigare erfarenheter.<p>Om du t.ex. anger tidsterminalariteten till daglig, kan förhandsgranskningen tala om för dig att varningen skulle ha utlösts för ett visst mått x gånger under de senaste 30 eller 31 dagarna.</p><p>Om för många aviseringar utlöses kan du justera tröskelvärdet i [Hantera aviseringar](alert-manager.md).</p><p>![](assets/alert-preview.png){width="50%"}</p> |

<!--

   ![](assets/alert-builder.png)

1. Specify the following options to configure the alert:

   | Option | Description | 
   |---------|----------|
   | [!UICONTROL **Title**]  | Specify a name for the alert. The alert name might contain the name of the report or the metrics threshold. | 
   | [!UICONTROL **Description (optional)**] | Specify a description for the alert. | 
   | [!UICONTROL **Time granularity**] | Select how often you want the metric to be checked: Hourly, Daily, Weekly, or Monthly.<p><b>Note:</b> For report suites with a custom calendar, monthly granularity in the Alert Builder is not supported.<!--true?--</p | 
   | [!UICONTROL **Recipients**] | Specify where the alert can be sent. An alert can be sent to an Analytics user, an Analytics group, a raw email address, or to a phone number.<p><b>Important:</b> The phone number must be preceded by `+` and a [country code](https://countrycode.org/).</p><p>The e-mail that a user would receive once an alert has been triggered looks similar to:</p><p>![](assets/alerts-email.PNG)</p> | 
   | [!UICONTROL **Expiration date**] | Set the date and time when you want the alert to expire. | 
   | [!UICONTROL **Send an alert when**] | [!UICONTROL **Any of these metrics trigger**]: Drag and drop metrics (including calculated metrics) here to create triggers for the alert.<p>An **"incompatible components"** message appears if not all the metrics, dimensions, or segments in the alert are compatible with the currently selected data view.</p><p>Determine the threshold that the metric must exceed before an alert is set. You can set this value to a threshold and then to one of the following conditions:</p><ul><li>anomaly exists</li><li>anomaly is above expected</li><li>anomaly is below expected</li><li>is above or equals</li><li>is below or equals</li><li>changes by</li><li>You can set a threshold of 90%, 95%, 99%, 99.75%, and 99.9%.</li></ul><p>[!UICONTROL **With all of these filters**]: Drag and drop segments or dimensions to add filters. For example, adding a *Mobile Devices Only* segment would mean that the rule triggers only for mobile devices. You can add additional filters by using an AND statement. You can add AND or OR rules by clicking the gear icon.</p><p>See [Alerts - use cases](/help/components/c-alerts/alerts-use-cases.md) for example.</p> | 
   | [!UICONTROL **Preview**] | The interactive alert preview shows you how often, approximately, an alert will fire based on past experience.<p>For example, if you set the time granularity to daily, the preview can tell you that the alert would have been triggered for a certain metric x times during the last 30 or 31 days. The preview approximation window is established by the alert frequency setting. For daily alert frequencies, the preview window approximates the previous 30 days. For weekly alert frequencies, the preview window approximates the last 12 weeks. For monthly alert frequencies, the preview window approximates the previous 12 months.</p><p>If you find that too many alerts will be triggered, you can adjust the threshold in the [Alert Manager](/help/components/c-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Select [!UICONTROL **Save**].

-->