---
description: Med alternativet Inkludera aktuella data i rapporter och analyser kan du visa de senaste Analytics-data, ofta innan data har bearbetats fullständigt och slutförts. Aktuella data visar de flesta mätvärden på några minuter och ger användbara data för snabba beslut.
subtopic: Current Data
title: Aktuella data
uuid: 601d3695-be13-4b7f-9df0-de01c8bd64ee
feature: Rapporter och analysgrunder
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 1%

---


# Aktuella data

Med alternativet Inkludera aktuella data i rapporter och analyser kan du visa de senaste Analytics-data, ofta innan data har bearbetats fullständigt och slutförts. Aktuella data visar de flesta mätvärden på några minuter och ger användbara data för snabba beslut.

Den är synlig som ett alternativ som en del av rapportens inställningar:

![Aktuella data, bild](assets/current_data.png)

Aktuella data är som standard aktiverat för alla rapporter som stöder det. Om du hellre vill visa alla mätvärden efter att data har bearbetats, finns det flera alternativ:

* Använd Analysis Workspace, som använder fullt bearbetade data.
* Klicka på Nej i den aktuella datarappningsinställningen om du bara vill använda fullständigt bearbetade data.
* Ta bort behörighetsobjektet Aktuella data från en produktprofil i Admin Console för att hindra användare som inte är administratörer från att se det här alternativet. Mer information finns i [Behörigheter för produktprofiler för analysverktyg](/help/admin/admin-console/permissions/analytics-tools.md) i användarhandboken för Admin.

På grund av prioriteringen av datatillgänglighet kan aktuella data för närvarande inte användas med segment, klassificeringar, uppdelningar, sökningar och vissa mätvärden. Om någon av dessa funktioner används tvingas aktuella data till Nej i rapporten och ett gult meddelande visas som förklarar varför aktuella data inte är tillgängliga.

![Aktuell datavisering](assets/current_data_notice.png)

## Vanlig svarstid för aktuella data

Mätvärdena visas i någon av de följande tre tidsbildrutorna. Klicka på klockikonen bredvid växlingsknappen Inkludera aktuella data för att visa det faktiska latensvärdet för varje mätvärde i en rapport.

| Tidsram | Mätvärden |
| --- | --- |
| Under 10 minuter | Instanser och sidvyer av trafikvariabler |
| Mellan 10 och 35 minuter | Konverteringshändelser, instanser och sidvyer för konverteringsvariabler |
| Mellan 45 och 120 minuter | Alla andra data, som besök, unika besökare och deltagande |

Eftersom vissa data som visas i den aktuella datavyn inte har bearbetats fullständigt, kan du se en skillnad mellan värden som rapporteras i den aktuella datavyn och den slutliga vyn. I trendrapporter är dataskalskillnaden vanligtvis inom 1 %.

## Beräknade mätvärden

Eftersom beräknade mätvärden kan skapas med mätvärden som har olika fördröjning, kan vissa senaste värden beräknas med hjälp av ofullständiga data i den aktuella datavyn.

Du kan t.ex. skapa det beräknade måttet Sidvyer per besök med formeln `Page Views divided by Visits`. Sidvyer visas vanligtvis inom 10 minuter, och besök visas vanligtvis inom 2 timmar, beräknade värden i det här tidsfönstret beräknas med hjälp av ofullständiga mätvärden. Om du publicerar en ny sida som får 4 000 träffar från 4 000 olika besök under en 2-timmars tidsram kan fördröjningsskillnaden mellan dessa värden orsaka ofullständiga beräkningar.

Den här dataskalskillnaden syns mest när du rapporterar nya värden eller använder korta tidsramar. När längre datumintervall används i en rapport är det osannolikt att de latensskillnader som uppstår under de senaste timmarna av rapportering har någon märkbar inverkan på de beräknade mätvärdena.

Om du har beräknade mätvärden som kan påverkas av dessa skillnader kan du antingen inaktivera aktuella data eller använda mätvärden med samma förväntade tidsfördröjningsfönster.

## Hämtade rapporter

När du laddar ned en rapport med den aktuella datavyn aktiverad, köas rapporten och genereras och skickas sedan tillbaka till webbläsaren. Om data samlas in medan rapporten genereras visas dessa data i rapporten. Detta tidsfönster kan leda till att den hämtade rapporten innehåller något mer data.
