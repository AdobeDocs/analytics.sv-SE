---
description: Integreringen av Data Connectors för Silverpop använder Analytics-variabler för att spåra olika Silverpop-mått.
title: Variabler för Analytics-integrering
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
exl-id: 0b8b31f5-65a8-41e0-97d1-d75fb1b91f62
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 4%

---

# Variabler för Analytics-integrering{#analytics-integration-variables}

Integreringen av Data Connectors för Silverpop använder Analytics-variabler för att spåra olika Silverpop-mått.

När du har identifierat de händelser och eVars som ska användas med Silverpop-integreringen kan du aktivera dem med Adobe Analytics Admin Console (se [Report Suites](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html)).

I följande tabell beskrivs de Analytics-variabler som behövs för Silverpop-integreringen.

## Obligatoriska variabler {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| Variabeltyp | Namn | Populationsmetod | Beskrivning |
|---|---|---|---|
| händelse (numerisk) | Studsar | Automatiskt importerad från Silverpop. | Med Bounces-händelsen kan du se antalet e-postmeddelanden som inte har levererats till mottagarna på grund av ett leveransproblem. |
| händelse (numerisk) | Klickningar | Automatiskt importerad från Silverpop. | Med händelsen Klickat kan du se antalet besökare som klickade på e-postmeddelandet. |
| händelse (numerisk) | Öppnar | Automatiskt importerad från Silverpop. | Med händelsen Öppnad kan du se antalet besökare som öppnade e-postmeddelandet. |
| händelse (numerisk) | Skickar | Automatiskt importerad från Silverpop. | Med händelsen Skicka kan du se hur många e-postmeddelanden som har skickats. |
| händelse (numerisk) | Avbeställ | Automatiskt importerad från Silverpop. | Med händelsen Avbeställ kan du se hur många besökare som har öppnat e-postmeddelandet men sedan klickat på länken Avbeställ för att avanmäla dig från framtida e-postmeddelanden från din organisation. |
| eVar | Silverpop-ID/besökar-ID | Samlas in från frågeparametrar i e-postlänkar via den automatiserade samlingsmetoden eller ett JavaScript-plugin-program. | Unikt besökar-ID |
| eVar eller s.campaign | Utskicks-ID | Samlas in från frågeparametrar i e-postlänkar via den automatiserade samlingsmetoden eller ett JavaScript-plugin-program. | Detta lagras ofta i kampanjvariabeln. |

## Valfria variabler {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| Variabeltyp | Namn | Populationsmetod | Beskrivning |
|---|---|---|---|
| händelse (räknare) | Filen har hämtats | Manuellt insamlade via Analytics-taggar. | Händelsen används för att identifiera användare som har laddat ned en fil på platsen. |
| händelse (räknare) | Formuläret har startats | Manuellt insamlade via Analytics-taggar. | Form Started används för att identifiera användare som påbörjar ett formulär, men som inte fyller i det. |
| händelse (räknare) | Formuläret har fyllts i | Manuellt insamlade via Analytics-taggar. | Formuläret Slutfört används för att identifiera besökare som påbörjar ett formulär och inte fyller i det. |
| eVar | E-postadress | Manuellt insamlade via Analytics-taggar. | E-postadressen används för att manuellt samla in e-postadressen på registreringssidor, inloggningssidor eller andra sidor som e-postadressen samlas in på. Den här variabeln används för att återmarknadsföra till användare som har valt att ta emot e-post, men som kanske inte har klickat via ett e-postmeddelande tidigare. |
| eVar | Hämtad fil | Manuellt insamlade via Analytics-taggar. | Hämtad fil identifierar vilken fil en besökare har laddat ned. |
| eVar | Formulärnamn | Manuellt insamlade via Analytics-taggar. | Formulärnamn identifierar vilket formulär en besökare överger. |
