---
title: Jämförelse av olika metoder för att utesluta robotar
description: Gör att du kan jämföra olika metoder för att utesluta stötar.
exl-id: c54ba98a-b396-479e-bfe8-dc6211b26f61
role: Admin
feature: Bot Removal
source-git-commit: 75c1585f88d9d3adcf66632c52cecf2a97fa2632
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 6%

---

# Jämförelse av olika metoder för att utesluta robotar

I följande tabell visas olika metoder för att exkludera robotar och hur de jämförs med varandra.

| Metod | Punktregler | Exkludera efter IP-adress | Kundattribut | Segmentering | Poäng + segmentering från tredje part | Utelämna serveranrop för starter vid körning | VISTA-regel för anpassad databas |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Beskrivning av metod för att exkludera data** | Exkludera baserat på användar-agent, IP-adress eller IP-adressintervall | IP-adress | En flagga i kundattribut som identifierar ECID som en robot | Kriterier i ett Analytics-segment som identifierar kända botar baserat på robotbeteendet | En tredje part som [Perimeter X](https://www.perimeterx.com) eller [Akamai Bot Manager](https://www.akamai.com/us/en/products/security/bot-manager.jsp) tilldelar varje sidvy en poäng som anger hur sannolikt det är att den är en robot. Score skickas till Analytics och segment kan användas för att filtrera data utifrån poängen. | Klientsidans logik hindrar Analytics-serveranropet från att köras för robotar. | En VISTA-regel kommer att flytta trafik från botar som uppfyller vissa villkor till en separat rapportserie. |
| **Punktnamn är tillgängliga för rapportering?** | Ja | Nej | Nej | Nej | Nej | Nej | Ja |
| **Kan du se vilka sidor som besöks av robotar?** | Ja | Nej | Nej | Nej | Ja | Nej | Ja |
| **Vill du öka serversamtalskostnaden för robotar?** | Ja | Ja | Ja | Ja | Ja | Nej | Ja |
| **Bot data tillgängliga i dataflöden?** | Nej | Nej | Ja | Nej | Ja | Nej | Ja |
| **Kan du rapportera om robottrafik som om det är faktiska serveranrop?** | Nej | Nej | Ja | Ja | Ja | Nej | Nej |
| **Kan data tas bort retroaktivt från en datauppsättning?** | Nej | Nej | Ja, när deklarerade ID:n har implementerats | Ja | Ja, när poängen är implementerade | Nej | Nej |
| **Är villkorsbegränsningar i Uniques?** | Nej | Nej | Nej | Ja | Nej | Nej | Nej |
| **Är en ytterligare kostnad?** | Nej | Nej | Möjligen beroende på Analytics-SKU | Nej | Ja | Nej | Ja - kostnad för att implementera och underhålla en VISTA-regel |
