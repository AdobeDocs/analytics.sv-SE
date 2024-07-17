---
description: Uppslagstabell som avgör typen av träff baserat på värdet för page_event.
keywords: Datafeed;page;event;page_event;post_page_event
title: Sökning efter sidhändelse
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 0%

---

# Sökning efter sidhändelse

Uppslagstabell som avgör typen av träff baserat på värdet för page_event.

| Träff-typ | `page_event` värde | `post_page_event` värde |
| --- | --- | --- |
| Sidvyer | 0: Alla sidvisningssamtal och `trackState` samtal från mobil-SDK:n | Samma värde som `page_event` |
| Länkspårning | 10: Anpassade länkar och `trackAction` anrop i mobil-SDK:s<br>11: Hämta länkar<br>12: Avsluta länkar | 100: Anpassade länkar och `trackAction` anrop i mobil-SDK:s<br>101: Hämta länkar<br>102: Avsluta länkar |
| Video om milstolpe | 31: Mediestart<br>32: Medieuppdateringar (ingen annan variabelbearbetning)<br>33: Medieuppdateringar (med andra variabler) | 76: Mediestart<br>77: Medieuppdateringar (ingen annan variabelbearbetning)<br>78: Medieuppdateringar (med andra variabler) |
| Hjärtslagen video | 50: Start av medieström (ej Primetime)<br>51: Stäng medieström (inte Primetime)<br>52: Bläddra i medieström (inte Primetime)<br>53: Medieströmmen fortsätter att vara aktiv (inte Primetime)<br>54: Medieströmmen och start (inte Primetime)<br>55: Medieströmmen och stäng (inte-tid Primetime)<br>56: Medieströmmar och rensning (ej Primetime)<br>60: Primetime-medieströmmen startar<br>61: Primetime-medieströmmen stängs<br>62: Primetime-medieströmmen rensas<br>63: Primetime-medieströmmen fortsätter att vara aktiv<br>64: Primetime-medieströmmen och start<br> 65: Primetimes medieström och stängning<br>66: Primetimes medieström och rensning | Samma värde som `page_event` |
| Undersökning | 40: Alla samtal som genererats från Survey | 80: Alla samtal som genererats från Survey |
| Analyser för Target | 70: Träff innehåller målaktivitetsdata | Samma värde som `page_event` |
