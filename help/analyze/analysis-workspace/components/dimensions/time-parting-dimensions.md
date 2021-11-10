---
description: Tidsdelning innebär att tidsstämpeln för insamlade träffar delas i mer meningsfulla dimensioner, till exempel"Dagens timme" eller"Veckodag".
title: Tidsdelning av dimensioner
uuid: c9fa7921-aa57-483c-b2f9-da55013ada17
feature: Workspace Basics
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
source-git-commit: b0baf1fbc8cf4cafe1d5292774e47556c9b0151b
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 2%

---

# Tidsdelning av dimensioner

Tidsdelning innebär att tidsstämpeln för insamlade träffar delas i mer meningsfulla dimensioner, till exempel&quot;Dagens timme&quot; eller&quot;Veckodag&quot;.

Här är en video om tidsdelningsdimensioner:

>[!VIDEO](https://video.tv.adobe.com/v/23727/?quality=12)

Tidsdelningsdimensionerna baseras på tidszonen för rapportsviten eller den virtuella rapportsviten. Dessa dimensioner finns i Analysis Workspace och kan ge svar på följande frågor:

* Vilken är den populäraste tiden på dagen för besökare som har tillgång till min webbplats eller app över ett stort datumintervall?
* Finns det några dagar i veckan, eller timmar på dagen, där konverteringen är högre på min webbplats eller app?
* Hur skiljer sig min helgsförsäljning från min veckodagsförsäljning?
* Genererar en viss marknadsföringskampanj högre konverteringar på morgonen eller på eftermiddagen?

>[!NOTE]
>
>Tidsdelningsdimensioner är bara tillgängliga i Analysis Workspace. Om du vill använda tidsdelningsdimensioner i andra Analytics-lösningar kan du implementera [getTimeParting, plugin](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/gettimeparting.html).

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
