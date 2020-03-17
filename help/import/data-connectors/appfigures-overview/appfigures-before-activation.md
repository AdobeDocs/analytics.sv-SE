---
description: Innan du aktiverar den här integreringen ska du granska följande artiklar mot dina distributioner av Adobe Analytics® och e-postprogramvaran.
title: Innan du aktiverar den här integreringen
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Innan du aktiverar den här integreringen {#before-you-activate-this-integration}

Innan du aktiverar den här integreringen ska du granska följande artiklar mot dina distributioner av Adobe Analytics® och e-postprogramvaran.

På så sätt säkerställs att bästa praxis eller krav finns innan aktiveringen, vilket ger en optimal och framgångsrik integrering.

## Krav för Adobe Analytics{#adobe-analytics-requirements}

Läs följande information om integreringen av dessa dataanslutningar i relation till Adobe Analytics:

* **Report-Suite-specifik:** Observera att den här integreringen är specifik för rapportsviten. Kontrollera att du har valt önskat rapportpaket innan du aktiverar integreringen och att rapportsviten innehåller data.
* **Tillgängliga och konfigurerade analysvariabler:** Den här integreringen kräver 10 anpassade händelser och 1 anpassad eVar. Se [Analytics-integreringsvariabler](appfigures-before-activation.md#analytics-integration-variables).

* **Report Suite initierad med Live-data:** Om du skapar en helt ny rapportserie för den här integreringen måste den ha fått vissa (minst en träff) data via kraven för live tracking appFigures. Om livedata inte har registrerats kan rapportsviten inte ta emot integrerade App Store-data.

* **Befintlig integrering med App Store:** Den här integreringen fyller i data i 13 månader. Om du vill undvika överlappning med någon tidigare app store-dataleverantör som du har kan du kontakta din appFigures-representant. Informera dem om det senaste datumet du tog emot data. appFigures justerar bakåtfyllnadsperioden i enlighet med detta.

## appFigures-krav{#appfigures-requirements}

Granska följande information om den här integreringen av dataanslutningar i relation till appFigures:

* **Aktuell appFigurer:** Den här integreringen kräver att du är användare av både Adobe och appFigures. Om du för närvarande inte är användare av programmetFigures Enterprise Plan har du inte den information som krävs för att slutföra integreringsguiden. Besök appFigures på webben för mer information.
* **appFigures-kontonyckel:** En appFigures-kontonyckel krävs för att aktivera appFigures-datakopplingen. Den här kontonyckeln kan genereras i avsnittet Tillägg. Mer information finns i [Konfigurera integreringen](../appfigures-overview/t-appfigures-integration.md) .

* **Datainsamling**: Information om nedladdning, försäljning och rankning synkroniseras varje dag för de senaste 7 dagarna. Efter 7 dagar betraktas data som slutgiltiga och uppdateras inte längre.

## Priser{#pricing}

Den här integreringen av dataanslutningar inkluderar prisöverväganden som du måste vara medveten om.

Följande avsnitt innehåller mer information:

### Adobe - prisöverväganden {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Det finns för närvarande inga avgifter som kan användas för den här integreringen. Du kan dock se en liten ökning av antalet serveranrop på grund av att datakällorna har importerats.

### appFigures - prisöverväganden {#section-c6afad08c34b43e3a7a3637eea3328c3}

Det finns för närvarande inga avgifter kopplade till den här integreringen. Den här integreringen är för närvarande bara tillgänglig för Enterprise-kunder. Kontakta [appFigures](https://appfigures.com/support/contact) om du vill ha mer information.

## Analytics-integrationsvariabler{#analytics-integration-variables}

Dataanslutningsintegrationen för appFigures använder Analytics-variabler för att spåra olika appFigures-mått.

I följande tabell beskrivs de Analytics-variabler som aktiveras automatiskt för appillustrationsintegreringen.

### Obligatoriska variabler {#section-3ca8dc46bab0436cba0c9ef827c8356a}

> [!NOTE] Den här integreringen använder dedikerade variabler för appbutiksdata, så du behöver inte tilldela anpassade handelsvariabler och händelser.

| Variabeltyp | Namn | Populationsmetod | Beskrivning |
|---|---|---|---|
| eVar | Objekt-ID för App Store | Importerad från appFigures. | Konfigurera den här eVar-instansen med förfallodatum för besök, senaste allokering och grundläggande underrelationer. |
| händelse (numerisk) | App Store-nedladdningar | Importerad från appFigures. | Antalet nedladdningar av mobilprogram. |
| händelse (numerisk) | App Store-inköp (i app) | Importerad från appFigures. | Antalet köp och prenumerationer i appen. |
| händelse (numerisk) | Rankning för App Store | Importerad från appFigures. | Används för att definiera det genomsnittliga beräknade måttet appFigures. Används inte direkt. |
| händelse (numerisk) | Rangordning för App Store | Importerad från appFigures. | Används för att definiera det genomsnittliga beräknade måttet appFigures. Används inte direkt. |
| händelse (numerisk) | App Store-klassificering | Importerad från appFigures. | Används för att definiera det genomsnittliga beräknade måttet appFigures. Används inte direkt. |
| händelse (numerisk) | Klassificeringsdivisor för App Store | Importerad från appFigures. | Används för att definiera det genomsnittliga beräknade måttet appFigures. Används inte direkt. |
| händelse (valuta) | App Store-intäkter (i app) | Importerad från appFigures. | Intäkter inifrån appen minus butiksavgiften. |
| händelse (valuta) | App Store-intäkter (en av) | Importerad från appFigures. | Totala intäkter från appinköp minus butiksavgiften. |
| händelse (valuta) | App Store Royalty (i app) | Importerad från appFigures. | Används inte |
| händelse (valuta) | App Store Royalty (en av) | Importerad från appFigures. | Används inte |
