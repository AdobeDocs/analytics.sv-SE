---
description: Lär dig hur du använder standardformatering och begränsad formatering i cellintervall.
title: Formatera datumet i Report Builder
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: User, Admin
exl-id: 9b251b09-9156-40b5-8e1f-fb6594a25c26
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---

# Formatera datum

{{legacy-arb}}

Förutom de standardalternativ för cellformatering som är tillgängliga via Excel-funktionen Format > Celler (Ctrl+1) kan du använda begränsad formatering för cellintervall med Report Builder. Dessa formateringsalternativ beror på vilket mätvärde du har valt.

När du har [lagt till dimensioner](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) i rutnätet för radetiketter klickar du på **[!UICONTROL Format]**.

Klicka på **[!UICONTROL Custom Format]** på menyn **[!UICONTROL Format]** om du vill använda anpassade format för datum som liknar funktionen för att lägga till och skjuta upp. Du kan t.ex. ange text som alltid infaller efter datumet (t.ex. A.D. B.C.E. A.H.). Du kan lägga till text före datumet, till exempel [!UICONTROL Start Date] och [!UICONTROL Start and End Date]. Dessutom kan du skapa ett anpassat datumuttryck från dag-, månad- och årsförkortningar samt använda en egen avgränsare mellan delar av datumet. Alla datumformat måste bestå av tre förkortningar inom parentes.

I följande tabell beskrivs hur du kan använda datumförkortningar i fältet [!UICONTROL Custom Format]:

| Förkortning | Betydelse | Exempel   med onsdag den 14 mars 2012 |
|--- |--- |--- |
| MM/dd/yyy | Fullständigt numeriskt datum | 03/14/2012 |
| M | Antal månader | 3 |
| MM | Antal månader med 0 utfyllnad för månader &lt; 10 | 03 |
| MMM | Kort namn på månad | Mars |
| MMMM | Långt namn på månad | Mars |
| D | Datumets långa namn | onsdagen den 14 mars 2012 |
| d | Antal dagar | 14 |
| dd | Antal dagar med 0 utfyllnad för dagar &lt; 10 | 01-09 |
| ddd | Kort namn på dagen | Wed |
| dddd | Dagens långa namn | onsdag |
| yy | Tvåsiffrigt år | 10 |
| yyyy | Fullständigt fyrsiffrigt år | 2012 |
