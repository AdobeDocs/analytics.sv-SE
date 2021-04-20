---
description: Tidsdelning innebär att tidsstämpeln för insamlade träffar delas i mer meningsfulla dimensioner, till exempel"Dagens timme" eller"Veckodag".
title: Tidsdelning av dimensioner
uuid: c9fa7921-aa57-483c-b2f9-da55013ada17
feature: Workspace Basics
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 2%

---


# Tidsdelning av dimensioner

Tidsdelning innebär att tidsstämpeln för insamlade träffar delas i mer meningsfulla dimensioner, till exempel&quot;Dagens timme&quot; eller&quot;Veckodag&quot;.

Tidsdelningsdimensionerna baseras på tidszonen för rapportsviten eller den virtuella rapportsviten. Dessa dimensioner finns i Analysis Workspace och kan ge svar på följande frågor:

* Vilken är den populäraste tiden på dagen för besökare som har tillgång till min webbplats eller app över ett stort datumintervall?
* Finns det några dagar i veckan, eller timmar på dagen, där konverteringen är högre på min webbplats eller app?
* Hur skiljer sig min helgsförsäljning från min veckodagsförsäljning?
* Genererar en viss marknadsföringskampanj högre konverteringar på morgonen eller på eftermiddagen?

>[!NOTE]
>
>Tidsdelningsdimensioner är bara tillgängliga i Analysis Workspace. Om du vill använda tidsdelningsdimensioner i andra Analytics-lösningar kan du implementera plugin-programmet [getTimeParting](https://docs.adobe.com/content/help/en/analytics/implementation/vars/plugins/gettimeparting.html).

Tidsdelningsdimensioner i Analysis Workspace är:

| Dimension | Exempelvärden |
|--- |--- |
| Timme på dagen | 0-23 |
| AM/PM | AM, PM |
| Veckodag | Måndag, tisdag, onsdag, torsdag, fredag, lördag, söndag |
| Helg/veckodag | Weekend, Veckodag |
| Dag i månaden | 1-31 |
| Månad på året | Januari-december |
| Dag på året | 1-366 |
| Kvartal på året | Q1, Q2, Q3, Q4 |
