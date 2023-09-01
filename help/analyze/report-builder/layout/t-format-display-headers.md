---
description: Lär dig att namnge rapporten och konfigurera hur rad- och kolumnrubriker ska visas.
title: Formatera visningsrubriker
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
feature: Report Builder
role: User, Admin
exl-id: 168daa6b-965c-4f8b-97b7-651a7ad55d6c
source-git-commit: d218d07ec16e981d7e148092b91fbbd5711e840f
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 2%

---

# Formatera sidhuvuden för visning

Du kan namnge rapporten och konfigurera hur rad- och kolumnrubriker ska visas. Länken Formatalternativ är tillgänglig för pivottabellerna och de anpassade layouttyperna.

1. Skapa en förfrågan på [!UICONTROL Request Wizard: Step 1].
1. Klicka på **[!UICONTROL Next]**.
1. På [!UICONTROL Request Wizard: Step 2] lägg till mått och mätdata i begäran efter behov.
1. Klicka på **[!UICONTROL Format Options]**.
1. Konfigurera [!UICONTROL Display] alternativ:

   | Element | Beskrivning |
   |--- |--- |
   | Rapportnamn | Visar antingen namnet på rapporttypen som du valde i trädet i begärandeguiden: Steg 1 (till exempel [!DNL Traffic Report]) eller det namn du skriver i [!DNL Name this Request] fält. |
   | Parametrar för filter | Visar dimensionsfilter, t.ex. ett sökfilter. |
   | Segment | Visar segmentparametern. |
   | Datagenomskinlighet | Visar parametrar för datagenstid. Till exempel: Datasäkerhet: Sidvyer (1,5 tim. sedan), Avslutar (30 min. sedan) Se [Alternativ](/help/analyze/report-builder/options.md) för information om aktuell databearbetning. |

   Om visningsordningen [!UICONTROL Row Label] rutnätet (i steg 2) innehåller ett objekt, som visas först i begäran. Annars används det första objektet som finns i [!UICONTROL Column Label] rutnät. Om det inte finns några rad- eller kolumnobjekt [!UICONTROL Metrics] rutnät visas.

   **Visa rad- och kolumnrubriker:** Lägger till en rad och en kolumn för att visa dessa objekt.

   I version 3.11 kan du visa en rubrik för varje objekt. Version 4 visar alla dessa objekt eller inget av dem. Om du skapade en begäran i version 3.11 och öppnade den i version 4.x uppmanar Report Builder dig i steg 2 att uppdatera intervallet med en cell för objekt som saknar rubrik.

   **Ändra sidhuvuden till autofilter i Excel:** Endast tillgängligt om rad- och kolumnrubriker visas. Med den här inställningen skapas ett automatiskt Excel-filter som läggs till i data som Report Builder returnerar för den här begäran.

   >[!NOTE]
   >
   >Excel har bara stöd för ett autofilter per kalkylblad. Om du skapar ett nytt automatiskt filter i ett kalkylblad där det redan finns ett automatiskt filter visas ingen varning om att det befintliga automatiska filtret kommer att ersättas.

   **Utför automatisk kontur:** Omvandlar det datum som Report Builder returnerade från en listvy till en trädvy.

   **Namnge den här förfrågan:** Gör att du kan skriva ett användardefinierat namn för begäran eller använda standardnamnet som valts i steg 1. Det här namnet visas som [!UICONTROL Report] namnet i [!UICONTROL Request Manager]. Se [Namnge en begäran](/help/analyze/report-builder/layout/name-a-request.md).

1. Klicka på **[!UICONTROL OK]**.
