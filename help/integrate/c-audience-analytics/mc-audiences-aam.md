---
description: Adobe Audience Manager (Adobe Audience Manager) är en kraftfull datahanteringsplattform som hjälper er att skapa unika målgruppsprofiler från första part, andra part/partner och tredjepartsdataintegreringar. För annonsörer hjälper de här målgruppsprofilerna till att definiera de mest värdefulla segmenten som kan användas i alla digitala kanaler.
solution: Experience Cloud
title: Audience Analytics - översikt
feature: Audience Analytics
exl-id: 1665a554-8a6f-4b20-99b7-bb3c2c4bf8cc
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 0%

---

# Audience Analytics - översikt

Adobe Audience Manager (Adobe Audience Manager) är en kraftfull datahanteringsplattform som hjälper er att skapa unika målgruppsprofiler från första part, andra part/partner och tredjepartsdataintegreringar. För annonsörer hjälper de här målgruppsprofilerna till att definiera de mest värdefulla segmenten som kan användas i alla digitala kanaler.

Med Audience Analytics-integreringen på plats kan ni införliva Adobe Audience Manager målgruppsdata som demografisk information (t.ex. kön eller inkomstnivå), psykografisk information (t.ex. intressen och hobbies), CRM-data och annonsvisningsdata i alla Analytics-arbetsflöden.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Audience Analytics](https://video.tv.adobe.com/v/25450?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


## Viktiga fördelar {#benefits}

Integreringen med Audience Analytics har följande viktiga fördelar:

* Det är den första producerade integreringen mellan en datahanteringsplattform (DMP) och en analysmotor på marknaden.
* Segment delas från Adobe Audience Manager till Analytics i realtid för att informera målgruppsidentifiering, segmentering och optimering.
* Alla Adobe Audience Manager-segment delas som standard, vilket ger helt nya kundprofiler i Analytics.
* Lösningsadministratörer kan aktivera integreringen via användargränssnittet med minimala kodändringar.
* Endast segment som följer Audience Manager dataexportkontroller delas.

## Så här fungerar Audience Analytics {#works}

![](assets/mc-aud-dataflow.png)

1. Varje gång en besökare kommer till era digitala resurser samlas träffar in och skickas till Analytics.
1. Med [vidarebefordran på serversidan](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md) skickas varje träff som Analytics tar emot automatiskt till Adobe Audience Manager i realtid.
1. Genom Audience Analytics-integreringen för varje träff slås en besökares målgruppsmedlemskap upp i Adobe Audience Manager och en lista över segment-ID returneras till Analytics för bearbetning i realtid.

Eftersom Adobe Audience Manager-segment infogas på samma träffbasis, kan du vara säker på att alla data som finns tillgängliga i Adobe Audience Manager om en besökare inte går förlorade och är aktuella för träffen. Detta är överlägset ett AppMeasurement-plugin-program eftersom ett plugin-program bara kan göra dessa segment tillgängliga vid nästa träff (i stället för vid den aktuella träffen).

Dessutom klassificerar vi automatiskt Adobe Audience Manager segment-ID:n till egna namn så att du inte behöver titta på alfanumeriska ID:n i Analytics-rapporter.

## Förutsättningar {#prerequisites}

Kontrollera att följande krav är uppfyllda:

* Du är kund till både Audience Manager och Adobe Analytics.
* Du är Audience Manager-administratör.
* Du använder identitetstjänsten v1.5 eller senare.
* Adobe Audience Manager och Adobe Analytics rapporteringsprogram är mappade till samma Experience Cloud-organisation.
* Du använder [vidarebefordran på serversidan](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md) och har implementerat modulen [Målgruppshantering](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=sv-SE) (ingen DIL-kod) - AppMeasurement 1.5 eller senare.

Dessa krav beskrivs i [Audience Analytics Workflow](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md).
