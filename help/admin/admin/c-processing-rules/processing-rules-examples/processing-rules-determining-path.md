---
description: Du kan kopiera värdet för en eVar till en propp för att aktivera målning.
subtopic: Processing rules
title: Bestäm en sökväg genom att kopiera ett eVar-värde till ett projekt
feature: Administratörsverktyg
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
exl-id: 23c978b9-a159-4364-9214-561a255d23e4
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 20%

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
