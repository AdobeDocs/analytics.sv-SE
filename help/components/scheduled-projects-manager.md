---
description: Se och hantera schemalagda rapporter i hela organisationen.
title: Schemalagd projektledare
feature: Admin Tools
exl-id: 8bc8d983-f680-48fa-8483-694c87a9ae4c
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# Schemalagda projekt

Schemalagda Analysis Workspace-projekt kan hanteras under **Analys > Komponenter > Schemalagda projekt**.

När du hanterar schemalagda projekt kan du redigera och ta bort återkommande projektscheman:

* Ändra filtyp (.csv eller PDF)
* Uppdatera projektbeskrivningen
* Lägga till eller ta bort mottagare
* Ändra frekvens

Ändra ett schemalagt projekt

1. Välj **Analys > Komponenter > Schemalagda projekt**.
1. Sök efter ett schema i sökfältet eller med filteralternativen i den vänstra listen. Du kan filtrera efter [!UICONTROL Tags], [!UICONTROL Owners], [!UICONTROL Favorites] och mer.

![Skärmbild som visar listan över schemalagda projekt med kolumnen med rubrik, ägare, taggar, levererade till och andra kolumner som beskrivs i avsnittet Tillgängliga kolumner.](assets/scheduled-project-manager2.png)

## Tillgängliga kolumner

| Fält | Beskrivning |
| --- | --- |
| [!UICONTROL Favorites] | Om du väljer stjärnikonen blir schemat en favorit. |
| [!UICONTROL Schedule ID] | Detta ID används främst för felsökning. |
| [!UICONTROL Title and description] | Projektets namn och beskrivning. |
| [!UICONTROL Owner] | Personen som skapade och äger projektet. |
| [!UICONTROL Tags] | (valfritt) Taggning är ett bra sätt att ordna projekt. Alla användare kan skapa taggar och använda en eller flera taggar i ett projekt. Men du kan bara se taggar för de projekt som du äger eller som har delats med dig. |
| [!UICONTROL Delivered to] | Mottagare av det här schemalagda projektet. |
| [!UICONTROL Expiration date] | För alla schemalagda projektfrekvenser kan du ange förfallodatumet för upp till ett år i framtiden. |
| [!UICONTROL Frequency] | Hur ofta du vill att det här schemaprojektet ska skickas till mottagarna. |
| [!UICONTROL Execution time] | Vid vilken tidpunkt på dagen det här schemalagda projektet skickas. |
| [!UICONTROL Number of queries] | Antalet frågor mot det här projektet. |

## Vanliga åtgärder

Följande är vanliga åtgärder i hanteraren för schemalagda projekt:

| Åtgärd | Beskrivning |
|---|---|
| **[!UICONTROL Edit]** | Välj schemats titel om du vill uppdatera dess leveransinställningar. |
| **[!UICONTROL Delete]** | Markera det schemalagda projektet i listan och klicka sedan på Ta bort på menyn. Detta tar bort det valda schemat för projektet. Själva projektet tas inte bort. |
| **[!UICONTROL Tag]** | Markera det schemalagda projektet i listan och välj sedan Tagga eller Godkänn för att ordna dina scheman och göra dem enklare att söka efter. |
| **[!UICONTROL View failed schedules]** | Navigera till den vänstra listen > Andra filter > Misslyckade för att se misslyckade scheman. |
| **[!UICONTROL View expired schedules]** | Navigera till den vänstra listen > Andra filter > Förfallen om du vill visa scheman som har upphört att gälla. Klicka på schemats rubrik för att ställa in ett nytt leveransschema. |
| **[!UICONTROL View schedule ID]** | Navigera till kolumnalternativen längst upp till höger och lägg till kolumnen Schedule-ID i tabellen. Det schemalagda ID:t är ofta användbart vid felsökning. |

I hanteraren för schemalagda projekt visas de objekt som en viss användare har skapat. Om användarkontot är inaktiverat i programmet stoppas alla schemalagda leveranser. Schemalagd projektägarskap kan överföras till en ny användare under **Admin** > **Analytics Users &amp; Assets** > **Transfer Assets**.
