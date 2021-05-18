---
description: Importera spårningsdata från tredjepartsprogram till Analytics.
title: Komma igång med Analytics-dataanslutningar
exl-id: 2ad117ba-1ef1-4808-a546-de9833dfa49d
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 0%

---

# Översikt över dataanslutningar

Adobe förser organisationer med åtgärdbar realtidsinformation om deras digitala strategier och marknadsföringsinitiativ. Med dataanslutningar kan ni importera spårningsdata från tredjepartsprogram till Analytics, så att ni kan samla in och använda data från en central plats. Om du använder någon av partnerprodukterna kan du skapa en integrering som importerar programdata till marknadsföringsrapporter. När de är integrerade kan du generera rapporter som innehåller data från programmet.

En e-postintegrering kan till exempel vilja använda en e-postpartner för att distribuera en e-postkampanj. När besökarna kommer till er webbplats vill ni veta vilka som kom som svar på er e-postkampanj. Dataanslutarna integrerar data från er e-postpartner i marknadsföringsrapporter, så att ni kan fastställa den här informationen för att mäta effektiviteten i er e-postkampanj.

>[!IMPORTANT]
>
>Adobe Data Connector-tekniken upphör den 1 augusti 2021. [Läs mer …](/help/import/data-connectors/data-connectors-eol.md)

**Systemkrav**

Dataanslutningar bör integreras på rätt sätt med de vanligaste webbläsarna. Rapporterna ser dock bäst ut och fungerar bäst på system som uppfyller följande rekommendationer:

* Webbläsare: Microsoft Internet Explorer version 6 och senare
* Cookies: Obligatoriskt
* JavaScript: Aktiverad
* Operativsystem: Windows-baserad
* Macromedia Flash Player: version 6 eller senare
* Bildskärmsupplösning: 1 024 × 768 (800 × 600 fungerar)
* Färgdjup: 16 bitar eller högre

Datainsamlingen förbättras dessutom när JavaScript är aktiverat i användarens webbläsare.

**Förutsättningar**

Innan du konfigurerar en dataanslutningsintegration för din produkt gör du följande:

* Ha de nödvändiga inloggningsuppgifterna för partnerproduktkontot, med rätt att få tillgång till alla data som du vill integrera med marknadsföringsrapporter. Du kanske vill skapa ett särskilt e-postkonto för rapportdistributörer och för meddelanden om de integrerade åtgärderna.
* Identifiera anpassade variabler som innehåller kampanjinformationen. Detta kallas vanligtvis kampanjspårningskod, men din organisation kan använda någon annan terminologi.
* Bestäm vilka händelser du vill ska ta emot visningar och klicka på data. Du kanske vill byta namn på händelserna i enlighet med detta.
* Placera lämplig kod på landningssidan så att Analytics kan göra lämplig modellering med data som kommer från partnerprodukten. Specifika instruktioner för respektive partnerprodukt finns i avsnittet i Data Connectors Showcase på fliken Resources.

## Lägg till en integrering

Du måste ha ett aktuellt konto för att komma åt startsidan för [!UICONTROL Data Connectors] (konsol). Vi rekommenderar också att du känner till Adobe Analytics.

1. Logga in på Adobe Experience Cloud.
1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data connectors]**.
1. Klicka på **[!UICONTROL Add New]**.
1. Gå igenom gränssnittet **[!UICONTROL Add Integration]**.

   Beroende på den enskilda produktintegreringen kan du behöva ange specifik konfigurationsinformation som en del av integrationsprocessen.

   När integreringen är klar visas partnerproduktikonen på sidan Data Connectors Network och är tillgänglig på menyer.

## Data Connectors Console

När du har aktiverat en integrering visas den på sidan [!UICONTROL Data Connectors]. Du kan visa information och göra konfigurationsändringar på konsolen. Ni kan visa aktiva integreringar och integreringar för alla rapportsviter i ert företag. Du kan också visa en aktivitetslogg, ange en integrering som en kontrollpanel, konfigurera en integrering och hitta hjälp.

![Data Connectors-konsol](assets/data-connectors-console.png)

## Återmarknadsföring av segment i dataanslutningar

Remarketing-segment är datafiler som skapas baserat på de variabler som används i en dataanslutningsintegrering.

Adobe Analytics skickar dessa i separata dagliga filer via data warehouse till en FTP som skapats av Adobe för tredje part. Den tredje parten distribuerar sedan dessa filer till klienten. Företagen använder ofta dessa för att marknadsföra sig mot dem som besökt webbplatsen och tittade på en produkt, men som inte köpte den. (Du kan till exempel kontakta en kund som erbjuder en rabatt på en produkt som de har tittat på, men som inte köpt den).

**Segment**

* [!UICONTROL Cart Abandonment]: Procentandelen besökare som lade till en artikel i kundvagnen men inte köpte den. Tekniskt sett är det ett beräknat mått som består av order dividerat med kundvagnstillägg.
* [!UICONTROL Purchases]: Mottagar-ID:n (eller besökar-ID:n) som gjorde inköp baserat på meddelande-ID:t i en viss produkt.
* [!UICONTROL Product Views]: Liknar  [!UICONTROL Cart Abandonment]det här är också ett beräknat mått. Den rapporterar [!UICONTROL Product Views] dividerat med beställningar, eftersom kundernas intresse för produkten är stort.

**Implementeringsexempel**

För att lyckas genomföra remarknadsföringssegmenten måste följande villkor vara uppfyllda:

* Ett avtal om dataanslutningar har upprättats och din organisation har slutfört implementeringsfasen med en konsult från Adobe.
* Motsvarande händelse utlöses samtidigt som produktvariabeln:
   * Cart Abandonment: `scAdd`-händelse
   * Inköp: `purchase`-händelse
   * Produktvyer: `prodView`-händelse

>[!NOTE]
>
>Om produkten definieras utan en associerad händelse utlöses händelsen `prodView` automatiskt.
>
>Om ovanstående krav inte uppfylls rapporteras inte motsvarande segment för återmarknadsföring korrekt.

[!UICONTROL Cart Abandonment]: utlöses efter att användaren har lagt till en produkt i kundvagnen:

```
s.products=";cat";
s.events="scAdd";
```

[!UICONTROL Purchases]: utlöses på bekräftelsesidan:

```
s.products=";
cat;1;50";
s.events="purchase";
//Note: Though optional, adding the purchaseID variable increases accuracy by preventing duplicate purchases
```

**Vanliga problem**

| Problem | Beskrivning |
| -----------| ---------- |  
| Ingen produkt-ID-information visas i filen Remarketing Segment. | Inträffar när rätt händelse utlöses, men det finns ingen produktvariabel på samma bildbegäran. För att korrigera detta måste du se till att variabeln products och motsvarande event utlöses på samma sida, vilket framgår av implementeringsexemplen ovan. |
| Marknadsföringssegmentfiler tas inte emot. | Om du inte får dina filer bör du be någon av de användare i organisationen som stöds att kontakta ClientCare för att ta reda på orsaken till att rapporterna inte har tagits emot. |


>[!IMPORTANT]
>
>Det är vanligt att konsulter även ställer in en data warehouse-förfrågan som en daglig schemalagd rapport utöver era vanliga segmentfiler för integrering av dataanslutningar. Den här data warehouse-begäran skulle innehålla både dataanslutningsvariabler och andra variabler än datakopplingar, och begäran kan schemaläggas enbart utifrån din organisations specifika begäran. För att undvika förvirring vid felsökning anger du om filen i fråga är den faktiska segmentfilen för återmarknadsföring, eller en data warehouse-begäran som innehåller icke-generiska variabler.
