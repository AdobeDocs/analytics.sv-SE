---
title: Unika besökare
description: Antalet unika besökar-ID.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: f26f406848ab26092738089aac64ed9b4fc08019
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---

# Unika besökare

[Mått](overview.md) för unika besökare visar antalet besökar-ID för dimensionsobjektet. Det är ett av de vanligaste måtten som används för att fastställa trafik, eftersom det ger en översikt på hög nivå över en dimensionsposts popularitet. En besökare kan till exempel komma till din webbplats varje dag i en månad, men de räknas ändå som en unik besökare.

Om du använder [Enhetsövergripande analys](../cda/overview.md) ersätts det här måttet med måttet [Unika enheter](unique-devices.md).

## unika besökare varje dag, vecka, månad, kvartal och år

Analysis Workspace behandlar unika besökare utifrån rapportens detaljrikedom. Om du till exempel använder dimensionen [Dag](../dimensions/day.md) visas unika besökare dagligen för varje dimensionsobjekt. För rapportsumman har den dock ersatts med unika besökare för friformstabellens datumintervall.

## Hur det här måttet beräknas

Det här måttet räknar antalet unika besökar-ID:n för en given dimensionspost. Mer information om hur Adobe Analytics identifierar unika besökare finns i [Översikt över besökaridentifiering](/help/implement/id/overview.md).
