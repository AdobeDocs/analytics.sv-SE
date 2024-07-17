---
title: Hantera datakällor
description: Navigera i gränssnittet för hantering av datakällor.
exl-id: 315501fb-26e1-436a-938d-5957ca037cd0
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%

---

# Hantera datakällor

Använd datakällhanteraren för att skapa, redigera eller inaktivera datakällor. Du kan också använda det här gränssnittet för att spåra status för filer som överförts till FTP-platser för datakällor.

**[!UICONTROL Admin]** > **[!UICONTROL All Admin]** > **[!UICONTROL Data sources]**

Använd rapportsvitens väljare i det övre högra hörnet för att växla mellan olika rapportsviter i organisationen.

Gränssnittet innehåller tre huvudflikar: **[!UICONTROL Manage]**, **[!UICONTROL Create]** och **[!UICONTROL File Log]**.

## Hantera

Fliken **[!UICONTROL Manage]** hanterar alla datakällor som din organisation har skapat. Du kan visa FTP-information, redigera variabler som används i mallfiler eller inaktivera datakällor helt.

![Hantera](assets/manage.png)

Den översta datakällan är alltid [!UICONTROL Web Beacon]. Den här datakällan används ofta för datainsamling via AppMeasurementet. Den kan inte redigeras eller inaktiveras.

Varje datakälla har följande alternativ:

* **[!UICONTROL Restart Processing]**: Startar om bearbetning av datakälla som tidigare avbröts på grund av fel. Bearbetningen fortsätter tills nästa fel påträffas. Datakällor avbryter endast bearbetning av en datakällfil när du väljer **[!UICONTROL Stop processing on errors]**.
* **[!UICONTROL Complete Processing]**: Används inte längre - den här knappen användes bara för [Fullständig bearbetning av datakällor](full-processing-eol.md).
* **[!UICONTROL Stop processing on errors]**: En kryssruta som instruerar bearbetningsservern att stoppa när ett fel påträffas. Datakällan återupptar inte bearbetningen förrän du väljer **[!UICONTROL Restart Processing]**. När en datakälla påträffar ett filfel får du ett meddelande om felet. Adobe flyttar filen med felet till en mapp med namnet `files_with_errors` på FTP-servern. När du har löst problemet skickar du filen igen för bearbetning.
* **[!UICONTROL Configure]**: En länk som tar dig genom guiden Skapa datakällor för den här datakällan. Med den här guiden kan du byta namn på datakällan eller konfigurera om variablerna som automatiskt inkluderas när du hämtar en mallfil.
* **[!UICONTROL FTP Info]**: En länk som tar dig till det sista steget i guiden Skapa datakällor där FTP-autentiseringsuppgifter visas.

När en datakälla tar emot data visas en tabell som innehåller flera kolumner för de överförda filerna.

* **[!UICONTROL Files In Processing Queue]**: Filens namn.
* **[!UICONTROL Rows]**: Det totala antalet rader i filen.
* **[!UICONTROL Errors]**: Antalet rader som innehöll fel och som inte kunde importeras.
* **[!UICONTROL Warnings]**: Antalet rader som innehöll varningar.
* **[!UICONTROL Received]**: Tidsstämpeln som filen togs emot i rapportsvitens tidszon.
* **[!UICONTROL Status]**: Status för filen (`Success` eller `Failed`).

## Skapa

Fliken **[!UICONTROL Create]** ger dig en startpunkt för guiden Skapa datakällor.

![Skapa](assets/create.png)

Datakällans kategori och typ var mer värdefull i tidigare versioner av Adobe Analytics. De har dock fortfarande begränsad användning:

* Datakälltypen visas på fliken [Hantera](#manage) för själva datakällan och på fliken [Fillogg](#file-log) för varje enskild fil.
* Vissa typer av datakällor tar automatiskt med variabler när mallfilen hämtas. Du kan dock inkludera alla tillgängliga dimensioner eller mätvärden så länge som de följer det etablerade [filformatet](file-format.md).

Utöver detta är alla datakällkategorier och typer som du kan välja i själva verket identiska. Välj den kategori och typ som bäst motsvarar ditt syfte att använda datakällor.

När [datakällor med fullständig bearbetning](full-processing-eol.md) har tagits ur bruk går det inte att välja flera kategorier och typer. Om du väljer en datakälltyp med fullständig bearbetning är knappen **[!UICONTROL Activate]** nedtonad.

## Fillogg

Fliken **[!UICONTROL File Log]** ger dig en sammanställd vy över alla datakällfiler som överförts för den angivna rapportsviten.

![Fillogg](assets/file-log.png)

Det finns ett sökfält som hjälper dig att hitta en viss datakälla. Tabellen visar följande kolumner:

* **[!UICONTROL Data Source Name]**: Datakällans namn.
* **[!UICONTROL Type]**: Datakällans typ.
* **[!UICONTROL Filename]**: Namnet på filen som överfördes.
* **[!UICONTROL Rows]**: Det totala antalet rader i filen.
* **[!UICONTROL Errors]**: Antalet rader som innehöll fel.
* **[!UICONTROL Warnings]**: Används inte längre. Antalet rader som innehöll varningar.
* **[!UICONTROL Received]**: Datum och tid då Adobe började bearbeta filen.
* **[!UICONTROL Status]**: Filens status (`Success` eller `Failed`).
