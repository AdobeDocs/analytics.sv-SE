---
description: Adobe Audience Manager (AAM) är en kraftfull datahanteringsplattform som hjälper er att skapa unika målgruppsprofiler från första part, andra part/partner och tredjepartsdataintegreringar. För annonsörer hjälper de här målgruppsprofilerna till att definiera de mest värdefulla segmenten som kan användas i alla digitala kanaler.
solution: Experience Cloud
title: Audience Analytics - översikt
uuid: 86ef9391-dd6a-495f-a10e-e98bc069dde4
exl-id: 1665a554-8a6f-4b20-99b7-bb3c2c4bf8cc
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# Audience Analytics - översikt

Adobe Audience Manager (AAM) är en kraftfull datahanteringsplattform som hjälper er att skapa unika målgruppsprofiler från första part, andra part/partner och tredjepartsdataintegreringar. För annonsörer hjälper de här målgruppsprofilerna till att definiera de mest värdefulla segmenten som kan användas i alla digitala kanaler.

Med integreringen av Audience Analytics kan ni införliva AAM målgruppsdata, t.ex. demografisk information (t.ex. kön eller inkomstnivå), psykografisk information (t.ex. intressen och hobbies), CRM-data och annonsvisningsdata i alla Analytics-arbetsflöden.

## Viktiga fördelar {#section_94816D17283349E0BA28521BE55BB868}

Integreringen av Audience Analytics har följande viktiga fördelar:

* Det är den första producerade integreringen mellan en datahanteringsplattform (DMP) och en analysmotor på marknaden.
* Segmenten delas från AAM till Analytics i realtid för att informera om målgruppsidentifiering, segmentering och optimering.
* Alla AAM delas som standard, vilket ger en helhetsbild av kundprofilerna i Analytics.
* Lösningsadministratörer kan aktivera integreringen via användargränssnittet med minimala kodändringar.
* Endast segment som följer dataexportkontrollerna i Audience Manager delas.

## Så här fungerar det {#section_CECDF5A0FEC64264B206EFEF54F19EF2}

![](assets/mc-aud-dataflow.png)

1. Varje gång en besökare kommer till era digitala resurser samlas träffar in och skickas till Analytics.
1. Med [vidarebefordran på serversidan](/help/admin/admin/c-server-side-forwarding/ssf.md) skickas varje träff som Analytics tar emot automatiskt till AAM i realtid.
1. Genom integreringen av Audience Analytics för varje träff slås en besökares målgruppsmedlemskap upp i AAM och en lista över segment-ID returneras till Analytics för bearbetning i realtid.

Eftersom AAM infogas på samma träffbasis, kan du vara säker på att alla data som är tillgängliga i AAM om en besökare inte går förlorade och är aktuella för träffen. Detta är överlägset en AppMeasurement-plugin, eftersom en plugin bara kan göra dessa segment tillgängliga vid nästa träff (i stället för vid den aktuella träffen).

Dessutom klassificerar vi automatiskt AAM segment-ID:n till egna namn så att du inte behöver titta på alfanumeriska ID:n i Analytics-rapporter.

## Förutsättningar {#section_A345DC31F7D44EAE9DC1AB53E824C0CC}

Kontrollera att följande krav är uppfyllda:

* Du är kund i både Audience Manager och Adobe Analytics.
* Du är Audience Manager-administratör.
* Du använder identitetstjänsten v1.5 eller senare.
* AAM och Adobe Analytics rapporteringsprogram är [mappade till samma Experience Cloud-organisation](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/report-suite-mapping.html).
* Du använder [vidarebefordran på serversidan](/help/admin/admin/c-server-side-forwarding/ssf.md) och har implementerat modulen [Audience Management](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) (ingen DIL-kod) - AppMeasurement 1.5 eller senare.

Dessa krav beskrivs i [arbetsflödet för Audience Analytics](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md).
