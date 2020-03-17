---
description: 'null'
keywords: DFA
title: Förutsättningar
topic: Data connectors
uuid: b5f5e30c-e269-41a4-9236-5ddc404bfd94
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Förutsättningar{#prerequisites}

Innan du startar Adobe Data Connectors-integreringen för DFA gör du följande:

* Bestäm om du vill integrera med version 1.5 av integreringen eller vänta på version 2.0. Detta beslut är beroende av vilka funktioner som används i ditt DFA-konto och den tidsram som du vill integrera.
* Bestäm hur DFA-annonsörer ska mappa till rapportsviter i Adobe Analytics. Om du till exempel har flera DFA-annonsörer och flera rapportsviter måste du bestämma vilka annonsörer som ska paras med vilka rapportsviter.
* Implementera koden för datainsamling från Adobe på alla sidor som du vill spåra med version H.22 eller senare av koden för datainsamling.
* Lär känna Advertiser-ID:t för ett DFA-konto som är en del av den Floodlight-konfiguration som du vill integrera. Integreringen importerar automatiskt alla annonsörer som finns i Floodlight-konfigurationen.
* Lär känna ditt DFA-konto Användarnamn och lösenord.
* Associera varje DFA Advertiser med endast en rapportserie från Adobe Analytics. Taggning till flera rapportsviter stöds inte med standardintegreringen Genesis för DFA.
* Lägg till en klickbar frågesträngsparameter på landningssidan för varje DFA-placering som ska ingå i integreringen. Frågesträngsparametern är nödvändig för att korrekt räkna klickningar.
* Konfigurera dina DFA-placeringar så att de inte omdirigerar besökare via flera domäner. En plats ska till exempel inte dirigera svaranden till en mikrowebbplats som finns på www.xyz.com om mikroplatsen sedan dirigerar om dem till en annan plats, www.fgh.com. Om kampanjsvaret omfattar flera domäner kan klicknings- och genomskinlighetsdata bli genererade och vilseledande.
* Identifiera en anpassad variabel i Rapporter och analyser för att lagra kampanjinformationen.
* Identifiera rapporter och analyser eVar för att lagra DFA-genomsiktsinformation. Använd endast den här eVar för den här DFA-integreringen.
* Identifiera de rapporter- och analyshändelser där du vill lagra exponeringar och klicka på data. Du kanske vill byta namn på händelserna.
* (Valfritt) Identifiera rapporter och analyshändelser som lagrar DFA-kostnadsdata. Du kanske vill byta namn på händelserna.
* (Valfritt) Identifiera en anpassad variabel för rapporter och analyser och en lyckad händelse som lagrar DFA-fel och tidsgränser. Dessa variabler hjälper till att diagnostisera problem som kan uppstå med integreringen.
* (Valfritt) Skapa ett särskilt e-postkonto för att ta emot information och meddelanden relaterade till integreringen av Data Connectors för DFA.

