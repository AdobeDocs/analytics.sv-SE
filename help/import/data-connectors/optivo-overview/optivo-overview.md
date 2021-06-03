---
description: Integrationen kombinerar styrkan i det integrerade systemet för feedback och beteenderapportering från Adobe Analytics, som hjälper er att skapa kraftfulla analyser och optimeringsmöjligheter för er organisation.
title: optivo® broadcast Data Connector for Adobe Analytics
uuid: bd713080-9d1a-49ee-aad0-86dd5c37c34a
exl-id: fff63047-afa6-420d-9188-ec8ebe407a46
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 0%

---

# optivo® broadcast Data Connector for Adobe Analytics{#optivo-broadmail-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>Adobe Data Connector-tekniken upphör den 1 augusti 2021. [Läs mer …](/help/import/data-connectors/data-connectors-eol.md)

Integrationen kombinerar styrkan i det integrerade systemet för feedback och beteenderapportering från Adobe Analytics, som hjälper er att skapa kraftfulla analyser och optimeringsmöjligheter för er organisation.

[!DNL ~Partner är ett professionellt ~] program för e-postmarknadsföring. Dess huvudsakliga funktion är att skapa, skicka och utvärdera nyhetsbrev och e-postkampanjer. `[~Partner~]` finns som molntjänst (programvara som tjänst).

Integreringen `[~Partner~]` erbjuder automatiserad återmarknadsföring och datasynkronisering, vilket leder till ökad konvertering och ökade intäkter. Tack vare integreringen kan marknadsförarna synkronisera automatiska segment för sina kunder utifrån deras e-postinteraktion och webbplatsbeteende. Det automatiserade datautbytet av anpassningsbara segment hjälper er att skapa extremt målinriktade e-postkampanjer som ökar försäljningen, till exempel övergivna kundvagnar och återmarknadsföring efter köp av produkter som är både större och större.

Den här integreringen utbyter också statistik om lyckade e-postkampanjer från `[~Partner~]` till Adobe Analytics. Viktiga data visas centralt i översikten över e-postkampanjer.

## Data Connectors Laboratory Program {#section-51f9864851b64d96873127b9ac9c9a2b}

Det här programmet är en snabb metod för Adobe tredjepartspartners att bygga integreringar och leverera dem till vår gemensamma marknad. Integreringarna är helt utvecklade av våra partner och görs tillgängliga på Adobe Experience Cloud enligt våra communitymetoder. De tillhandahålls utan extra kostnad till Adobe-kunder i Adobe Analytics och andra lösningar och tillhandahålls i befintligt skick utan underförstådda garantier från Adobe på grund av integrationernas karaktär som tredje part.

Kontakta din kontoansvarige på Adobe om du har frågor om din aktuella service, garanti eller licensiering.

## Viktiga fördelar och funktioner{#key-benefits-and-features}

Integreringen innehåller följande viktiga fördelar:

* Återuppta kunder som surfar och överger
* Öka försäljningen med riktad korsförsäljning och merförsäljning
* Automatiska segmentbaserade kampanjer
* Optimerade pågående kampanjer
* Segment i [!DNL ~Partner~] för riktad återmarknadsföring
* Mätuppdateringar för konstant kampanj
* Automatiska konversationsutlösare

## Dynamiska marknadsföringssegment{#dynamic-marketing-segments}

Integrationen omfattar följande dynamiska marknadsföringssegment:

* **Inköpsprofiler:** Öka antalet upprepade order och det genomsnittliga ordervärdet genom kampanjer riktade mot besökares inköpsmönster.
* **Beteendeprofil för produkt-/innehållsvy:** Nå potentiella kunder genom marknadsföringssegment baserat på produktvyer och profiler för innehållsåtkomst.
* **Cart Abandonment Profile:** Hjälp besökarna att konvertera till kunder med finjusterade kampanjer som är särskilt utformade för dem som tvekar att slutföra kundvagnen.
* **Effektiv marknadsföring:** Kunderna kan också skapa och schemalägga anpassade marknadsföringssegment som är specifika för deras användarbehov.

## Innan du aktiverar{#before-you-activate}

Innan du startar integreringen av Data Connectors för ska du uppfylla följande krav:

## Adobe Analytics-krav {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Report Suite-specifik:** Var uppmärksam på att den här integreringen är rapportsvitsspecifik. Kontrollera att du har valt önskat rapportpaket innan du aktiverar integreringen.
* **Tillgängliga och konfigurerade Adobe Analytics-variabler:** Integreringen kräver anpassade händelser och anpassade eVars-variabler.

* **Auktoriserad representant:** Observera att aktiveringen av integreringen kan medföra att ditt företag debiteras i enlighet med ditt serviceavtal med Adobe, Inc. eller ditt serviceavtal med någon av Adobe tillförlitliga partners, beroende på vad som är tillämpligt. Genom att aktivera integreringen intygar du härmed att du är en behörig representant för ditt företag; och som sådan går ditt företag med på att betala eventuella avgifter som anges i det serviceavtal som beskrivs ovan.
* **Meddelande-ID:** Integreringen kräver att vi hämtar och lagrar ett meddelande-ID inom en Adobe Analytics-variabel (eVar). Dessa ID:n behövs för att identifiera de utskick du skickade. Som en del av konfigurationsprocessen måste du identifiera en eVar för detta när du uppmanas till det av guiden.
* **Partner:** Integreringen kräver att vi samlar in och lagrar ett  [!UICONTROL ~~] partnerskap inom en Adobe Analytics-variabel (eVar). Detta ID är en kodad eller numerisk representation av en e-postadress från systemet [!UICONTROL ~Partner~]. Denna [!UICONTROL ~partner~] är kopplad till besökares beteende längre fram i kedjan på webbplatsen (kundvagnsöverläggningar, inköp osv.) som hämtas till [!UICONTROL ~Partner~]-systemet och kan utnyttjas för återmarknadsföring. Som en del av konfigurationsprocessen måste du identifiera en eVar för detta när du uppmanas till det av guiden.
* **Tid efter klickning:** Som en del av konfigurationsprocessen kräver den här integreringen en tilldelning till en eVar som motsvarar tidpunkten för en postklicksåtgärd. Detta krävs för att överföra information om en mottagaråtgärd till [!UICONTROL ~Partner~] efter att mottagaren klickat på en länk i ett e-postmeddelande.

* **Produkt efter klickning:** Som en del av konfigurationsprocessen kräver den här integreringen en tilldelning till en eVar som motsvarar den erbjudna produkten som är kopplad till en åtgärd efter klickning. Detta krävs för att överföra information om en mottagaråtgärd till [!UICONTROL ~Partner~] efter att mottagaren klickat på en länk i ett e-postmeddelande.

* **Åtgärdstyp efter klickning:** Som en del av konfigurationsprocessen kräver den här integreringen en tilldelning till en eVar som motsvarar typen av åtgärd efter klickning. Detta krävs för att överföra information om en mottagaråtgärd till [!UICONTROL ~Partner~] efter att mottagaren klickat på en länk i ett e-postmeddelande.

* **Integritetsefterlevnad:** Du bör förstå att den här funktionen kan spåra personlig identifierbar information om webbplatsens besökare genom att aktivera spårning av mottagare eller besökar-ID. Detta påverkar integriteten och kräver att organisationen implementerar lämpliga procedurer, som att meddela besökarna på webbplatsen och ge dem sitt samtycke.

## Priser{#pricing}

Observera att aktiveringen av den här integreringen kan medföra att ditt företag debiteras i enlighet med ditt serviceavtal med Adobe, Inc. eller ditt serviceavtal med någon av Adobe tillförlitliga partners, beroende på vad som är tillämpligt.

Genom att aktivera integreringen intygar du härmed att du är en behörig representant för ditt företag; och som sådan går ditt företag med på att betala eventuella avgifter som anges i det serviceavtal som beskrivs ovan.

### Prisöverväganden för Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Nuvarande kunder av Adobe Analytics-lösningen har inga extrakostnader kopplade till användningen av denna Data Connectors Integration. Kunder som ännu inte flyttat till den nya Adobe Analytics-produkten bör kontakta sin kontorepresentant på Adobe för mer information.

### Hänsyn till partnerpriser {#section-f8ca71df32224412a5101efb6e356529}

Integrationen är tillgänglig för [!DNL ~Partner~]-kunder, men ytterligare integreringsavgifter tillkommer. Kontakta sales@optivo.com för närmare information om priser. Kontakta [!DNL ~Partner~] för prisinformation.

## Adobe Analytics Variables{#adobe-analytics-variables}

Den här integreringen kräver Adobe Analytics-variabler för att spåra mätvärden.

När du har identifierat de händelser och eVars som ska användas med den här integreringen måste de aktiveras i Analytics-Admin Console (mer information finns i [Report Suites](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html)).
