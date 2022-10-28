---
title: VISTA-regler i Adobe Analytics
description: Läs mer om VISTA-regler och deras funktioner.
source-git-commit: 1e2284fd4a62816b27b33a91f3bee2575a852107
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---


# VISTA-regler i Adobe Analytics

VISTA-regler är en alternativ form av anpassad dataändring som du kan använda mellan datainsamling och bearbetning. Se [Bearbetningsorder](processing-order.md) om du vill ha mer information om exakt hur långt i dataflödet VISTA-reglerna är. VISTA:s regler påverkar endast aktuella data när de samlas in, befintliga data inte ändras.

Några vanliga användningsområden för VISTA-reglerna är:

* Kopiera en Analytics-träff från en rapportserie till en annan, och ändra data till den kopierade rapportsviten om du vill
* Undantag för anpassad IP som överskrider användningsexemplen från [Exkludera efter IP](/help/admin/admin/exclude-ip.md)
* Ändra variabelvärden villkorligt eller globalt
* Duplicera variabelvärden till andra variabler
* Överför filer till en FTP-plats i Adobe som kan påverka variabelvärden

Många användningsområden för VISTA-regler finns redan i [Bearbetar regler](/help/admin/admin/c-processing-rules/processing-rules.md), [Punktregler](/help/admin/admin/bot-removal/bot-rules.md), [Virtuella rapportsviter](/help/components/vrs/vrs-about.md)eller bara uppdatera er Adobe Analytics-implementering. Adobe rekommenderar endast VISTA-regler som en sista utväg.

>[!IMPORTANT]
>
>VISTA-reglerna kräver ett betalt avtal mellan er organisation och Adobe Professional Services. Kontakta din organisations kontoansvarige på Adobe om du vill skapa eller uppdatera en VISTA-regel.

## Skapa en VISTA-regel

Du måste arbeta med Adobe Professional Services för att kunna skapa en VISTA-regel. Kontakta din organisations kontoansvarige på Adobe om du vill skapa en VISTA-regel.

## Se befintliga VISTA-regler

Adobe har inget gränssnitt för att visa befintliga VISTA-regler. Kontakta er kontoansvarige eller kundtjänst på Adobe för att få en lista över befintliga VISTA-regler.
