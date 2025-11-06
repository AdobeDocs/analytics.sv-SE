---
title: VISTA-regler i Adobe Analytics
description: Läs mer om VISTA-regler och deras funktioner.
exl-id: fab2acc3-b037-48f9-bb20-625ccb75b4cc
feature: Analytics Basics
source-git-commit: b1c22031b9254ff077dfdc04ab90ab231b504299
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 0%

---

# VISTA-regler i Adobe Analytics

VISTA-regler är en alternativ form av anpassad dataändring som du kan använda mellan datainsamling och bearbetning. Se [Bearbetningsordning](processing-order.md) om du vill ha mer information om exakt vilket stadium i dataredjan som VISTA-regler gäller för. VISTA-reglerna påverkar endast aktuella data när de samlas in, men ändrar inte befintliga data.

Några vanliga användningsområden för VISTA-reglerna är:

* Kopiera en Analytics-träff från en rapportserie till en annan, och ändra data till den kopierade rapportsviten om du vill
* Anpassat IP-undantag som överskrider de användningsfall som erbjuds av [Uteslut av IP](/help/admin/tools/exclude-ip.md)
* Ändra ett variabelvärde villkorligt eller globalt
* Duplicera variabelvärden till andra variabler
* Överför filer till en Adobe FTP-plats som kan påverka variabelvärden

Många användningsexempel för VISTA-regler finns redan i [Bearbetningsregler](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md), [PUNKTSREGLER](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md), [Virtuella rapportsviter](/help/components/vrs/vrs-about.md) eller bara när du uppdaterar din Adobe Analytics-implementering. Adobe rekommenderar endast VISTA-regler som en sista utväg.

>[!IMPORTANT]
>
>Implementering och konfigurering av VISTA-regler kräver ett betalt avtal mellan din organisation och Adobe Professional Services. Kontakta Adobe Account Team om du vill skapa eller uppdatera en VISTA-regel.
>
>Observera:
>
>* Skapande av VISTA-regel inkluderar endast den inledande implementeringen. Löpande underhåll eller uppdateringar av VISTA-regler kräver ett separat betalt åtagande.
>
>* VISTA-reglerna bygger på specifika villkor i dina data. Om du till exempel ändrar implementeringen av Adobe Analytics, datatyperna eller längden på strängar som samlas in, ändringar av tabellerna som används för DB VISTA eller andra ändringar av indatamönster kan det leda till att en VISTA-regel slutar fungera som förväntat. Adobe rekommenderar att du regelbundet granskar VISTA-reglerna för att avgöra om uppdateringar eller borttagning behövs.

## Skapa en VISTA-regel {#create}

Du måste arbeta med Adobe Professional Services för att kunna skapa en VISTA-regel. Kontakta Adobe Account Team om du vill skapa en VISTA-regel.

## Se befintliga VISTA-regler {#see}

Adobe har inget gränssnitt för att visa befintliga VISTA-regler. Kontakta Adobe Account Team eller kundtjänst och be om en lista över befintliga VISTA-regler.
