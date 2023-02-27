---
description: Översikt över vilka data Adobe Analytics samlar in och andra sekretessvillkor.
keywords: sekretess
title: Sekretessöversikt
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: 77e50dec593722855f30c517f63141e84f665519
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 88%

---

# Sekretessöversikt

Adobe rekommenderar att du ger besökarna enkel och lättförståelig information om möjligheten att avanmäla sig från att få sin surfinformation inhämtad av Adobes produkter eller tjänster.

Besökarna kan lära sig mer om hur Adobe i allmänhet använder information som samlas in i [Adobes sekretesscenter](https://www.adobe.com/se/privacy.html). Det är upp till er organisation att redovisa hur ni använder Adobes produkter och tjänster, eftersom ni exklusivt styr hur ni ska implementera Adobes tjänster. Du ansvarar för att skapa din egen sekretesspolicy, för att följa din sekretesspolicy, för att följa ditt serviceavtal med Adobe och för att följa alla gällande lagar.

## Uppdelning av datainsamling {#section_F59D958D7AE44747846993E643CD4BF2}

Adobe Analytics samlar in följande data:

| Typ av data | Samlar Adobe Analytics in dessa data? |
|---|---|
| URL:er till webbsidor på kundens webbplats | Ja |
| Webbsidans namn | Ja |
| Tid som har använts på sidan | Ja |
| Tid på dagen | Ja |
| URL:er för webbsidor på icke-anslutna webbplatser | **Nej** |
| Cookie-ID:n (slumpmässigt genererade) | Ja |
| URL till sidan som användaren besökt innan han/hon besökte kundsidan | Ja |
| Sökfråga när konsumenten klickar på länken till kundsidan | Ja |
| Typ av webbläsare | Ja |
| Enhetstyp | Ja |
| Operativsystem | Ja |
| ISP/anslutningshastighet | Ja |
| Visningsinställningar (till exempel skärmstorlek och upplösning) | Ja |
| IP-adress (används för att beräkna plats) | Ja&#42; |
| Information som konsumenter tillhandahåller i formulär på kundwebbplatsen | Ja |
| Information som konsumenter tillhandahåller i formulär på sociala webbplatser | **Nej** |
| Om konsumenten klickat på annonsen | Ja |
| Om konsumenten klickat på länken, bilden eller texten på webbplatsen | Ja |
| Oavsett om konsumenten hämtat en fil, en bild osv. | Ja |
| Inköpta artiklar | Ja |
| Artiklar kvar i kundvagnen | Ja |
| Information på sociala nätverk (inklusive foton, användar-ID, ålder, kön, plats) | **Nej** |
| Personlig information som användaren tillhandahåller utanför våra tjänster | Ja |
| Framgångssiffror för annonskampanjer | Ja |
| Produktinformation, t.ex. färger, priser, format, foton | Ja |

&#42;Om inte Adobe-kunden väljer att ta bort IP-adressen.

## Andra sekretessfrågor {#section_60AF6AD6FBD046EEAF9F083A9726EF8A}

| Region/land | Villkor |
|--- |--- |
| Globalt | Adobe rekommenderar starkt att man avstår från att skicka personligt identifierbar information (PII) till Adobe, särskilt i situationer där PII inte behövs för Analytics. |
| Globalt | Användarna måste få meddelanden och valmöjligheter vid profilering. Detta krävs enligt lag i Kanada, Australien, Europeiska unionen (anmälan för vissa länder) och många länder i Latinamerika och Asien-Stillahavsområdet. |
| Globalt | Om man använder cookies från första part är Analytics-avanmälan unik för en kund; du kan inte lita på en avanmälan på Adobe.com. |
| Globalt | Förstapartsanalys omfattas inte av det självreglerande programmet för beteendeannonsering online (&quot;AdChoices&quot;). |
| Globalt | Enhetsövergripande data får inte sammanfogas om de inte är knutna till en identifierare som kunden har angett (till exempel hash-kodat användarnamn). |
| Globalt | Det finns troligtvis begränsningar för kunden när det gäller att kombinera annonsvisningsinformation med PII. |
| Europa | De flesta länder i EU anser inte att cookies i analyser är absolut nödvändiga. |
| Europa | Adobe har aktiverat inställningen IP-Obfuscation: Aktiverad - IP Borttagen (x.x.x.x) som standard för alla kunder med en rapportsvit som angetts i EMEA. Med den här inställningen ersätts IP-adressen helt med värdet (x.x.x.x) efter geosökning och är inte längre tillgänglig som en datapunkt. Den här grundläggande ersättningsmetoden kan inte bakåtkompileras till en unik, specifik IP-adress. Varken kunden eller Adobe kan komma åt IP-adressen. den är irreversibelt anonymiserad. Mer information om andra inställningar för IP-döljning finns i [Allmänna kontoinställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) i användarhandboken för Admin. |
| Globalt | En kund kan ställa in variabeln för cookie-livstid i JavaScript-mätningskoden på värdet &quot;none&quot;, &quot;session&quot; eller något annat angivet värde mätt i sekunder. |
| Europa | Adobe har utvecklat en ny inställning för &quot;sekretess efter design&quot; som nu kan aktiveras av Adobe ClientCare för Adobe Analytics (tidigare SiteCatalyst) version 14.9 och 15.4. När den här nya inställningen är aktiverad ersätts den sista oktetten (den sista delen) av IP-adressen omedelbart med värdet 0 när IP-adressen har samlats in av Adobe. Denna anonymisering utförs innan någon behandling av IP-adressen utförs, inklusive innan både en valfri geosökning och en ISP-sökning av IP-adressen har gjorts. |
| Tyskland | Om du inte redan har ett databehandlingsavtal för Adobe Analytics med Adobe bör du kontakta din kontoansvarige på Adobe eller kundframgångsansvarige, som kommer att arbeta tillsammans med Adobe juridiska avdelning för att få avtalet på plats. |

## Plats för EMEA-datacenter {#section_3DD2329B983849D3B8C24AEF7CD8DFB3}

Följande EMEA-datacenter är för närvarande värd för Adobe Analytics-data:

| Adobe-namn | Adress | Resurstyp (operatör) | Lösningskomponenter som stöds | Certifieringar |
|--- |--- |--- |--- |--- |
| LON5 | 3 Centro  Boundary Way Hemel Hempather HP2 7SU UK | Samlokaliseringsfacilitet (Gyron) | Multichannel Analytics, Digital Analytics | SSAE 16 |