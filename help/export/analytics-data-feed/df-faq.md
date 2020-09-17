---
description: Vanliga frågor och svar om dataflöden
keywords: Data Feed;job;pre column;post column;case sensitivity
title: Vanliga frågor om dataflöden
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---


# Vanliga frågor om dataflöden

Vanliga frågor och svar om dataflöden.

## Vad är skillnaden mellan kolumner med ett `post_` prefix och kolumner utan ett `post_` prefix?

Kolumner utan prefixet innehåller data exakt som de skickades till datainsamlingen. `post_` Kolumner med ett `post_` prefix innehåller värdet efter bearbetningen. Exempel som kan ändra ett värde är variabelbeständighet, bearbetningsregler, VISTA-regler, valutakonvertering eller annan logik på serversidan som gäller Adobe. Adobe rekommenderar att du använder `post_` versionen av en kolumn där det är möjligt.

Om en kolumn inte innehåller någon `post_` version (till exempel `visit_num`) kan kolumnen betraktas som en postkolumn.

## Hur hanterar dataflöden skiftlägeskänslighet?

I Adobe Analytics betraktas de flesta variabler som skiftlägeskänsliga i rapporteringssyfte. Till exempel betraktas alla&quot;snö&quot;,&quot;snö&quot;,&quot;snö&quot; och&quot;sNow&quot; som samma värde. Skiftlägeskänsligheten bevaras i dataflöden.

Om du ser olika skiftlägesvariationer av samma värde mellan icke-post- och postkolumner (till exempel&quot;snö&quot; i pre-kolumnen och&quot;Snö&quot; i post-kolumnen), använder implementeringen både versaler och gemener på webbplatsen. Skiftlägesvariationen i postkolumnen överfördes tidigare och lagras i den virtuella cookien, eller bearbetades samtidigt för rapportsviten.

## Filtreras robotar av administratörskonsolens robotregler i dataflöden?

Dataflöden inkluderar inte botar som filtrerats av administratörskonsolens [robotregler](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Varför ser jag flera `000` värden i `event_list` - eller `post_event_list` dataflödeskolumnen?

Vissa kalkylbladsredigerare, särskilt Microsoft Excel, rundar automatiskt av mycket stora tal. Kolumnen innehåller många kommaavgränsade tal, vilket ibland kan göra att Excel hanterar den som ett stort antal. `event_list` Det avrundar de sista siffrorna till `000`.

Adobe rekommenderar att du inte öppnar `hit_data.tsv` filer i Microsoft Excel automatiskt. Använd i stället Excel-dialogrutan Importera data och se till att alla fält behandlas som text.
