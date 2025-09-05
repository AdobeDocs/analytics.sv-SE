---
description: Lär dig mer om hur tidsdelningsdimensioner tar tidsstämpeln för insamlade händelser och delar upp dessa händelser i mer meningsfulla dimensioner, som t.ex. Timme på dagen eller Veckodag.
title: Tidsdelningsdimensioner
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# Tidsdelningsdimensioner

Tidsdelning innebär att tidsstämpeln för insamlade träffar delas i mer meningsfulla dimensioner, till exempel **Timme på dagen** eller **Dag på veckan**.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Tidsdelningsdimensioner](https://video.tv.adobe.com/v/23727?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


Tidsdelningsdimensionerna baseras på tidszonen för rapportsviten eller den virtuella rapportsviten. Dessa dimensioner finns i Analysis Workspace och kan ge svar på följande frågor:

* Vilken är den populäraste tiden på dagen för besökare som har tillgång till min webbplats eller app över ett stort datumintervall?
* Finns det några dagar i veckan, eller timmar på dagen, där konverteringen är högre på min webbplats eller app?
* Hur skiljer sig min helgsförsäljning från min veckodagsförsäljning?
* Genererar en viss marknadsföringskampanj högre konverteringar på morgonen eller på eftermiddagen?

>[!NOTE]
>
>Tidsdelningsdimensioner är bara tillgängliga i Analysis Workspace. Om du vill använda tidsdelningsdimensioner i andra Analytics-lösningar kan du implementera plugin-programmet [getTimeParting](/help/implement/vars/plugins/gettimeparting.md).

Tidsdelningsdimensioner i Analysis Workspace är:

| Dimension | Exempelvärden |
| --- | --- |
| Timme på dagen | 0-23 |
| AM/PM | AM, PM |
| Veckodag | Måndag, tisdag, onsdag, torsdag, fredag, lördag, söndag |
| Helg/veckodag | Weekend, Veckodag |
| Dag i månaden | 1-31 |
| Månad på året | Januari-december |
| Dag på året | 1-366 |
| Kvartal på året | Q1, Q2, Q3, Q4 |
