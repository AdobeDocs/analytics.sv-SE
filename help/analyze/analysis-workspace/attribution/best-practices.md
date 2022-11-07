---
title: Bästa praxis för attribuering
description: Vilka är de bästa sätten att fatta beslut om en attribueringsmodell?
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# Bästa praxis för attribuering

Hur ni väljer rätt attribueringsmodell för er organisation beror på ett antal överväganden. I den här artikeln utforskas en metod och några allmänna bästa metoder.

## Steg 1: Experimentell analys

>[!NOTE]
>Denna analys måste ske innan du väljer en attribueringsmodell.

Den här fasen består till att börja med av att förstå kundbeteende och definiera konverteringsmått. Baserat på konverteringsstatistik kan verktyg som [Dataflöden](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html) (för rådata) eller Analysis Workspace underlättar för dig att förstå

* Hur många kunder tar sig an olika marknadsföringskanaler innan de konverterar?
* Andelen/fördelningen av dessa beteenden.

Om 50 % av kunderna till exempel rör tre kanaler innan de konverterar, finns det någon interaktion mellan dessa tre kanaler?
Sedan kan ni göra analyser både internt och externt för att öka er förståelse.

### Övre trattanalys

Analyser av de vanligaste kanalerna som används för att skapa varumärkes- eller produktmedvetenhet. Målet för de flesta TV-annonser är till exempel varumärkesmedvetenhet. Du kan använda [&quot;Time Decay&quot;-attribueringsmodell](/help/analyze/analysis-workspace/attribution/models.md), eftersom folk kommer att glömma bort din TV-annons över tiden.

### Nedre trattanalys

I den här analysen antas att folk redan känner till ert varumärke och att ni vill att de ska konvertera. Använd e-post- eller push-meddelanden eller Facebook-annonser.

## Steg 2: Regelbaserad attribuering

Syftet med det här steget är att validera dina hypoteser.

**Exempel 1**

Låt oss säga att din hypotes är &quot;Min första-beröringskanal har större effekt på konverteringen än min sista-beröringskanal. Då använder du [&quot;Omvänd J-formad&quot; attribueringsmodell](/help/analyze/analysis-workspace/attribution/models.md) för att testa hypotesen. Den här modellen ger 60 % av äran till den första beröringspunkten.

**Exempel 2**

Din hypotes kan vara: &quot;I vår bransch (t.ex. resebranschen) är attribueringsfönstret 60 eller 90 dagar, inte 30 dagar, eftersom kunderna gör mycket efterforskningar innan de köper en produkt. Du skulle då ändra din [uppslagsfönster](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html#lookback-windows) till 90 dagar.

## Steg 3: Använd algoritmisk attribuering

Eftersom det är mycket svårt att validera ett stort antal möjliga hypoteser och kombinationer kan du använda [algoritmisk attribuering](/help/analyze/analysis-workspace/attribution/algorithmic.md) för att lämna detta arbete åt inbyggda algoritmer. Om du redan har hittat den perfekta attribueringsmodellen som besvarar alla dina frågor och är perfekt, behöver du naturligtvis inte ta det här steget.

## Andra överväganden

* Du kan behöva använda en datavetare istället för att förlita dig på Analysis Workspace.
* Du kan förlita dig på rådata, som i dataflöden från Adobe.
* Överväg att använda [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html)om du till exempel vill ta hänsyn till dina Impressions-data.
