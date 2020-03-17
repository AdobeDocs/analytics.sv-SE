---
description: Adobe Audience Manager (AAM) är en kraftfull datahanteringsplattform som hjälper er att skapa unika målgruppsprofiler från första part, andra part/partner och dataintegreringar från tredje part. För annonsörer hjälper de här målgruppsprofilerna till att definiera de mest värdefulla segmenten som kan användas i alla digitala kanaler.
solution: Experience Cloud
title: Audience Analytics - översikt
uuid: 86ef9391-dd6a-495f-a10e-e98bc069dde4
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Audience Analytics - översikt

Adobe Audience Manager (AAM) är en kraftfull datahanteringsplattform som hjälper er att skapa unika målgruppsprofiler från första part, andra part/partner och dataintegreringar från tredje part. För annonsörer hjälper de här målgruppsprofilerna till att definiera de mest värdefulla segmenten som kan användas i alla digitala kanaler.

Med Audience Analytics-integreringen på plats kan ni införliva AAM-målgruppsdata som demografisk information (t.ex. kön eller inkomstnivå), psykografisk information (t.ex. intressen och hobbies), CRM-data och annonsvisningsdata i alla Analytics-arbetsflöden.

## Viktiga fördelar {#section_94816D17283349E0BA28521BE55BB868}

Integreringen med Audience Analytics har följande viktiga fördelar:

* Det är den första producerade integreringen mellan en datahanteringsplattform (DMP) och en analysmotor på marknaden.
* Segment delas från AAM till Analytics i realtid för att informera målgruppsidentifiering, segmentering och optimering.
* Alla AAM-segment delas som standard, vilket ger helt berikande kundprofiler i Analytics.
* Lösningsadministratörer kan aktivera integreringen via användargränssnittet med minimala kodändringar.
* Endast segment som följer kontrollerna för export av data i Audience Manager delas.

## Så här fungerar det {#section_CECDF5A0FEC64264B206EFEF54F19EF2}

![](assets/mc-aud-dataflow.png)

1. Varje gång en besökare kommer till era digitala resurser samlas träffar in och skickas till Analytics.
1. Med vidarebefordran [på](/help/admin/admin/c-server-side-forwarding/ssf.md)serversidan skickas varje träff som Analytics tar emot automatiskt till AAM i realtid.
1. Genom Audience Analytics-integreringen, för varje träff, slås en besökares målgruppsmedlemskap upp i AAM och en lista över segment-ID returneras till Analytics för bearbetning i realtid.

Eftersom AAM-segment infogas på samma träffbasis, kan du vara säker på att alla data som är tillgängliga i AAM om en besökare inte går förlorade och är aktuella för träffen. Detta är överlägset en AppMeasurement-plugin, eftersom en plugin bara kan göra dessa segment tillgängliga vid nästa träff (i stället för vid den aktuella träffen).

Dessutom klassificerar vi automatiskt AAM-segment-ID:n till egna namn så att du inte behöver titta på alfanumeriska ID:n i Analytics-rapporter.

## Förutsättningar {#section_A345DC31F7D44EAE9DC1AB53E824C0CC}

Kontrollera att följande krav är uppfyllda:

* Du är kund till både Audience Manager och Adobe Analytics.
* Du är Audience Manager-administratör.
* Du använder identitetstjänsten v1.5 eller senare.
* AAM- och Adobe Analytics-rapportsviter är [mappade till samma Experience Cloud-organisation](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).
* Du använder vidarebefordran [på](/help/admin/admin/c-server-side-forwarding/ssf.md) serversidan och har implementerat modulen [](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) Audience Management (ingen DIL-kod) - AppMeasurement 1.5 eller senare.

Dessa krav beskrivs i [målgruppsanalysarbetsflödet](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md).
