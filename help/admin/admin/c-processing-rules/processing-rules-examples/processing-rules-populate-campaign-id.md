---
description: Du kan fylla i en variabel med hjälp av en frågesträngsparameter.
subtopic: Processing rules
title: Fylla i ett kampanj-ID från en frågesträngsparameter
feature: Admin Tools
uuid: 2bc61f9f-d8d2-41b7-bd39-4a9df30ff013
exl-id: 526d2727-b7f6-4b41-be86-e5f5bc5e6c2b
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 19%

---

# Fylla i ett kampanj-ID från en frågesträngsparameter

Du kan fylla i en variabel med hjälp av en frågesträngsparameter.

I de flesta fall använder du ett plugin-program för att fylla i variabler från frågesträngen. Om ett typfel eller liknande problem förhindrar att värdet fylls i kan du fylla i variabeln med bearbetningsregler.

Du bör alltid kontrollera om ett värde är tomt eller innehåller det förväntade värdet innan du skriver över det.

| Regeluppsättning | Värde |
|---|---|
| Villkor | Kampanjen har inte angetts |
| Åtgärd | Skriv över värdet för Campaign till frågesträngsparameter cpid |

Exempel:

![](assets/set-campaign-conditionally.png)
