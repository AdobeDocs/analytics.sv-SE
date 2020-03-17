---
description: Datalagret innehåller en funktion som gör att du kan extrahera en lista med besökar-ID:n. Dessa ID:n är inte cookie-ID:n, utan ID:n som du hämtar i en av dina konverteringsvariabler. Även om det finns andra sätt att komma åt den här informationen är följande exempel en genväg till att generera en begäran för ett datalager.
title: Användningsfall - Extraherar besökar-ID:n
topic: Admin tools
uuid: ed228334-619c-43d7-b781-a18af73b00bb
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Användningsfall - Extraherar besökar-ID:n

Datalagret innehåller en funktion som gör att du kan extrahera en lista med besökar-ID:n. Dessa ID:n är inte cookie-ID:n, utan ID:n som du hämtar i en av dina konverteringsvariabler. Även om det finns andra sätt att komma åt den här informationen är följande exempel en genväg till att generera en begäran för ett datalager.

Anta till exempel att ert företag skickar e-post med marknadsföring till kunder och potentiella kunder. Var och en av dessa e-postmottagare har ett unikt ID i e-postsystemet (till exempel *`EMAIL Contact ID`*). Du konfigurerar dina e-postmeddelanden så att besökaren, när kontakterna får ett e-postmeddelande och klickar på någon av länkarna, kommer till webbplatsen med ett kampanj-ID och ett unikt e-postkontakt-ID. E-postlänken kan till exempel resultera i följande:

```js
https://www.test.com/?cid=springmailblast&mid=1363660158
```

Genom att ställa in dessa i konverteringsvariabler (eVars) kan du se hur varje e-postmeddelande har utförts (via kampanj-ID) och hur ofta varje e-postmottagare besökt webbplatsen (via e-postkontaktens ID).

Anta att du hämtar dessa ID:n. De flesta marknadsförare vill segmentera sin webbplats och sedan se om de kan återmarknadsföra till dem som uppfyller vissa kriterier. Du kan till exempel skicka ett återmarknadsföringsmejl till alla e-postmottagare som kom till webbplatsen från e-postmeddelandet och visade (eller ifyllda) ett webbplatsformulär. Du kan göra detta genom att hitta ett sätt att identifiera e-post-ID:n för de som fyller i det specifika formuläret.

Ett sätt att göra detta är att använda en Conversion Subrelation-rapport för att dela upp eVar-värdet i formulär-ID:t för eVar-kontakten i EMAIL. En fördefinierad funktion finns dock tillgänglig för att göra detta med hjälp av datalagret. Med den här funktionen kan du se vilken eVar som lagrar dina unika användar-ID:n (i det här fallet EMAIL-kontakt-ID) och du enkelt kan extrahera dessa ID:n med datalagret. Med den här funktionen kan du automatiskt skapa en begäran om datalager som hämtar de unika besökar-ID:n som du är intresserad av.
