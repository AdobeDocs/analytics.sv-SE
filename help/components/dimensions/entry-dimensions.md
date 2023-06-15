---
title: Postdimensioner
description: Visar postdimensioner och deras användning.
keywords: startsida, startwebbplatsavsnitt, startserver, anpassad information
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
source-git-commit: 43e483f157f1c2527f671eb43a165db86c77a7ce
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# Postdimensioner

*Den här hjälpsidan beskriver hur poster fungerar som en dimension. Mer information om hur poster fungerar som mått finns i [Poster](../metrics/entries.md) mätvärden.*

Postdimensionerna är [besöksbaserad](../metrics/visits.md). De registrerar den första dimensionsposten och behåller den under hela besökets längd. Postdimensioner är tillgängliga för alla variabler med panorering aktiverad under [Trafikvariabler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) i Rapportsvitens inställningar.

## Fyll i postdimensioner med data

En given inmatningsdimension baseras på dess associerade trafikvariabel. Om variabeln som inte är en post har data innehåller dess associerade inmatningsdimension även data. Inga implementeringsändringar krävs för postdimensioner om dina trafikvariabler innehåller data.

## Dimensioner

Eftersom inmatningsvariabler vanligtvis baseras på anpassade strängar i implementeringen avgör organisationen vilka dimensionsobjekten är. Värden i en given inmatningsdimension matchar dimensionsobjekt i dess associerade icke-inmatningsdimension. Dimensionsobjekt i dimensionen &quot;Inmatningssida&quot; innehåller till exempel liknande dimensionsobjekt i dimensionen &quot;Sida&quot;.

## Startsida, original

Dimensionen&quot;Inmatningssidans ursprungliga&quot; fungerar annorlunda än andra inmatningsdimensioner. Istället för att bevara anmälningssidan för ett visst besök, bevaras den första anmälningssidan under hela besökarens cookie. Om du till exempel landar på `https://example.com/page4` för ditt första besök på webbplatsen, och därefter ett år senare `https://example.com/store`, Dimensionslistorna för startsidan `https://example.com/page4` som dimensionsobjekt.
