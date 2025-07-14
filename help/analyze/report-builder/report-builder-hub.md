---
title: Vad är Report Builder Hub i Adobe Analytics?
description: Beskriver Report Builder Hub-komponenterna
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: e18381ea-b7d4-4d7a-9ded-23b2d06fa204
source-git-commit: d3d74042f6c282db490483393f4b58cddd6b1525
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 1%

---

# Report Builder Hub

Använd Report Builder nav för att skapa, uppdatera, ta bort och hantera datablock.

Report Builder-hubben innehåller knapparna Skapa, Hantera och Schemalägg, KOMMANDON och QUICK EDIT-panelen.

<img src="./assets/hub51.png" alt="Report Builder Hub"/>


## Knapparna Skapa, Hantera och Schemalägg

Använd knapparna Skapa, Hantera och Schemalägg för att skapa nya datablock, hantera befintliga datablock eller schemaläggningsdatabaser.

## KOMMANDON

Använd KOMMANDON-panelen för att komma åt kommandon som är kompatibla med de markerade cellerna eller en tidigare åtgärd.

### Kommandon

| Visade kommandon | Tillgängligt när.. | Syfte |
|------|------------------|--------|
| Redigera datablock | Det markerade cellområdet eller cellområdet ingår endast i ett datablock. | Används för att redigera ett datablock |
| Uppdatera datablock | Markeringen innehåller minst ett datablock. Kommandot uppdaterar bara datablocken i markeringen. | Används för att uppdatera ett eller flera datablock |
| Uppdatera alla datablock | Arbetsboken innehåller ett eller flera datablock. | Används för att uppdatera ALLA datablock i arbetsboken |
| Skicka arbetsbok |   | Skicka en arbetsbok enligt ett schema. |
| Kopiera datablock | Det markerade cellområdet eller cellområdet ingår i ett eller flera datablock. | Används för att kopiera ett datablock |
| Klipp ut datablock |   | Används för att klippa ut ett datablock |
| Ta bort datablock | Det markerade cellområdet eller cellområdet ingår endast i ett datablock. | Används för att ta bort ett datablock |

## SNABBREDIGERING, panel

När du markerar ett eller flera datablock i ett kalkylblad visas panelen SNABBREDIGERING i Report Builder. Du kan använda panelen QUICK EDIT för att ändra parametrar i ett enda datablock eller för att ändra parametrar i flera datablock samtidigt.

![Panelen Snabbredigering i Report Builder](./assets/hub2.png)

De ändringar du gör i snabbredigeringsavsnitten gäller för alla markerade datablock.

### Rapportsviter

Datablocken hämtar data från ett valt rapportpaket. Om flera datablock är markerade i ett kalkylblad och de inte hämtar data från samma rapportserie, visas länken **Rapportsviter** *Flera*.

När du ändrar rapportsviten antar alla datablock i urvalet den nya rapportsviten. Komponenterna i datablocket matchas mot den nya rapportsviten baserat på ID, till exempel matchning av ```evars```). Om en komponent inte hittas i ett datablock visas ett varningsmeddelande och komponenten tas bort från datablocket.

Om du vill ändra rapportsviten väljer du en ny rapportserie i listrutan.

![Report Builder-hubben visar listrutan för rapportsviten.](./assets/image16.png)

### Datumintervall

**[!UICONTROL Date range]** visar datumintervallet för de markerade datablocken. Om flera datablock har markerats med flera datumintervall visas **[!UICONTROL Date range]**-länken *Flera*. [Läs mer](/help/analyze/report-builder/select-date-range.md)

### Segment

Länken **Segment** visar en sammanfattningslista över de segment som används av de markerade datablocken. Om flera datablock har markerats med flera segment visas länken **Segment** *Flera*. [Läs mer](/help/analyze/report-builder/work-with-segments.md)
