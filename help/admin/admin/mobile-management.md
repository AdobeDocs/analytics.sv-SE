---
description: Om apphantering aktiveras aktiveras mobillösningens variabler som hämtar livscykel och andra mätvärden från mobilprogram.
title: Apphantering
feature: Administratörsverktyg
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 2%

---

# Apphantering

Om apphantering aktiveras aktiveras mobillösningens variabler som hämtar livscykel och andra mätvärden från mobilprogram.

Integrationen mellan Adobe Analytics och Mobile Services:

* Här kan du dela dina KPI-data (Key Performance Indicator) från mobiltjänster till Adobe Analytics.
* Gör att du kan aktivera platsspårning.
* Lägger till nya rapporter under Analytics > Reports > Mobile App.
* Lägger till 25 nya Adobe Mobile-klassificeringar.
* Lägger till fem nya mobilmått för Adobe.
* Lägger till nya mobildimensioner för Adobe.
* Synkroniserar data med Analytics var 15:e minut

**[!UICONTROL Analytics]** >  **[!UICONTROL Admin]** >  **[!UICONTROL Report Suites]** >  **[!UICONTROL Edit Settings]** >  **[!UICONTROL App Management]** >  **[!UICONTROL App Reporting]**.

## Steg 1. Aktivera apprapporter {#section_FBADF80AED2B4978A904ABB770B3B931}

Aktivera apprapporter v3.0 för att mäta följande mått:

* **Anskaffning**  - spåra refererande URL:er för nedladdningskampanjer för appar.
* **Livscykel**  - grundnivån för rapportering som tillhandahålls genom mätningar som skickas vid varje programstart.
* **Programåtgärder**  - Rapporter och kundvägar baserade på åtgärder i appen.
* **Livstidsvärde**  - Få en förståelse för hur användare får upp värde över tiden med hjälp av nyckeltal för appar (t.ex. köp, annonsvisningar, videokompletteringar, sociala resurser, fotoöverföringar).
* **Timed Events**  - mät hur lång tid det tar (i appen och total tid) mellan viktiga programåtgärder (till exempel tid före första köpet).

## Steg 2. Aktivera platsspårning {#section_2CCBD205191C4CA3B7B71A6F11FF97EC}

Om du aktiverar platsspårning kan du:

* Spåra latitud- och longituddata och rapportera om dem i Analysis Workspace och Mobile Services.
* Identifiera, skapa och visualisera specifika intressepunkter inom mobiltjänster. POI måste definieras i den mobila SDK-konfigurationsfilen.
* Spåra bluetooth-fyrar (UUID, major, minor och närhet).

## Steg 3. (Valfritt) Aktivera/inaktivera äldre rapportering och attribuering för bakgrundstödraster {#section_1708BCAA87AA4884986F7532759C5DD4}

Aktiverade bakgrundstötningar (träffar som genereras när programmet är i bakgrunden) innebär att de behandlas som vanliga förgrundstötningar. De visas nu i regelbundna rapporter och detta påverkar även attribuering. Den här konfigurationen är vanligtvis bara önskvärd för att vara konsekvent med tidigare implementeringar.

Vi rekommenderar i stället att du&quot;tar med bakgrundstötar&quot; i en [virtuell rapportsvit](/help/components/vrs/vrs-about.md). På så sätt kan du se träffarna, men de påverkar inte besöks- och besökarantal negativt.
Mobilklassificeringar aktiveras när du aktiverar **[!UICONTROL App Management]** > **[!UICONTROL App Reporting]**.

Klassificeringar används för att kategorisera värden i grupper och rapportera på gruppnivå. Du kan t.ex. klassificera alla betalsökningskampanjer i en kategori som&quot;popmusiktermer&quot; och rapportera om hur framgångsrik den kategorin är i förhållande till mått som Instances (a.k.a.). Klickningar) och konvertering till lyckade händelser.

| Klassificering | Definition |
|--- |--- |
| Första startdatum | Datum för första start efter installation eller ominstallation.   MM/DD/ÅÅÅ |
| Program-ID | Lagrar programnamnet och versionen i följande format:   `[AppName] [BundleVersion]` Exempel: `myapp 1.1.` |
| Startnummer | Antal gånger som programmet startades eller togs bort från bakgrunden. |
| Dagar sedan första användningen | Antal dagar sedan första körningen. |
| Dagar sedan senaste användning | Antal dagar sedan senaste användning. |
| Timme på dagen | Mäter timmen då appen startades och använder det numeriska 24-timmarsformatet. Används för tidsdelning för att bestämma maximal användningstid. |
| Veckodag | Antal veckor som appen startades. |
| Enhetsnamn | Lagrar enhetsnamnet.  Kommaavgränsad tvåsiffrig sträng som identifierar enheten. Det första talet representerar vanligtvis enhetsgenereringen och det andra numret är vanligtvis olika versioner av olika medlemmar i enhetsfamiljen. |
| Operativsystemsversion | OS-version. |
| Upplösning | Bredd x höjd i pixlar. |
| Livstidsvärde (eVar) | Fylls i av trackLifetimeValue-metoder. |
| Anskaffningskälla |  |
| Medelvärvning |  |
| Anskaffningstid |  |
| Förvärva innehåll |  |
| Anskaffningsnamn |  |
| Placering (ned till 10 km) | Fylls i av trackLocation-metoder. |
| Plats (ned till 100 m) | Fylls i av trackLocation-metoder. |
| Plats (ned till 1 m) | Fylls i av trackLocation-metoder. |
| Intressepunktens namn | Fylls i av trackLocation-metoder när enheten är i en definierad POI. |
| Avstånd till intressecentrum | Fylls i av trackLocation-metoder när enheten är i en definierad POI. |
| Meddelande-ID i appen |  |
| Meddelande i appen online |  |
| Push Opt-In |  |
| Nyttolast-ID |  |
