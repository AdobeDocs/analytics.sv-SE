---
description: Identifiering av besökare på olika enheter hjälper er att koppla samman besökare på olika enheter. Identifiering av besökare på olika enheter använder variabeln besökar-ID, s.visitorID, för att associera en användare på olika enheter.
keywords: Analytics Implementation
subtopic: Visitors
title: Koppla samman användare på olika enheter
topic: Developer and implementation
uuid: 6243957b-5cc1-49ef-aa94-5b5ec4eac313
translation-type: tm+mt
source-git-commit: 0439440e10dddf8a5d64e4ea8f9868b521e5ca20

---


# Koppla samman användare på olika enheter

> [!IMPORTANT] Den här metoden för att identifiera besökare på olika enheter rekommenderas inte längre. Se [Enhetsövergripande analys](/help/components/cda/cda-home.md) i användarhandboken för komponenter.

Identifiering av besökare på olika enheter hjälper er att koppla samman besökare på olika enheter. Identifiering av besökare på olika enheter använder variabeln för att koppla en användare till olika enheter. `visitorID` Variabeln har den högsta prioriteten när det gäller att identifiera unika besökare. `visitorID`

När du skickar en träff med ett anpassat besökar-ID söker Adobe efter besökarprofiler som har ett matchande besökar-ID. Om det finns en sådan används den besökarprofil som redan finns i systemet från och med den punkten och den tidigare besökarprofilen används inte längre.

Inställningen av variabeln är vanligtvis inställd efter autentiseringen eller efter att en besökare utför någon annan åtgärd som gör att du kan identifiera dem unikt oberoende av den enhet som används. `visitorID` Effektiva identifierare innehåller ett hash-värde av användarnamn, e-postadress eller ett internt ID som inte innehåller någon personligt identifierbar information.

När kunden har loggat in från varje enhet är de alla knutna till samma användarprofil. Om besökaren loggar ut senare på en enhet fortsätter de att tillhöra samma besökarprofil eftersom Adobe känner igen att webbläsarens cookie på varje enhet tillhör samma besökarprofil. Adobe rekommenderar att du använder variabeln när det är möjligt om webbläsar-cookien tas bort. `visitorID`

## Begränsningar

Genom att använda egna besökar-ID:n får du större kontroll över hur besökare identifieras, men det har sina begränsningar.

* **Avduplicering av besökare är inte retroaktiv**: Om en besökare öppnar er webbplats för första gången autentiseras, räknas två unika besökare. En unik besökare räknas automatiskt för det generiska analys-ID:t och en annan räknas för det anpassade besökar-ID:t när de loggar in. Den här dupliceringen av unika besökare förekommer varje gång en besökare använder en ny enhet eller rensar sina cookies.
* **Inkompatibelt med Experience Cloud ID-tjänsten**: Sedan vi introducerade besöksidentifiering på olika enheter har Adobe släppt kraftfullare och tillförlitligare sätt att spåra besökare på olika enheter. Dessa nya identifieringsmetoder är inte kompatibla med åsidosättningen av det anpassade besökar-ID:t. Om du tänker använda ID-tjänsten, enhetsövergripande analys (CDA) eller Device co-op rekommenderar Adobe starkt att du inte använder `visitorID` -variabeln.
