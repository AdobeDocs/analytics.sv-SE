---
description: Du kan kopiera värdet för en eVar till en propp för att aktivera målning.
subtopic: Processing rules
title: Bestäm en bana genom att kopiera ett eVar-värde till en propp
feature: Admin Tools
role: Admin
exl-id: 23c978b9-a159-4364-9214-561a255d23e4
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 1%

---

# Bestäm en bana genom att kopiera ett eVar-värde till en propp

Du kan kopiera värdet för en eVar till en propp för att aktivera målning.

När du anger värden får variabeln till vänster värdet (även om den är tom) från variabeln till höger.

| Regeluppsättning | Värde |
|---|---|
| Villkor | Ingen (kör alltid) |
| Åtgärd | Skriv över värdet för Prop1 med eVar1 |

Du kan bara ändra den här regeln för att ange värdet för Prop1 om den inte redan innehåller ett värde som liknar följande:

| Regeluppsättning | Värde |
|---|---|
| Villkor | Om Prop1 inte har angetts |
| Åtgärd | Skriv över värdet för Prop1 med eVar1 |

Exempel:

![](assets/overwrite-empty-prop.png)
