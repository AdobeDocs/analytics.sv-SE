---
description: Uppslagstabell som avgör typen av träff baserat på värdet för page_event.
keywords: Data Feed;page;event;page_event;post_page_event
title: Sökning efter sidhändelse
topic: Reports and analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Sökning efter sidhändelse

Uppslagstabell som avgör typen av träff baserat på värdet för page_event.

| Träff-typ | `page_event` value | `post_page_event` value |
| --- | --- | --- |
| Sidvyer | 0: Alla sidvisningssamtal och `trackState` samtal från mobil-SDK:n | Samma värde som `post_page_event` |
| Länkspårning | 10: Anpassade länkar och `trackAction` samtal i mobil-SDK<br>11: Ladda ned länkar<br>12: Avsluta länkar | 100: Anpassade länkar och `trackAction` samtal i mobil-SDK:s<br>101: Ladda ned länkar<br>102: Avsluta länkar |
| Video om milstolpe | 31: Mediestart<br>32: Medieuppdateringar (ingen annan variabelbearbetning)<br>33: Medieuppdateringar (med andra variabler) | 76: Mediestart<br>77: Medieuppdateringar (ingen annan variabelbearbetning)<br>78: Medieuppdateringar (med andra variabler) |
| Hjärtslagen video | 50: Start av medieström (ej Primetime)<br>51: Stäng medieström (ej Primetime)<br>52: Skrubbning av medieström (ej Primetime)<br>53: Medieströmmen hålls vid liv (ej Primetime)<br>54: Medieström och start (ej Primetime)<br>55: Medieström och stängning (ej Primetime)<br>56: Medieström och rensning (ej Primetime)<br>60: Primetime-medieström, start<br>61: Primetime-medieström, stäng<br>62: Skrubbning av Primetime-medieström<br>63: Primetimes medieström håller sig vid liv<br>64: Primetime-medieström och start<br>65: Primetime-medieström och stäng<br>66: Primetimes medieström och rensning | Samma värde som `post_page_event` |
| Undersökning | 40: Alla samtal som genererats från undersökningen | 80: Alla samtal som genererats från undersökningen |
| Analyser för Target | 70: Träffen innehåller målaktivitetsdata | Samma värde som `post_page_event` |
