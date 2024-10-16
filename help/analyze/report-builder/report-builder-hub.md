---
title: Vad är Report Builder Hub i Adobe Analytics?
description: Beskriver komponenterna för Report Builder Hub
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: eedabc6295f9b918e1e00b93993680e676c216c3
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---

# Report Builder Hub

Använd Report Builder nav för att skapa, uppdatera, ta bort och hantera datablock.

Navet Report Builder innehåller knapparna Skapa och Hantera, KOMMANDON och QUICK EDIT-panelerna.

<img src="./assets/hub51.png" alt="Report Builder Hub"/>


## Knapparna Skapa, Hantera och Schemalägg

Använd knapparna Skapa, Hantera och Schemalägg för att skapa nya datablock, hantera befintliga datablock eller schemaläggningsdatabaser.

## KOMMANDON

Använd KOMMANDON-panelen för att komma åt kommandon som är kompatibla med de markerade cellerna eller en tidigare åtgärd.

### Kommandon

| Visade kommandon | Tillgängligt när.. | Syfte |
|------|------------------|--------|
| Skapa datablock | En eller flera celler markeras i arbetsboken. | Används för att skapa ett datablock |
| Redigera datablock | Det markerade cellområdet eller cellområdet ingår endast i ett datablock. | Används för att redigera ett datablock |
| Uppdatera datablock | Markeringen innehåller minst ett datablock. Kommandot uppdaterar bara de markerade datablocken. | Används för att uppdatera ett eller flera datablock |
| Uppdatera alla datablock | Arbetsboken innehåller ett eller flera datablock. | Används för att uppdatera ALLA datablock i arbetsboken |
| Skicka arbetsbok |   | Skicka en arbetsbok enligt ett schema. |
| Kopiera datablock | Det markerade cellområdet eller cellområdet ingår i ett eller flera datablock. | Används för att kopiera ett datablock |
| Ta bort datablock | Det markerade cellområdet eller cellområdet ingår endast i ett datablock. | Används för att ta bort ett datablock |

## SNABBREDIGERING, panel

När du markerar ett eller flera datablock i ett kalkylblad visas panelen QUICK EDIT i Report Builder. Du kan använda panelen QUICK EDIT för att ändra parametrar i ett enda datablock eller för att ändra parametrar i flera datablock samtidigt.

![Panelen Snabbredigering i Report Builder](./assets/hub2.png)

De ändringar du gör i snabbredigeringsavsnitten gäller för alla markerade datablock.

### Rapportsviter

Datablocken hämtar data från ett valt rapportpaket. Om flera datablock är markerade i ett kalkylblad och de inte hämtar data från samma rapportserie, visas länken **Rapportsviter** *Flera*.

När du ändrar rapportsviten antar alla datablock i urvalet den nya rapportsviten. Komponenterna i datablocket matchas mot den nya rapportsviten baserat på ID, till exempel matchning av ```evars```). Om en komponent inte hittas i ett datablock visas ett varningsmeddelande och komponenten tas bort från datablocket.

Om du vill ändra rapportsviten väljer du en ny rapportserie i listrutan.

![Navet Report Builder visar listrutan för rapportsviten.](./assets/image16.png)

### Datumintervall

**[!UICONTROL Date range]** visar datumintervallet för de markerade datablocken. Om flera datablock har markerats med flera datumintervall visas **[!UICONTROL Date range]**-länken *Flera*.

### Filter

Länken **Filter** visar en sammanfattningslista över de filter som används av de markerade datablocken. Om flera datablock har markerats med flera filter visas länken **Filter** *Flera*.
