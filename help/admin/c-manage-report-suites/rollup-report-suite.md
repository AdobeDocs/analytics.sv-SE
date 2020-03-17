---
description: Sammanslagningsrapportsviter samlar in data från flera underordnade rapportsviter och visar dem i en sammanfattande datauppsättning.
title: Sammanslagning och globala rapportsviter
topic: Admin tools
uuid: c90b8e38-2c95-4318-8165-a362106b6142
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Sammanslagning och globala rapportsviter

Sammanslagningsrapportsviter samlar in data från flera underordnade rapportsviter och visar dem i en sammanfattande datauppsättning. De är en praktisk plats där du kan se summerade summor som sidvisningar, intäkter eller andra grundläggande dimensioner. Samlingar används ofta eftersom de inte kräver någon ytterligare implementering.

## Definitioner av rapporttyper

**Global rapportsvit**: Implementeringen ändras för att skicka bildbegäranden mellan domäner till en enda global rapportserie. Om träffar också skickas till enskilda rapportsviter kallas detta för märkning av flera programsviter.

**Rapport**: Skapat i Admin Tools. Tar summan av varje mätvärde i slutet av varje dag.

* Det är fritt att använda sammanslagningar och det ökar inte användningen av serveranrop.
* Sammanslagningar ger totaldata, men rapporterar inte enskilda värden i rapporter. eVar1-värden inkluderas till exempel inte, men dess sammanlagda summa kan vara det.
* Data dedupliceras inte när data kombineras mellan olika rapportsviter.
* Upprullningar körs på nattbasis.
* När du lägger till en rapportserie i en befintlig sammanslagning inkluderas inte historiska data i sammanslagningen.
* Alla underordnade rapportsviter måste ha data för att en sammanslagning ska fungera. Om nya rapportsviter ingår i en sammanslagning måste du skicka minst en sidvy till dessa rapportsviter.
* Sammanslagningsrapportsviter är begränsade till högst 40 underordnade rapportsviter.
* Sammanslagningsrapportsviter är begränsade till högst 100 händelser.
* Data i sammanfattningsrapportsviter stöder inte uppdelningar eller segment.
* Sidrapporten ersätts med rapporten Most Popular Sites (Populära platser), som rapporterar mått på underordnad svitnivå.

## Sammanslagning jämfört med globala rapportsviter

**Sekundära serveranrop**: Vid sammanslagning uppstår inga ytterligare serveranrop utöver vad en enda rapportserie samlar in. Om din organisation använder taggar för flera programsviter görs sekundära serveranrop för varje extra rapportsvit som ingår i en bildbegäran.

> [!TIP] Om du bara använder en global rapportserie med [virtuella rapportsviter](../../components/vrs/vrs-considerations.md)behövs inga sekundära serveranrop.

**Implementeringsändringar**: Vid sammanslagning krävs inga implementeringsändringar, medan globala rapportsviter kräver att du inkluderar det globala rapportsvitens ID i implementeringen.

**Duplicering**: Globala rapportsviter dubblerar unika besökare, men inte sammanslagningar. Om en användare till exempel besöker tre av dina domäner under samma dag, kommer sammanslagningar att räkna tre unika besökare per dag. Global rapportserie registrerar en unik besökare.

**Tidsram**: Samlingar behandlas endast vid midnatt varje kväll, medan globala rapportsviter rapporterar data med standardfördröjning.

**Bredd**: Uppsättningar kan inte kommunicera mellan rapportsviter. Globala rapportsviter kan attribuera konverteringar till konverteringsvariabler mellan olika rapportsviter, samt tillhandahålla sökvägar mellan rapportsviter.

**Historiska data**: Sammanslagningar kan samla in historiska data, medan globala rapportsviter bara rapporterar data från den punkt de implementerades.

**Rapporter**: Globala rapportsviter innehåller data om alla dimensioner. sammanslagningar tillhandahåller aggregerade data på enbart högnivårapporter.

**Produkter** som stöds: Samlingar kan bara användas i rapporter och analyser. De stöds inte i Analysis Workspace, Data Warehouse eller Ad Hoc Analysis. Globala rapportsviter kan användas för alla produkter.

**Antal aggregerade rapportsviter**: Samlingar stöder endast maximalt 40 underordnade rapportsviter. Globala rapportsviter kan implementeras på valfritt antal domäner eller appar som du äger.
