---
title: Bästa praxis för attribuering
description: Vilka är de bästa sätten att fatta beslut om en attribueringsmodell?
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 0%

---

# Bästa praxis för attribuering

Hur ni väljer rätt attribueringsmodell för er organisation beror på ett antal överväganden. I den här artikeln utforskas en metod och några allmänna bästa metoder.

## Steg 1: Experimentell analys

>[!NOTE]
>Denna analys måste ske innan du väljer en attribueringsmodell.

Den här fasen består till att börja med av att förstå kundbeteende och definiera konverteringsmått. Baserat på konverteringsstatistik kan verktyg som [Dataflöden](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=sv-SE) (för rådata) eller Analysis Workspace underlätta din förståelse av

* Antalet kunder som rör olika marknadsföringskanaler innan de konverterar
* Andelen/fördelningen av dessa beteenden

Om 50 % av kunderna till exempel rör tre kanaler innan de konverterar, finns det någon interaktion mellan dessa tre kanaler?
Sedan kan ni göra analyser både internt och externt för att öka er förståelse.

### Övre trattanalys

Analyskanaler med övergripande trattteknik används för att skapa varumärkes- eller produktmedvetenhet. Målet för de flesta TV-annonser är till exempel varumärkesmedvetenhet. Du kan använda attribueringsmodellen [&quot;Time Decay&quot; ](/help/analyze/analysis-workspace/attribution/models.md), eftersom folk kommer att glömma bort din TV-annons över tiden.

### Nedre trattanalys

I en analys med liten marginal antas att folk redan känner till ert varumärke och att ni vill att de ska konvertera. Använd e-post, push-meddelanden eller Facebook-annonser.

## Steg 2: Regelbaserad attribuering

Syftet med det här steget är att validera dina hypoteser.

**Exempel 1**

Anta att din hypotes är:&quot;Min Första-beröringskanal har större effekt på konverteringen än min sista beröringskanal.&quot;

I det här fallet använder du den [&quot;omvända J-formade&quot; attribueringsmodellen ](/help/analyze/analysis-workspace/attribution/models.md) för att testa hypotesen. Den här modellen ger 60 % av äran till den första beröringspunkten.

**Exempel 2**

Anta att din hypotes är:&quot;I vår bransch (t.ex. resebranschen) är attribueringsfönstret 60 eller 90 dagar, inte 30 dagar, eftersom kunderna gör en hel del efterforskningar innan de köper en produkt.&quot;

I det här fallet ändrar du [uppslagsfönstret](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=sv-SE#lookback-windows) till 90 dagar.

## Steg 3: Använd algoritmisk attribuering

Om du ännu inte har någon attribueringsmodell som ger tillfredsställande svar på alla dina frågor kan du använda [algoritmisk attribuering](/help/analyze/analysis-workspace/attribution/algorithmic.md). Eftersom det är mycket svårt att validera ett stort antal möjliga hypoteser och kombinationer använder algoritmisk attribuering inbyggda algoritmer för att allokera krediter mellan dimensionsposter.

## Andra överväganden

* Du kan behöva använda en datavetare istället för att förlita dig på Analysis Workspace.
* Du kan förlita dig på rådata, som i dataflöden från Adobe.
* Du kan till exempel använda [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=sv-SE) om du vill ta hänsyn till dina Impressions-data.
