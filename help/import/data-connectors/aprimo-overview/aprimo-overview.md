---
description: Denna e-postintegrering med Adobe® Data Connectors™ kombinerar beteendeinformation från Adobe Analytics® med e-postmarknadsföring för att skapa ett kraftfullt verktyg för att omdefiniera framgångsmått och inrikta er på målgrupper med mer relevanta meddelanden.
title: Aprimo Data Connector för Adobe Analytics
uuid: 590ded4b-b250-43b4-9cec-68508b853e00
exl-id: cd5191c9-68fb-42ad-98f6-23d5a72878da
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 1%

---

# Aprimo Data Connector för Adobe Analytics{#aprimo-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>Adobe Data Connector-tekniken upphör den 1 augusti 2021. [Läs mer …](/help/import/data-connectors/data-connectors-eol.md)

Denna e-postintegrering med Adobe® Data Connectors™ kombinerar beteendeinformation från Adobe Analytics® med e-postmarknadsföring för att skapa ett kraftfullt verktyg för att omdefiniera framgångsmått och inrikta er på målgrupper med mer relevanta meddelanden.

Leverans av relevanta e-postmeddelanden till dessa marknadssegment kan leda till helt nya intäktsmöjligheter och leda till ökad konvertering och ökade intäkter bland nya och befintliga e-postkampanjer. Att leverera relevanta e-postmeddelanden baserade på produkter som visats under ett besök eller produkter som lämnats i en övergiven kundvagn har till exempel visat sig ha en dramatisk inverkan på intäkterna, med minimal inverkan på kostnaden eftersom det bara är att dra nytta av besökare som sajten redan får.

Denna ökning av marknadsföringseffektiviteten är en av de största fördelarna med att integrera [!DNL Adobe Analytics] med April. Dessutom synkroniserar den här integreringen automatiskt e-poststatistik med [!DNL Adobe Analytics]-data så ofta som timvis för rapporter med slutna slingor.

## Viktiga fördelar och funktioner{#key-benefits-and-features}

Integreringen innehåller följande viktiga fördelar:

* Samla marknadsförings- och analysdata via e-post i ett enda rapporteringsgränssnitt.
* Optimera e-postkampanjer genom konvertering och bidrag till intäkter och webbplatsens framgång.
* Återmarknadsför till viktiga besökare och marknadssegment baserat på dynamiska marknadsföringssegment.

## Dynamiska marknadsföringssegment{#dynamic-marketing-segments}

Integrationen omfattar följande dynamiska marknadsföringssegment:

* **Inköpsprofiler:** Öka antalet upprepade order och det genomsnittliga ordervärdet genom kampanjer riktade mot besökares inköpsmönster.
* **Beteendeprofil för produkt-/innehållsvy:** Nå potentiella kunder genom marknadsföringssegment baserat på produktvyer och profiler för innehållsåtkomst.
* **Cart Abandonment Profile:** Hjälp besökarna att konvertera till kunder med finjusterade kampanjer som är särskilt utformade för dem som tvekar att slutföra kundvagnen.
* Kunderna kan också skapa och schemalägga anpassade marknadsföringssegment som är specifika för användarnas behov.

## Innan du aktiverar{#before-you-activate}

Innan du startar integreringen av Data Connectors för ska du uppfylla följande krav:

### Adobe Analytics-krav {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Report Suite-specifik:** Var uppmärksam på att den här integreringen är rapportsvitsspecifik. Kontrollera att du har valt önskat rapportpaket innan du aktiverar integreringen.
* **Tillgängliga och konfigurerade Adobe Analytics-variabler:** Den här integreringen kräver anpassade händelser och anpassade eVars samt eventuellt ytterligare händelser och ytterligare eVars-variabler.
* **Auktoriserad representant:** Observera att aktiveringen av integreringen kan medföra att ditt företag debiteras i enlighet med ditt serviceavtal med Adobe, Inc. eller ditt serviceavtal med någon av Adobe tillförlitliga partners, beroende på vad som är tillämpligt. Genom att aktivera integreringen intygar du härmed att du är en behörig representant för ditt företag; och som sådan går ditt företag med på att betala eventuella avgifter som anges i det serviceavtal som beskrivs ovan.
* **data warehouse™:** Den här integreringen kräver att Data warehouse är aktiverat för att återmarknadsföringssegment ska kunna genereras. Om du inte har aktiverat Data warehouse kontaktar du Adobe för mer information.
* **[!UICONTROL Partner~]:** Integreringen kräver att vi hämtar och lagrar en  [!DNL ~partner~] inom en Adobe Analytics-variabel (eVar). Detta ID är en kodad eller numerisk representation av en e-postadress från systemet [!DNL ~Partner~]. Denna &quot; [!DNL ~partner~]&quot; är kopplad till besökarbeteenden längre fram i kedjan på webbplatsen (kundvagnsöverläggningar, inköp osv.) som hämtas till [!DNL ~Partner~]-systemet och kan utnyttjas för återmarknadsföring. Som en del av konfigurationsprocessen måste du identifiera en eVar för detta när du uppmanas till det av guiden.
* **Extern spårning:** Om du för närvarande inte följer den bästa metoden att aktivera extern spårning för varje e-postkampanj du skickar måste du göra det för att integreringen ska lyckas. Mer information finns i avsnittet [!DNL ~Partner~] nedan.
* **Integritetsefterlevnad:** Du bör förstå att den här funktionen kan spåra personlig identifierbar information om webbplatsens besökare genom att aktivera spårning av mottagare eller besökar-ID. Detta påverkar integriteten och kräver att organisationen implementerar lämpliga procedurer, som att meddela besökarna på webbplatsen och ge dem sitt samtycke.

## Priser{#pricing}

Observera att aktiveringen av den här integreringen kan medföra att ditt företag debiteras i enlighet med ditt serviceavtal med Adobe, Inc. eller ditt serviceavtal med någon av Adobe tillförlitliga partners, beroende på vad som är tillämpligt.

Genom att aktivera integreringen intygar du härmed att du är en behörig representant för ditt företag; och som sådan går ditt företag med på att betala eventuella avgifter som anges i det serviceavtal som beskrivs ovan.

### Prisöverväganden för Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Det kan finnas återkommande kostnader och implementeringskostnader som är kopplade till den här integreringen, inklusive kostnader för ett ökat antal serversamtal som uppstår genom den här integreringen. Kontakta din kontorepresentant på Adobe för att få prisuppgifter.

### ~Funderna ~ om partnerpriser  {#section-f8ca71df32224412a5101efb6e356529}

Det kan finnas återkommande avgifter och implementeringsavgifter som är kopplade till den här integreringen. Kontakta [!DNL ~Partner~] för prisinformation.

## Adobe Analytics Variables{#adobe-analytics-variables}

Den här integreringen kräver Adobe Analytics-variabler för att spåra mätvärden.

När du har identifierat de händelser och eVars som ska användas med den här integreringen måste de vara aktiverade i Adobe Analytics Admin Console (mer information finns i [Report Suites](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html)).
