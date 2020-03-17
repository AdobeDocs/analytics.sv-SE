---
description: Denna e-postintegrering med Adobe® Data Connectors™ kombinerar beteendeinformation från Analytics® med e-postmarknadsföring för att skapa ett kraftfullt verktyg för att omdefiniera framgångsmått och inrikta er på målgrupper med mer relevanta meddelanden.
title: DreamMail Data Connector for Adobe Analytics
uuid: f6c01bf8-4e6a-4163-9d41-f24fb5f06bdc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# DreamMail Data Connector for Adobe Analytics{#dreammail-data-connector-for-adobe-analytics}

Denna e-postintegrering med Adobe® Data Connectors™ kombinerar beteendeinformation från Analytics® med e-postmarknadsföring för att skapa ett kraftfullt verktyg för att omdefiniera framgångsmått och inrikta er på målgrupper med mer relevanta meddelanden.

Leverans av relevanta e-postmeddelanden till dessa marknadssegment kan leda till helt nya intäktsmöjligheter och leda till ökad konvertering och ökade intäkter bland nya och befintliga e-postkampanjer. Att leverera relevanta e-postmeddelanden baserade på produkter som visats under ett besök eller produkter som lämnats i en övergiven kundvagn har till exempel visat sig ha en dramatisk inverkan på intäkterna, med minimal inverkan på kostnaden eftersom det bara är att dra nytta av besökare som sajten redan får.

Den här ökningen av marknadsföringseffektiviteten är en av de största fördelarna med att integrera [!DNL Analytics] med [!DNL ~Partner~]. Dessutom synkroniserar den här integreringen automatiskt e-poststatistik med [!DNL Analytics] data så ofta som en timme för rapporter med slutna slingor.

## Viktiga fördelar och funktioner{#key-benefits-and-features}

Integreringen innehåller följande viktiga fördelar:

* Samla marknadsförings- och analysdata via e-post i ett enda rapporteringsgränssnitt.
* Optimera e-postkampanjer genom konvertering och bidrag till intäkter och webbplatsens framgång.
* Återmarknadsför till viktiga besökare och marknadssegment baserat på dynamiska marknadsföringssegment.

## Dynamiska marknadsföringssegment{#dynamic-marketing-segments}

Integrationen omfattar följande dynamiska marknadsföringssegment:

* **Inköpsprofiler:** Öka antalet upprepade order och det genomsnittliga ordervärdet genom kampanjer riktade mot besökares inköpsmönster.
* **Beteendeprofil för produkt-/innehållsvy:** Nå potentiella kunder genom marknadsföringssegment baserat på produktvisningar och profiler för innehållsåtkomst.
* **Cart Abandonment Profile:** Hjälp besökarna att konvertera till kunder med finjusterade kampanjer som är särskilt utformade för dem som tvekar att slutföra kundvagnen.
* Kunderna kan också skapa och schemalägga anpassade marknadsföringssegment som är specifika för användarnas behov.

## Innan du aktiverar{#before-you-activate}

Fyll i följande krav innan du startar integreringen av Data Connectors för :

## Krav för Adobe Analytics {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Report Suite-specifik:** Den här integreringen är specifik för rapportsviten. Kontrollera att du har valt önskat rapportpaket innan du aktiverar integreringen.
* **Tillgängliga och konfigurerade analysvariabler:** Den här integreringen kräver anpassade händelser och anpassade eVars-variabler, samt eventuellt ytterligare händelser och ytterligare eVars-variabler.

* **Auktoriserat ombud:** Observera att aktiveringen av integreringen kan medföra att ditt företag debiteras i enlighet med ditt serviceavtal med Adobe, Inc. eller ditt serviceavtal med någon av Adobes betrodda partners, beroende på vad som är tillämpligt. Genom att aktivera integreringen intygar du härmed att du är en behörig representant för ditt företag; och som sådan går ditt företag med på att betala eventuella avgifter som anges i det serviceavtal som beskrivs ovan.
* **Datalager™:** Den här integreringen kräver att datalagret är aktiverat för att generera segment för återmarknadsföring. Om du inte har aktiverat datalager kontaktar du Adobe för mer information.
* **[!DNL ~Partner~]:**Integreringen kräver att vi hämtar och lagrar en e-postadress inom en Analytics-variabel (eVar). &quot;[!DNL ~Partner~]&quot; är kopplad till besökares beteende längre fram i kedjan på webbplatsen (kundvagnsöverläggningar, inköp osv.) som förs in i[!DNL ~Partner~]-systemet och kan utnyttjas för återmarknadsföring. Som en del av konfigurationsprocessen måste du identifiera en eVar för detta när du uppmanas till det av guiden.
* **Extern spårning:** Om du för närvarande inte följer den bästa metoden att aktivera extern spårning för varje e-postkampanj som du skickar måste du göra det för att integreringen ska lyckas. Mer information finns i avsnittet [!DNL ~Partner~] nedan.
* **Integritetsefterlevnad:** Genom att aktivera spårning av mottagare eller besökar-ID kan den här funktionen spåra personligt identifierbar information om webbplatsens besökare. Detta påverkar integriteten och kräver att organisationen implementerar lämpliga procedurer, som att meddela besökarna på webbplatsen och ge dem sitt samtycke.

## Priser{#pricing}

Observera att aktiveringen av integreringen kan medföra att ditt företag debiteras i enlighet med ditt serviceavtal med Adobe, Inc. eller ditt serviceavtal med någon av Adobes betrodda partners, beroende på vad som är tillämpligt.

Genom att aktivera integreringen intygar du härmed att du är en behörig representant för ditt företag; och som sådan går ditt företag med på att betala eventuella avgifter som anges i det serviceavtal som beskrivs ovan.

### Adobe - prisöverväganden {#section-1f4f46c0d969435db57d38c1c310a05a}

Det kan finnas återkommande kostnader och implementeringskostnader som är kopplade till den här integreringen, inklusive kostnader för ett ökat antal serversamtal som uppstår genom den här integreringen. Kontakta din Adobe-kontorepresentant för att få prisuppgifter.

### ~Överväganden~ om partnerpriser {#section-f8ca71df32224412a5101efb6e356529}

Det kan finnas återkommande avgifter och implementeringsavgifter som är kopplade till den här integreringen. Kontakta Adobe [!DNL DreamMail] för närmare prisuppgifter.

## Analytics-integrationsvariabler{#analytics-integration-variables}

Den här integreringen kräver analysvariabler för att spåra mätvärden.

När du har identifierat de händelser och eVars som ska användas med den här integreringen måste de aktiveras i administrationskonsolen för Analytics (se [Rapportsviter](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) för instruktioner).
