---
description: Den här e-postintegreringen med Adobe® Data Connectors™ kombinerar beteendeinformation från Analytics® med e-postmarknadsföring för att skapa ett kraftfullt verktyg för att omdefiniera framgångsmått och inrikta er på målgrupper med mer relevanta meddelanden.
title: Emarsys Data Connector for Adobe Analytics
uuid: 6f2fbabc-dc6c-4975-887d-ec22eba42f9e
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Emarsys Data Connector for Adobe Analytics{#emarsys-data-connector-for-adobe-analytics}

Den här e-postintegreringen med Adobe® Data Connectors™ kombinerar beteendeinformation från Analytics® med e-postmarknadsföring för att skapa ett kraftfullt verktyg för att omdefiniera framgångsmått och inrikta er på målgrupper med mer relevanta meddelanden.

Leverans av relevanta e-postmeddelanden till dessa marknadssegment kan leda till helt nya intäktsmöjligheter och leda till ökad konvertering och ökade intäkter bland nya och befintliga e-postkampanjer. Att leverera relevanta e-postmeddelanden baserade på produkter som visats under ett besök eller produkter som lämnats i en övergiven kundvagn har till exempel visat sig ha en dramatisk inverkan på intäkterna, med minimal inverkan på kostnaden eftersom det bara är att dra nytta av besökare som sajten redan får.

Denna ökning av marknadsföringseffektiviteten är en av de största fördelarna med att integrera [!DNL Analytics] med datasystem. Dessutom synkroniserar den här integreringen automatiskt e-poststatistik med [!DNL Analytics] data så ofta som en timme för rapporter med slutna slingor.

## Viktiga fördelar{#key-benefits}

Viktiga fördelar med den här integreringen.

* Samla marknadsförings- och analysdata via e-post i ett enda rapporteringsgränssnitt
* Optimera e-postkampanjer genom konvertering och bidrag till intäkter och webbplatsens framgång
* Återmarknadsföring till viktiga besökare och marknadssegment baserat på dynamiska marknadsföringssegment

## Dynamiska marknadsföringssegment{#dynamic-marketing-segments}

Den här e-postintegreringen av Data Connectors stöder dynamiska marknadsföringssegment som hjälper er att utveckla verksamheten.

Den här integreringen innehåller följande marknadsföringssegment:

* **Inköpsprofiler:** Öka antalet upprepade order och det genomsnittliga ordervärdet genom kampanjer riktade mot besökares inköpsmönster.
* **Beteendeprofil för produkt-/innehållsvy:** Nå potentiella kunder genom marknadsföringssegment baserat på produktvisningar och profiler för innehållsåtkomst.
* **Cart Abandonment Profile:** Hjälp besökarna att konvertera till kunder med finjusterade kampanjer som är särskilt utformade för dem som tvekar att slutföra kundvagnen.
* Kunderna kan också skapa och schemalägga anpassade marknadsföringssegment som är specifika för användarnas behov.

## Integreringsförfarande och krav{#integration-procedure-and-prerequisites}

Med hjälp av en plug and play-guide får du stegvisa steg för steg hjälp i arbetet med att synkronisera system och initiera integreringen.

Integreringen av dessa Data Connectors kräver följande:

### Krav från Adobe {#section-bce14015fb7f41b3bc754da0eb7567bc}

* Datalager
* Adobe- [!DNL Analytics] konto
* Tillgängliga och konfigurerade [!DNL Analytics] variabler, inklusive eVars och anpassade händelser.

### Krav för partners: {#section-bcb904574ccf42308bcf7a15e45b4d58}

* Ett aktivt emarsys-konto

Instruktioner för stegvis integrering finns i [Köra integreringsguiden för Data Connectors.](/help/import/data-connectors/emarsys-overview/emarsys-wizard.md)

## Priser{#pricing}

Integreringen av dessa Data Connectors inkluderar prisöverväganden som du måste vara medveten om.

### Adobe - prisöverväganden {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Det kan finnas återkommande avgifter och implementeringsavgifter som är kopplade till den här integreringen. Kontakta din Adobe-kontorepresentant för att få prisuppgifter.

### Hänsyn till partnerpriser {#section-c6afad08c34b43e3a7a3637eea3328c3}

Det kan finnas avgifter kopplade till den här integreringen. Kontakta din relationshanterare för att få prisinformation.

## Vad du bör veta innan du aktiverar integreringen{#what-you-should-know-before-activating-this-integration}

Innan du aktiverar den här integreringen ska du granska följande objekt mot dina distributioner av Adobe Analytics och ditt e-postprogram.

På så sätt säkerställs att bästa praxis och förutsättningar finns på plats före aktiveringen, vilket ger en optimal och lyckad integrering. Granska följande information om den här integreringen av Data Connectors i relation till emarsys:

* **Giltigt emarsys-konto:** För att kunna använda e-postintegreringen för Data Connectors måste klienten ha ett giltigt e-postkonto.
* **Befintlig kund:** Integreringen kräver att du är kund till både Adobe och Mac. Om du inte redan är kund med e-postmeddelanden har du inte den information som krävs för att slutföra integreringsguiden. Om du för närvarande är kund med e-postsystem behöver du ditt konto-ID eller den unika identifierare som tilldelats din organisation för att kunna slutföra integreringsguiden.
* När du är klar med guiden för dataanslutningar kontaktar du kontohanteraren för ditt system för att aktivera integreringen i din eMarketing Suite.

### Adobe Analytics{#adobe-analytics}

Läs följande information om den här integreringen av Data Connectors när det gäller Adobe Analytics:

* **Report Suite-specifik:** Den här integreringen är specifik för rapportsviten. Kontrollera att du har valt önskat rapportpaket innan du aktiverar integreringen.
* **Auktoriserat ombud:** Observera att aktiveringen av integreringen kan medföra att ditt företag debiteras i enlighet med ditt serviceavtal med Adobe, Inc. eller ditt serviceavtal med någon av Adobes betrodda partners, beroende på vad som är tillämpligt. Genom att aktivera integreringen intygar du härmed att du är en behörig representant för ditt företag; och som sådan går ditt företag med på att betala eventuella avgifter som anges i det serviceavtal som beskrivs ovan.
* **Datalager:** Den här integreringen kräver att datalagret är aktiverat för att generera segment för återmarknadsföring. Om du inte har aktiverat datalagret kontaktar du Adobe för mer information.
* **Mottagar-ID:** Integreringen kräver att vi hämtar och lagrar ett &quot;Visitor ID&quot; i en Analytics-variabel (eVar). Besökar-ID (kallas ofta för &quot;Mottagar-ID&quot;) är en kodad eller numerisk representation av en e-postadress från e-postsystemet. Detta&quot;Mottagar-ID&quot; är kopplat till besökarbeteende längre fram i kedjan på webbplatsen (kundvagnsöverläggningar, inköp osv.) som förs in i datasystemet och kan utnyttjas för återmarknadsföring. Som en del av konfigurationsprocessen måste du identifiera en eVar för detta när du uppmanas till det av guiden.
* **Extern spårning:** Om du för närvarande inte följer den bästa metoden att aktivera extern spårning för varje e-postkampanj som du skickar måste du göra det för att integreringen ska lyckas. Mer information finns i meddelandeavsnittet nedan.
* **Integritetsefterlevnad:** Genom att aktivera spårning av mottagare eller besökar-ID kan den här funktionen spåra personligt identifierbar information om webbplatsens besökare. Detta påverkar integriteten och kräver att organisationen implementerar lämpliga procedurer, som att meddela besökarna på webbplatsen och ge dem sitt samtycke.

