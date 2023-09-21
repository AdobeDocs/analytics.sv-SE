---
title: Timme
description: Den timme som mätvärdet inträffade på.
feature: Dimensions
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---

# Timme

Timme [dimension](overview.md) rapporterar timmen då ett givet mätresultat inträffade (avrundat nedåt). Den första dimensionsartikeln är den första timmen i datumintervallet, och den sista dimensionsartikeln är den sista timmen i datumintervallet. Denna dimension är värdefull för trendrapporter eftersom den gör att du kan se mätvärden över tid.

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensioner

Dimensioner omfattar en viss timme inom rapportens datumintervall tillsammans med dess datum. Det är formaterat som `HH:HH YYYY-MM-DD`.

## Besparingstid för dagsljus

Sommartid är en övning där klockor ställs in en timme framåt på våren och backa en timme i hösten. Om DST används i en rapportsvits tidszon justerar Adobe data efter den timmen.

* **När sommartid börjar**: I mars visar rapporter vanligtvis ett timgap i data där sommartid börjar. Timmen fanns inte, så den ingår inte i datainsamlingen. Observera att en liten mängd data fortfarande kan göra det till den här timmen. Adobe datainsamlingsservrar tar flera sekunder (upp till en minut) att ta hänsyn till DST-justeringar.
* **När sommartid slutar**: I november visas vanligtvis en dubbel-staplad timme där sommartid tar slut. Timmen inträffade två gånger, så båda timmarna sammanställs i rapporter.
