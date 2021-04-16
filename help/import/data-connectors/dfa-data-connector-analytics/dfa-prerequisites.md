---
description: Krav för att använda DFA-dataanslutningen med Adobe Analytics.
keywords: DFA
title: Förutsättningar
feature: Data Connectors
uuid: b5f5e30c-e269-41a4-9236-5ddc404bfd94
exl-id: aa47c54f-d98a-47cb-806f-3f16d783c207
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 1%

---

# Förutsättningar{#prerequisites}

Innan du startar integreringen av DFA med Adobe Data Connectors gör du följande:

* Bestäm om du vill integrera med version 1.5 av integreringen eller vänta på version 2.0. Detta beslut är beroende av vilka funktioner som används i ditt DFA-konto och den tidsram som du vill integrera.
* Bestäm hur DFA-annonsörer ska mappa till Adobe Analytics rapporteringsprogram. Om du till exempel har flera DFA-annonsörer och flera rapportsviter måste du bestämma vilka annonsörer som ska paras med vilka rapportsviter.
* Implementera datainsamlingskoden för Adobe på alla sidor som du vill spåra med version H.22 eller senare av datainsamlingskoden.
* Lär känna Advertiser-ID:t för ett DFA-konto som är en del av den Floodlight-konfiguration som du vill integrera. Integreringen importerar automatiskt alla annonsörer som finns i Floodlight-konfigurationen.
* Lär känna ditt DFA-konto Användarnamn och lösenord.
* Koppla varje DFA-annonsör till endast en Adobe Analytics-rapportsvit. Taggning till flera rapportsviter stöds inte med standardintegreringen för Genesis för DFA.
* Lägg till en klickbar frågesträngsparameter på landningssidan för varje DFA-placering som ska ingå i integreringen. Frågesträngsparametern är nödvändig för att korrekt räkna klickningar.
* Konfigurera dina DFA-placeringar så att de inte omdirigerar besökare via flera domäner. En plats ska till exempel inte dirigera svaranden till en mikrowebbplats som finns på www.xyz.com om mikroplatsen sedan dirigerar om dem till en annan plats, www.fgh.com. Om kampanjsvaret omfattar flera domäner kan klicknings- och genomskinlighetsdata bli genererade och vilseledande.
* Identifiera en anpassad variabel i Rapporter och analyser för att lagra kampanjinformationen.
* Identifiera en Rapporter och analys-eVar för att lagra DFA-genomsiktsinformation. Använd endast den här eVar för den här DFA-integreringen.
* Identifiera de rapporter- och analyshändelser där du vill lagra exponeringar och klicka på data. Du kanske vill byta namn på händelserna.
* (Valfritt) Identifiera rapporter och analyshändelser som lagrar DFA-kostnadsdata. Du kanske vill byta namn på händelserna.
* (Valfritt) Identifiera en anpassad variabel för rapporter och analyser och en lyckad händelse som lagrar DFA-fel och tidsgränser. Dessa variabler hjälper till att diagnostisera problem som kan uppstå med integreringen.
* (Valfritt) Skapa ett särskilt e-postkonto för att ta emot information och meddelanden relaterade till integreringen av Data Connectors för DFA.
