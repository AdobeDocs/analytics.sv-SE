---
title: Postdimensioner
description: Visar postdimensioner och deras användning.
keywords: startsida, startwebbplatsavsnitt, startserver, anpassad information
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---

# Postdimensioner

*Den här hjälpsidan beskriver hur poster fungerar som en [dimension](overview.md). Mer information om hur poster fungerar som mått finns i måttet [Poster](../metrics/entries.md).*

Ingångsdimensionerna är [besöksbaserade](../metrics/visits.md). De registrerar den första dimensionsposten och behåller den under hela besökets längd. Postdimensioner är tillgängliga för alla variabler med målning aktiverad under [Trafikvariabler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) i inställningarna för rapportsviten.

>[!TIP]
>Om du vill visa data baserat på den första träffen av ett besök i stället för det första värdet som visas under ett besök kan du använda ett [segment](/help/components/segmentation/seg-overview.md). Använd en träffbehållare där [Träffdjupet](hit-depth.md) är lika med 1 och använd sedan segmentet med den önskade variabeln.

## Fyll i postdimensioner med data

En given post [dimension](overview.md) baseras på dess associerade trafikvariabel. Om variabeln som inte är en post har data innehåller dess associerade inmatningsdimension även data. Inga implementeringsändringar krävs för postdimensioner om dina trafikvariabler innehåller data.

## Dimensioner

Eftersom inmatningsvariabler vanligtvis baseras på anpassade strängar i implementeringen avgör organisationen vilka dimensionsobjekten är. Värden i en given inmatningsdimension matchar dimensionsobjekt i dess associerade icke-inmatningsdimension. Dimensionsobjekt i dimensionen &quot;Inmatningssida&quot; innehåller till exempel liknande dimensionsobjekt i dimensionen &quot;Sida&quot;.

## Startsida, original

Dimensionen&quot;Ingångssidans ursprungliga&quot; fungerar annorlunda än andra inmatningsdimensioner. Istället för att bevara anmälningssidan för ett visst besök, bevaras den första anmälningssidan under hela besökarens cookie. Om du t.ex. landar på `https://example.com/page4` för ditt första besök på webbplatsen, kommer du ett år senare att landa på `https://example.com/store`, kommer måttet&quot;Ingångssidans ursprungliga&quot; `https://example.com/page4` att anges som dimensionsobjekt.
