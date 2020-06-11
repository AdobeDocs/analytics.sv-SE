---
title: Avsluta dimensioner
description: Visar avslutningsdimensioner och deras användning.
keywords: exit page, exit site section, exit server, exit custom insight
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---


# Avsluta dimensioner

*På den här hjälpsidan beskrivs hur avslutas fungerar som en dimension. Mer information om hur avslutar fungerar som ett mått finns i[Exits](../metrics/exits.md)-måttet.*

Avsluta dimensioner registrerar det sista dimensionsvärdet och använd det retroaktivt på alla träffar under besöket. Exit-dimensioner är tillgängliga för alla variabler med målning aktiverad under [Traffic-variabler](/help/admin/admin/c-traffic-variables/traffic-var.md) i inställningarna för Report Suite.

## Fyll i avslutningsdimensioner med data

En given avslutningsdimension baseras på dess associerade trafikvariabel. Om variabeln inte avslutar har data, innehåller den tillhörande avslutningsdimensionen också data. Inga implementeringsändringar krävs för avslutningsdimensioner om trafikvariablerna innehåller data.

## Dimensionsvärden

Eftersom avslutsvariabler vanligtvis baseras på anpassade strängar i implementeringen avgör organisationen vilka dimensionsvärdena är. Värden i en given avslutningsdimension matchar dimensionsvärden i dess associerade icke-avslutningsdimension. Dimensionsvärden i dimensionen &#39;Avsluta sida&#39; innehåller till exempel liknande dimensionsvärden i dimensionen &#39;Sida&#39;.
