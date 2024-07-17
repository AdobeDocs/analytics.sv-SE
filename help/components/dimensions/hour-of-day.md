---
title: Timme på dagen
description: Dagens numeriska timme, oavsett vilken dag.
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 0%

---

# Timme på dagen

Timme för dag [dimension](overview.md) rapporterar den numeriska timmen för en given dag som en dimensionspost. Om du till exempel har en rapport som sträcker sig från 1 januari till 7 grupperas den första timmen för varje dag till samma dimensionsobjekt. Den här rapporten är värdefull om du vill att en rapport ska delas upp efter relativ tid på dagen, men inte vill ha en statisk timme som dimensionsobjekt. Det är särskilt värdefullt som en dimension i schemalagda rapporter, eftersom den här dimensionen följer det valda datumintervallet.

Denna dimension baseras på rapportsvitens tidszon, och inte på besökarens lokala tidszon. Om din rapportsvit till exempel är i Berg och en besökare i Kalifornien besöker din webbplats kl. 10.00 PST-tid, grupperar träffarna under dimensionsposten `11:00 AM`. Om du vill ha en dimension som registrerar den lokala besökarens tid rekommenderar Adobe att du använder plugin-programmet [getTimeParting](/help/implement/vars/plugins/gettimeparting.md).

## Fyll den här dimensionen med data

Den här dimensionen fungerar som den ska för alla implementeringar. Om en rapportsvit innehåller data fungerar den här dimensionen.

## Dimensioner

Dimensionen innehåller `12:00 AM` - `11:00 PM` som representerar timmen på dagen då träffen inträffade (avrundat nedåt). Om en träff till exempel genererades klockan 17:58 grupperas den under dimensionsobjektet `3:00 PM`.

## Besparingstid för dagsljus

Sommartid är en övning där klockor ställs in en timme framåt på våren och backa en timme i hösten. Om DST används i en rapportsvits tidszon justerar Adobe data efter den timmen.

* **När sommartid börjar**: I mars visas vanligtvis ett timintervall i data där sommartid börjar. Timmen fanns inte, så den ingår inte i datainsamlingen. Observera att en liten mängd data fortfarande kan göra det till den här timmen. Adobe datainsamlingsservrar tar flera sekunder (upp till en minut) att ta hänsyn till DST-justeringar.
* **När sommartid slutar**: I november visas vanligtvis en dubbel staplad timme där sommartid slutar. Timmen inträffade två gånger, så båda timmarna sammanställs i rapporter.
