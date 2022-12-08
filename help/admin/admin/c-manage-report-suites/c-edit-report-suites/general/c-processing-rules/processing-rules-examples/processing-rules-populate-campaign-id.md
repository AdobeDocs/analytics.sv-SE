---
description: Du kan fylla i en variabel med hjälp av en frågesträngsparameter.
subtopic: Processing rules
title: Fylla i ett kampanj-ID från en frågesträngsparameter
feature: Admin Tools
uuid: 2bc61f9f-d8d2-41b7-bd39-4a9df30ff013
exl-id: 526d2727-b7f6-4b41-be86-e5f5bc5e6c2b
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 17%

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
