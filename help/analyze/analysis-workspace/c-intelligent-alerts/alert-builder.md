---
description: 'null'
title: Alert Builder
uuid: ebc2d457-4abd-4b1a-9357-489b5aeb3f64
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 1%

---


# Alert Builder

>[!IMPORTANT]
>
>Intelligenta aviseringar är endast tillgängliga för kunder som har Analytics Prime och Adobe Analytics Ultimate.

## Access Alert Builder

Få åtkomst till varningsverktyget på ett av fyra sätt:

* Genom att använda följande kortkommando i Analysis Workspace:

   `ctrl (or cmd) + shift + a`
* Genom att gå till **[!UICONTROL Workspace]** > **[!UICONTROL Components]** > **[!UICONTROL New Alert]**.
* Genom att markera ett eller flera frihandsritningsobjekt högerklickar och väljer du **[!UICONTROL Create Alert from Selection]**.
* I en rapport från Reports &amp; Analytics går du till **[!UICONTROL More]** > **[!UICONTROL Add Alert]**.

## Skapa aviseringar

Gränssnittet i Alert Builder är bekant för dem som har byggt segment eller beräknade värden i Analytics:

![](assets/alert_builder.png)

<!--Meike, I edited this table for validation -->

**Aviseringsnamn**

Ange ett namn för aviseringen. Varningsnamnet kan innehålla rapportens namn eller måttets tröskelvärde.

**Tidsgranularitet**

Ange när du vill att måttet ska kontrolleras: Varje timme, Varje dag, Varje vecka eller Varje månad.

>[!NOTE]
>
>För rapportsviter med en anpassad kalender har vi inte stöd för månatlig granularitet i varningsverktyget.

**Mottagare**

Ange var aviseringen kan skickas. En varning kan skickas till en Analytics-användare, en Analytics-grupp, en oformaterad e-postadress eller till ett telefonnummer.

>[!IMPORTANT]
>
>Telefonnumret måste föregås av ett plustecken (+) och en [landskod](https://countrycode.org/).

Det e-postmeddelande som en användare får när en varning har utlösts ser ut ungefär så här:

![](assets/alerts-email.PNG)

**Förfallodatum**

Ange aviseringens förfallodatum.

**Skicka en avisering när...**

*... Någon av dessa metriska utlösare*

* Dra och släpp mätvärden på arbetsytan som lägger till utlösare.

   Ett **&quot;inkompatibla komponenter&quot;** visas om inte alla komponenter (mått/dimensioner/segment) i aviseringen är kompatibla med den valda rapportsviten.
* Ange tröskelvärdet som måttet måste överskrida innan en avisering anges. Du kan ange ett tröskelvärde och sedan något av följande villkor:

   * avvikelse finns
   * avvikelsen är större än förväntat
   * avvikelsen är under förväntad
   * är över eller lika med
   * är under eller lika med
   * ändras med
   * Du kan ange ett tröskelvärde på 90 %, 95 %, 99 %, 99,75 % och 99,9 %.
   Observera att du även kan använda beräknade värden.

*... Med dessa filter*

* Dra och släpp segment eller dimensioner för att lägga till filter. Om du till exempel lägger till segmentet&quot;Endast mobila enheter&quot; innebär det att regeln bara aktiveras för mobila enheter.
* Ytterligare filter läggs till med en AND-programsats.

**Lägg till en regel**

Du kan lägga till OCH- eller OR-regler genom att klicka på kugghjulsikonen.

## Förhandsgranska aviseringar {#section_10D75BA7B77E4C5FAF58A719C082E070}

I förhandsgranskningen av den interaktiva aviseringen visas hur ofta, ungefär, en avisering utlöses baserat på tidigare erfarenheter.

Om du t.ex. anger tidsterminalariteten till daglig, kan förhandsgranskningen tala om för dig att varningen skulle ha utlösts för ett visst mått x gånger under de senaste 30 eller 31 dagarna.

Om du upptäcker att för många aviseringar skulle ha utlösts kan du justera tröskelvärdet i [Varningshanteraren](/help/components/c-alerts/alert-manager.md).

![](assets/alert_preview.png)
