---
description: Du kan kopiera värdet för en eVar till en propp för att aktivera målning.
subtopic: Processing rules
title: Bestäm en bana genom att kopiera ett eVar-värde till ett projekt
topic: Admin tools
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Bestäm en bana genom att kopiera ett eVar-värde till ett projekt

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

