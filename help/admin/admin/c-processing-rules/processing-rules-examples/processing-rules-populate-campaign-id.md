---
description: Du kan fylla i en variabel med hjälp av en frågesträngsparameter.
subtopic: Processing rules
title: Fylla i ett kampanj-ID från en frågesträngsparameter
topic: Admin tools
uuid: 2bc61f9f-d8d2-41b7-bd39-4a9df30ff013
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

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

