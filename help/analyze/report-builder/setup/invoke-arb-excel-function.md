---
description: Den här möjligheten integrerar användningen av Report Builder i det naturliga Excel-arbetsflödet utan att du behöver använda användargränssnittet i Report Builder.
title: Anropa Report Builder-funktioner från Microsoft Excel-funktioner
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
feature: Report Builder
role: User, Admin
exl-id: b412f2b5-affe-4297-af4b-85e8c6dfd257
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 3%

---

# Anropa Report Builder-funktioner från Microsoft Excel-funktioner

Den här möjligheten integrerar användningen av Report Builder i det naturliga Excel-arbetsflödet utan att du behöver använda användargränssnittet i Report Builder.

Du kan till exempel automatiskt uppdatera Report Builder-begäranden vars indatafilter baseras på data som hämtats i Excel från andra källor. Nu kan du göra detta med strängen RefreshRequestsInCellsRange(..) funktion. Alla anrop är asynkrona. De returnerar omedelbart och väntar inte på att ett anrop ska köras helt.

>[!NOTE]
>
>Du måste ha Report Builder 5.0 (eller senare) installerat för att den här funktionen ska fungera.

Här följer en tabell med en lista över funktioner som visas:

| Funktionsnamn | Beskrivning |
|---|---|
| string AsyncRefreshAll() | Uppdaterar alla Report Builder-begäranden som finns i en arbetsbok. |
| string AsyncRefreshRange(strängintervallAddressInA1Format) | Uppdaterar alla Report Builder-begäranden som finns i den angivna cellintervalladressen (ett stränguttryck som representerar ett cellintervall i A1-format, till exempel &quot;Sheet1!A2:A10&quot;). |
| string AsyncRefreshRangeAltTextParam() | Uppdaterar alla Report Builder-begäranden som finns i det angivna cellintervallet som skickas via den alternativa texten i MS Form Control. |
| string AsyncRefreshActiveWorksheet() | Uppdaterar alla Report Builder-begäranden som finns i det aktiva kalkylbladet. |
| string AsyncRefreshWorksheet(string worksheetName) | Uppdaterar alla Report Builder-begäranden som finns i det angivna kalkylbladet (kalkylbladets namn så som det visas på fliken). |
| string AsyncRefreshWorksheetAltTextParam(); | Uppdaterar alla Report Builder-begäranden som finns i det specifika kalkylbladsnamnet som skickades via den alternativa texten i MS-formulärkontrollen |
| string GetLastRunStatus() | Returnerar en sträng som beskriver statusen för den senaste körningen. |

Gå till [!UICONTROL Formulas] > [!UICONTROL Insert Function]. Längst ned i kategorilistan finns Adobe.ReportBuilder.Bridge:

![](assets/arb_functions.png)

## Använd de här funktionerna i en formel {#section_034311081C8D4D7AA9275C1435A087CD}

Formeln

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

säger&quot;Om värdet i cell P5 är text eller tomt, uppdaterar du det intervall som finns i cell P9.&quot;

## Använda Report Builder-funktioner med formatkontroll {#section_26123090B5BD49748C8D8ED7A1C5ED84}

Nu kan du tilldela ett makro till en kontroll som du har skapat och den kontrollen kan vara en funktion som uppdaterar en arbetsboksförfrågan. Funktionen AsyncRefreshActiveWorksheet uppdaterar till exempel alla begäranden i ett kalkylblad. Ibland kanske du bara vill uppdatera vissa förfrågningar, inte alla.

1. Ange makroparametern.
1. Högerklicka på kontrollen och välj **[!UICONTROL Assign Macro]**.
1. Ange funktionsnamnet för Report Builder (inga parametrar eller parenteser).

![](assets/assign_macro.png)

## Skicka parametrar till Report Builder via formatkontroll {#section_ECCA1F4990D244619DFD79138064CEF0}

De två funktionerna som tar en parameter kan användas med Formatkontroll, men endast via fältet Alt-text:

* AsyncRefreshRange(strängintervallAddressInA1Format)
* AsyncRefreshWorksheet(string worksheetName)

1. Högerklicka på kontrollen och välj **[!UICONTROL Format Control]**.

   ![](assets/format_control.png)

1. Klicka på [!UICONTROL Alt Text] -fliken.

   ![](assets/alt_text.png)

1. Under [!UICONTROL Alternative text]anger du cellområdet som du vill uppdatera.
1. Öppna listan över parametrar för Report builder under [!UICONTROL Formulas] > [!UICONTROL Insert Function]> [!UICONTROL Adobe.ReportBuilder.Bridge].

1. Välj en av de två funktionerna som slutar med AltTextParam och klicka på **[!UICONTROL OK]**.
