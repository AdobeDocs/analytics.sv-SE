---
title: VISTA-regler i Adobe Analytics
description: Läs mer om VISTA-regler och deras funktioner.
exl-id: fab2acc3-b037-48f9-bb20-625ccb75b4cc
feature: Analytics Basics
source-git-commit: c697530103ea7cd279cc3560c1daec796759e7a1
workflow-type: tm+mt
source-wordcount: '263'
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

Många användningsområden för VISTA-regler finns redan i [Bearbetar regler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md), [Punktregler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md), [Virtuella rapportsviter](/help/components/vrs/vrs-about.md)eller bara uppdatera er Adobe Analytics-implementering. Adobe rekommenderar endast VISTA-regler som en sista utväg.

>[!IMPORTANT]
>
>VISTA-reglerna kräver ett betalt avtal mellan er organisation och Adobe Professional Services. Kontakta kontoteamet på Adobe om du vill skapa eller uppdatera en VISTA-regel.

## Skapa en VISTA-regel

Du måste arbeta med Adobe Professional Services för att kunna skapa en VISTA-regel. Kontakta kontoteamet på Adobe om du vill skapa en VISTA-regel.

## Se befintliga VISTA-regler

Adobe har inget gränssnitt för att visa befintliga VISTA-regler. Kontakta kontoteamet eller kundtjänst på Adobe med önskad rapportsvit för att få en lista över befintliga VISTA-regler.
