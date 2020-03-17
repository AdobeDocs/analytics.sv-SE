---
description: Du kan namnge rapporten och konfigurera hur rad- och kolumnrubriker ska visas. Länken Formatalternativ är tillgänglig för pivottabellerna och de anpassade layouttyperna.
title: Formatera visningsrubriker
topic: Report builder
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Formatera visningsrubriker

Du kan namnge rapporten och konfigurera hur rad- och kolumnrubriker ska visas. Länken Formatalternativ är tillgänglig för pivottabellerna och de anpassade layouttyperna.

1. Skapa en förfrågan på [!UICONTROL Request Wizard: Step 1]webben.
1. Klicka på **[!UICONTROL Next]**.
1. Lägg till mått och mätdata i [!UICONTROL Request Wizard: Step 2] formuläret efter behov.
1. Klicka på **[!UICONTROL Format Options]**.
1. Konfigurera [!UICONTROL Display] alternativen:

   | Element | Beskrivning |
   |--- |--- |
   | Rapportnamn | Visar namnet på rapporttypen som du valde i trädet i begärandeguiden: Steg 1 (till exempel [!DNL Traffic Report]) eller det namn du skriver i [!DNL Name this Request] fältet. |
   | Parametrar för filter | Visar dimensionsfilter, t.ex. ett sökfilter. |
   | Segment | Visar segmentparametern. |
   | Datasynkronisering | Visar parametrar för datagenstid. Till exempel:    Dataveriod: Sidvyer (för 1,5 tim. sedan), Avslutar (för 30 min. sedan) Se [Alternativ](/help/analyze/report-builder/options.md) för information om aktuell databearbetning. |

   När det gäller visningsordningen visas den först i begäran om stödrastret (i steg 2) innehåller ett objekt. [!UICONTROL Row Label] Annars används det första objektet i [!UICONTROL Column Label] rutnätet. Om det inte finns några rad- eller kolumnobjekt visas det första objektet i [!UICONTROL Metrics] rutnätet.

   **Visa rad- och kolumnrubriker:** Lägger till en rad och en kolumn för att visa dessa objekt.

   I version 3.11 kan du visa en rubrik för varje objekt. Version 4 visar alla dessa objekt eller inget av dem. Om du har skapat en begäran i version 3.11 och öppnat den i version 4.x får du en uppmaning i steg 2 att uppdatera intervallet med en cell för objekt som saknar rubrik.

   **Ändra sidhuvuden till autofilter i Excel:** Endast tillgängligt om rad- och kolumnrubriker visas. Den här inställningen skapar ett automatiskt Excel-filter och lägger till det i Data Report Builder-returer för den här begäran.

   >[!NOTE]
   >
   >Excel stöder bara ett autofilter per kalkylblad. Om du skapar ett nytt automatiskt filter i ett kalkylblad där det redan finns ett automatiskt filter visas ingen varning om att det befintliga automatiska filtret kommer att ersättas.

   **Utför automatisk kontur:** Omvandlar det datum som returneras av Report Builder från en listvy till en trädvy.

   **Namnge denna begäran:** Gör att du kan skriva ett användardefinierat namn för begäran eller använda standardnamnet som valts i steg 1. Det här namnet visas som [!UICONTROL Report] namn i [!UICONTROL Request Manager]. Se [Namnge en begäran](/help/analyze/report-builder/layout/name-a-request.md).

1. Klicka på **[!UICONTROL OK]**.
