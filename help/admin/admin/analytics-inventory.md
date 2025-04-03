---
description: Använda Analytics-inventeringen
title: Analysinventering
feature: Admin Tools
role: Admin
hide: true
hidefromtoc: true
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: fceb28b7af480e6d87abf09c26f45a7afb2d3270
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 2%

---

# Analyslager {#analytics-inventory}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory"
>title="Analyslager"
>abstract="På den här sidan finns en omfattande översikt över din Adobe Analytics-miljö, inklusive antalet projekt och komponenter, rapportsviter, användare med mera. Den här informationen är särskilt värdefull när du börjar förbereda dig för att uppgradera till Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

Analysinventeringen ger en omfattande översikt över din Adobe Analytics-miljö, inklusive antalet projekt och komponenter, rapportsviter, användare med mera. Den här informationen är särskilt värdefull när du börjar förbereda dig för att uppgradera till Customer Journey Analytics.

Programmets mål är att hjälpa dig att svara på följande frågor:

* Vilka resurser (till exempel rapportsviter, segment, användare, arbetsyteprojekt, dataflöden) behöver du uppgradera för din organisation och vilka resurser kan du lämna kvar?

* När du har fastställt vilken resurs som behöver migreras:

   * Bör du rensa resurser före uppgraderingen?

   * Ska du göra en inventariekonsolidering som en del av processen?

   * Vad ska uppgraderingssekvensen vara för dina mediefiler?

   * Vilken grupp av rapportsviter ska du uppgradera först? sist?

## Behörigheter

Analysinventering är tillgängligt för användare med Adobe Analytics produktadministratörsbehörighet i [Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/admin-roles-in-analytics).

## Access Analytics-inventering

1. Klicka på **[!UICONTROL Analytics Inventory]** på menyn **[!UICONTROL Admin]**. Eller gå till **[!UICONTROL All admin]** > **[!UICONTROL Analytics Inventory]**.

![Analytics-Inventory-menu](assets/an-inventory-menu.png)

1. På huvudskärmen visas en omfattande förteckning över din Adobe Analytics-miljö:

   ![Huvudlagerskärm](assets/an_inventory.png)

>[!IMPORTANT]
>
>   I den här initiala versionen kan du se sammanfattningsnummer för Workspace-projekt, segment, beräknade värden, avancerade data (Media Analytics) och användare. För närvarande är rapportsviter de enda objekt som kan användas.


## Komponenter {#components}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-components"
>title="Komponenter"
>abstract="I det här avsnittet visas antalet projekt, segment och beräknade värden som finns i din Adobe Analytics-miljö. Projekt och komponenter kan migreras till Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

I den här första versionen kan du se en sammanfattning av lagernumren för Workspace-projekt, segment och beräknade värden. I efterföljande versioner kan du analysera dessa komponenter.

## Datakonfiguration och insamling {#data-config}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-data-config"
>title="Datakonfiguration och insamling"
>abstract="I det här avsnittet visas antalet rapportsviter i din Adobe Analytics-miljö samt din åtkomst till direktuppspelningsmedia. "

<!-- markdownlint-enable MD034 -->

### Analysera rapportsviter

1. Om du vill analysera rapportsviter och bestämma vilka som ska migreras går du till **[!UICONTROL Data configuration and collection]** > **[!UICONTROL Report suites]** och klickar på **[!UICONTROL Analyze]**.

   ![Lista över rapportsviter](assets/an_inv_rs.png)

   | Element | Beskrivning |
   | --- | --- |
   | Namn | Namnet på rapportsviten |
   | ID | Rapportsvitens ID (rsid). Anger ett unikt ID som bara kan innehålla alfanumeriska tecken. Detta ID kan inte ändras efter att det har skapats. Adobe anger det ID-prefix som krävs och kan inte heller ändras. |
   | Förekomster (de senaste 90 dagarna) |  |
   | Mätvärden | Hur |
   | Mått |  |
   | Analyser för mål (A4T) har aktiverats |  |
   | Marknadsföringskanaler är aktiverade |  |
   | Source Connector är aktiverat | Följ |
   | Kalendertyp | Mer information finns i [Anpassade kalendrar](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/custom-calendar#) |

1. Observera att..

### Exportera till CSV

1. Om du vill exportera listan med rapportsviter till en CSV-fil klickar du på **[!UICONTROL Export to CSV]**.

1. CSV-filen visas i mappen Downloads.

1. Öppna och spara den med ett kalkylbladsprogram på enheten.


## Användarhantering {#user-management}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-user-management"
>title="Användarhantering"
>abstract="I det här avsnittet visas antalet användare i din Adobe Analytics-miljö."

<!-- markdownlint-enable MD034 -->

Användarhantering kommer att vara tillgänglig i en senare version av Analytics-inventeringen.