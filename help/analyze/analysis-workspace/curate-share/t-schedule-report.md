---
description: Skicka ett Analysis Workspace-projekt via e-post eller schemalägg det för leverans.
keywords: Analysis Workspace
title: Schemalägg projekt
feature: Curate and Share
role: User, Admin
exl-id: 2d6854f7-8954-4d55-b2be-25981cfb348b
source-git-commit: bf9f04ce6ff057ca66bcf0d9cf66540cea160444
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 1%

---

# Schemalägg projekt

Från arbetsytan **Dela-menyn** kan du skicka Analysis Workspace-projekt via e-post till utvalda mottagare. Filer kan skickas i CSV- eller PDF-format.

## Skicka filen nu

Så här skickar du en fil direkt till mottagarna via e-post:

1. Klicka på **[!UICONTROL Share]>[!UICONTROL Send File Now]**.
1. Ange filtypen (CSV eller PDF).
1. (Valfritt) Lägg till en beskrivning som ska inkluderas i e-postmeddelandet för att förklara filen som tas emot.
1. Lägg till mottagare eller grupper. Du kan även ange e-postadresser.
1. Klicka på **[!UICONTROL Send Now]**.
1. (Valfritt) Klicka på **[!UICONTROL Show scheduling options]** för att ange ett leveransschema.

![Skicka filen nu](assets/send-file-now.png)

## Skicka fil enligt schema

Så här skickar du en fil i ett återkommande schema till mottagarna via e-post:

1. Klicka på **[!UICONTROL Share]>[!UICONTROL Send File on Schedule]**.
1. Ange filtypen (CSV eller PDF).
1. (Valfritt) Lägg till en beskrivning som ska inkluderas i e-postmeddelandet för att förklara filen som tas emot.
1. Lägg till mottagare eller grupper. Du kan även ange e-postadresser.
1. Ange intervallet som schemat ska levereras över genom att ändra Inledande och Avslutande på indata. Slutdatumet måste vara inom ett år från den dag då schemat skapas eller ändras.
1. Ange leveransfrekvens. Varje frekvens tillåter olika anpassningar.
1. Klicka på **[!UICONTROL Send on schedule]**.

![](assets/send-on-schedule.png)

## Schemalagd projekthanterare

Schemalagda Analysis Workspace-projekt kan hanteras under **Analytics > Components > Scheduled Projects**.

I Hanteraren för schemalagda projekt kan du redigera och ta bort återkommande projektscheman. Sök efter ett schema i sökfältet eller med filteralternativen i den vänstra listen. Du kan filtrera efter tagg, godkända scheman, ägare med mera.

![](assets/scheduled-project-manager2.png)

| Fält | Beskrivning |
| --- | --- |
| [!UICONTROL Favorites] | Om du väljer stjärnikonen blir schemat en favorit. |
| [!UICONTROL Schedule ID] | Detta ID används främst för felsökning. |
| [!UICONTROL Title and Description] | Projektets namn och beskrivning. |
| [!UICONTROL Owner] | Personen som skapade och äger projektet. |
| [!UICONTROL Tags] | (valfritt) Taggning är ett bra sätt att ordna projekt. Alla användare kan skapa taggar och använda en eller flera taggar i ett projekt. Men du kan bara se taggar för de projekt som du äger eller som har delats med dig. |
| [!UICONTROL Delivered To] | Mottagare av det här schemalagda projektet. |
| [!UICONTROL Expiration Date] | Standardförfallodatumet beror på schemafrekvensen. Se &quot;Schemalagda förfallodatum för projekt&quot; nedan. |
| [!UICONTROL Frequency] | Hur ofta du vill att det här schemaprojektet ska skickas till mottagarna. |
| [!UICONTROL Execution Time] | Vid vilken tidpunkt på dagen det här schemalagda projektet skickas. |
| [!UICONTROL Number of Queries] | Antalet frågor mot det här projektet. |

## Vanliga åtgärder

Följande är vanliga åtgärder i hanteraren för schemalagda projekt:

| Åtgärd | Beskrivning |
|---|---|
| **[!UICONTROL Edit schedule]** | Klicka på schemats rubrik för att uppdatera dess leveransinställningar. |
| **[!UICONTROL Delete schedule]** | Markera det schemalagda projektet i listan och klicka sedan på Ta bort på menyn. Detta kommer att ta bort det valda schemat för projektet. själva projektet inte tas bort. |
| **[!UICONTROL Add tags]** | Markera det schemalagda projektet i listan och välj sedan Tagga eller Godkänn för att ordna dina scheman och göra dem enklare att söka efter. |
| **[!UICONTROL View failed schedules]** | Navigera till den vänstra listen > Andra filter > Misslyckade för att se misslyckade scheman. |
| **[!UICONTROL View expired schedules]** | Navigera till den vänstra listen > Andra filter > Förfallen om du vill visa scheman som har upphört att gälla. Klicka på schemats rubrik för att ställa in ett nytt leveransschema. |
| **[!UICONTROL View schedule ID]** | Navigera till kolumnalternativen längst upp till höger och lägg till kolumnen Schedule-ID i tabellen. Det schemalagda ID:t är ofta användbart vid felsökning. |

I Hanteraren för schemalagda projekt visas de objekt som en viss användare har skapat. Om användarkontot är inaktiverat i programmet stoppas alla schemalagda leveranser. Schemalagd projektägare kan vara **överförd** till en ny användare under **Admin > Analytics Users &amp; Assets > Transfer Assets**.

## Schemalagda förfallodatum för projekt

Utgångsdatum för schemalagda projekt beror på den schemalagda leveransfrekvensen:

* Leveranser per timme går ut om en vecka.
* Dagliga leveranser går ut om en månad.
* Leveranser per vecka går ut om 6 månader.
* Leveranser per månad eller år går ut om ett år.
