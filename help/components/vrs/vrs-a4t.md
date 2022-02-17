---
description: Specialöverväganden när du använder virtuella A4T- och Adobe Analytics-rapportsviter
title: Virtuella rapportsviter och analyser för Target (A4T)
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---

# Virtuella rapportsviter och analyser för Target (A4T)

Tänk på följande kavattningar när du använder virtuella rapportsviter i Adobe Target-sammanhang:

* Du kan inte skicka data direkt från Target till en virtuell rapportserie, bara till en riktig rapportserie.
* Du kan rapportera om A4T-aktiviteter i en virtuell rapportserie. A4T-data är dock begränsade till de rader som matchar det virtuella rapportsvitsegmentet (och andra segment som används). Om du till exempel har skapat en virtuell rapportsvit för dina EMEA-kunder, speglar A4T-data i den virtuella rapportsviten endast Target-data för dina EMEA-kunder.
* Du kan inte publicera segment från en virtuell rapportserie tillbaka till Target för aktivering.
