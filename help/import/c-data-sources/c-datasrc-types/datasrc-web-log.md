---
description: Med webbloggdatakällor kan du importera standardloggfiler för webbservrar.
subtopic: Data sources
title: Webblogg
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 11c4f21a-de07-436e-a05e-ab6769cb3e21
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 2%

---

# Webblogg

Med webbloggdatakällor kan du importera standardloggfiler för webbservrar.

Följande vanliga loggtyper för webbservrar stöds:

| Kolumnnamn | Beskrivning |
|--- |--- |
| Gemensam NCSA-logg | Apache-standard |
| NCSA Extended (kombinerat) | Apache |
| Utökad W3C-logg | Används av IIS 4.0 och senare |
| Microsoft IIS-logg | Används av IIS 3.0 och tidigare |

De primära loggfilsfälten som Datakällor bearbetar är IP-adress, datum/tid för begäran och URL. I ett fåtal fall, t.ex. NCSA Extended, bearbetar datakällor även fälten Referent och Användaragent.

Du kan visa webbloggdata med hjälp av vanliga marknadsföringsrapporter för sidvyer, besök och besökare. Eftersom rapportmätvärden i första hand baseras på cookies, och webbserverloggarna baseras på IP-adressen, rekommenderar Adobe att du importerar webbserverloggarna till en separat rapportserie särskilt för detta ändamål.

Mer information om webbserverns loggfiler finns i webbserverns dokumentation.
