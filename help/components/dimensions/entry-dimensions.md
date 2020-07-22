---
title: Postdimensioner
description: Visar postdimensioner och deras användning.
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---


# Postdimensioner

*Den här hjälpsidan beskriver hur poster fungerar som en dimension. Mer information om hur poster fungerar som mått finns i[Posterna](../metrics/entries.md).*

Ingångsdimensioner är besöksbaserade. De registrerar den första dimensionsposten och behåller den under hela besökets längd. Postdimensioner är tillgängliga för alla variabler med målning aktiverad under [Trafikvariabler](/help/admin/admin/c-traffic-variables/traffic-var.md) i inställningarna för rapportsviten.

## Fyll i postdimensioner med data

En given inmatningsdimension baseras på dess associerade trafikvariabel. Om variabeln som inte är en post har data innehåller dess associerade inmatningsdimension även data. Inga implementeringsändringar krävs för postdimensioner om dina trafikvariabler innehåller data.

## Dimensionsobjekt

Eftersom inmatningsvariabler vanligtvis baseras på anpassade strängar i implementeringen avgör organisationen vilka dimensionsobjekten är. Värden i en given inmatningsdimension matchar dimensionsobjekt i dess associerade icke-inmatningsdimension. Dimensionsobjekt i dimensionen &quot;Inmatningssida&quot; innehåller till exempel liknande dimensionsobjekt i dimensionen &quot;Sida&quot;.

## Startsida, original

Dimensionen&quot;Inmatningssidans ursprungliga&quot; fungerar annorlunda än andra inmatningsdimensioner. Istället för att bevara anmälningssidan för ett visst besök, bevaras den första anmälningssidan under hela besökarens cookie. Om du t.ex. landar `https://example.com/page4` på webbplatsen för första gången, och ett år senare landar på `https://example.com/store`, visas dimensionerna&quot;Införselsidans original&quot; `https://example.com/page4` som dimensionsobjekt.
