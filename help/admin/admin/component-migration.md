---
description: Beskriver hur du migrerar komponenter och projekt från Adobe Analytics till Customer Journey Analytics.
title: Migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics
feature: Admin Tools
source-git-commit: 73cbfbbad4d8e7bb3107ee08861a6342aba85e84
workflow-type: tm+mt
source-wordcount: '1133'
ht-degree: 4%

---

# Migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics

Adobe Analytics-administratörer kan migrera Adobe Analytics-komponenter och -projekt till Customer Journey Analytics.

Migreringsprocessen omfattar:

* Återskapande av Adobe Analytics-projekt i Customer Journey Analytics.

* Matchande mått och mätvärden från Adobe Analytics rapporteringsprogram till mått och mätvärden i datavyer i Customer Journey Analytics.

  Vissa dimensioner och mätvärden matchas automatiskt. Andra måste du matcha manuellt som en del av migreringsprocessen.

## Förbereda för migrering

### Förutsättningar

Innan dina projekt och tillhörande mått och mätvärden är klara att migreras måste du:

* Använd Analytics-källkopplingen för att visa Adobe Analytics rapportsvitsdata i Customer Journey Analytics. Om du vill göra det måste du:

   * [Ställ in rapportsviter för konsumtion i Adobe Experience Platform och Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

   * [Infoga och använda data](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html)

* Se till att användare i Customer Journey Analytics är tilldelade datavyer där data matchas.

  Mer information finns i [Customer Journey Analytics behörigheter i Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) in [Åtkomstkontroll för Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

  Fliken Behörigheter ingår i varje produktprofil i Admin Console. Du kan lägga till användare i specifika produktprofiler. Sedan tilldelar du rättigheter till specifika datavyer och anger vilka behörigheter användarna i en produktprofil har.

* Skapa en migreringsplan enligt beskrivningen i avsnittet nedan, [Skapa en migreringsplan som en organisation](#create-a-migration-plan-as-an-organization).

### Förstå vad som ingår i en migrering

I följande tabell visas vilka element i ett projekt och en komponent som ingår i en migrering:


|  | Projekt | Dimensioner och mätvärden |
|---------|----------|---------|
| **Datumintervall** | Ja | Ej tillämpligt |
| **Segment** | Ja | Ej tillämpligt |
| **Snabbsegment** | Ja | Ej tillämpligt |
| **Paneler** | Ja | Ej tillämpligt |
| **Visualiseringar** | Ja | Ej tillämpligt |
| **Ägare** | (Definieras av användaren som utför migreringen) | ? |
| **Insamling** | Nej | Ej tillämpligt |
| **Delning (projektroller)** | Nej | Nej |
| **Anteckningar** | Nej | Ej tillämpligt |
| **Mappstruktur** | Nej | Ej tillämpligt |
| **Beskrivning** | Ja | ? |
| **Taggar** | ? | ? |
| **Scheman** | ? | Ej tillämpligt |
| **Attribution (on dimensions)** | Ej tillämpligt | ? |
| **Avvikelseidentifiering** | ? | Ej tillämpligt |
| **Bidragsanalys** | ? | Ej tillämpligt |
| **Larm** | ? | Ej tillämpligt |

{style="table-layout:auto"}

### Skapa en migreringsplan som en organisation

Eftersom alla komponenter som matchas för en viss projektmigrering gäller för alla framtida projektmigreringar för hela organisationen är det viktigt att organisationen planerar alla projektmigreringar i förväg.

För att undvika att enskilda administratörer fattar beslut i en silo när ett projekt migreras bör ni som organisation bestämma vilka dimensioner och mätvärden som ska matchas mot vad som matchas med vad.

## Migrera Adobe Analytics-projekt till Customer Journey Analytics

>[!IMPORTANT]
>
>Läs mer om hur du migrerar projekt i [Planera migreringen](#plan-the-migration) ovan.
>
>Alla dimensioner och mätvärden som du matchar är permanenta, både för det här projektet och för alla framtida projekt som migreras i hela organisationen. Alla matchningar du gör kan inte ändras.



1. I Adobe Analytics väljer du [!UICONTROL **Administratör**] tabbtangenten och sedan välja [!UICONTROL **Alla administratörer**].

1. Under [!UICONTROL **Datakonfiguration och insamling**], markera [!UICONTROL **Komponentmigrering**].

1. (Villkorligt) Om du snabbt vill hitta det projekt som du vill migrera kan du antingen:

   * Filtrera projektlistan genom att välja Filterikonen.

     Du kan filtrera efter följande kriterier:

      * Status

      * Taggar

      * Rapportsvit

      * Ägare

      * Andra filter

   * Använd sökfältet för att söka efter det projekt som du vill migrera.

1. För musen över projektet som du vill migrera och välj sedan **Migrera** icon ![Migrera projekt](assets/migrate.svg).

   eller

   Välj det projekt som du vill migrera och välj sedan [!UICONTROL **Migrera till Customer Journey Analytics**].

   Du kan bara välja ett projekt åt gången för migrering.

   The [!UICONTROL **Migrera project_name till Customer Journey Analytics**] visas.

   <!-- add screenshot -->

1. I [!UICONTROL **Projektägare**] börjar du skriva namnet på den användare som du vill ange som projektägare i Customer Journey Analytics och väljer sedan namnet i listrutan.

   Ägaren som du anger har fullständig behörighet till projektet.

1. I [!UICONTROL **Matcha schema för rapportsviter**] väljer du en rapportsvit.

1. I [!UICONTROL **Datavy**] väljer du datavyn i Customer Journey Analytics där du vill att projektet och komponenterna ska migreras.

1. Välj [!UICONTROL **Matcha schema**].

1. I [!UICONTROL **Matcha schema**] -avsnittet expanderar du [!UICONTROL **Dimensioner**] och [!UICONTROL **Mått**] -avsnitt.

   Vissa mått och mätvärden i Adobe Analytics matchas automatiskt mot en dimension eller ett mätvärde i Customer Journey Analytics. Andra måste matchas manuellt.

   **Automatiskt matchade dimensioner och mätvärden**

   Vissa mått och mätvärden i Adobe Analytics matchas automatiskt mot en dimension eller ett mätvärde i Customer Journey Analytics. Du kan inte fatta några matchande beslut för de här dimensionerna och måtten.

   Till exempel **Besök** i Adobe Analytics matchas automatiskt med **Sessioner** mätvärden i Customer Journey Analytics.

   Du kan välja vilken dimension eller vilket mätvärde som helst för att visa deras associerade ID:n.

   <!-- update screenshot after I can see the Status column -->

   ![Projektmigreringsschema](assets/project-migration-schema.png)

   **Matcha dimensioner och mätvärden manuellt**

   Andra mått och mätvärden i Adobe Analytics kan inte matchas automatiskt mot en dimension eller mätvärden i Customer Journey Analytics.

   När en dimension eller ett mätvärde inte kan matchas automatiskt visas en orange räknare bredvid [!UICONTROL **Dimensioner**] eller [!UICONTROL **Mått**] avsnittsrubrik, som anger antalet dimensioner eller mått som behöver matchas manuellt. I tabellen visas en varningsikon ![varningsikon](assets/schema-warning.png) visas bredvid varje dimension eller mätvärde som behöver matchas manuellt.

   <!-- update screenshot after I can see the Status column -->

   ![Manuell matchning av migreringsschema](assets/schema-manual-map.png)

1. Om du vill matcha mått och mått manuellt väljer du en dimension eller ett mått som innehåller en varningsikon ![varningsikon](assets/schema-warning.png)och sedan i [!UICONTROL **Matchande Customer Journey Analytics-mått**] fält (eller [!UICONTROL **Matchande Customer Journey Analytics-dimension**] om du matchar en dimension) väljer du den dimension eller det mått i Customer Journey Analytics som du vill matcha med den dimension eller det mått som du valde.

   ![matcha mått och mätvärden](assets/schema-manual-map-drop-down.png)

   Upprepa den här processen för varje dimension eller mätvärde som innehåller varningsikonen.

   När alla dimensioner och mått i Adobe Analytics rapportserie har matchats mot en dimension eller mätvärden i datavyn i Customer Journey Analytics, visas en grön bock ![bock](assets/report-suite-check.png) visas bredvid rapportsvitens namn i [!UICONTROL **Matcha schema för rapportsviter**] -avsnitt.

1. (Villkorligt) Om projektet som du migrerar innehåller mer än en rapportsvit väljer du en annan rapportsvit i [!UICONTROL **Matcha schema för rapportsviter**] och sedan upprepa steg 6 genom steg 10. <!-- double-check that the step numbers are still correct -->

1. Välj [!UICONTROL **Migrera**].

   >[!WARNING]
   >
   >   Ett varningsmeddelande visas när du har valt [!UICONTROL **Migrera**]. Innan du fortsätter måste du vara medveten om att alla dimensioner och mätvärden du matchar är permanenta, både för det här projektet och för alla framtida projekt som migreras i hela organisationen. Om du fortsätter går det inte att ändra de matchningar du gör.
