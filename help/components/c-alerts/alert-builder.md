---
description: Använd varningar i Analysis Workspace.
title: Översikt över Alert Builder
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 0%

---

# Alert Builder

>[!IMPORTANT]
>
>Intelligenta aviseringar är tillgängliga för Adobe [!DNL Analytics] Prime och Adobe [!DNL Analytics] Endast de ultimata kunderna.

Få åtkomst till varningsverktyget på ett av fyra sätt:

* Genom att använda följande kortkommando i Analysis Workspace:

   `ctrl (or cmd) + shift + a`
* Genom att gå till **[!UICONTROL Workspace]** > **[!UICONTROL Components]** > **[!UICONTROL New Alert]**.
* Genom att markera ett eller flera objekt på en frihandsritabell högerklickar och väljer du **[!UICONTROL Create Alert from Selection]**.
* Från en [!UICONTROL Reports & Analytics] rapport, genom att gå till **[!UICONTROL More]** > **[!UICONTROL Add Alert]**.

Gränssnittet i Alert Builder är bekant för dem som har skapat segment eller beräknade värden i [!DNL Analytics]:

![](assets/alert_builder.png)

**Aviseringsnamn**

Ange ett namn för aviseringen. Varningsnamnet kan innehålla rapportens namn eller måttets tröskelvärde.

**Tidsgranularitet**

Ange när du vill att måttet ska kontrolleras: Varje timme, Varje dag, Varje vecka eller Varje månad.

>[!NOTE]
>
>För rapportsviter med en anpassad kalender har vi inte stöd för månatlig granularitet i varningsverktyget.

**Mottagare**

Ange var aviseringen kan skickas. En varning kan skickas till en [!DNL Analytics] användare, en [!DNL Analytics] grupp, en obearbetad e-postadress eller ett telefonnummer.

>[!IMPORTANT]
>
>Telefonnumret måste föregås av ett plustecken (+) och ett [landskod](https://countrycode.org/).

**Förfallodatum**

Ange aviseringens förfallodatum.

**Skicka en avisering när...**

*... Någon av dessa metriska utlösare*

* Dra och släpp mätvärden på arbetsytan som lägger till utlösare.

   Observera att **&quot;inkompatibla komponenter&quot;** meddelandet visas om inte alla komponenter (mått/dimensioner/segment) i aviseringen är kompatibla med den valda rapportsviten.

* Ange tröskelvärdet som måttet måste överskrida innan en avisering anges. Du kan ange ett tröskelvärde och sedan något av följande villkor:

   * avvikelse finns
   * avvikelsen är större än förväntat
   * avvikelsen är under förväntad
   * avvikelsen överskrider
   * är över eller lika med
   * är under eller lika med
   * ändras med

* &quot;Anomaly överskrider&quot; är ett nytt villkor som överskrider de befintliga (statiska) tröskelvärdena. Den hämtar in algoritmer för avvikelseidentifiering som dynamiskt definierar utlösaren. Du kan ange ett tröskelvärde på 90 %, 95 %, 99 %, 99,75 % och 99,9 %.
* Timgranulariteter sätts till ett tröskelvärde på 99,75 % och daglig granularitet till 99 %.
* Observera att du även kan använda beräknade värden.

*... Med dessa filter*

Dra och släpp segment eller dimensioner för att lägga till filter. Om du till exempel lägger till segmentet&quot;Endast mobila enheter&quot; innebär det att regeln bara aktiveras för mobila enheter.

Ytterligare filter läggs till med en AND-programsats.

**Lägg till en regel**

Du kan lägga till OCH- eller OR-regler genom att klicka på kugghjulsikonen.

## Förhandsgranska varning {#section_10D75BA7B77E4C5FAF58A719C082E070}

I förhandsgranskningen av den interaktiva aviseringen visas hur ofta, ungefär, en avisering utlöses baserat på tidigare erfarenheter.

Om du t.ex. anger tidsterminalariteten till daglig, kan förhandsgranskningen tala om för dig att varningen skulle ha utlösts för ett visst mått x gånger under de senaste 30 eller 31 dagarna.

Om du upptäcker att för många aviseringar skulle ha utlösts kan du justera tröskelvärdet i [Aviseringshanteraren](/help/components/c-alerts/alert-manager.md).

![](assets/alert_preview.png)
