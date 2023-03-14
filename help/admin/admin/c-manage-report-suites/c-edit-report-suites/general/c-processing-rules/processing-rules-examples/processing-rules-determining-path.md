---
description: Du kan kopiera värdet för en eVar till en propp för att aktivera målning.
subtopic: Processing rules
title: Bestäm en sökväg genom att kopiera ett eVar-värde till ett projekt
feature: Admin Tools
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
exl-id: 23c978b9-a159-4364-9214-561a255d23e4
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Bestäm en sökväg genom att kopiera ett eVar-värde till ett projekt

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
