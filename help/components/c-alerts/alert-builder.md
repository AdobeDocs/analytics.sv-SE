---
description: Använd varningar i Analysis Workspace.
title: Översikt över Alert Builder
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: a71c3c6911ed2c2eb9202c8f149a44d6364017b8
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Skapa aviseringar

>[!NOTE]
>
>Det går bara att använda aviseringar med avvikelseidentifiering (kallas även _Intelligent Alerts_) för organisationer med ett Adobe Analytics Select-, Prime- eller Ultimate-paket.

Med varningar i Adobe Analytics kan du meddelas baserat på ändrade procentsatser eller specifika datapunkter. Beroende på ditt Adobe Analytics-paket kan du även använda varningar som utlöses baserat på avvikelsetrösklar. (Varningar om användning av serversamtal är en annan typ av varning som bara är tillgänglig för Analytics-administratörer. Dessa varningar meddelar dig om risken för eller förekomsten av en överbelastning i serversamtalsförbrukning och åtagandedata. Mer information finns i [Varningar om användning av serversamtal](/help/admin/admin/c-server-call-usage/scu-alerts.md).)

Mer detaljerad översiktsinformation om aviseringar finns i [Översikt över aviseringar](/help/components/c-alerts/intellligent-alerts.md).

Så här skapar du en varning:

1. Börja skapa en avisering med hjälp av varningsverktyget. Du kan öppna varningsverktyget på något av följande sätt:

   * Öppna ett projekt i Analysis Workspace och välj sedan **[!UICONTROL Components]** > **[!UICONTROL Create alert]**.
   * Öppna ett projekt i Analysis Workspace och använd sedan följande kortkommando:

     `ctrl (or cmd) + shift + a`
   * Öppna ett projekt i Analysis Workspace, markera ett eller flera linjeobjekt i en frihandstabell, högerklicka och välj **[!UICONTROL Create alert from selection]**.

     Varningsbyggaren fylls i automatiskt för att skapa en avisering med rätt mätvärden och filter.
   * Skapa en avisering [från aviseringshanteraren](/help/components/c-alerts/alert-manager.md#create-alerts).

   Varningsbyggaren visas. Det här gränssnittet är bekant för dem som har skapat segment eller beräknade värden i Analytics:

   ![](assets/alert-builder.png)

1. Ange följande alternativ för att konfigurera varningen:

   | Alternativ | Beskrivning |
   |---------|----------|
   | [!UICONTROL **Titel**] | Ange ett namn för aviseringen. Varningsnamnet kan innehålla rapportens namn eller måttets tröskelvärde. |
   | [!UICONTROL **Beskrivning (valfritt)**] | Ange en beskrivning för aviseringen. |
   | [!UICONTROL **Tidsgranularitet**] | Välj hur ofta du vill att måttet ska kontrolleras: varje timme, varje dag, varje vecka eller varje månad.<p><b>Obs!</b>För datavyer med en anpassad kalender har vi inte stöd för månatlig granularitet i varningsverktyget.<!--true?--></p> |
   | [!UICONTROL **Mottagare**] | Ange var aviseringen kan skickas. En avisering kan skickas till en Analytics-användare, en Analytics-grupp, en raw-e-postadress eller till ett telefonnummer.<p><b>Viktigt!</b>Telefonnumret måste föregås av ett plustecken och en [landskod](https://countrycode.org/).</p><p>Det e-postmeddelande som en användare får när en varning har utlösts ser ut ungefär så här:</p><p>![](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **Förfallodatum**] | Ange det datum och den tidpunkt då du vill att aviseringen ska förfalla. |
   | [!UICONTROL **Skicka en avisering när**] | [!UICONTROL **Någon av dessa mätvärden utlöser**]: Dra och släpp mätvärden (inklusive beräknade värden) här för att skapa utlösare för aviseringen.<p>Ett **&quot;inkompatibla komponenter&quot;**-meddelande visas om inte alla mått, dimensioner eller segment i aviseringen är kompatibla med den datavyn som är vald.</p><p>Fastställ tröskelvärdet som måttet måste överskrida innan en avisering anges. Du kan ange ett tröskelvärde och sedan något av följande villkor:</p><ul><li>avvikelse finns</li><li>avvikelsen är större än förväntat</li><li>avvikelsen är under förväntad</li><li>är över eller lika med</li><li>är under eller lika med</li><li>ändras med</li><li>Du kan ange ett tröskelvärde på 90 %, 95 %, 99 %, 99,75 % och 99,9 %.</li></ul><p>[!UICONTROL **Med alla dessa filter**]: Dra och släpp segment eller dimensioner för att lägga till filter. Om du till exempel lägger till segmentet&quot;Endast mobila enheter&quot; innebär det att regeln bara aktiveras för mobila enheter. Du kan lägga till ytterligare filter med en AND-programsats. Du kan lägga till OCH- eller OR-regler genom att klicka på kugghjulsikonen.</p><p>Se [Varningar - användningsfall](/help/components/c-alerts/alerts-use-cases.md) använder till exempel fall.</p> |
   | [!UICONTROL **Förhandsgranska**] | I förhandsgranskningen av den interaktiva aviseringen visas hur ofta, ungefär, en avisering utlöses baserat på tidigare erfarenheter.<p>Om du t.ex. anger tidsterminalariteten till daglig, kan förhandsgranskningen tala om för dig att varningen skulle ha utlösts för ett visst mått x gånger under de senaste 30 eller 31 dagarna.</p><p>Om du upptäcker att för många aviseringar skulle ha utlösts kan du justera tröskelvärdet i [Varningshanteraren](/help/components/c-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Välj [!UICONTROL **Spara**].
