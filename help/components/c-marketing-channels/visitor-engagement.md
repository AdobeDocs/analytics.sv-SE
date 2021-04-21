---
description: Lär dig hur du anger förfallodatum för besökarengagemang i marknadsföringskanaler.
subtopic: Marketing channels
title: Utgångsdatum för marknadsföringskanal
feature: Rapporter och analysgrunder
uuid: 47f1ccaf-3ce7-494d-b456-956a3a3c6c9a
exl-id: a9df659b-3b6a-4bdb-bd77-f4490d2b7c79
translation-type: tm+mt
source-git-commit: cddf2a76ca36914f133379959b7cbb5246bdd695
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# Utgångsdatum för marknadsföringskanal

Lär dig hur du anger förfallotiden, eller besökarengagemangsperioden, för marknadsföringskanaler.

Besökarengagemanget är hur mycket tid du vill att besökarens tidigare aktivitet på webbplatsen ska tillskrivas den första beröringskanalen. Standardinställningen för förfallodatum är 30 dagar.

Om besökaren använder webbplatsen ofta följer besökarfönstret med. De måste vara inaktiva i 30 dagar för att perioden ska gå ut och kanalerna ska återställas. Både den första och sista beröringskanalen för en besökare återställs efter 30 dagars inaktivitet i den webbläsaren.

Exempel:

* Dag 1: Användaren kommer till webbplatsen på skärmen. Första och sista-beröringskanalen ställs in på Visning.
* Dag 2: Användaren kommer till webbplatsen för naturlig sökning. Första beröringen är fortfarande Visning och Sista beröringen är inställd på Naturlig sökning.
* Dag 35: Användaren har inte varit på webbplatsen på 33 dagar och återkommer med fliken som han/hon hade öppnat i sin webbläsare. Om man utgår ifrån ett 30-dagars interaktionsfönster skulle fönstret ha stängts och cookies för marknadsföringskanaler skulle ha gått ut. Den första berörings- och den sista beröringskanalen återställs och ställs in på Sessionsuppdatering sedan användaren kom från en intern URL.

## Utgångsdatum för marknadsföringskanal

Förfallotid:

| Fält | Definition |
|--- |--- |
| Inaktivitetsdagar | Antalet dagar som måste gå innan besökarens första beröringsengagemang upphör. Standardvärdet är 30. |
| Aldrig | Besökarens anställningsperiod går inte ut. |
| Återställ kanal | Förfaller alla besökares interaktionsperioder.  Om ni behöver återställa alla marknadsföringskanaldata kan ni förfalla alla besökares interaktionsperioder. Du kan behöva återställa data om bearbetningsreglerna tidigare har konfigurerats felaktigt. Alla värden för den första och sista beröringskanalen upphör omedelbart och återställs när besökarna kommer tillbaka. |

## Definiera utgångsdatum för marknadsföringskanal {#define-expiration}

Ange besökarens anställningsperiod.

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
2. I [!UICONTROL Report Suite Manager] klickar du på **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Expiration]**.

   ![](assets/mchannel_expiration.png)

3. Konfigurera fälten för besökarens interaktionsperiod.
4. Klicka på **[!UICONTROL Save.]**
