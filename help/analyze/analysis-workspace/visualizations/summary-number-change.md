---
description: Använd visualiseringarna Sammanfattningsnummer och Ändra för att visa viktiga datapunkter i ett projekt.
title: Sammanfattning av antal och förändring
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
source-git-commit: c4f6a7a3d81160a1c86ebfa70d1e376882ccfee2
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 2%

---

# [!UICONTROL Summary Number] och [!UICONTROL Summary Change]

Här är en video om dessa två visualiseringar:

>[!VIDEO](https://video.tv.adobe.com/v/335564/?quality=12)

## [!UICONTROL Summary Number] visualisering {#summary-number}

Använd [!UICONTROL Summary Number] visualisering för att framhäva ett stort antal som är viktiga i ett projekt. Den här visualiseringen fungerar på följande sätt:

* Markerar kolumnsumman om ingen cell är markerad.
* Om en enskild cell är markerad visas sammanfattningen för den cellen.
* Om flera celler är markerade visas den första cellen som är markerad.
* Om kolumnen är markerad väljs det första cellvärdet i kolumnen.

Klicka på **Visualiseringsinställningar** växla till det övre högra hörnet för att konfigurera inställningarna för Sammanfattningsnummer:

| Inställning | Definition |
|--- |--- |
| [!UICONTROL Percentages] | Visa procenttal i stället för råa tal. |
| [!UICONTROL Legend visible] | Visa information om måttet som visas. |
| [!UICONTROL Abbreviate value] | Välj om du vill förkorta värden och visa upp till tre decimaler. |
| [!UICONTROL Summarize value by] | Välj om du vill visa max, min, medelvärde, median eller summan för ett dataurval. |

## [!UICONTROL Summary Change] visualisering {#summary-change}

Använd [!UICONTROL Summary Change] visualisering för att visa delta (ändring) mellan två tal. Den gröna och röda färgen i [!UICONTROL Summary Change] kan styras genom [anpassad händelsepolaritet](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) eller ett beräknat mått [Visa uppåttrend som](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) alternativ.

Den här visualiseringen fungerar på följande sätt:

* Om ingen cell är markerad jämförs de två första cellvärdena i kolumnen.
* Om en cell är markerad visas 0, eftersom cellvärdet jämförs med sig själv.
* Om två celler är markerade tas den första markerade cellen som täljare och den andra som nämnare.
* Om fler än två celler är markerade kommer endast de första två att användas för jämförelse.
* Om ett cellintervall är markerat jämförs den första med den sista cellen i intervallet.
* Om kolumnen är markerad jämförs det första värdet med sig självt, vilket innebär en ändring på 0.


![](assets/summary-change.png)


Klicka på **Visualiseringsinställningar** växla till det övre högra hörnet för att konfigurera inställningarna för Sammanfattningsändring:

| Inställning | Definition |
| --- | --- |
| [!UICONTROL Percentages] | Visa procenttal i stället för råa tal. |
| [!UICONTROL Legend visible] | Visa information om måttet som visas. |
| [!UICONTROL Show Percent Change] | Visar procentändringen mellan de två talen. |
| [!UICONTROL Show Raw Difference] | Visar den obearbetade skillnaden mellan de två talen. Med det här alternativet kan du även förkorta värden och visa upp till tre decimaler. |
