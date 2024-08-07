---
title: Jämförelse av olika metoder för att utesluta robotar
description: Gör att du kan jämföra olika metoder för att utesluta stötar.
exl-id: c54ba98a-b396-479e-bfe8-dc6211b26f61
role: Admin
feature: Bot Removal
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 6%

---

# Jämförelse av olika metoder för att utesluta robotar

I följande tabell visas olika metoder för att exkludera robotar och hur de jämförs med varandra.

| Metod | Punktregler | Exkludera efter IP-adress | Kundattribut | Segmentering | Poäng + segmentering från tredje part | Utelämna &#x200B; för serveranrop för &#x200B; vid körning | VISTA-regel för anpassad databas |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Beskrivning av metod för att exkludera data** | Uteslut &#x200B; baserat på användaragent, IP-adress eller IP-adressintervall | IP-adress | &#x200B; En flagga i kundattribut som identifierar ECID som en robot | &#x200B; i ett Analytics-segment som identifierar kända botar baserat på robotbeteendet | &#x200B; En tredje part som [Perimeter X](https://www.perimeterx.com) eller [Akamai Bot Manager](https://www.akamai.com/us/en/products/security/bot-manager.jsp) tilldelar varje sidvy en poäng som anger hur sannolikt det är att den är en robot. Score skickas till Analytics och segment kan användas för att filtrera data utifrån poängen. | &#x200B; logik på klientsidan hindrar Analytics-serveranropet från att köras för robotar. | &#x200B; En VISTA-regel kommer att flytta trafik från botar som uppfyller vissa villkor till en separat rapportserie. |
| **&#x200B; punktnamn är tillgängliga för rapportering?** | Ja | Nej | Nej | Nej | Nej | Nej | Ja |
| **&#x200B; kan du se vilka sidor som besöks av robotar?** | Ja | Nej | Nej | Nej | Ja | Nej | Ja |
| &#x200B;**Vill du öka serversamtalskostnaden för robotar?** | Ja | Ja | Ja | Ja | Ja | Nej | Ja |
| **Bot data tillgängliga i dataflöden?** | Nej | Nej | Ja | Ja | Ja | Nej | Ja |
| **Kan &#x200B; rapportera om robottrafik som om det är faktiska serveranrop?** | Nej | Nej | Ja | Ja | Ja | Nej | Nej |
| **Kan data tas bort retroaktivt från en datauppsättning?** | Nej | Nej | &#x200B; Ja, när deklarerade ID:n har implementerats | Ja | Ja, när poängen är implementerade | Nej | Nej |
| **Är villkorsbegränsningar i Uniques?** | Nej | Nej | Nej | Ja | Nej | Nej | Nej |
| **Är &#x200B; föremål för extra kostnad?** | Nej | Nej | &#x200B;, eventuellt beroende på Analytics-SKU | Nej | Ja | Nej | &#x200B; Ja - kostnad för att implementera och underhålla en VISTA-regel |
