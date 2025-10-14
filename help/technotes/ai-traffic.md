---
description: Förstå hur man rapporterar om trafik från AI-chattbotar
title: Analysera trafik från AI-chattbottar
feature: Metrics, Data Configuration and Collection
source-git-commit: d16214865a037efe41b9f95682758daa577a12ed
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# Analysera trafik från konversationsbaserade AI-verktyg

Adobe Analytics tillhandahåller verktyg för analys av AI-trafik på er webbplats.

När du analyserar AI-trafik måste du först förstå vilka typer av AI-trafik som kan förekomma och vilka typer som genererar träffar. Sedan kan du analysera trafiken i Analysis Workspace.

## Förstå AI-trafik

### Förstå typerna av AI-trafik

AI-trafik på din webbplats kan förekomma under följande omständigheter:

* **Under förutbildningen**: Inträffar sällan när innehåll från din webbplats klipps ut och hämtas till AI-utbildningsdata.

* **När användaren besvarar uppmaningar på begäran**: Inträffar när användaren frågar AI med en fråga och AI-chatbot svarar. AI-chattbot utför en webbsökning och innehåll från din webbplats ingår i svaret. (Den här typen av interaktioner kallas ibland Retrieval-Augmented Generation (RAG).)

  Vissa AI-chatbot-svar innehåller länkar till källmaterialet på din webbplats, andra gör det inte.

* **Vid körning av autentiska arbetsflöden**: Inträffar när en AI-agent besöker din webbplats när han/hon klickar igenom en serie webbsidor i en webbläsare för att svara på en användarförfrågan. I det här fallet fungerar AI som en agent för den användare som gjorde begäran.

### Förstå när träffar genereras för AI-trafik

En träff skapas på en webbsida när JavaScript körs på sidan. Beroende på vilken typ av AI-trafik som förekommer på din webbplats kan JavaScript köras eller inte.

| AI-trafiktyp | Skapar träffar | Överväganden |
|---------|----------|---------|
| **Förutbildning** | Ja | Träffar genereras under förutbildningen när innehållet från din webbplats hämtas till AI. Men förträning sker sällan, och innehåll som ingår i en AI-förutbildning kan återanvändas gång till gång i framtida åtgärder utan att några träffar genereras på webbplatsen. <p>Med andra ord kan en enda träff som inträffar under en AI-förutbildning återanvändas om och om igen för flera on-demand-svar utan att några ytterligare träffar genereras på webbplatsen.</p><p>Mer information om hur du analyserar den här typen av AI-trafik i Analysis Workspace finns i [Analysera AI-trafik med robotidentifiering](#analyze-ai-traffic-using-bot-detection).</p> |
| **On demand-meddelanden** | Nej | AI-svaret genererar inga träffar eftersom svaret använder en kombination av:<ul><li>Förtränade data <br/>Information ingår redan i AI:s förutbildade kunskap, så AI kör inte JavaScript på sidor.</li><li>On-demand-webbsökning <br/>Hämtar endast oformaterad HTML för webbsidan under webbsökningen, så AI kör inte JavaScript på sidor.</li></ul> |
| **Source materiallänkar i AI-svar** | Ja | Träffar genereras när en användare klickar på länken till källmaterial som ingår i AI-svaret. En träff genereras inte om en länk inkluderas i svaret och länken inte klickas av användaren. <p>Vissa AI-chatbot-svar innehåller länkar till källmaterialet och andra gör det inte. </p><p>Information om hur du analyserar den här typen av AI-trafik i Analysis Workspace finns i [Analysera AI-trafik efter referenstyp](#analyze-ai-traffic-by-referrer-type).</p> |
| **Aktiva arbetsflöden** | Ja | Träffar genereras på varje sida när AI-agenten klickar genom arbetsflödet för användarens räkning. <p>Information om hur du analyserar den här typen av AI-trafik i Analysis Workspace finns i [Analysera AI-trafik efter referenstyp](#analyze-ai-traffic-by-referrer-type).</p> |

## Analysera AI-trafik i Analysis Workspace

### Analysera AI-trafik efter typ av referens

Du kan använda referensdimensionen i Analysis Workspace för att analysera följande typer av AI-trafik:

* Source materiallänkar i AI-svar

* Byråbaserade arbetsflöden

Referenttypsdimensionen innehåller dimensionsobjektet [Konversationsverktyg för AI ](/help/components/dimensions/referrer-type.md#conversational-ai-tools). Dimensionsobjektet innehåller en fördefinierad lista med AI-chattbotar.

Mer information finns i [Referenstyp](/help/components/dimensions/referrer-type.md).

### Analysera AI-trafik med robotidentifiering

Du kan använda robotidentifiering i Analysis Workspace för att analysera AI-trafik som kommer från förutbildning.

