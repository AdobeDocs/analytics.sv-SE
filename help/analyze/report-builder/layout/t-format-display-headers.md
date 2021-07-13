---
description: Du kan namnge rapporten och konfigurera hur rad- och kolumnrubriker ska visas. Länken Formatalternativ är tillgänglig för pivottabellerna och de anpassade layouttyperna.
title: Formatera sidhuvuden för visning
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
feature: Report Builder
role: User, Admin
exl-id: 168daa6b-965c-4f8b-97b7-651a7ad55d6c
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 3%

---

# Formatera sidhuvuden för visning

Du kan namnge rapporten och konfigurera hur rad- och kolumnrubriker ska visas. Länken Formatalternativ är tillgänglig för pivottabellerna och de anpassade layouttyperna.

1. Skapa en begäran på [!UICONTROL Request Wizard: Step 1].
1. Klicka på **[!UICONTROL Next]**.
1. På [!UICONTROL Request Wizard: Step 2]-formuläret lägger du till mått och mätdata i begäran efter behov.
1. Klicka på **[!UICONTROL Format Options]**.
1. Konfigurera alternativen för [!UICONTROL Display]:

   | Element | Beskrivning |
   |--- |--- |
   | Rapportnamn | Visar namnet på rapporttypen som du valde i trädet i begärandeguiden: Steg 1 (till exempel [!DNL Traffic Report]) eller det namn du skriver i fältet [!DNL Name this Request]. |
   | Parametrar för filter | Visar dimensionsfilter, t.ex. ett sökfilter. |
   | Segment | Visar segmentparametern. |
   | Datasynkronisering | Visar parametrar för datagenstid. Till exempel:    Dataveriod: Sidvyer (för 1,5 tim. sedan), Avslutar (för 30 min. sedan) Se [Alternativ](/help/analyze/report-builder/options.md) för information om aktuell databearbetning. |

   Om [!UICONTROL Row Label]-rutnätet (i steg 2) innehåller ett objekt visas det först i begäran. Annars används det första objektet i [!UICONTROL Column Label]-rutnätet. Om det inte finns några rad- eller kolumnobjekt visas det första objektet i rutnätet [!UICONTROL Metrics].

   **Visa rad- och kolumnrubriker:** Lägger till en rad och kolumn för att visa dessa objekt.

   I version 3.11 kan du visa en rubrik för varje objekt. Version 4 visar alla dessa objekt eller inget av dem. Om du har skapat en begäran i version 3.11 och öppnat den i version 4.x får du en uppmaning i steg 2 att uppdatera intervallet med en cell för objekt som saknar rubrik.

   **Ändra rubriker till autofilter för Excel:** Endast tillgängligt om rad- och kolumnrubriker visas. Den här inställningen skapar ett automatiskt Excel-filter och lägger till det i Data Report Builder-returer för den här begäran.

   >[!NOTE]
   >
   >Excel har bara stöd för ett autofilter per kalkylblad. Om du skapar ett nytt automatiskt filter i ett kalkylblad där det redan finns ett automatiskt filter visas ingen varning om att det befintliga automatiska filtret kommer att ersättas.

   **Utför autodisposition:** Omvandlar det datum som returneras av rapportbyggaren från en listvy till en trädvy.

   **Ge begäran ett namn:** Gör att du kan ange ett användardefinierat namn för begäran eller använda standardnamnet som valts i steg 1. Det här namnet visas som [!UICONTROL Report]-namn i [!UICONTROL Request Manager]. Se [Namnge en begäran](/help/analyze/report-builder/layout/name-a-request.md).

1. Klicka på **[!UICONTROL OK]**.
