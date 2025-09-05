---
description: Data Warehouse har en funktion som gör att du kan extrahera en lista med besökar-ID:n. Dessa ID:n är inte cookie-ID:n, utan ID:n som du hämtar i en av dina konverteringsvariabler. Även om det finns andra sätt att komma åt den här informationen är följande exempel en genväg till att generera en Data Warehouse-begäran.
title: Användningsfall - Extraherar besökar-ID:n
feature: Admin Tools
role: Admin
exl-id: b1fc41af-31c7-42cd-aab7-0c659577781d
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# Användningsfall - Extraherar besökar-ID:n

Data Warehouse har en funktion som gör att du kan extrahera en lista med besökar-ID:n. Dessa ID:n är inte cookie-ID:n, utan ID:n som du hämtar i en av dina konverteringsvariabler. Även om det finns andra sätt att komma åt den här informationen är följande exempel en genväg till att generera en Data Warehouse-begäran.

Anta till exempel att ert företag skickar e-post med marknadsföring till kunder och potentiella kunder. Var och en av dessa e-postmottagare har ett unikt ID i e-postsystemet (till exempel *`EMAIL Contact ID`*). Du konfigurerar dina e-postmeddelanden så att besökaren, när kontakterna får ett e-postmeddelande och klickar på någon av länkarna, kommer till webbplatsen med ett kampanj-ID och ett unikt e-postkontakt-ID. E-postlänken kan till exempel resultera i följande:

```js
https://www.example.com/?cid=springmailblast&mid=1363660158
```

Genom att ställa in dessa i konverteringsvariabler (eVars) kan du se hur varje e-postmeddelande som skickas (via kampanj-ID) och hur ofta varje e-postmottagare besökt webbplatsen (via e-postkontaktens ID).

Anta att du hämtar dessa ID:n. De flesta marknadsförare vill segmentera sin webbplats och sedan se om de kan återmarknadsföra till dem som uppfyller vissa kriterier. Du kan till exempel skicka ett återmarknadsföringsmejl till alla e-postmottagare som kom till webbplatsen från e-postmeddelandet och visade (eller ifyllda) ett webbplatsformulär. Du kan göra detta genom att hitta ett sätt att identifiera e-post-ID:n för de som fyller i det specifika formuläret.

Ett sätt att göra detta är att använda en Conversion Subrelation-rapport för att bryta ned värdet för formulär-ID eVar av eVar för e-postens kontakt-ID. Det finns dock en färdig funktion för att göra detta med Data Warehouse. Med den här funktionen kan du se vilka eVar som lagrar dina unika användar-ID:n (i det här fallet e-postkontakt-ID) och du enkelt kan extrahera dessa ID:n med datalagret. Med den här funktionen kan du automatiskt skapa en begäran om datalager som hämtar de unika besökar-ID:n som du är intresserad av.
