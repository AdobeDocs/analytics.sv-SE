---
title: Avsluta dimensioner
description: Visar avslutningsdimensioner och deras användning.
keywords: exit page, exit site section, exit server, exit custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---


# Avsluta dimensioner

*På den här hjälpsidan beskrivs hur avslutas fungerar som en dimension. Mer information om hur avslutar fungerar som ett mått finns i[Exits](../metrics/exits.md)-måttet.*

Avsluta dimensioner registrerar den sista dimensionsposten och använd den retroaktivt på alla träffar under besöket. Exit-dimensioner är tillgängliga för alla variabler med målning aktiverad under [Traffic-variabler](/help/admin/admin/c-traffic-variables/traffic-var.md) i inställningarna för Report Suite.

## Fyll i avslutningsdimensioner med data

En given avslutningsdimension baseras på dess associerade trafikvariabel. Om variabeln inte avslutar har data, innehåller den tillhörande avslutningsdimensionen också data. Inga implementeringsändringar krävs för avslutningsdimensioner om trafikvariablerna innehåller data.

## Dimensionsobjekt

Eftersom avslutsvariabler vanligtvis baseras på anpassade strängar i implementeringen avgör organisationen vilka dimensionsobjekten är. Värden i en given avslutningsdimension matchar dimensionsobjekt i dess associerade icke-avslutningsdimension. Dimensionsobjekt i dimensionen &#39;Avsluta sida&#39; innehåller till exempel liknande dimensionsobjekt i dimensionen &#39;Sida&#39;.
