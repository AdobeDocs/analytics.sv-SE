---
description: Vanliga frågor och svar om dataflöden
keywords: Data Feed;job;pre column;post column;case sensitivity
title: Vanliga frågor om dataflöden
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Vanliga frågor om dataflöden

Vanliga frågor och svar om dataflöden.

## Vad är skillnaden mellan kolumner med ett `post_` prefix och kolumner utan ett `post_` prefix?

Kolumner utan prefixet innehåller data exakt som de skickades till datainsamlingen. `post_` Kolumner med ett `post_` prefix innehåller värdet efter bearbetningen. Exempel som kan ändra ett värde är variabelbeständighet, bearbetningsregler, VISTA-regler, valutakonvertering eller annan serverlogik som Adobe tillämpar. Adobe rekommenderar att du använder `post_` versionen av en kolumn där det är möjligt.

Om en kolumn inte innehåller någon `post_` version (till exempel `visit_num`) kan kolumnen betraktas som en postkolumn.

## Hur hanterar dataflöden skiftlägeskänslighet?

I Adobe Analytics betraktas de flesta variabler som skiftlägeskänsliga i rapporteringssyfte. Till exempel betraktas alla&quot;snö&quot;,&quot;snö&quot;,&quot;snö&quot; och&quot;sNow&quot; som samma värde. Skiftlägeskänsligheten bevaras i dataflöden.

Om du ser olika skiftlägesvariationer av samma värde mellan icke-post- och postkolumner (till exempel&quot;snö&quot; i pre-kolumnen och&quot;Snö&quot; i post-kolumnen), använder implementeringen både versaler och gemener på webbplatsen. Skiftlägesvariationen i postkolumnen överfördes tidigare och lagras i den virtuella cookien, eller bearbetades samtidigt för rapportsviten.