---
description: Denna e-postintegrering med Adobe® Data Connectors kombinerar beteendeinformation från Adobe Analytics® med e-postmarknadsföring från Datran för att skapa ett kraftfullt verktyg för att omdefiniera framgångsmått och inrikta er på målgrupper med mer relevanta meddelanden.
title: Datran Data Connector för Adobe Analytics
uuid: f97655c4-9623-4d06-a3c6-894246eba80f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Datran Data Connector för Adobe Analytics {#datran-data-connector-for-adobe-analytics}

Denna e-postintegrering med Adobe® Data Connectors kombinerar beteendeinformation från Adobe Analytics® med e-postmarknadsföring från Datran för att skapa ett kraftfullt verktyg för att omdefiniera framgångsmått och inrikta er på målgrupper med mer relevanta meddelanden.

Leverans av relevanta e-postmeddelanden till dessa marknadssegment kan leda till helt nya intäktsmöjligheter och leda till ökad konvertering och ökade intäkter bland nya och befintliga e-postkampanjer. Att leverera relevanta e-postmeddelanden baserade på produkter som visats under ett besök eller produkter som lämnats i en övergiven kundvagn har till exempel visat sig ha en dramatisk inverkan på intäkterna, med minimal inverkan på kostnaden eftersom det bara är att dra nytta av besökare som sajten redan får. Den ökade marknadsföringseffektiviteten är en av de största fördelarna med att integrera Adobe Analytics med Dataran. Dessutom synkroniserar den här integreringen automatiskt e-poststatistik med Adobe Analytics-data så ofta som en timme för rapporter med slutna slingor.

## Viktiga fördelar{#key-benefits}

Integreringen innehåller följande viktiga fördelar:

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
* Adobe Analytics-konto
* Tillgängliga och konfigurerade Adobe Analytics-variabler, inklusive eVars och anpassade händelser.

### Förutsättningar för datan {#section-bcb904574ccf42308bcf7a15e45b4d58}

* Aktivt StormPost-konto med e-post aktiverat och aktiva inloggningsuppgifter.

Granska följande information om den här integreringen av Data Connectors när det gäller Datran:

* **Giltigt datanakonto:** För att kunna använda e-postintegreringen för Data Connectors måste klienten ha ett giltigt Datran-konto.
* **Aktuell datakund:** Integreringen kräver att du är kund till både Adobe och Datran. Om du inte redan använder Datran har du inte den information som krävs för att slutföra integreringsguiden. Om du för närvarande är kund hos Datran behöver du ditt konto-ID eller den unika identifierare som tilldelats din organisation för att kunna slutföra integreringsguiden.
* Kontakta kontohanteraren för att få anvisningar om hur du konfigurerar StormPost.

## Priser{#pricing}

Integreringen av dessa Data Connectors inkluderar prisöverväganden som du måste vara medveten om.

Följande avsnitt innehåller mer information:

### Adobe - prisöverväganden {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Det kan finnas återkommande avgifter och implementeringsavgifter som är kopplade till den här integreringen. Kontakta din Adobe-kontorepresentant för att få prisuppgifter.

### Funderna om datapriser {#section-c6afad08c34b43e3a7a3637eea3328c3}

Det kan finnas avgifter kopplade till den här integreringen.

* Skicka ett e-postmeddelande till oss med prisinformation på esp@datranmedia.com.

## Vad du bör veta innan du aktiverar integreringen{#what-you-should-know-before-activating-this-integration}

Innan du aktiverar den här integreringen ska du granska följande artiklar mot dina distributioner av Adobe Analytics® och e-postprogramvaran.

På så sätt säkerställs att bästa praxis och förutsättningar finns på plats före aktiveringen, vilket ger en optimal och lyckad integrering.

### Adobe Analytics{#adobe-analytics}

Läs följande information om den här integreringen av Data Connectors när det gäller Adobe Analytics:

* **Report Suite-specifik:** Den här integreringen är specifik för rapportsviten. Kontrollera att du har valt önskat rapportpaket innan du aktiverar integreringen.
* **Auktoriserat ombud:** Observera att aktiveringen av integreringen kan medföra att ditt företag debiteras i enlighet med ditt serviceavtal med Adobe, Inc. eller ditt serviceavtal med någon av Adobes betrodda partners, beroende på vad som är tillämpligt. Genom att aktivera integreringen intygar du härmed att du är en behörig representant för ditt företag; och som sådan går ditt företag med på att betala eventuella avgifter som anges i det serviceavtal som beskrivs ovan.
* **Omniture Data Warehouse™:** Den här integreringen kräver att datalagret är aktiverat för att generera segment för återmarknadsföring. Om du inte har aktiverat datalagret kontaktar du Adobe för mer information.
* **Mottagar-ID:** Integreringen kräver att vi hämtar och lagrar ett besökar-ID i en Adobe Analytics-variabel (eVar). Besökar-ID (kallas ofta för &quot;Mottagar-ID&quot;) är en kodad eller numerisk representation av en e-postadress från Datran-systemet. Detta&quot;Mottagar-ID&quot; är kopplat till besökarbeteende längre fram i kedjan på webbplatsen (kundvagnsöverläggningar, inköp osv.) som förs in i datasystemet och kan utnyttjas för återmarknadsföring. Som en del av konfigurationsprocessen måste du identifiera en eVar för detta när du uppmanas till det av guiden.
* **Extern spårning:** Om du för närvarande inte följer den bästa metoden att aktivera extern spårning för varje e-postkampanj som du skickar måste du göra det för att integreringen ska lyckas. Mer information finns i datasektionen nedan.
* **Integritetsefterlevnad:** Genom att aktivera spårning av mottagare eller besökar-ID kan den här funktionen spåra personligt identifierbar information om webbplatsens besökare. Detta påverkar integriteten och kräver att organisationen implementerar lämpliga procedurer, som att meddela besökarna på webbplatsen och ge dem sitt samtycke.
