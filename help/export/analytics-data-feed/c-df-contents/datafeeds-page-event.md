---
description: Uppslagstabell som avgör typen av träff baserat på värdet för page_event.
keywords: Datafeed;page;event;page_event;post_page_event
title: Sökning efter sidhändelse
feature: Rapporter och analyser - Grunderna och analyser
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---

# Sökning efter sidhändelse

Uppslagstabell som avgör typen av träff baserat på värdet för page_event.

| Träff-typ | `page_event` value | `post_page_event` value |
| --- | --- | --- |
| Sidvyer | 0: Alla sidvisningssamtal och `trackState` samtal från mobil-SDK:n | Samma värde som `post_page_event` |
| Länkspårning | 10: Anpassade länkar och `trackAction` anrop i mobil-SDK:s<br>11: Ladda ned länkar<br>12: Avsluta länkar | 100: Anpassade länkar och `trackAction` anrop i mobil-SDK:s<br>101: Hämta länkar<br>102: Avsluta länkar |
| Video om milstolpe | 31: Mediestart<br>32: Medieuppdateringar (ingen annan variabelbearbetning)<br>33: Medieuppdateringar (med andra variabler) | 76: Mediestart<br>77: Medieuppdateringar (ingen annan variabelbearbetning)<br>78: Medieuppdateringar (med andra variabler) |
| Hjärtslagen video | 50: Start av medieström (ej Primetime)<br>51: Stäng medieström (ej Primetime)<br>52: Skrubbning av medieström (ej Primetime)<br>53: Medieströmmen hålls vid liv (ej Primetime)<br>54: Medieström och start (ej Primetime)<br>55: Medieström och stängning (ej Primetime)<br>56: Medieström och rensning (ej Primetime)<br>60: Primetime-medieströmmens start<br>61: Stäng Primetime-medieström<br>62: Skrubbning av primär medieström<br>63: Primetimes medieström håller sig levande<br>64: Primetimes medieström och start<br>65: Primetime-medieström och stäng<br>66: Primetimes medieström och rensning | Samma värde som `post_page_event` |
| Undersökning | 40: Alla samtal som genererats från undersökningen | 80: Alla samtal som genererats från undersökningen |
| Analyser för Target | 70: Träffen innehåller målaktivitetsdata | Samma värde som `post_page_event` |
