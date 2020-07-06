---
description: 'När Data Connectors DFA-integreringen har aktiverats ger den följande mätvärden för dina Adobe Analytics-rapporter '
keywords: DFA
title: Integreringsfunktioner
topic: Data connectors
uuid: 4ad8e6e8-3449-498a-8596-37c0ac1657cd
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 1%

---


# Integreringsfunktioner{#integration-features}

När Data Connectors DFA-integreringen har aktiverats ger den följande mätvärden för dina Adobe Analytics-rapporter:

* Genomgångar
* DFA-klick
* Impressions
* (valfritt) DFA-kostnadsdata
* (valfritt) DFA-frågefel, timeout

>[!NOTE]
>
>Den här integreringen har inte stöd för klickningsspårare (tidigare klickningskommandon). Klickspårare används för att registrera antalet klick på textlänkar, länkar i e-postmeddelanden eller på andra element som är hårdkodade på en webbplats.

DFA-integreringen för Data Connectors skapar automatiskt DFA-spårningskoder från data som returneras av DFA. Dessa spårningskoder är utformade för att unikt identifiera en annons tillsammans med tillhörande placering och kreativ. Följande visar strukturen för spårningskoden, beroende på version av integreringen. Version 1.5 ser ut så här:

![](assets/DFA_id_struct1_5.png)

Version 2.0 ser ut så här:

![](assets/DFA_id_struct2.png)

Dessa ID:n fungerar som en delad nyckel mellan Genesis och DFA för att associera korrekta klassificeringar och mätvärden.

| Plats-ID | Den webbplats från tredje part där annonsen var värd. Klassificeringen Platsnamn innehåller ett beskrivande namn för det här plats-ID:t. |
|---|---|
| Annons-ID | Ett ID för det kommersiella meddelande som levereras till en användare. Ad Name-klassificeringen innehåller annonsens namn enligt din organisations definition i DFA-systemet. Exempel: `Hybrid Coup Textlink - Build`. |
| Placement-ID | En representation på ditt DFA-konto för en webbplats, del av en webbplats eller grupp av webbplatser där du har köpt annonsutrymme. |
| Kreativt ID | Bilden, Flash SWF eller annan resurs som ska visas för besökaren. Klassen Creative Name innehåller det namn du angett för den här kreativa personen i DFA-gränssnittet. |

De andra två klassificeringarna, Delivery Tool (DoubleClick for Advertisers) och Channel (Banner Ad), har samma värden för alla DFA-kampanjer och hjälper till att skilja på DFA-importerade data.

## Avduplicering av SearchCenter {#section-f809b3bb5e5142aa8ff89bcd5f0d0e49}

DFA-integreringen är nu Adobe SearchCenter-medveten. Genom att aktivera borttagning av dubbletter i SearchCenter via guiden Data Connectors kommer sökdrivna besökare inte att få data att hämtas från DFA:s Floodlight Server och *`s.campaign`* fylls inte i av DFA, vilket gör att SearchCenter kan fylla i dem. DFA och SearchCenter fyller nu i dedupliceringsvärden i variablerna för varje produkt.

I listan nedan beskrivs logiken som aktiveras när borttagning av dubbletter i SearchCenter är aktiverad:

Om **[!UICONTROL DFA]** > **[!UICONTROL SearchCenter deduplication]** är valt i guiden:

* Vid en DFA-klickning fylls strängen&quot;DFA Clickthrough&quot; i av integreringen till den konfigurerade SCM eVar.
* Om det är en DFA-vy fyller integreringen i strängen &quot;DFA Viewthrough&quot; till SCM eVar.

Om **[!UICONTROL SearchCenter]** > **[!UICONTROL DFA deduplication]** är valt i guiden:

* Om det är en DFA-vy fyller integreringen i strängen &quot;DFA Viewthrough&quot; till SCM eVar.

>[!NOTE]
>
>Om SearchCenter > DFA deduplicering är aktiverat och frågesträngsparametern SearchCenter är inställd, kommer besöket inte att användas för DFA-bearbetning. Det innebär att frågesträngsparametern SearchCenter ska skilja sig från DFA-klickningsparametern och att inga visningsannonser ska ange frågesträngsparametern SearchCenter.

