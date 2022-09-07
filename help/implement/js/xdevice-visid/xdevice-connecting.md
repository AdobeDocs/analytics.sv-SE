---
description: Identifiering av besökare på olika enheter hjälper er att koppla samman besökare på olika enheter. Identifiering av besökare på olika enheter använder variabeln besökar-ID, s.visitorID, för att associera en användare på olika enheter.
keywords: Implementering av analyser
subtopic: Visitors
title: Koppla samman användare på olika enheter
feature: Implementation Basics
exl-id: dfe278db-01de-4bba-b07a-66d52de1dbe2
source-git-commit: be913fb9bae7954864b180490364c275c7bf7f15
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# Koppla samman användare på olika enheter

>[!IMPORTANT]
>
>Den här metoden för att identifiera besökare på olika enheter rekommenderas inte längre. Se [Enhetsövergripande analys](/help/components/cda/overview.md) i användarhandboken för komponenter.

Identifiering av besökare på olika enheter hjälper er att koppla samman besökare på olika enheter. Identifiering av besökare på olika enheter använder `visitorID` variabel för att associera en användare mellan olika enheter. The `visitorID` variabeln har högsta prioritet när unika besökare identifieras.

När du skickar en träff med ett anpassat besökar-ID söker Adobe efter besökarprofiler som har ett matchande besökar-ID. Om det finns en sådan används den besökarprofil som redan finns i systemet från och med den punkten och den tidigare besökarprofilen används inte längre.

Ange `visitorID` variabeln ställs vanligtvis in efter autentisering eller efter att en besökare utför någon annan åtgärd som gör att du kan identifiera dem unikt oberoende av den enhet som används. Effektiva identifierare innehåller ett hash-värde av användarnamn, e-postadress eller ett internt ID som inte innehåller någon personligt identifierbar information.

När kunden har loggat in från varje enhet är de alla knutna till samma användarprofil. Om besökaren loggar ut senare på en enhet fortsätter de att tillhöra samma besökarprofil eftersom Adobe känner igen att webbläsarens cookie på varje enhet tillhör samma besökarprofil. Adobe rekommenderar att du använder `visitorID` variabel när det är möjligt om webbläsarens cookie tas bort.

## Begränsningar

Genom att använda egna besökar-ID:n får du större kontroll över hur besökare identifieras, men det har sina begränsningar.

* **Avduplicering av besökare är inte retroaktiv**: Om en besökare öppnar er webbplats för första gången autentiseras, räknas två unika besökare. En unik besökare räknas automatiskt för det generiska analys-ID:t och en annan räknas för det anpassade besökar-ID:t när de loggar in. Den här dupliceringen av unika besökare förekommer varje gång en besökare använder en ny enhet eller rensar sina cookies.
* **Inkompatibelt med Experience Cloud ID-tjänsten**: Sedan introduktionen av besöksidentifiering på olika enheter har Adobe släppt kraftfullare och mer tillförlitliga sätt att spåra besökare på olika enheter. Dessa nya identifieringsmetoder är inte kompatibla med åsidosättningen av det anpassade besökar-ID:t. Om du tänker använda ID-tjänsten eller CDA (Cross-Device Analytics) rekommenderar Adobe starkt att du inte använder `visitorID` variabel.
