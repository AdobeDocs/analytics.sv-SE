---
title: Avsluta dimensioner
description: Visar avslutningsdimensioner och deras användning.
keywords: avsluta sida, avsluta webbplatsavsnittet, avsluta server, avsluta anpassad information
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---

# Avsluta dimensioner

*På den här hjälpsidan beskrivs hur avslutas fungerar som en dimension. Mer information om hur avslutar fungerar som ett mått finns i [Avslutar](../metrics/exits.md) mätvärden.*

Avsluta dimensioner registrerar den sista dimensionsposten och använd den retroaktivt på alla träffar under besöket. Utgångsdimensioner är tillgängliga för alla variabler med panorering aktiverad under [Trafikvariabler](/help/admin/admin/c-traffic-variables/traffic-var.md) i Rapportsvitens inställningar.

## Fyll i avslutningsdimensioner med data

En given avslutningsdimension baseras på dess associerade trafikvariabel. Om variabeln inte avslutar har data, innehåller den tillhörande avslutningsdimensionen också data. Inga implementeringsändringar krävs för avslutningsdimensioner om trafikvariablerna innehåller data.

## Dimensioner

Eftersom avslutsvariabler vanligtvis baseras på anpassade strängar i implementeringen avgör organisationen vilka dimensionsobjekten är. Värden i en given avslutningsdimension matchar dimensionsobjekt i dess associerade icke-avslutningsdimension. Dimensionsobjekt i dimensionen &#39;Avsluta sida&#39; innehåller till exempel liknande dimensionsobjekt i dimensionen &#39;Sida&#39;.
