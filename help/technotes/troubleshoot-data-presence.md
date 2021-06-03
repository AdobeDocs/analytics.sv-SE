---
title: Felsöka datatillgänglighet
description: Lär dig vilka steg du kan ta när du inte ser data i rapporter.
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---


# Felsöka datatillgänglighet

I Analysis Workspace returnerar vissa projektinställningar noll rader. I Rapporter och analyser visas följande meddelande när du visar vissa rapporter:

**&quot;Det finns inga data för de valda villkoren.&quot;**

Följ de här stegen för att avgöra varför en rapport inte visar data.

## Data finns men har filtrerats bort

Rapportsviten innehåller data, men de specifika komponenter som används i rapporten filtrerar bort alla data.

* **Segment**: Segment kan enkelt förhindra att alla data visas i en rapport. Kontrollera alla segmentdefinitioner och ta bort alla segment för att se om ett segment gör att dina data inte visas.
* **Mätvärden**: Kontrollera att rätt mätvärden används. Ändra måttet till [förekomster](/help/components/metrics/occurrences.md) för att kontrollera att måttet inte är rapportören till en rapport utan data.
* **Datumintervall**: Datumintervallet är för långt tidigare eller så returneras inga data i framtiden. Din organisations [datalagringspolicy](data-retention.md) avgör hur långt tillbaka data behålls.
* **Filter**: Ta bort alla sökfilter från rapporten.

## Data finns inte

Om det inte finns några segment är mätvärdet förekomster, datumintervallet är den aktuella månaden och det inte finns några sökfilter, kontrollera följande:

* **Verifiera rapportsviten**: Se till att du har en rapportserie som innehåller data. Många organisationer har nya rapportsviter, testsviter och utvecklingsrapportsviter som vanligtvis inte innehåller så mycket data.
* **Latens**: Om du visar senaste data kan det bero på att data bara är fördröjda. Mer information finns i [Latens](latency.md).
* **Validera datainsamling**: Navigera till den webbegenskap som rapportsviten ska spåra och öppna felsökningsprogrammet för  [Adobe](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html). Kontrollera att det finns en förfrågan om Analytics-bild när du läser in en sida. Om du ser en bildbegäran måste du se till att den använder rätt ID för rapportsviten, att den innehåller en giltig [currencyCode](/help/implement/vars/config-vars/currencycode.md) och att [stöd för tidsstämpling](/help/implement/vars/page-vars/timestamp.md) matchar bildbegäran och rapportsviten.
