---
description: Få aviseringar när projektkomponenterna når vissa tröskelvärden.
title: Alert Builder (Analysis Workspace)
feature: Alerts
role: User, Admin
exl-id: aae28c90-bfdf-49ff-bd38-c9ef63880bf4
source-git-commit: a979fc8787fa96f8fa8317996ac66341a6f54354
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 0%

---

# Varningsverktyg

>[!NOTE]
>
>Intelligenta aviseringar är endast tillgängliga för Adobe Analytics Prime- och Adobe Analytics Ultimate-kunder.

## Access Alert Builder

Få åtkomst till varningsverktyget på ett av fyra sätt:

* Genom att använda följande kortkommando i Analysis Workspace:

  `ctrl (or cmd) + shift + a`
* Genom att gå till **[!UICONTROL Workspace]** > **[!UICONTROL Components]** > **[!UICONTROL New Alert]**.
* Genom att markera ett eller flera objekt på en frihandsritabell högerklickar och väljer du **[!UICONTROL Create Alert from Selection]**.

## Skapa aviseringar

Gränssnittet i Alert Builder är bekant för dem som har skapat segment eller beräknade värden i Analytics:

![](assets/alert_builder.png)

<!--Meike, I edited this table for validation -->

**Aviseringsnamn**

Ange ett namn för aviseringen. Varningsnamnet kan innehålla rapportens namn eller måttets tröskelvärde.

**Tidsnoggrannhet**

Ange när du vill att måttet ska kontrolleras: Varje timme, Varje dag, Varje vecka eller Varje månad.

>[!NOTE]
>
>För rapportsviter med en anpassad kalender har vi inte stöd för månatlig granularitet i varningsverktyget.

**Mottagare**

Ange var aviseringen kan skickas. En avisering kan skickas till en Analytics-användare, en Analytics-grupp, en raw-e-postadress eller till ett telefonnummer.

>[!IMPORTANT]
>
>Telefonnumret måste föregås av ett plustecken och ett [landskod](https://countrycode.org/).

Det e-postmeddelande som en användare får när en varning har utlösts ser ut ungefär så här:

![](assets/alerts-email.PNG)

**Förfallodatum**

Ange aviseringens förfallodatum.

**Skicka en avisering när...**

*... Någon av dessa metriska utlösare*

* Dra och släpp mätvärden på arbetsytan som lägger till utlösare.

  An **inkompatibla komponenter** meddelandet visas om inte alla komponenter (mått/dimensioner/segment) i aviseringen är kompatibla med den valda rapportsviten.
* Fastställ tröskelvärdet som måttet måste överskrida innan en avisering anges. Du kan ange ett tröskelvärde och sedan något av följande villkor:

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

Om du upptäcker att för många aviseringar skulle ha utlösts kan du justera tröskelvärdet i [Aviseringshanteraren](/help/components/c-alerts/alert-manager.md).

![](assets/alert_preview.png)
