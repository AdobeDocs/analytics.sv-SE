---
description: Funktioner för tillgänglighetsstöd i Analysis Workspace
title: Tillgänglighet i Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: 2bacbee8-097c-4fc5-8be4-7e4f284db08c
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---

# Tillgänglighet i Analysis Workspace

Läs om tillgänglighetsstöd i [!UICONTROL Analysis Workspace], det främsta analysverktyget för Adobe Analytics.

Med hjälpmedel avses att göra produkter användbara för personer med funktionshinder som syn-, hörsel-, kognitiv-, motor- eller andra funktionshinder. Exempel på hjälpmedelsfunktioner för programprodukter är skärmläsarstöd, textmotsvarigheter för grafik, kortkommandon, ändringar av visningsfärger till hög kontrast osv.

[!UICONTROL Analysis Workspace] innehåller verktyg som gör den tillgänglig för användning, bland annat:

## Navigera till [!UICONTROL Workspace] med hjälp av tangentbordet

Navigering i [!UICONTROL Analysis Workspace] fungerar överst > nedåt och vänster > höger. Följande navigeringselement underlättar tillgängligheten:

* Med tangenten `Tab` kan du skapa genvägar mellan större avsnitt i Workspace. I den vänstra listen kan du med `Tab` även gå från ett dragbart alternativ till nästa.
* `left/right arrows` förflyttas mellan enskilda element när `Tab` har markerat det.
* `F6` navigerar till den första panelen i projektet och förflyttar sig mellan visualiseringarna på den panelen. Sedan flyttas den till nästa panel i projektet och upprepas.
* Vi använder fokusindikatorer så att synkade tangentbordsanvändare får en tydlig indikation på vilket gränssnittselement som är i fokus. Indikatorn är en blå ram runt det markerade elementet.

  ![Fokusindikator](assets/focus-indicator.png)

### Tangentbordsnavigering för menyraden

1. Tabba tills du har nått menyraden.
1. Använd vänster-/högerpilstangenterna för att navigera till den meny som du vill använda.
1. Tryck på `Enter` för att markera menyn och visa dess alternativ.
1. Använd upp-/nedpilarna för att navigera till det menyalternativ du vill använda.
1. Tryck på `Enter` för att välja alternativet.

### Tangentbordsnavigering för dra och släpp-interaktioner

[!UICONTROL Analysis Workspace] är ett dra och släpp-användargränssnitt. Användarna kan dock lägga till komponenter med tangentbordet i stället:

1. Gå till en komponent i den vänstra listen.
1. Tryck på `Enter` för att markera.
1. Använd piltangenterna för att navigera till det område där du vill släppa komponenten.
1. Tryck på `Enter` för att montera komponenten.

### Kortkommandon (snabbtangenter)

[!UICONTROL Analysis Workspace] erbjuder en mängd [kortkommandon](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=sv-SE) för ett smidigare arbetsflöde. Nedan listas några vanliga genvägar för navigering, skapande av analyser och demokratisering av insikter.

#### Navigering

| Genväg | Åtgärd |
| --- | --- |
| `[Alt + Shift + 1 / 2 / 3]` | Hoppa till olika skenor: [!UICONTROL Panels], [!UICONTROL Visualizations] eller [!UICONTROL Components] |
| `[Alt + Left / Right]` | Navigera mellan paneler |
| `[Alt + M]` | Komprimera/expandera alla paneler |
| `[Alt + Ctrl + M]` | Komprimera/expandera aktiv panel |
| `[Ctrl + /]` | Söka i vänster ratt |

#### Analysgenerering

| Genväg | Åtgärd |
| --- | --- |
| `[Alt + 1]` | Ny frihandstabell |
| `[Ctrl + Shift + C]` | Nytt beräknat mått |
| `[Ctrl + Shift + D]` | Nytt datumintervall |
| `[Ctrl + Shift + E]` | Nytt segment |
| `[Ctrl + Z]` | Ångra |
| `[Component drag + Shift]` | Skapa ett nedrullningsbart filter |

#### Demokratisering

| Genväg | Åtgärd |
| --- | --- |
| `[Ctrl + S]` | Spara |
| `[Ctrl + Shift + G]` | Kurva |
| `[Ctrl + G]` | Dela |
| `[Alt + Shift + S]` | Schema |
| `[Alt + L]` | Hämta länk till projekt |
| `[Ctrl + Shift + B]` | Ladda ned PDF |

## Stöd för skärmläsare och skärmförstorare

En skärmläsare läser upp text som visas på datorskärmen. Den läser även information som inte är text, t.ex. knappetiketter eller bildbeskrivningar i programmet, som finns i hjälpmedelstaggar eller -attribut.

## Färgpaletter och kontrast

[!UICONTROL Analysis Workspace] strävar efter WCAG 2.1-överensstämmelse, inklusive krav på färgkontrast.

Dessutom kan användare ange en egen önskad färgpalett för ett projekt under **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Projektfärgpalett](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=sv-SE).

## Obligatorisk fältvalidering i komponentbyggare

När du skapar en komponent valideras de obligatoriska fälten när du sparar. Om ett obligatoriskt fält inte godkänns vid valideringen visas det i rött med en felikon. En skriftlig beskrivning visas av problemet som behöver åtgärdas.

När en komponent har validerats stängs byggaren när du trycker på `Save`.

![Felvalidering](assets/error-validation.png)

## Stöd för hjälpmedelsfunktioner för operativsystem

Analysis Workspace har stöd för inbyggda hjälpmedelsfunktioner för MS Windows och macOS, som högkontrastläge, klisterlappar och långsamma tangenter/filtertangenter. Det innehåller även information om användargränssnittet till operativsystemet för att möjliggöra interaktion med hjälpmedelstekniker, inklusive skärmläsare som VoiceOver för macOS och NVDA i Windows.
