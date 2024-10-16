---
description: Lär dig att namnge rapporten och konfigurera hur rad- och kolumnrubriker ska visas.
title: Formatera visningsrubriker
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
feature: Report Builder
role: User, Admin
exl-id: 168daa6b-965c-4f8b-97b7-651a7ad55d6c
source-git-commit: 12d048b42c6a61e03dbbe73acb9d34df3e37693c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 1%

---

# Formatera visningsrubriker

Du kan namnge rapporten och konfigurera hur rad- och kolumnrubriker ska visas. Länken Formatalternativ är tillgänglig för pivottabellerna och de anpassade layouttyperna.

1. Skapa en begäran på [!UICONTROL Request Wizard: Step 1].
1. Klicka på **[!UICONTROL Next]**.
1. Lägg till mått och mätdata i formuläret [!UICONTROL Request Wizard: Step 2] efter behov.
1. Klicka på **[!UICONTROL Format Options]**.
1. Konfigurera alternativen för [!UICONTROL Display]:

   | Element | Beskrivning |
   |--- |--- |
   | Rapportnamn | Visar antingen namnet på den rapporttyp som du valde i trädet i begärandeguiden: Steg 1 (till exempel [!DNL Traffic Report]) eller namnet som du skriver i fältet [!DNL Name this Request]. |
   | Parametrar för filter | Visar dimensionsfilter, t.ex. ett sökfilter. |
   | Segment | Visar segmentparametern. |
   | Datagenomskinlighet | Visar parametrar för datagenstid. Till exempel:    Datasäkerhet: Sidvyer (för 1,5 tim sedan), Avslutar (för 30 min sedan) Se [Alternativ](/help/analyze/legacy-report-builder/options.md) för information om aktuell databearbetning. |

   Om [!UICONTROL Row Label]-rutnätet (i steg 2) innehåller ett objekt visas det först i begäran. Annars används det första objektet i rutnätet [!UICONTROL Column Label]. Om det inte finns några rad- eller kolumnobjekt visas det första objektet i rutnätet [!UICONTROL Metrics].

   **Visa rad- och kolumnrubriker:** Lägger till en rad och kolumn för att visa dessa objekt.

   I version 3.11 kan du visa en rubrik för varje objekt. Version 4 visar alla dessa objekt eller inget av dem. Om du skapade en begäran i version 3.11 och öppnade den i version 4.x uppmanar Report Builder dig i steg 2 att uppdatera intervallet med en cell för objekt som saknar rubrik.

   **Ändra rubriker till automatiska Excel-filter:** Endast tillgängligt om rad- och kolumnrubriker visas. Med den här inställningen skapas ett automatiskt Excel-filter som läggs till i data som Report Builder returnerar för den här begäran.

   >[!NOTE]
   >
   >Excel har bara stöd för ett autofilter per kalkylblad. Om du skapar ett nytt automatiskt filter i ett kalkylblad där det redan finns ett automatiskt filter visas ingen varning om att det befintliga automatiska filtret kommer att ersättas.

   **Utför autodisposition:** Omvandlar det datum som Report Builder returnerade från en listvy till en trädvy.

   **Namnge denna begäran:** Du kan ange ett användardefinierat namn för begäran eller använda standardnamnet som valts i steg 1. Det här namnet visas som [!UICONTROL Report]-namn i [!UICONTROL Request Manager]. Se [Namnge en begäran](/help/analyze/legacy-report-builder/layout/name-a-request.md).

1. Klicka på **[!UICONTROL OK]**.
