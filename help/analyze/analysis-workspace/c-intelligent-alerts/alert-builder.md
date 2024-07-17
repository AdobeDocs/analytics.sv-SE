---
description: Få aviseringar när projektkomponenterna når vissa tröskelvärden.
title: Alert Builder (Analysis Workspace)
feature: Alerts
role: User, Admin
exl-id: aae28c90-bfdf-49ff-bd38-c9ef63880bf4
source-git-commit: 58e1d3025b455de7fa07037b3b0659330c8324c7
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 0%

---

# Skapa aviseringar

>[!NOTE]
>
>Intelligenta aviseringar är endast tillgängliga för Adobe Analytics Prime- och Adobe Analytics Ultimate-kunder.

Med intelligenta aviseringar (eller bara &quot;aviseringar&quot;) i Adobe Analytics kan du få meddelanden direkt när onormala händelser inträffar i dina data. (Varningar om användning av serversamtal är en annan typ av varning som bara är tillgänglig för Analytics-administratörer. Dessa varningar meddelar dig om risken för eller förekomsten av en överbelastning i serversamtalsförbrukning och åtagandedata. Mer information finns i [Varningar om användning av serversamtal](/help/admin/admin/c-server-call-usage/scu-alerts.md).)

Mer detaljerad översiktsinformation om intelligenta aviseringar finns i [Översikt över intelligenta aviseringar](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md).

Så här skapar du en intelligent varning:

1. Börja skapa en avisering med hjälp av varningsverktyget. Du kan öppna varningsverktyget på något av följande sätt:

   * Öppna ett projekt i Analysis Workspace och välj sedan **[!UICONTROL Components]** > **[!UICONTROL Create alert]**.
   * Öppna ett projekt i Analysis Workspace och använd sedan följande kortkommando:

     `ctrl (or cmd) + shift + a`
   * Öppna ett projekt i Analysis Workspace, markera ett eller flera linjeobjekt i en frihandstabell, högerklicka och välj **[!UICONTROL Create alert from selection]**.

     Varningsbyggaren fylls i automatiskt för att skapa en avisering med rätt mätvärden och filter.
   * Skapa en avisering [från aviseringshanteraren](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-manager.md#create-alerts).

   Varningsbyggaren visas. Det här gränssnittet är bekant för dem som har skapat segment eller beräknade värden i Analytics:

   ![](assets/alert-builder.png)

1. Ange följande alternativ för att konfigurera varningen:

   | Alternativ | Beskrivning |
   |---------|----------|
   | [!UICONTROL **Titel**] | Ange ett namn för aviseringen. Varningsnamnet kan innehålla rapportens namn eller måttets tröskelvärde. |
   | [!UICONTROL **Beskrivning (valfritt)**] | Ange en beskrivning för aviseringen. |
   | [!UICONTROL **Tidsgranularitet**] | Välj hur ofta du vill att måttet ska kontrolleras: Varje dag, Varje vecka eller Varje månad.<p><b>Obs!</b>För datavyer med en anpassad kalender har vi inte stöd för månatlig granularitet i varningsverktyget.<!--true?--></p> |
   | [!UICONTROL **Mottagare**] | Ange var aviseringen kan skickas. En avisering kan skickas till en Analytics-användare, en Analytics-grupp, en raw-e-postadress eller till ett telefonnummer.<p><b>Viktigt!</b>Telefonnumret måste föregås av ett plustecken och en [landskod](https://countrycode.org/).</p><p>Det e-postmeddelande som en användare får när en varning har utlösts ser ut ungefär så här:</p><p>![](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **Förfallodatum**] | Ange det datum och den tidpunkt då du vill att aviseringen ska förfalla. |
   | [!UICONTROL **Skicka en avisering när**] | [!UICONTROL **Någon av dessa mätvärden utlöser**]: Dra och släpp mätvärden (inklusive beräknade värden) här för att skapa utlösare för aviseringen.<p>Ett **&quot;inkompatibla komponenter&quot;**-meddelande visas om inte alla mått, dimensioner eller segment i aviseringen är kompatibla med den datavyn som är vald.</p><p>Fastställ tröskelvärdet som måttet måste överskrida innan en avisering anges. Du kan ange ett tröskelvärde och sedan något av följande villkor:</p><ul><li>avvikelse finns</li><li>avvikelsen är större än förväntat</li><li>avvikelsen är under förväntad</li><li>är över eller lika med</li><li>är under eller lika med</li><li>ändras med</li><li>Du kan ange ett tröskelvärde på 90 %, 95 %, 99 %, 99,75 % och 99,9 %.</li></ul><p>[!UICONTROL **Med alla dessa filter**]: Dra och släpp segment eller dimensioner för att lägga till filter. Om du till exempel lägger till segmentet&quot;Endast mobila enheter&quot; innebär det att regeln bara aktiveras för mobila enheter. Du kan lägga till ytterligare filter med en AND-programsats. Du kan lägga till OCH- eller OR-regler genom att klicka på kugghjulsikonen.</p><p>Se [Intelligenta aviseringar - användningsfall](/help/analyze/analysis-workspace/c-intelligent-alerts/alerts-use-cases.md), t.ex. fall.</p> |
   | [!UICONTROL **Förhandsgranska**] | I förhandsgranskningen av den interaktiva aviseringen visas hur ofta, ungefär, en avisering utlöses baserat på tidigare erfarenheter.<p>Om du t.ex. anger tidsterminalariteten till daglig, kan förhandsgranskningen tala om för dig att varningen skulle ha utlösts för ett visst mått x gånger under de senaste 30 eller 31 dagarna.</p><p>Om du upptäcker att för många aviseringar skulle ha utlösts kan du justera tröskelvärdet i [Varningshanteraren](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Välj [!UICONTROL **Spara**].
