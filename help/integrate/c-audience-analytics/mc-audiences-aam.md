---
description: Adobe Audience Manager (Adobe Audience Manager) är en kraftfull datahanteringsplattform som hjälper er att skapa unika målgruppsprofiler från första part, andra part/partner och tredjepartsdataintegreringar. För annonsörer hjälper de här målgruppsprofilerna till att definiera de mest värdefulla segmenten som kan användas i alla digitala kanaler.
solution: Experience Cloud
title: Audience Analytics - översikt
feature: Audience Analytics
exl-id: 1665a554-8a6f-4b20-99b7-bb3c2c4bf8cc
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 1%

---

# Audience Analytics - översikt

Adobe Audience Manager (Adobe Audience Manager) är en kraftfull datahanteringsplattform som hjälper er att skapa unika målgruppsprofiler från första part, andra part/partner och tredjepartsdataintegreringar. För annonsörer hjälper de här målgruppsprofilerna till att definiera de mest värdefulla segmenten som kan användas i alla digitala kanaler.

Med integreringen av Audience Analytics kan ni införliva Adobe Audience Manager målgruppsdata, t.ex. demografisk information (t.ex. kön eller inkomstnivå), psykografisk information (t.ex. intressen och hobbies), CRM-data och annonsvisningsdata i alla Analytics-arbetsflöden.

>[!VIDEO](https://video.tv.adobe.com/v/25450/?quality=12)

## Viktiga fördelar {#section_94816D17283349E0BA28521BE55BB868}

Integreringen av Audience Analytics har följande viktiga fördelar:

* Det är den första producerade integreringen mellan en datahanteringsplattform (DMP) och en analysmotor på marknaden.
* Segment delas från Adobe Audience Manager till Analytics i realtid för att informera målgruppsidentifiering, segmentering och optimering.
* Alla Adobe Audience Manager-segment delas som standard, vilket ger helt nya kundprofiler i Analytics.
* Lösningsadministratörer kan aktivera integreringen via användargränssnittet med minimala kodändringar.
* Endast segment som följer dataexportkontrollerna i Audience Manager delas.

## Så här fungerar det {#section_CECDF5A0FEC64264B206EFEF54F19EF2}

![](assets/mc-aud-dataflow.png)

1. Varje gång en besökare kommer till era digitala resurser samlas träffar in och skickas till Analytics.
1. Med [vidarebefordran på serversidan](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)skickas varje träff som Analytics tar emot automatiskt till Adobe Audience Manager i realtid.
1. Genom integreringen av Audience Analytics för varje träff slås en besökares målgruppsmedlemskap upp i Adobe Audience Manager och en lista över segment-ID returneras till Analytics för bearbetning i realtid.

Eftersom Adobe Audience Manager-segment infogas på samma träffbasis, kan du vara säker på att alla data som finns tillgängliga i Adobe Audience Manager om en besökare inte går förlorade och är aktuella för träffen. Detta är överlägset ett plugin-program för AppMeasurement eftersom ett plugin-program bara kan göra dessa segment tillgängliga vid nästa träff (i stället för vid den aktuella träffen).

Dessutom klassificerar vi automatiskt Adobe Audience Manager segment-ID:n till egna namn så att du inte behöver titta på alfanumeriska ID:n i Analytics-rapporter.

## Förutsättningar {#section_A345DC31F7D44EAE9DC1AB53E824C0CC}

Kontrollera att följande krav är uppfyllda:

* Du är kund i både Audience Manager och Adobe Analytics.
* Du är Audience Manager-administratör.
* Du använder identitetstjänsten v1.5 eller senare.
* Adobe Audience Manager och Adobe Analytics rapportsviter mappas till samma Experience Cloud-organisation.
* Du använder [vidarebefordran på serversidan](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md) och har implementerat [Målgruppshanteringsmodul](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) (ingen DIL-kod) - AppMeasurement 1.5 eller senare.

Dessa krav beskrivs i [Audience Analytics Workflow](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md).
