---
description: Integrationen kombinerar kraften i det integrerade systemet för feedback och beteenderapportering i Adobe Analytics, som hjälper er att skapa kraftfulla analyser och optimeringsmöjligheter för er organisation.
title: optivo® broadcast Data Connector for Adobe Analytics
uuid: bd713080-9d1a-49ee-aad0-86dd5c37c34a
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# optivo® broadcast Data Connector for Adobe Analytics{#optivo-broadmail-data-connector-for-adobe-analytics}

Integrationen kombinerar kraften i det integrerade systemet för feedback och beteenderapportering i Adobe Analytics, som hjälper er att skapa kraftfulla analyser och optimeringsmöjligheter för er organisation.

[!DNL ~Partner~] är ett professionellt program för e-postmarknadsföring. Dess huvudsakliga funktion är att skapa, skicka och utvärdera nyhetsbrev och e-postkampanjer. `[~Partner~]` finns som molntjänst (programvara som tjänst).

Integreringen erbjuder automatiserad återmarknadsföring och datasynkronisering, vilket leder till ökad konvertering och ökade intäkter. `[~Partner~]` Tack vare integreringen kan marknadsförarna synkronisera automatiska segment för sina kunder utifrån deras e-postinteraktion och webbplatsbeteende. Det automatiserade datautbytet av anpassningsbara segment hjälper er att skapa extremt målinriktade e-postkampanjer som ökar försäljningen, till exempel övergivna kundvagnar och återmarknadsföring efter köp av produkter som är både större och större.

Denna integrering utbyter också statistik om framgångsrika e-postkampanjer från `[~Partner~]` till Adobe Analytics. Viktiga data visas centralt i översikten över e-postkampanjer.

## Data Connectors Laboratory Program {#section-51f9864851b64d96873127b9ac9c9a2b}

Programmet är en snabbspårningsmetod för Adobes tredjepartspartners att bygga integreringar och leverera dem till vår gemensamma marknad. Integreringarna har utvecklats i sin helhet av våra partner och är tillgängliga via Adobe Experience Cloud enligt communitymetoder. De tillhandahålls utan extra kostnad till Adobe-kunder som har Adobe Analytics och andra lösningar och tillhandahålls i befintligt skick utan underförstådda garantier från Adobe på grund av integrationernas karaktär som tredje part.

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
* **Beteendeprofil för produkt-/innehållsvy:** Nå potentiella kunder genom marknadsföringssegment baserat på produktvisningar och profiler för innehållsåtkomst.
* **Cart Abandonment Profile:** Hjälp besökarna att konvertera till kunder med finjusterade kampanjer som är särskilt utformade för dem som tvekar att slutföra kundvagnen.
* **Effektiv återmarknadsföring:** Kunderna kan också skapa och schemalägga anpassade marknadsföringssegment som är specifika för användarnas behov.

## Innan du aktiverar{#before-you-activate}

Fyll i följande krav innan du startar integreringen av Data Connectors för :

## Krav för Adobe Analytics {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Report Suite-specifik:** Den här integreringen är specifik för rapportsviten. Kontrollera att du har valt önskat rapportpaket innan du aktiverar integreringen.
* **Tillgängliga och konfigurerade Adobe Analytics-variabler:** För den här integreringen krävs anpassade händelser och anpassade eVars-variabler.

* **Auktoriserat ombud:** Observera att aktiveringen av integreringen kan medföra att ditt företag debiteras i enlighet med ditt serviceavtal med Adobe, Inc. eller ditt serviceavtal med någon av Adobes betrodda partners, beroende på vad som är tillämpligt. Genom att aktivera integreringen intygar du härmed att du är en behörig representant för ditt företag; och som sådan går ditt företag med på att betala eventuella avgifter som anges i det serviceavtal som beskrivs ovan.
* **Meddelande-ID:** Integreringen kräver att vi hämtar och lagrar ett meddelande-ID i en Adobe Analytics-variabel (eVar). Dessa ID:n behövs för att identifiera de utskick du skickade. Som en del av konfigurationsprocessen måste du identifiera en eVar för detta när du uppmanas till det av guiden.
* **Partner:** Integreringen kräver att vi samlar in och lagrar en [!UICONTROL ~partner~] inom en Adobe Analytics-variabel (eVar). Detta ID är en kodad eller numerisk representation av en e-postadress från [!UICONTROL ~partnersystemet~] . Den här [!UICONTROL ~partnern~] är kopplad till besökares beteende längre fram i kedjan på webbplatsen (kundvagnsöverläggningar, inköp osv.) som förs in i [!UICONTROL ~Partner~] -systemet och kan utnyttjas för återmarknadsföring. Som en del av konfigurationsprocessen måste du identifiera en eVar för detta när du uppmanas till det av guiden.
* **Tid för efterklickning:** Som en del av konfigurationsprocessen kräver den här integreringen en tilldelning till en eVar som motsvarar tidpunkten för en åtgärd efter klickning. Detta behövs för att skicka information om en mottagaråtgärd till [!UICONTROL ~partnern~] när mottagaren klickat på en länk i ett utskick.

* **Produkt efter klickning:** Som en del av konfigurationsprocessen kräver den här integreringen en tilldelning till en eVar som motsvarar den erbjudna produkt som är associerad med en åtgärd efter klickning. Detta behövs för att skicka information om en mottagaråtgärd till [!UICONTROL ~partnern~] när mottagaren klickat på en länk i ett utskick.

* **Typ av åtgärd efter klickning:** Som en del av konfigurationsprocessen kräver den här integreringen en tilldelning till en eVar som motsvarar typen av en efterklickningsåtgärd. Detta behövs för att skicka information om en mottagaråtgärd till [!UICONTROL ~partnern~] när mottagaren klickat på en länk i ett utskick.

* **Integritetsefterlevnad:** Genom att aktivera spårning av mottagare eller besökar-ID kan den här funktionen spåra personligt identifierbar information om webbplatsens besökare. Detta påverkar integriteten och kräver att organisationen implementerar lämpliga procedurer, som att meddela besökarna på webbplatsen och ge dem sitt samtycke.

## Priser{#pricing}

Observera att aktiveringen av integreringen kan medföra att ditt företag debiteras i enlighet med ditt serviceavtal med Adobe, Inc. eller ditt serviceavtal med någon av Adobes betrodda partners, beroende på vad som är tillämpligt.

Genom att aktivera integreringen intygar du härmed att du är en behörig representant för ditt företag; och som sådan går ditt företag med på att betala eventuella avgifter som anges i det serviceavtal som beskrivs ovan.

### Adobe - prisöverväganden {#section-1f4f46c0d969435db57d38c1c310a05a}

Nuvarande kunder av Adobe Analytics-lösningen har inga extrakostnader kopplade till användningen av denna Data Connectors Integration. Kunder som ännu inte har bytt till den nya Adobe Analytics-produkten bör kontakta sin Adobe-kontorepresentant för mer information.

### Hänsyn till partnerpriser {#section-f8ca71df32224412a5101efb6e356529}

Den här integreringen är tillgänglig för [!DNL ~partnerkunder~] , men ytterligare integreringsavgifter tillkommer. Kontakta sales@optivo.com för närmare information om priser. Kontakta [!DNL ~partnern~] om du vill ha prisinformation.

## Adobe Analytics-variabler{#adobe-analytics-variables}

Den här integreringen kräver Adobe Analytics-variabler för att spåra mätvärden.

När du har identifierat de händelser och eVars som ska användas med den här integreringen måste de aktiveras i administrationskonsolen för Analytics (se [Rapportsviter](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) för instruktioner).
