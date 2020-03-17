---
description: Innan du aktiverar den här integreringen ska du granska följande artiklar mot dina distributioner av Adobe Analytics® och e-postprogramvaran.
title: Innan du aktiverar den här integreringen
uuid: b911edc6-2265-48ed-9e3c-c79cc20dd9b2
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Innan du aktiverar den här integreringen{#before-you-activate-this-integration}

Innan du aktiverar den här integreringen ska du granska följande artiklar mot dina distributioner av Adobe Analytics® och e-postprogramvaran.

På så sätt säkerställs att bästa praxis och förutsättningar finns på plats före aktiveringen, vilket ger en optimal och lyckad integrering.

## Adobe Analytics{#adobe-analytics}

Läs följande information om den här integreringen av Data Connectors när det gäller Adobe Analytics:

* **Report Suite-specifik:** Den här integreringen är specifik för rapportsviten. Kontrollera att du har valt önskat rapportpaket innan du aktiverar integreringen.
* **Tillgängliga och konfigurerade analysvariabler:** Denna integrering kräver 5 anpassade händelser och 2 anpassade eVars, samt 3 ytterligare händelser och 3 ytterligare eVars (valfritt). Se [Analytics-integreringsvariabler](/help/import/data-connectors/silverpop-overview/silverpop-variables.md).

* **Auktoriserat ombud:** Observera att aktiveringen av integreringen kan medföra att ditt företag debiteras i enlighet med ditt serviceavtal med Adobe, Inc. eller ditt serviceavtal med någon av Adobes betrodda partners, beroende på vad som är tillämpligt. Genom att aktivera integreringen intygar du härmed att du är en behörig representant för ditt företag; och som sådan går ditt företag med på att betala eventuella avgifter som anges i det serviceavtal som beskrivs ovan.
* **Datalager™:** Den här integreringen kräver att datalagret är aktiverat för att generera segment för återmarknadsföring. Om du inte har aktiverat datalagret kontaktar du Adobe för mer information.
* **Mottagar-ID:** Integreringen kräver att vi hämtar och lagrar ett &quot;Visitor ID&quot; i en Analytics-variabel (eVar). Besökar-ID (kallas ofta för &quot;Mottagar-ID&quot;) är en kodad eller numerisk representation av en e-postadress från Silverpop-systemet. Detta&quot;Mottagar-ID&quot; är kopplat till besökarbeteende längre fram i kedjan på webbplatsen (kundvagnsöverläggningar, inköp osv.) som förs in i Silverpop-systemet och kan utnyttjas för återmarknadsföring. Som en del av konfigurationsprocessen måste du identifiera en eVar för detta när du uppmanas till det av guiden.
* **Extern spårning:** Om du för närvarande inte följer den bästa metoden att aktivera extern spårning för varje e-postkampanj som du skickar måste du göra det för att integreringen ska lyckas. Mer information finns i Silverpop-avsnittet nedan.
* **Integritetsefterlevnad:** Genom att aktivera spårning av mottagare eller besökar-ID kan den här funktionen spåra personligt identifierbar information om webbplatsens besökare. Detta påverkar integriteten och kräver att organisationen implementerar lämpliga procedurer, som att meddela besökarna på webbplatsen och ge dem sitt samtycke.

## Integrering av Silverpop Data Connector{#silverpop-data-connector-integration}

Granska följande information om den här integreringen av Data Connector i relation till Silverpop:

* **Giltigt Silverpop-konto:** Om du vill använda e-postintegreringen för Data Connectors måste klienten ha ett aktivt Silverpop-konto med e-post aktiverat och aktiva användarautentiseringsuppgifter.
* **Kontakta din Silverpop-representant**. Den här integreringen aktiveras inte automatiskt av Silverpop. Du måste kontakta din Silverpop-representant för att starta Silverpop-konfigurationen innan data importeras eller exporteras från Analytics.

> [!NOTE] Den här integreringen fungerar endast med engagerande organisationer (inte Transact).

## Priser{#pricing}

Integreringen av dessa Data Connectors inkluderar prisöverväganden som du måste ta hänsyn till innan aktiveringen.

### Adobe - prisöverväganden {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Det kan finnas återkommande avgifter och implementeringsavgifter som är kopplade till den här integreringen. Kontakta din Adobe-kontorepresentant för att få prisuppgifter.

### Hänsyn till partnerpriser {#section-c6afad08c34b43e3a7a3637eea3328c3}

Det kan finnas avgifter kopplade till den här integreringen. Kontakta din relationshanterare för att få prisinformation.
