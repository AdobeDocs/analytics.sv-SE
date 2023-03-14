---
description: Förutom de standardalternativ för cellformatering som är tillgängliga via Excel-funktionen Format > Celler (Ctrl+1) kan du använda begränsad formatering för cellintervall med Report Builder. Dessa formateringsalternativ beror på vilket mätvärde du har valt.
title: Formatera datum
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: User, Admin
exl-id: 9b251b09-9156-40b5-8e1f-fb6594a25c26
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 6%

---

# Formatera datum

Förutom de standardalternativ för cellformatering som är tillgängliga via Excel-funktionen Format > Celler (Ctrl+1) kan du använda begränsad formatering för cellintervall med Report Builder. Dessa formateringsalternativ beror på vilket mätvärde du har valt.

Efter [lägg till dimensioner](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) till stödrastret Radetiketter klickar du på **[!UICONTROL Format]**.

I **[!UICONTROL Format]** meny, klicka **[!UICONTROL Custom Format]** om du vill använda anpassade format för datum som liknar prepend- och postpend-funktionen. Du kan t.ex. ange text som alltid infaller efter datumet (t.ex. A.D. B.C.E. A.H. osv.). Du kan lägga till text före datumet, till exempel [!UICONTROL Start Date] och [!UICONTROL Start and End Date]. Dessutom kan du skapa ett anpassat datumuttryck från dag-, månad- och årsförkortningar samt använda en egen avgränsare mellan delar av datumet. Alla datumformat måste bestå av tre förkortningar inom parentes.

I följande tabell beskrivs hur du kan använda datumförkortningar i [!UICONTROL Custom Format] fält:

| Förkortning | Betydelse | Exempel på användning av onsdag den 14 mars 2012 |
|--- |--- |--- |
| MM/dd/yyy | Fullständigt numeriskt datum | 03/14/2012 |
| M | Antal månader | 3 |
| MM | Antal månader med 0 utfyllnad för månader &lt; 10 | 03 |
| MMM | Kort namn på månad | Mars |
| MMMM | Långt namn på månad | Mars |
| D | Datumets långa namn | onsdagen den 14 mars 2012 |
| d | Antal dagar | 14 |
| dd | Antal dagar med 0 utfyllnad för dagar &lt; 10 | 01 - 09 |
| ddd | Kort namn på dagen | Wed |
| dddd | Dagens långa namn | onsdag |
| yy | Tvåsiffrigt år | 10 |
| yyyy | Fullständigt fyrsiffrigt årtal | 2012 |
