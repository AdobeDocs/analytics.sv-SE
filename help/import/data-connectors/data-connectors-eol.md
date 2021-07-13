---
description: Läs om när och varför Analytics-dataanslutningar upphör.
title: Förannonsering i slutet av livscykeln för Analytics-dataanslutningar
exl-id: b407675a-9fcf-4f24-bc88-69ccdb5b3658
source-git-commit: 5238ea3393deb6bc1089460b44b46a8e5cd7ffd0
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 8%

---

# Slutet av livscykeln för Adobe-dataanslutningar

I över ett decennium har Adobe Analytics siktat på att tillhandahålla den bästa lösningen för webb- och marknadsföringsanalys som uppfyller kundernas behov. I takt med att teknologi- och affärsbehoven utvecklas strävar vi efter att kontinuerligt leverera och uppfylla de högsta standarderna.  Tyvärr uppfyller de API:er som stöder den här integreringen inte längre dessa standarder och kan inte användas i den moderna Adobe Analytics-teknikinfrastrukturen.

**Från och med den 1 augusti 2021** har Adobe för avsikt att upphöra med integreringar av dataanslutningar. Slutet av livscykeln är en del av en teknikprodukts livscykel och Adobe vill göra övergången så smidig som möjligt för våra kunder och partners. Många av dessa integreringar är tillgängliga via Adobe Exchange och kan fortsätta att användas.

## Varför upphör den här funktionen?

Den här funktionen drivs av äldre teknik som inte längre är användbar eller stöds. Vi har en ny standard i [Adobe Exchange Partner Program](https://partners.adobe.com/exchangeprogram/experiencecloud), som bör implementeras för alla integreringar som ska användas och stödjas framöver.

## Hur påverkar borttagningen av den här funktionen dig?

Om du är Adobe-partner hittar du [information här](https://adobeexchangeec.zendesk.com/hc/en-us/articles/360003867071-Adobe-Analytics-Integration-Tools) i vår dokumentation om hur du migrerar din integrering till vårt nya Adobe Exchange-program.

Om du är en Data Connector-kund och vill begära att den integrering du använder ska migreras, ska du *dirigera alla begäranden direkt till integreringspartnern*. Att skicka en begäran till Adobe via kundtjänst ger inte samma resultat.

Alla företag som erbjuder en integrering fick möjlighet att migrera sin integrering till Adobe Exchange eller avbryta integreringen. Nedan följer en sammanfattning av varje aktuell integration och deras tillhörande beslut.

Om du har ytterligare frågor eller support kan du kontakta Adobe kundtjänst.

## Status för Data Connector-partner

| Partner | Status |
| --- | --- |
| Acxiom | Undertryckt |
| Anpassa | Undertryckt |
| Justera | Migrerar till Adobe Exchange |
| Adobe Campaign | Migrera till Adobe Exchange (se anm. nedan) |
| Använder | Migrerar till Adobe Exchange |
| Appen | Undertryckt |
| AppsFlyer | Migrerar till Adobe Exchange |
| aprimo Enterprise Marketing Engagement | Undertryckt |
| Apteligent | Undertryckt |
| BlueHornet eMarketing Suite | Undertryckt |
| Gren | Migrerar till Exchange |
| BrightEdge 2.0, BrightEdge, BrightEdge Express | Undertryckt |
| Bronto Software | Undertryckt |
| CheetahMail av Experian | Migrerar till Exchange |
| ClickTale | Undertryckt |
| Klickbar certifikatutfärdare | Undertryckt |
| Konduktor 2.0, konduktor, konduktor, organisk statistik | Undertryckt |
| ContactLab 2.0 (Contact Send Connector) | Undertryckt |
| Coradiant TrueSight | Undertryckt |
| D&amp;B Visitor Intelligence | Undertryckt |
| Datran Media | Undertryckt |
| Decibel Insight | Undertryckt |
| Decipher | Undertryckt |
| Delivra | Undertryckt |
| Demandbase CA | Undertryckt |
| Demandbase v3 | Undertryckt |
| DialogTech | Finns på Adobe Exchange |
| [DoubleClick for Advertisers (DFA)](/help/import/data-connectors/dfa-data-connector-analytics/dfa-eol.md) | Undertryckt |
| DREAM | Undertryckt |
| DREAMmail 1.0, DREAMmail 2.0 | Undertryckt |
| Dynamisk signal (Nital Vora) | Migrerar till Exchange |
| eDialog Precision Central | Undertryckt |
| eC-messenger | Undertryckt |
| Emailvision Campaign Commander | Undertryckt |
| emarsys xpress | Undertryckt |
| Epsilon Harmony | Migrerar till Exchange |
| AllaSociala för Adobe Analytics | Undertryckt |
| ExactTarget, ExactTarget 2.0 | Undertryckt |
| Fiksu | Undertryckt |
| Foresee (v2.0), Foresee Feedback, Foresee Results | Undertryckt |
| Gigya | Undertryckt |
| Hootsuite | Undertryckt |
| hybris | Undertryckt |
| Kampyle (nu Medallia) Feedback Analytics (1.1) | Undertryckt |
| Listrak | Migrerar till Exchange |
| Lyris HQ | Undertryckt |
| MaritzCX (V 2.0) | Undertryckt |
| Merkle | Undertryckt |
| Oraclets officiella Eloqua-integrering | Migrerar till Exchange |
| optivo broadmail (Episerver) | Undertryckt |
| Qualtrics v2 | Migrerar till Exchange |
| Responsys 1.0, Responsys 2.0 | Undertryckt |
| Salesforce.com | Undertryckt |
| Selligent | Undertryckt |
| seoClarity, seoClarity 2.0 | Undertryckt |
| Silverpop Engage (v2.0) | Undertryckt |
| Sizmek | Undertryckt |
| SmartFOCUS Digital | Undertryckt |
| SpotEffects | Undertryckt |
| StrongMail Systems, Inc | Undertryckt |
| Syngeri!360 | Undertryckt |
| ThinData EMS | Undertryckt |
| TUNE | Undertryckt |
| Stads flygbolag | Undertryckt |
| Verktyget UserZoom Survey | Undertryckt |
| WhatCounts Email | Undertryckt |
| wywy | Undertryckt |
| Yesmail Enterprise | Undertryckt |
| Zeta Interactive | Undertryckt |

## Undantag: Adobe Campaign Classic

ETT undantag till datumet 1 augusti 2021 är Adobe Campaign Classic-integreringen. Denna integrering kommer officiellt att bli inaktuell den 1 mars 2022.

Den 1 augusti 2021 kommer Adobe Campaign Classic att tas bort från användargränssnittet för Data Connectors tillsammans med alla andra integreringar. Befintliga Campaign-integreringar kommer dock att fortsätta att samla in och skicka data till Adobe Analytics fram till den 1 mars 2022. Den 1 mars 2022 upphör integreringen att samla in och skicka uppgifter till Adobe Analytics. Om ni använder den här integreringen måste ni gå över till den nya anslutningen för Campaign-Analytics före den 1 mars 2022. Läs mer i [Adobe Campaign Classic-dokumentation](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/aa-connector-migration.html).