---
description: Uppslagstabell som avgör typen av träff baserat på värdet för page_event.
keywords: Datafeed;page;event;page_event;post_page_event
title: Sökning efter sidhändelse
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Sökning efter sidhändelse

Uppslagstabell som avgör typen av träff baserat på värdet för page_event.

| Träff-typ | `page_event` value | `post_page_event` value |
| --- | --- | --- |
| Sidvyer | 0: Alla sidvisningsanrop och `trackState` samtal från mobil-SDK:s | Samma värde som `page_event` |
| Länkspårning | 10: Egna länkar och `trackAction` samtal i mobil-SDK:s<br>11: Hämta länkar<br>12: Avsluta länkar | 100: Egna länkar och `trackAction` samtal i mobil-SDK:s<br>101: Hämta länkar<br>102: Avsluta länkar |
| Video om milstolpe | 31: Mediestart<br>32: Medieuppdateringar (ingen annan variabelbearbetning)<br>33: Medieuppdateringar (med andra variabler) | 76: Mediestart<br>77: Medieuppdateringar (ingen annan variabelbearbetning)<br>78: Medieuppdateringar (med andra variabler) |
| Hjärtslagen video | 50: Start av medieström (ej Primetime)<br>51: Stäng medieström (ej Primetime)<br>52: Skrubbning av medieström (ej Primetime)<br>53: Medieströmmen hålls vid liv (ej Primetime)<br>54: Medieström och start (ej Primetime)<br>55: Medieström och stängning (ej Primetime)<br>56: Medieström och rensning (ej Primetime)<br>60: Start för Primetime-medieström<br>61: Stäng primär medieström<br>62: Rensa medieströmmar i Primetime<br>63: Primetime-medieströmmen hålls vid liv<br>64: Start av medieström från Primetime<br>65: Primetime-medieström och stängning<br>66: Primetimes medieström och rensning | Samma värde som `page_event` |
| Undersökning | 40: Alla samtal som genererats från undersökningen | 80: Alla samtal som genererats från undersökningen |
| Analyser för Target | 70: Träffen innehåller målaktivitetsdata | Samma värde som `page_event` |
