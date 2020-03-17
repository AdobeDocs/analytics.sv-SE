---
description: 'null'
title: Publicera till Power BI - översikt
uuid: ad688817-6e3c-45da-983d-48c123465309
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Publicera till Power BI - översikt

Microsoft Power BI är en serie instrumentpaneler för affärsanalys för att analysera data och dela insikter. Tack vare Adobe Analytics-integreringen med Power BI kan ni visualisera analysdata från Report Builder i Microsoft Power BI och enkelt dela dem i hela organisationen.

Tidigare skulle du som analytiker schemalägga att Report Builder-arbetsböcker ska distribueras via e-post (eller ftp). Du kan nu ge dina företagsanvändarintressenter åtkomst (inifrån deras Power BI-konton) till korrekta och aktuella data i en webbaserad miljö som är tillgänglig över olika plattformar och enheter.

Genom att kombinera rapportgenereringsfunktionen i Report Builder med visualiseringsfunktionerna i Power BI blir informationen mer tillgänglig för alla i organisationen. Med Power BI kan ni även integrera Adobe Analytics med andra datakällor (t.ex. försäljningsplats, CRM) för att identifiera unika kundinsikter, associationer och möjligheter.

![](assets/aaplusbi.png)

Tack vare integreringen med Adobe Report Builder kan du

* [Publicera schemalagda Report Builder-arbetsböcker till Power BI](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)
* [Publicera alla formaterade tabeller i arbetsboken som Power BI-datauppsättningstabeller](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)
* [Publicera alla Report Builder-begäranden som Power BI-datauppsättningstabeller](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)

## Systemkrav {#section_0B71092D853446F38FA36447DAC0D32B}

* Adobe Report Builder 5.5 [installerat](/help/analyze/report-builder/setup/t-install-arb.md)
* Aktivt Microsoft-konto som gör att du kan logga in på Power BI

## Publicera arbetsbok till Power BI {#section_21CA66229EC240D49594A9A7D3FBA687}

Schemalagda arbetsböcker formateras med Excel-kalkylblad som innehåller data från Adobe Analytics och skickas regelbundet enligt schema.

**Publicera arbetsbok i Report Builder**

1. Generera och spara en arbetsbok i Report Builder.
1. Klicka på **[!UICONTROL Schedule]** > **[!UICONTROL New]** i verktygsfältet Report Builder.

1. Markera kryssrutan invid **[!UICONTROL Publish Workbook to Microsoft Power BI]** guiden Grundläggande schemaläggning.

   ![](assets/simple-schedule-wizard.png)

1. Ange din e-postadress och skicka omedelbart eller ange schemaläggningsfrekvens (timme, dag, osv.).
1. Klicka **[!UICONTROL OK]** för att publicera.
1. Du ombeds nu logga in på ditt Microsoft-konto. Ange dina autentiseringsuppgifter.
1. Arbetsboken i Report Builder schemaläggs och publiceras i Power BI.

   För varje schemalagd instans och när schemaläggningsprocessen i Report Builder har uppdaterat arbetsboken med uppdaterade analysdata publiceras arbetsboken till Microsoft Power BI.

**Visa arbetsboksdata i Report Builder i Power BI**

1. I Power BI dubbelklickar du på arbetsboken under [!UICONTROL Workbooks] menyn.

   ![](assets/workbooks-power-bi.png)

1. Nu kan du visa arbetsbokens kontrollpanelsdata.  ![](assets/view-data-pbi.png)

1. Du kan sedan fästa ett område i den här arbetsboken för att inkludera det i någon av dina Power BI-instrumentpaneler.

## Publicera alla formaterade tabeller i arbetsboken som Power BI-datamängdsregister {#section_7C54A54E75184DD6BAEF4ACCE241239A}

> [!NOTE] Om arbetsboken innehåller ett makro kommer&quot;Publicera alla formaterade tabeller i arbetsboken som Power BI-datauppsättningstabeller&quot; att inaktiveras.

I stället för att importera hela arbetsboken kan du bara importera innehållet i alla formaterade tabeller i arbetsboken.

**Användningsfall**: Du har en Excel-arbetsbok som hämtar data från flera Report Builder-begäranden och skapar en sammanfattningstabell med många formler. Du kan bara importera sammanfattningstabellen till Power BI och skapa en visualisering för den.

**Publicera en formaterad tabell i Report Builder**

1. Generera en datatabell med en rubrikrad, följt av en datarad i Report Builder.
1. Markera tabellen och välj **[!UICONTROL Format as Table]** på [!UICONTROL Home] menyn. Tabellen namnges som standard (Tabell 1, Tabell 2 osv.), men du kan ändra namnet på [!UICONTROL Design]menyn.

1. Klicka på **[!UICONTROL Schedule]** > **[!UICONTROL New]** i verktygsfältet Report Builder.

1. Klicka på i guiden Grundläggande schemaläggning **[!UICONTROL Advanced Scheduling Options]**.
1. Markera kryssrutan bredvid på [!UICONTROL Scheduling Wizard - Advanced]fliken **[!UICONTROL Publishing Options]** . **[!UICONTROL Publish all Formatted Tables as Power BI dataset tables]**.

   ![](assets/advanced-schedule-wizard2.png)

1. (Valfritt) Du kan anpassa namnet på den publicerade resursen i Power BI. Detta kan vara användbart om du använder versionshantering som en del av arbetsbokens namn (t.ex. myworkbook_v1.1.xlsx) och du inte vill att versionsnumret ska visas i namnet på den publicerade Power BI-resursen. Den har en fördel som den publicerade resursen inte kommer att ändras om versionsnumret ändras. (Se [specifikationerna](/help/analyze/report-builder/c-publish-power-bi/specifications-limits.md) här.)

**Visa tabelldata i Power BI**

1. Gå till menyn **[!UICONTROL Workspaces]** > **[!UICONTROL Datasets]** i Power BI.

   ![](assets/datasets-menu.png)

1. Markera den datauppsättning som du publicerade och klicka på [!UICONTROL Create report] ikonen bredvid den. Observera att tabellerna kommer att visas som fält.

   ![](assets/formatted-tables.png)

1. Markera en tabell och dess associerade kolumner.

   ![](assets/view-table-dataset.png)

1. På [!UICONTROL Visualizations] menyn kan du välja hur en tabell ska visas i Power BI. Du kan till exempel välja att presentera data som ett linjediagram:

   ![](assets/bi-line-graph.png)

1. Härifrån kan du skapa visualiseringar från den här datauppsättningstabellen.

## Publicera alla Report Builder-begäranden som Power BI-datauppsättningstabeller {#section_0C26057C7DBB4068A643FDD688F6E463}

Ni kan förvandla alla era förfrågningar till datauppsättningstabeller och skapa visualiseringar ovanpå dem.

>[!IMPORTANT]
>
>Om arbetsboken innehåller fler än 100 begäranden publiceras endast de första 100 förfrågningarna till Power BI. För varje begäran som publiceras till Power BI publiceras dessutom bara de 10 000 första dataraderna. Så även om dessa förfrågningar kan levereras via schemaläggning är publiceringens omfattning begränsad till Power BI.

1. Öppna eller skapa en arbetsbok med Report Builder-begäranden i Report Builder.
1. Klicka på **[!UICONTROL Schedule]** > **[!UICONTROL New]** i verktygsfältet Report Builder.

1. Klicka på i guiden Grundläggande schemaläggning **[!UICONTROL Advanced Scheduling Options]**.
1. Markera kryssrutan invid [!UICONTROL Scheduling Wizard - Advanced]på **[!UICONTROL Publishing Options]** fliken **[!UICONTROL Publish all Report Builder Requests as Power BI Dataset Tables]**![](assets/advanced-schedule-wizard2.png)

1. Klicka på **[!UICONTROL OK]**.

**Visa begärandedata i Power BI**

Varje schemalagd Report Builder-begäran publiceras som en tabell i datauppsättningen. Varje begärandetabell namnges efter den primära dimensionen i begäran och har en [!UICONTROL Report Suite] och en [!UICONTROL Segments] kolumn.

1. Gå till menyn **[!UICONTROL Workspaces]** > **[!UICONTROL Datasets]** i Power BI.

1. Markera den förfrågan som du har publicerat och klicka på [!UICONTROL Create report] ikonen bredvid den.

   Observera att förfrågningarna visas som tabeller på [!UICONTROL Fields] menyn.

   ![](assets/published-requests.png)

   >[!NOTE]
   >
   >Oavsett hur du konfigurerade din Report Builder-begäran så att den kan placeras på kalkylbladet (pivottayout, anpassad layout, vissa kolumner är osynliga) kommer Report Builder alltid att publicera din begäran i samma tvådimensionella radformat med en rubrik: Datum, Dimensioner, Metrisk, Rapportsviter, Segment.

1. Lägg också märke till att det finns en annan tabell som heter **[!UICONTROL Legend]**. Om du tar en begäran ur Report Builder-kontexten kan det vara svårt att komma ihåg vad varje begäran står för. Syftet med förklaringstabellen är till exempel att visa namnet på varje begäran under Tabell-ID. Du kan också lägga till de andra förklaringskolumnerna för att få en fullständig vy över begäran.

   ![](assets/legend-table.png)

