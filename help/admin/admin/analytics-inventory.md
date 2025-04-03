---
description: Använda Analytics-inventeringen
title: Analysinventering
feature: Admin Tools
role: Admin
hide: true
hidefromtoc: true
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: 1e52aecdbb26dce0875b2df685ed2fa860eaba85
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 1%

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

   Den här skärmytan

   * Det totala antalet Analysis Workspace- och Mobile Scorecard-projekt som är aktiva under den här organisationen för alla användare.
   * Det totala antalet segment och beräknade värden som är aktiva under den här organisationen för alla användare.
   * Det totala antalet basrapportsviter som har definierats (virtuella rapportsviter ingår inte).
   * Om funktionen Media Analytics är aktiv och i så fall i vilket läge.
   * Det totala antalet användare som definieras under den organisationen.


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

### Rapportsviter

Vyn Rapportsviter visar alla rapportsviter som definierats under en organisation. Här kan du besvara följande frågor:

* Vilka rapportsviter har fått flest träffar de senaste 90 dagarna?
* Vilka rapportsviter har inte fått någon träff de senaste 90 dagarna?
* Vilka rapportsviter har det största antalet definierade dimensioner?
* Vilka rapportsviter har det största antalet definierade mätvärden?

Svaren på dessa frågor ger er en bra uppfattning om vilka rapporteringsprogram som är de bästa kandidaterna till migrering.

1. Om du vill analysera rapportsviter går du till **[!UICONTROL Data configuration and collection]** > **[!UICONTROL Report suites]** och klickar på **[!UICONTROL Analyze]**.

   ![Lista över rapportsviter](assets/an_inv_rs.png)

   | Element | Beskrivning |
   | --- | --- |
   | Namn | Namnet på rapportsviten |
   | ID | Rapportsvitens ID (rsid). Anger ett unikt ID som bara kan innehålla alfanumeriska tecken. Detta ID kan inte ändras efter att det har skapats. Adobe anger det ID-prefix som krävs och kan inte heller ändras. |
   | Förekomster (de senaste 90 dagarna) | Hur många träffar fick den här rapportsviten de senaste 90 dagarna? |
   | Mätvärden | Hur många mätvärden definieras i denna rapportserie? |
   | Mått | Hur många dimensioner definieras i den här rapportsviten? |
   | Analyser för mål (A4T) har aktiverats | Är den här rapportsviten aktiverad för [Analytics för Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t)? |
   | Marknadsföringskanaler är aktiverade | Är den här rapportsviten aktiverad för [marknadsföringskanaler](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel)? |
   | Source Connector är aktiverat | [Under utveckling] Är den här rapportsviten aktiverad för [Adobe Analytics Source Connector för rapportsvitsdata](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/analytics) i Adobe Experience Platform? Med andra ord, kan den här rapportsviten migreras till Customer Journey Analytics med Analytics Source Connector? |
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