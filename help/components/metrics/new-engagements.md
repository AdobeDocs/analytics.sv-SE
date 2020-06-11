---
title: Nya åtaganden
description: Antalet gånger som en första beröringskanal ställs in.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# Nya åtaganden

Måttet&quot;Nytt engagemang&quot; visar hur många gånger en besökare matchar en marknadsföringskanal för första gången i besökarens engagemangsperiod. Det här måttet är användbart när du vill jämföra en dimension med en besökare som för första gången matchar en bearbetningsregel för en marknadsföringskanal.

## Hur det här måttet beräknas

Under databearbetningen körs varje träff genom regler [för bearbetning av](../c-marketing-channels/c-rules.md)marknadsföringskanaler. Om en träff matchar någon regel för hantering av marknadsföringskanaler och besökaren inte redan har en första beröringskanal är träffen ett nytt engagemang. Om en träff inte matchar några regler för bearbetning av marknadsföringskanaler eller om besökaren redan har en första beröringskanal är träffen inte något nytt engagemang.

Besökarna kan ha mer än ett nytt engagemang om de låter besökarnas engagemang löpa ut.