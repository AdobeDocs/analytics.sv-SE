---
description: Rättigheter för beräknade värden skiljer sig mellan användare på administratörsnivå och icke-administratörer.
title: Rollbaserade rättigheter för beräknade mätvärden
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 0%

---

# Beräknade mått: rollbaserade rättigheter

Rättigheter för beräknade värden skiljer sig mellan användare på administratörsnivå och icke-administratörer.

|  | Skapa | Dela | Visa/hantera | Godkänn | Använd |
|--- |--- |--- |--- |--- |--- |
| Användare på administratörsnivå | Administratörer kan skapa beräknade mätvärden samt skapa produktprofiler i Admin Console för att begränsa användarnas behörighet att skapa beräknade mätvärden. | Kan delas med hela företaget, med användargrupper och med enskilda användare. | Report Builder: Kan visa/redigera/ta bort/etc. sina egna beräknade värden och de som delas med dem. | Kan godkänna beräknade värden som kanoniska. | Kan använda alla beräknade värden i hela organisationen. |
| Användare på annan nivå än administratörsnivå | Som standard kan användare skapa beräknade värden. Dessa rättigheter kan dock begränsas av administratörer. | Kan endast dela med enskilda användare | Kan visa/redigera/ta bort/etc. bara deras egna beräknade värden. Icke-adminanvändare måste ha tillgång till alla komponenthändelser för att kunna se delade mått (behörigheterna i Admin Console används fortfarande).  Om en instrumentpanel eller schemalagd rapport delas med en icke-admin-användare och de inte har mätvärdena delade med sig, kommer rapporten att köras med det mätvärde som används (förutsatt att de har behörighet att visa händelserna). De kommer dock inte att kunna se definitionen eller redigera måttet. | Kan endast förbruka godkända beräknade värden; kan inte markeras som godkända. | Kan använda egna beräknade värden och segment som har delats med dem. |