---
description: Inställningar som definierar hur alla rapporter visas och information som mappar standardmenyalternativen till deras plats på den förenklade menyn.
title: Visningsinställningar och navigering för rapporter
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 2c2d4d59-b189-42e0-887e-77dc7a48721a
source-git-commit: 246fbe068898ad04db2f324975fc27cb24bc7f58
workflow-type: tm+mt
source-wordcount: '1465'
ht-degree: 7%

---

# Visningsinställningar och navigering för rapporter

{{ra-eol}}

Inställningar som definierar hur alla rapporter visas och information som mappar standardmenyalternativen till deras plats på den förenklade menyn.

## Visningsinställningar och navigering för rapporter {#concept_09832A2CA0FF4982B1AA37C1B635220B}

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL All Components]** > **[!UICONTROL Report settings]**

| Element | Beskrivning |
|--- |--- |
| **Allmänna inställningar** |  |
| Inkludera relaterat måttavsnitt | Relaterade mätvärden är nära relaterade till den rapport som du för närvarande visar (till exempel de fem främsta sidorna i rapporten över sidvisningar). |
| Visa Internet-medelvärde i informationsavsnittet | Uttrycker det genomsnittliga värdet för en viss statistik, taget på flera tusen företagswebbplatser. När det här avsnittet är aktiverat visas det som en separat kolumn i avsnitten för rapportsammanfattning och rapportinformation. Den här funktionen används endast av trafikrapporter i teknikgruppen samt av sökmotorer, språk och domänrapporter. |
| Visa menystrukturen för Adobe | Ignorerar inställningarna i administratörsverktygen, där administratörer anpassar rapportmenyer efter användarinställningar och återställer rapportmenyn till standardinställningarna. |
| Tvinga kolumnbredder när rapporter visas | Tvingar fram kolumnbredder för rapporter till en estetiskt tilltalande konsekvens. Den här inställningen är användbar när fler än tre mätvärden visas. |
| **Diagram** |  |
| Markera helger i trenddiagram | Markerar heltalsdatum i trendrapportdiagram lodrätt. Trendrapporter kan vara mycket enklare att utvärdera när helger identifieras. |
| Inkludera prognos i diagram och sammanfattning | Uppskattar hur mycket en viss statistik kommer att uppkomma i framtiden. Prognosen visas i rapportsammanfattningsavsnittet när den är aktiverad. |
| Inkludera kalenderhändelser i rapporter | Spåra platsprestanda i förhållande till specifika händelser. När det här alternativet är aktiverat visas dessa händelser i dina rapporter. |
| Använd Flash diagram | Aktiverar diagram för Flash i dina rapporter. Med Flash-diagram blir bilderna skarpare och mer interaktiva, men du kan inte enkelt kopiera eller spara dem. Om du snabbt vill kopiera eller spara bilder inaktiverar du det här alternativet (bilderna kommer att vara i .gif-format). Om du avmarkerar det här alternativet visas inte knappen för att kopiera diagram i rapportverktygsfältet. |
| Visa&quot;Alla andra&quot;-data i markerade diagram | Visar alla andra under de fem översta grupperade i ett enskilt objekt. (I stapeldiagram visas de fem populäraste webbsidorna eller andra data i rapporten.) |
| Visa&quot;Ingen&quot;,&quot;Ospecificerad&quot; och&quot;Typad/Bokmärkt&quot;-data i rapportdiagram | Visar mått där inget värde fick kredit för det angivna måttet. |
| Visa miniatyrbilder i rankade rapporter | Visar ett miniatyrdiagram i fältet för rankade rapporter. Detta ger en snabb bild av den övergripande trenden utan att man behöver generera en separat rapport. |
| **Acceleration** |  |
| Aktivera Report Accelerator för att visa rapporter snabbare | Aktiverar rapportacceleratorn, som använder en tidsbaserad algoritm för att cachelagra nyligen begärda rapporter och undersöker endast de mest förekommande unika objekten, vilket ger ännu snabbare rapportleverans. Genom att cachelagra begärda rapporter i 15 minuter kan rapportacceleratorn hämta dessa rapporter för efterföljande begäranden nästan direkt. Den här inställningen är användbar när du bläddrar fram och tillbaka, skriver ut rapporter eller ofta vill få tillgång till samma rapporter. När det är inaktiverat genereras rapporter om varje gång de begärs. |
| Aktivera Dashboard Accelerator och visa tillgängliga cachade versioner | Aktiverar instrumentpanelsacceleratorn, som lagrar en cachelagrad version av instrumentpanelen för efterföljande visning. Genom att cachelagra en vy av instrumentpanelen i 24 timmar kan instrumentpanelsacceleratorn hämta den vyn nästan direkt eftersom den intensiva databasfrågan och bearbetningen görs i förväg. Om den tillgängliga cachelagrade versionen är äldre än 24 timmar skapas en ny instrumentpanel och en ny cachelagrad version skapas. På samma sätt skapas en ny cachelagrad version när du uppdaterar kontrollpanelen (eller en rapport som visas på kontrollpanelen). Cachen är användarbaserad. Andra användare som visar en delad kontrollpanel ser en version som baseras på deras egen användning av instrumentpanelsacceleratorn och uppdatering av instrumentpanelen. |
| Aktivera nätverksacceleration för förbättrade rapportprestanda | Snabbar upp leveransen av data till din plats genom att optimera vägen mellan infrastrukturen i Adobe och din miljö. |
| Aktivera regional acceleration för en snabbare användarupplevelse i Kina | Regional Accelerator använder regionspecifika accelererade domäner för att ge en snabbare användarupplevelse i en viss region. För närvarande stöds regional acceleration bara för Kina. Om du aktiverar den här funktionen för användare som inte finns i Kina blir användarupplevelsen långsammare. När du har aktiverat regional acceleration måste du logga in igen för att inställningen ska få effekt. Om du vill inaktivera Regional Accelerator avmarkerar du den här kryssrutan. |
| **Språk/valuta/kodning** |  |
| Tusentalsavgränsare | Välj en avgränsare för varje tusende (decimal eller komma). I många länder används ett decimaltal för att avgränsa tusentaltalet. (Den här avgränsaren används på alla tal i hela systemet, inte bara i valuta.) |
| Använd rapportsvitens standardvaluta | Anger om rapportsvitens standardvaluta ska användas. |
| Valuta | Valutan som du vill konvertera data till. När du väljer ett värde i den här inställningen påverkas inte data som lagras i databasen, utan visas som ett konverterat värde baserat på den aktuella dagens valutakonverteringsgrad. När valutaalternativen inte är konfigurerade (inställda på standardvärden) sker ingen valutakonvertering och alla värden lagras och visas i USD. Om du vill konvertera valutan när data bearbetas (innan de visas) kontaktar du kontogruppen på Adobe. |
| Schemalagd rapportkodning | SHIFT-JIS för japansk teckenkodning. EUC-JP för utökad Unix-kod, främst för japanska, koreanska och förenklad kinesiska. |
| CSV-avgränsningstecken | Det tecken som du vill använda för att avgränsa CSV-värden. |

## Navigeringsmeny {#concept_1525EE52F8094535B4240F03B70DD75D}

<!-- 

nav_menu.xml

 -->

Om du är van vid standardmenyn gör följande tabell det enklare att hitta menyalternativen på den förenklade menyn.

| Plats på standardmenyn | Plats på förenklad meny |
|---|---|
| **Mätvärden för webbplats** |  |  |
|   | Webbplatsöversikt | Mått > Webbplatsöversikt |
|   | Nyckeltal | Metrics > Key Metrics |
|   | Sidvisningar | Mått > Sidvyer |
|   | Besök | Metrisk > Besök |
|   | Besökare | Metrisk > Besökare |
|   | Tid per besök | Mått > Tid per besök |
|   | Tid före händelse | Konvertering > Tid före händelse |
|   | Inköp | Metrisk > Inköp |
|   | Kundvagn | Metrisk > Kundvagn |
|   | Anpassade händelser | Metrisk > Egna händelser |
|   | Robotar | Audience > Bots |
|   | Avvikelseidentifiering | Metrisk > Anomaly Detection |
|   | Realtid | Metrics > Real-Time |
| **Webbplatsinnehåll** |  |  |
|   | Sidor | Innehåll > Sidor |
|   | Webbplatsavsnitt | Innehåll > Platsavsnitt |
|   | Servrar | Content > Servers |
|   | Länkar | Navigation > Custom Links; Navigation > Exit Links; Navigation > ClickMap; Navigation > File Downloads |
|   | Sidor som inte hittades | Navigering > Sidor hittades inte |
| **Mobil** |  |  |
|   | Enheter | Audience > Mobile > Devices |
|   | Enhetstyp | Målgrupp > Mobil > Enhetstyp |
|   | Tillverkare | Audience > Mobile > Manufacturer |
|   | Skärmstorlek | Målgrupp > Mobil > Skärmstorlek |
|   | Skärmhöjd | Målgrupp > Mobil > Skärmhöjd |
|   | Skärmbredd | Målgrupp > Mobil > Skärmbredd |
|   | Cookie-stöd | Audience > Mobile > Cookie Support |
|   | Bildstöd | Målgrupp > Mobil > Bildstöd |
|   | Färgdjup | Målgrupp > Mobil > Färgdjup |
|   | Ljudstöd | Audience > Mobile > Audio Support |
|   | Stöd för video | Audience > Mobile > Video Support |
|   | Operativsystem | Målgrupp > Mobil > Operativsystem |
| **Sökvägar** |  |  |
|   | Sidor | Navigering > Banor > Sidor |
|   | Interna sökvillkor | Navigering > Banor > Interna sökvillkor |
| **Trafikkällor** |  |  |
|   | Söknyckelord - alla | Traffic Sources > Search Keyword - All |
|   | Söknyckelord - Betald | Traffic Sources > Search Keyword - Paid |
|   | Söknyckelord - naturligt | Traffic Sources > Search Keyword - Natural |
|   | Sökmotorer - alla | Traffic Sources > Search Engines - All |
|   | Sökmotorer - betalda | Traffic Sources > Search Engines - Paid |
|   | Sökmotorer - naturliga | Traffic Sources > Search Engines - Natural |
|   | Alla söksidrankning | Traffic Sources > All Search Page Ranking |
|   | Refererande domäner | Trafikkällor > Refererande domäner |
|   | Ursprungliga referensdomäner | Trafikkällor > Ursprungliga referensdomäner |
|   | Referenter | Traffic Sources > Referrers |
|   | Refererartyper | Trafikkällor > Refererartyper |
| **Kampanjer** |  |  |
|   | Konverteringstratt för kampanj | Traffic Sources > Campaigns > Campaign Conversion Trnel |
|   | Spårningskod | Traffic Sources > Campaigns > Tracking Code |
| **Produkter** |  |  |
|   | Konverteringstratt för produkter | Conversion > Products > Products Conversion Trnel |
|   | Produkter | Conversion > Products > Products |
|   | Korsförsäljning | Conversion > Products > Cross Sell |
|   | Kategorier | Konvertering > Produkter > Kategorier |
| **Kvarhållning av besökare** |  |  |
|   | Återbesöksfrekvens | Målgrupp > Behåll besökare > Returfrekvens |
|   | Återbesök | Målgrupp > Behåll besökare > Returbesök |
|   | Dagliga återbesök | Målgrupp > Behåll besökare > Dagliga besök |
|   | Besöksnummer | Målgrupp > Behåll besökare > Besök nummer |
|   | Försäljningscykel | Audience > Visitor Retention > Sales Cycle |
| **Besökarprofil** |  |  |
|   | Geosegmentering | Audience > Visitor Profile > GeoSegmentation |
|   | Språk | Målgrupp > Besökarprofil > Språk |
|   | Tidszoner | Målgrupp > Besökarprofil > Tidszoner |
|   | Domäner | Målgrupp > Besökarprofil > Domäner |
|   | Domäner på översta nivån | Målgrupp > Besökarprofil > Domäner på översta nivån |
|   | Teknik | Audience > Visitor Profile > Technology |
|   | Besökarläge | Målgrupp > Besökarprofil > Besökarläge |
|   | Besökarens postnummer | Målgrupp > Besöksprofil > Postnummer för besökare |
| **Anpassad konvertering** |  |  |
|   | Anpassad konvertering 1-10 | Konvertering > Anpassad konvertering > Anpassad konvertering 1-10 |
|   | Anpassad konvertering 11-20 | Konvertering > Anpassad konvertering > Anpassad konvertering 11-20 |
| **Anpassad trafik** |  |  |
|   | Anpassad trafik 1-10 | Innehåll > Anpassad trafik > Anpassad trafik 1-10 |
| **Test&amp;Target** |  | Konvertering > Test&amp;Target |
| **Undersökning** |  | Audience > Survey |
| **Marknadsföringskanaler** |  |  |
|   | Kanalöversiktsrapport | Traffic Sources > Marketing Channels > Channel Overview Report |
|   | Första beröringskanalen | Traffic Sources > Marketing Channels > First Touch Channel |
|   | Första beröringskanaldetalj | Traffic Sources > Marketing Channels > First Touch Channel Detail |
|   | Senaste beröringskanal | Traffic Sources > Marketing Channels > Last Touch Channel |
|   | Senaste beröringskanaldetalj | Traffic Sources > Marketing Channels > Last Touch Channel Detail |
| **Mobilapp** |  |  |
|   | Översikt över mobilappar | Innehåll > Mobilapp > Översikt över mobilappar |
|   | Livscykelrapporter | Innehåll > Mobilapp > Livscykelrapporter |
| **Anpassade rapporter** |  |  |
|   | Anpassade rapporter visas bara för dig som har någon konfiguration. | Anpassade rapporter |
|   |  |  |
