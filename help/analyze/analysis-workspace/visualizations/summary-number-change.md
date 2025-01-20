---
description: Använd visualiseringarna Sammanfattningsnummer och Ändra för att visa viktiga datapunkter i ett projekt.
title: Sammanfattningsnummer och sammanfattning
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
source-git-commit: 76abe4e363184a9577622818fe21859d016a5cf7
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 1%

---

# [!UICONTROL Summary Number] och [!UICONTROL Summary Change]

_I den här artikeln dokumenteras visualiseringar av sammanfattningsnummer och sammanfattningsändringar i_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Se [Sammanfattningsnummer och Sammanfattningsändring](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/summary-number-change) för_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**-versionen av den här artikeln._

Här är en video om dessa två visualiseringar:

>[!VIDEO](https://video.tv.adobe.com/v/335564/?quality=12)

## [!UICONTROL Summary Number]-visualisering {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Sammanfattningsnummer"
>abstract="Skapa en visualisering som visar summor och delsummor."

<!-- markdownlint-enable MD034 -->

Använd visualiseringen [!UICONTROL Summary Number] för att markera ett stort tal som är viktigt i ett projekt. Den här visualiseringen fungerar på följande sätt:

* Markerar kolumnsumman om ingen cell är markerad.
* Om en enskild cell är markerad visas sammanfattningen för den cellen.
* Om flera celler är markerade visas den första cellen som är markerad.
* Om kolumnen är markerad väljs det första cellvärdet i kolumnen.

Klicka på **Visualiseringsinställningarna** i det övre högra hörnet för att konfigurera inställningarna för Sammanfattningsnummer:

| Inställning | Definition |
|--- |--- |
| [!UICONTROL Percentages] | Visa procenttal i stället för råa tal. |
| [!UICONTROL Legend visible] | Visa information om måttet som visas. |
| [!UICONTROL Abbreviate value] | Välj om du vill förkorta värden och visa upp till tre decimaler. |
| [!UICONTROL Summarize value by] | Välj om du vill visa max, min, medelvärde, median eller summan för ett dataurval. |

## [!UICONTROL Summary Change]-visualisering {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="Sammanfattningsändring"
>abstract="Skapa en visualisering som visar delta (ändring) mellan två tal"

<!-- markdownlint-enable MD034 -->

Använd visualiseringen [!UICONTROL Summary Change] för att visa delta (ändring) mellan två tal. Den gröna och röda färgen för [!UICONTROL Summary Change] kan styras med [anpassad händelsepolaritet](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) eller det beräknade måttets [Visa uppåttrend som](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) -alternativ.

Den här visualiseringen fungerar på följande sätt:

* Om ingen cell är markerad jämförs de två första cellvärdena i kolumnen.
* Om en cell är markerad visas 0, eftersom cellvärdet jämförs med sig själv.
* Om två celler är markerade tas den första markerade cellen som täljare och den andra som nämnare.
* Om fler än två celler är markerade kommer endast de första två att användas för jämförelse.
* Om ett cellintervall är markerat jämförs den första med den sista cellen i intervallet.
* Om kolumnen är markerad jämförs det första värdet med sig självt, vilket innebär en ändring på 0.


![](assets/summary-change.png)


Klicka på **Visualiseringsinställningarna** i det övre högra hörnet för att konfigurera inställningarna för Sammanfattningsändring:

| Inställning | Definition |
| --- | --- |
| [!UICONTROL Percentages] | Visa procenttal i stället för råa tal. |
| [!UICONTROL Legend visible] | Visa information om måttet som visas. |
| [!UICONTROL Show Percent Change] | Visar procentuell ändring mellan de två talen. |
| [!UICONTROL Show Raw Difference] | Visar den obearbetade skillnaden mellan de två talen. Med det här alternativet kan du även förkorta värden och visa upp till tre decimaler. |
