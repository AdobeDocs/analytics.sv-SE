---
description: Vanliga frågor och svar om dataflöden
keywords: Datautmatning;jobb;förkolumn;efterkolumn;skiftlägeskänslighet
title: Vanliga frågor om dataflöden
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
translation-type: tm+mt
source-git-commit: c6d4095fdf86be52c7921aed84b9229ac3b27f82
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# Vanliga frågor om dataflöden

Vanliga frågor och svar om dataflöden.

## Vad är skillnaden mellan kolumner med ett `post_`-prefix och kolumner utan ett `post_`-prefix?

Kolumner utan prefixet `post_` innehåller data exakt som de skickades till datainsamlingen. Kolumner med ett `post_`-prefix innehåller värdet efter bearbetning. Exempel som kan ändra ett värde är variabelbeständighet, bearbetningsregler, VISTA-regler, valutakonvertering eller annan logik på serversidan som gäller Adobe. Adobe rekommenderar att du använder `post_`-versionen av en kolumn där det är möjligt.

Om en kolumn inte innehåller en `post_`-version (till exempel `visit_num`) kan kolumnen betraktas som en postkolumn.

## Hur hanterar dataflöden skiftlägeskänslighet?

I Adobe Analytics betraktas de flesta variabler som skiftlägeskänsliga i rapporteringssyfte. Till exempel betraktas alla&quot;snö&quot;,&quot;snö&quot;,&quot;snö&quot; och&quot;sNow&quot; som samma värde. Skiftlägeskänsligheten bevaras i dataflöden.

Om du ser olika skiftlägesvariationer av samma värde mellan icke-post- och postkolumner (till exempel&quot;snö&quot; i pre-kolumnen och&quot;Snö&quot; i post-kolumnen), använder implementeringen både versaler och gemener på webbplatsen. Skiftlägesvariationen i postkolumnen överfördes tidigare och lagras i den virtuella cookien, eller bearbetades samtidigt för rapportsviten.

## Filtreras robotar av administratörskonsolens robotregler i dataflöden?

Dataflöden inkluderar inte botar som filtrerats av [administratörskonsolens robotregler](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Varför ser jag flera `000`-värden i `event_list`- eller `post_event_list`-dataflödeskolumnen?

Vissa kalkylbladsredigerare, särskilt Microsoft Excel, rundar automatiskt av mycket stora tal. Kolumnen `event_list` innehåller många kommaavgränsade tal, vilket ibland kan göra att Excel hanterar den som ett stort antal. Det avrundar de sista siffrorna till `000`.

Adobe rekommenderar att du inte öppnar `hit_data.tsv`-filer automatiskt i Microsoft Excel. Använd i stället Excel-dialogrutan Importera data och se till att alla fält behandlas som text.

## Varför kan jag inte extrahera&quot;timvisa&quot; filer från data som är mer än 7 dagar gamla?

För data som är äldre än 7 dagar kombineras en dags&quot;timvisa&quot;-filer till en enda&quot;daglig&quot; fil.

Exempel: En ny datafeed skapas den 9 mars 2021 och informationen från 1 januari 2021 till 9 mars levereras som &quot;Varje timme&quot;. Filerna&quot;Varje timme&quot; före 2 mars 2021 kombineras dock i en enda&quot;daglig&quot; fil. Du kan bara extrahera&quot;timvisa&quot; filer från data som är mindre än 7 dagar gamla från det datum då de skapades. I detta fall från den 2 mars till den 9 mars.
