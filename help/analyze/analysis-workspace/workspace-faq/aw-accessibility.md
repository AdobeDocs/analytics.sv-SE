---
description: Läs om tillgänglighetsfunktionerna i Analysis Workspace.
title: Tillgänglighet i Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: 2bacbee8-097c-4fc5-8be4-7e4f284db08c
source-git-commit: 70d87e62441f8d5c3c6041721353a07432fef912
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---


# Tillgänglighet i Analysis Workspace

Läs om tillgänglighetsstöd i [!UICONTROL Analysis Workspace], det främsta analysverktyget för Customer Journey Analytics.

Med hjälpmedel avses att göra produkter användbara för personer med funktionshinder som syn-, hörsel-, kognitiv-, motor- eller andra funktionshinder. Exempel på hjälpmedelsfunktioner för programvaror är:

* stöd för skärmläsare,
* textmotsvarigheter för grafik,
* kortkommandon,
* ändring av visningsfärger till hög kontrast,
* med mera.

[!UICONTROL Analysis Workspace] innehåller verktyg som gör den tillgänglig för användning, bland annat:

## Tangentbordsnavigering

Navigering i [!UICONTROL Analysis Workspace] fungerar uppifrån och ned och från vänster till höger. Följande navigeringselement underlättar tillgängligheten:

* Med tangenten **[!UICONTROL Tab]** kan du skapa genvägar mellan större avsnitt i Workspace. I den vänstra panelen kan du i **[!UICONTROL Tab]** även gå från ett dragbart alternativ till nästa.
* }︎ ◀ och {1 }︎ flyttas mellan enskilda element efter att tangenten ▶ har markerat ett element.**[!UICONTROL Tab]**
* **[!UICONTROL F6]**-tangenten navigerar till den första panelen i projektet och förflyttar sig mellan visualiseringarna på den panelen. Sedan flyttas den till nästa panel i projektet och upprepas.
* Fokusindikatorer används så att synkade tangentbordsanvändare har en tydlig indikation på vilket gränssnittselement som är i fokus. Indikatorn är en blå kantlinje för den panel som är i fokus. Och grå bakgrund för den senast valda funktionen och markeringen i funktionen. I exemplet har [!UICONTROL Components] och siddimensionen nyligen valts.

  ![Friformstabell med en fokusindikator för en blå kant runt friformstabellen.](assets/focus-indicator.png)

### Tangentbordsnavigering för menyraden

1. Tabba tills du har nått menyraden.
1. Använd piltangenterna för att navigera mellan menyer och menyalternativ.
1. Tryck på **[!UICONTROL Enter]** för att öppna en meny eller markera ett menyalternativ.
1. Stäng en meny med **[!UICONTROL Esc]**.

### Tangentbordsnavigering för dra och släpp-interaktioner

[!UICONTROL Analysis Workspace] är ett dra och släpp-användargränssnitt. Användarna kan dock lägga till komponenter med tangentbordet i stället:

1. Flikar vid en komponent på den vänstra panelen.
1. Tryck på **[!UICONTROL Enter]** för att markera.
1. Använd piltangenterna för att navigera till det område där du vill släppa komponenten.
1. Tryck på **[!UICONTROL Enter]** för att montera komponenten.

### Kortkommandon (snabbtangenter)

[!UICONTROL Analysis Workspace] erbjuder en mängd [kortkommandon](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) för ett smidigare arbetsflöde.

## Stöd för skärmläsare och skärmförstorare

En skärmläsare läser upp text som visas på datorskärmen. Den läser även information som inte är text, t.ex. knappetiketter eller bildbeskrivningar i programmet.

## Färgpaletter och kontrast

[!UICONTROL Analysis Workspace] strävar efter WCAG 2.1-överensstämmelse, inklusive krav på färgkontrast.

Dessutom kan användare ange en egen önskad färgpalett för ett projekt under **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Projektfärgpalett](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md).

## Nödvändig validering

När du skapar en komponent, en visualisering eller en panel valideras de fält som krävs när du sparar. Om ett obligatoriskt fält inte godkänns vid valideringen visas det i rött med en felikon. En skriven beskrivning förklarar vad som behöver åtgärdas.

![Segment Builder och felvalideringsindikator.](assets/error-validation.png)

## Stöd för hjälpmedelsfunktioner för operativsystem

Analysis Workspace har stöd för inbyggda hjälpmedelsfunktioner för Windows och macOS, som högkontrastläge, klisterlappar och långsamma tangenter/filtertangenter. Det innehåller även information om användargränssnittet till operativsystemet för att möjliggöra interaktion med hjälpmedelstekniker, inklusive skärmläsare som VoiceOver för macOS och NVDA i Windows.


<!--

# Accessibility in Analysis Workspace

Learn about accessibility support in [!UICONTROL Analysis Workspace], the premier analysis tool for Adobe Analytics. 

Accessibility refers to making products usable for people with visual, auditory, cognitive, motor, and other disabilities. Examples of accessibility features for software products include screen reader support, text equivalents for graphics, keyboard shortcuts, change of display colors to high contrast, and so on. 

[!UICONTROL Analysis Workspace] provides some tools that make it accessible to use, including:

## Navigate [!UICONTROL Workspace] using the keyboard

Navigation in [!UICONTROL Analysis Workspace] works top > down, and left > right. The following navigational elements facilitate accessibility:

* The `Tab` key enables landmark shortcuts, moving between larger sections within Workspace. In the left rail, `Tab` also enables you to move from one draggable option to the next.
* The `left/right arrows` move between individual elements after `Tab` has highlighted it. 
* The `F6` navigates to the first panel in the project and  moves between the visualizations within that panel. Then, it moves to the next panel in the project and repeats. 
* We apply focus indicators so that sighted keyboard users have a clear indication of which UI element currently has focus. The indicator is a blue border around the selected element.

    ![Focus Indicator](assets/focus-indicator.png)

### Keyboard navigation for the menu bar 

1. Tab until you have reached the menu bar.
1. Use left/right arrow keys to navigate to the menu you want.
1. Press `Enter` to select the menu and show its options.
1. Use up/down arrow keys to navigate to the menu option you want.
1. Press `Enter` to select the option.

### Keyboard navigation for drag & drop interactions 

[!UICONTROL Analysis Workspace] is a drag & drop user interface. However, users can add components using the keyboard instead:

1. Tab to a component in the left rail.
1. Press `Enter` to select.
1. Use arrow keys to navigate to the area where you want to drop the component.
1. Press `Enter` to place the component.

### Keyboard shortcuts (hotkeys) 

[!UICONTROL Analysis Workspace] offers a rich set of [keyboard shortcuts](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html) for a more seamless workflow. Some common shortcuts for navigation, analysis creation, and insight democratization are listed below. 

#### Navigation

| Shortcut | Action |
| --- | --- |
| `[Alt + Shift + 1 / 2 / 3]` | Jump to different rails: [!UICONTROL Panels], [!UICONTROL Visualizations], or [!UICONTROL Components] | 
| `[Alt + Left / Right]` | Navigate between panels |
| `[Alt + M]` | Collapse/expand all panels |
| `[Alt + Ctrl + M]` | Collapse/expand active panel |
| `[Ctrl + /]` | Search left rail |

#### Analysis creation

| Shortcut | Action |
| --- | --- |
| `[Alt + 1]` | New freeform table |
| `[Ctrl + Shift + C]` | New calculated metric |
| `[Ctrl + Shift + D]` | New date range |
| `[Ctrl + Shift + E]` | New segment |
| `[Ctrl + Z]` | Undo |
| `[Component drag + Shift]` | Create a drop-down filter |

#### Democratization

| Shortcut | Action |
| --- | --- |
| `[Ctrl + S]` | Save |
| `[Ctrl + Shift + G]` | Curate |
| `[Ctrl + G]` | Share |
| `[Alt + Shift + S]` | Schedule |
| `[Alt + L]` | Get link to project |
| `[Ctrl + Shift + B]` | Download PDF |

## Support for screen readers and screen magnifiers

A screen reader reads text that appears on the computer screen. It also reads non-textual information, such as button labels or image descriptions in the application, provided in accessibility tags or attributes.  

## Color palettes & contrast  

[!UICONTROL Analysis Workspace] strives for WCAG 2.1 AA conformance, including requirements for color contrast. 

In addition, users can set their own preferred color palette for a project under **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Project color palette](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html). 

## Required field validation in component builders 

When building a component, required fields are validated when you save. If a required field does not pass validation, it will be outlined in red with an error icon. A written description appears of the issue that needs to be fixed.  

Once a component is fully validated, pressing `Save` closes the builder. 

![Error validation](assets/error-validation.png)

## Support for operating system accessibility features  

Analysis Workspace supports built-in MS Windows and macOS accessibility features like high-contrast mode, sticky keys, and slow keys/filter keys. It also provides information about the user interface to the operating system to enable interaction with assistive technologies, including screen readers such as VoiceOver for macOS and NVDA on Windows.

-->