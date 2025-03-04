---
description: Lär dig mer om Data Warehouse och hur du filtrerar data så att du kan skapa och köra anpassade rapporter.
title: Översikt över Data Warehouse
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# Översikt över Datan Warehouse

Med Data Warehouse kan du kopiera Adobe Analytics-data för lagring och för att skapa anpassade rapporter, som du kan köra genom att filtrera data.

## Översikt över rapporter

Data Warehouse kan visa avancerade datarelationer från rådata baserat på dina unika frågor. De kan innehålla ett obegränsat antal rader i en enda begäran (för enskilda rapporter, schemalagda rapporter och hämtade rapporter).

>[!NOTE]
>
>Datan Warehouse rapporterar det första värdet som påträffats under rapporteringsperioden.

>[!IMPORTANT]
>
>Vid segmentering på klassificerade värden behandlar Analysis Workspace och Data Warehouse ospecificerade värden på olika sätt. &#39;Ospecificerad&#39; i Workspace avser värden som inte är klassificerade, medan &#39;Ospecificerad&#39; i Datan Warehouse hänvisar till värden som du klassificerat som &#39;Ospecificerad&#39;.

## Leveransöversikt

Data Warehouse-rapporter skickas via e-post eller skickas till en molnlagringsleverantör och kan ta upp till 72 timmar att bearbeta. Bearbetningstiden beror på frågans komplexitet och mängden data som begärs.

Datan Warehouse packar automatiskt alla filer som är större än 1 MB. Den maximala storleken för e-postbilagor är 10 MB.

## Åtkomst

Adobe aktiverar endast Data Warehouse för användare på administratörsnivå för särskilda rapportsviter. (Den kan aktiveras för globala och underordnade rapportsviter, men inte för sammanslagningsrapportsviter.) Administratören kan skapa en grupp som har åtkomst till Data Warehouse och sedan associera icke-administratörsnivåanvändare till den gruppen.

Se [Hantera behörigheter för Data Warehouse](/help/export/data-warehouse/t-dw-group.md).

## Skapa en begäran om Data Warehouse

Mer information om hur du skapar en begäran om Data Warehouse finns i [Skapa en begäran om Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

## Hantera förfrågningar från Data Warehouse

Mer information om hur du hanterar förfrågningar från Data Warehouse finns i [Hantera förfrågningar från Data Warehouse](/help/export/data-warehouse/data-warehouse-requests-manage.md).

