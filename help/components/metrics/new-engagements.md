---
title: Nya åtaganden
description: Antalet gånger som en första beröringskanal ställs in.
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Nya åtaganden

Det nya engagemanget [mått](overview.md) visar hur många gånger en besökare matchar en marknadsföringskanal för första gången i besökarens interaktionsperiod. Det här måttet är användbart när du vill jämföra en dimension med en besökare som för första gången matchar en bearbetningsregel för en marknadsföringskanal.

## Hur det här måttet beräknas

Under databearbetningen körs varje träff genom [Bearbetningsregler för marknadsföringskanaler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md). Om en träff matchar någon regel för hantering av marknadsföringskanaler och besökaren inte redan har en första beröringskanal är träffen ett nytt engagemang. Om en träff inte matchar några regler för bearbetning av marknadsföringskanaler eller om besökaren redan har en första beröringskanal är träffen inte något nytt engagemang.

Besökarna kan ha mer än ett nytt engagemang om de låter besökarnas anställningsperiod löpa ut.
