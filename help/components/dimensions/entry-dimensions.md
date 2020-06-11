---
title: Postdimensioner
description: Visar postdimensioner och deras användning.
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---


# Postdimensioner

*Den här hjälpsidan beskriver hur poster fungerar som en dimension. Mer information om hur poster fungerar som mått finns i[Posterna](../metrics/entries.md).*

Ingångsdimensioner är besöksbaserade. De registrerar det första dimensionsvärdet och behåller det under hela besökets längd. Postdimensioner är tillgängliga för alla variabler med målning aktiverad under [Trafikvariabler](/help/admin/admin/c-traffic-variables/traffic-var.md) i inställningarna för rapportsviten.

## Fyll i postdimensioner med data

En given inmatningsdimension baseras på dess associerade trafikvariabel. Om variabeln som inte är en post har data innehåller dess associerade inmatningsdimension även data. Inga implementeringsändringar krävs för postdimensioner om dina trafikvariabler innehåller data.

## Dimensionsvärden

Eftersom inmatningsvariabler vanligtvis baseras på anpassade strängar i implementeringen avgör organisationen vilka dimensionsvärdena är. Värden i en given inmatningsdimension matchar dimensionsvärden i dess associerade icke-inmatningsdimension. Dimensionsvärden i dimensionen &quot;Inmatningssida&quot; innehåller till exempel liknande dimensionsvärden i dimensionen &quot;Sida&quot;.

## Startsida, original

Dimensionen&quot;Inmatningssidans ursprungliga&quot; fungerar annorlunda än andra inmatningsdimensioner. Istället för att bevara anmälningssidan för ett visst besök, bevaras den första anmälningssidan under hela besökarens cookie. Om du t.ex. landar `https://example.com/page4` på webbplatsen för första gången, och ett år senare landar på `https://example.com/store`, visas dimensionerna &quot;Ingångssidans original&quot; `https://example.com/page4` som dimensionsvärde.
