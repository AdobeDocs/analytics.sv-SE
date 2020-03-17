---
description: Tidsdelning innebär att tidsstämpeln för insamlade träffar delas i mer meningsfulla dimensioner, till exempel"Dagens timme" eller"Veckodag".
title: Tidsdelningsdimensioner
uuid: c9fa7921-aa57-483c-b2f9-da55013ada17
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Tidsdelningsdimensioner

Tidsdelning innebär att tidsstämpeln för insamlade träffar delas i mer meningsfulla dimensioner, till exempel&quot;Dagens timme&quot; eller&quot;Veckodag&quot;.

Tidsdelningsdimensionerna baseras på tidszonen för rapportsviten eller den virtuella rapportsviten. Dimensionerna är tillgängliga i Analysis Workspace och kan hjälpa till att besvara följande frågor:

* Vilken är den populäraste tiden på dagen för besökare som har tillgång till min webbplats eller app över ett stort datumintervall?
* Finns det några dagar i veckan, eller timmar på dagen, där konverteringen är högre på min webbplats eller app?
* Hur skiljer sig min helgsförsäljning från min veckodagsförsäljning?
* Genererar en viss marknadsföringskampanj högre konverteringar på morgonen eller på eftermiddagen?

> [!NOTE] Tidsdelningsdimensioner är bara tillgängliga i Analysis Workspace. Om du vill använda tidsdelningsdimensioner i andra Analytics-lösningar kan du implementera plugin-programmet [getTimeParting](https://marketing.adobe.com/resources/help/en_US/sc/implement/getTimeParting.html).

Tidsdelningsdimensionerna i Analysis Workspace är:

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
