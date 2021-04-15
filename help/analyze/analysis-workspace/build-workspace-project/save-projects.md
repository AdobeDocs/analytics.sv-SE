---
description: Lär dig mer om de olika alternativen för att spara automatiskt, spara som och spara som mall.
title: Spara projekt
feature: Grundläggande om arbetsytan
role: Business Practitioner, Administrator
exl-id: e8206956-6e24-4a3a-8c3f-8acf1fb9d800
translation-type: tm+mt
source-git-commit: b6bf9e97c2eada3b9510d50c4c9196d7b09b5a65
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 2%

---

# Spara projekt

Om du vill spara ändringarna i ett projekt går du till menyn Arbetsyta **[!UICONTROL Project]**. Dessutom sparar Adobe projekt automatiskt i vissa fall.

## Spara projektalternativ {#Save}

Det finns olika åtgärder att spara som du kan utföra under menyn **[!UICONTROL Project]**, beroende på hur du vill komma åt analysen i framtiden.

| Åtgärd | Beskrivning |
|---|---| 
| **[!UICONTROL Save]** | Spara ändringar i projektet. Om projektet delas visas även ändringarna av projektmottagarna. När du sparar projektet första gången uppmanas du att ge projektet ett namn, en (valfri) beskrivning och (valfritt) att lägga till taggar. |
| **[!UICONTROL Save with notes]** | Lägg till anteckningar om vad som ändrats i projektet innan projektet sparas. Anteckningarna lagras med projektversionen och är tillgängliga för alla redigerare under Projekt > Öppna föregående version. |
| **[!UICONTROL Save as]** | Skapa en kopia av projektet. Det ursprungliga projektet påverkas inte. |
| **[!UICONTROL Save as template]** | Spara projektet som en [anpassad mall](https://docs.adobe.com/content/help/sv-SE/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html) som blir tillgänglig för din organisation under **[!UICONTROL Project > New]** |

![](assets/save-project.png)

## Spara {#Autosave} automatiskt

Befintliga projekt, dvs. projekt som har sparats minst en gång tidigare, sparas automatiskt varannan minut på den lokala datorn. Nya projekt som aldrig har sparats sparas för närvarande inte automatiskt.

Det finns några scenarier som kan leda dig bort från osparade ändringar i ett projekt, vilket resulterar i olika tillgängliga åtgärder.

### Öppna ett annat arbetsyteprojekt

I Adobe kan du spara innan du lämnar sidan. När du har lämnat ett befintligt projekt tas den automatiskt sparade lokala kopian bort.

![](assets/existing-save.png)

### Navigera bort eller stänga en flik

Webbläsaren varnar för att ändringar som inte sparats går förlorade. Du kan välja att avbryta eller avbryta.

![](assets/browser-image.png)

### Webbläsaren kraschar eller sessionstider ut

När användaren återgår till arbetsytan för **befintliga**-projekt visas en modal **projektåterställning**. Om du väljer Ja återställs projektet från den automatiskt sparade lokala kopian. &quot;Nej&quot; tar bort den automatiskt sparade lokala kopian och öppnar den senast sparade versionen av projektet.

![](assets/project-recovery.png)

För **nya**-projekt som aldrig har sparats går det inte att återställa ändringar som inte har sparats.

## Öppna föregående version {#previous-version}

Så här öppnar du en tidigare version av ett projekt:

1. Gå till Projekt > Öppna föregående version
1. Granska listan över tidigare versioner. Tidsstämpel och redigerare tillhandahålls, förutom anteckningar om de lades till när redigeraren sparades. Versioner utan anteckningar lagras i 90 dagar. versioner med anteckningar lagras i ett år.
1. Välj en tidigare version och klicka på Läs in.
1. Den föregående versionen läses in med ett meddelande. Den tidigare versionen blir inte den aktuella sparade versionen av projektet förrän du klickar på Spara. Om du navigerar bort från den inlästa versionen visas den senast sparade versionen av projektet när du kommer tillbaka.
