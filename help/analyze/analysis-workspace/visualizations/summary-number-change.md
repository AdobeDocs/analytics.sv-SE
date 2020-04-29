---
description: 'null'
title: Sammanfattningsnummer och sammanfattning
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Sammanfattningsnummer och sammanfattning

## Visualisering av sammanfattningsnummer

* Markerar kolumnsumman om ingen cell är markerad.
* Om en enskild cell är markerad visas sammanfattningen för den cellen.
* Om flera celler är markerade visas den första cellen som är markerad.
* Om kolumnen är markerad väljs det första cellvärdet i kolumnen.

![](assets/summary-number.png)

## Visualisering av sammanfattningsändring

* Om ingen cell är markerad jämförs de två första cellvärdena i kolumnen.
* Om en cell är markerad visas 0, eftersom cellvärdet jämförs med sig själv.
* Om två celler är markerade tas den första markerade cellen som täljare och den andra som nämnare.
* Om fler än två celler är markerade kommer endast de första två att användas för jämförelse.
* Om ett cellintervall är markerat jämförs den första med den sista cellen i intervallet.
* Om kolumnen är markerad jämförs det första värdet med sig självt, vilket innebär en ändring på 0.
* Den gröna och röda färgen i sammanfattningsändringen kan styras med:
   * [Anpassad händelsepolaritet](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html).
   * Alternativet [Visa uppåttrend som](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) för ett beräknat mått.

## Ändra inställningar för sammanfattning {#section_2581AC0107634FB4990AB8347E5897AA}

Klicka på kugghjulsikonen bredvid visualiseringen för att konfigurera summeringsinställningarna:

| Inställning | Definition |
|--- |--- |
| Procenttal | Använd procenttal i stället för råtal. |
| Förklaring synlig | Visar de mått som används. |
| Alternativ för sammanfattningsnummer: Förkortningsvärde | Du kan välja mellan 0 och 3 decimaler för förkortade värden. |
| Alternativ för sammanfattning: Visa procentuell ändring | Visar ändringen i procent mellan de två talen. |
| Alternativ för sammanfattning: Visa råskillnad | Visar den obearbetade skillnaden mellan de två talen. |
