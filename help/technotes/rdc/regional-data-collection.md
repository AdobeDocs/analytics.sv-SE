---
title: Regional datainsamling
description: Information om regional datainsamling
feature: Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: f75d123c93d446776492dd933d03d32c2496fa69
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Regional datainsamling

Adobe Experience Cloud använder Regional Data Collection (RDC) så att interaktionen mellan besökarna och Adobe sker så nära besökarna som möjligt. När data har samlats in regionalt på ett datainsamlingscenter (DCC) vidarebefordras de via en säker anslutning till ett datacenter (DPC). Efter bearbetning är uppgifterna tillgängliga för Adobe Experience Cloud-produkter. Kontakta Adobe kundtjänst om du vill ändra din RDC-typ.

I den regionala datainsamlingsprocessen används följande steg:

1. DNS löser automatiskt samlingens värdnamn till IP-adressen för datainsamlingscentret närmast besökaren.
1. Besökaren skickar data till den platsen.
1. Uppgifterna vidarebefordras omedelbart via en säker anslutning till Data Processing Center, där de behandlas och görs tillgängliga för Adobe Experience Cloud-produkterna.

Att använda regional datainsamling ger flera fördelar:

* **Prestanda**: Med RDC kan besökarna ansluta till närmaste DCC. Denna optimering ger den snabbaste svarstiden, vilket ger mer exakt spårning och snabbare laddningstider.
* **Redundans**: Om kommunikationen mellan DCC och din DPC avbryts, sparar Adobe RDC-infrastrukturen data lokalt och vidarebefordrar den sedan till DPC när kommunikationen återställs.

Följande platser (kan ändras) ingår för närvarande i RDC:

## Datainsamling från tredje part

| Typ av domänkontrollant | Datainsamlingscentral |
| --- | --- |
| Standard | Oregon, Virginia, Irland, Paris, Mumbai, Singapore, Tokyo, Sydney, Kina* |

{style="table-layout:auto"}

*China RDC kräver China Add-On-paketet. Se [Prestandaoptimering för Kina](#china-performance-optimization) nedan.

>[!NOTE]
>
>Om din Analytics-bildförfrågan skickas till `adobedc.net`, `2o7.net` eller `omtrdc.net` slutpunkter, och sedan har du datainsamling från tredje part. Du kan avgöra detta om du ser någon av slutpunkterna i URL:en för dina förfrågningar.

## Insamling av data från första part

| Typ av domänkontrollant | Datainsamlingscentral |
| --- | --- |
| Global (standard) | Oregon, Virginia, Irland, Paris, Mumbai, Singapore, Tokyo, Sydney |
| Global + Kina* | Kina*, Oregon, Virginia, Irland, Paris, Mumbai, Singapore, Tokyo, Sydney |
| Endast Amerika | Oregon, Virginia |
| Endast Europa | Irland, Paris |
| Endast Asien och Stillahavsområdet | Mumbai, Singapore, Tokyo, Sydney |
| Endast Kina* | Beijing |

{style="table-layout:auto"}

*Endast Kina och Global + China RDC-typer kräver paketet China Add-On. Global + Kina skickar data från Kina till Adobe Kina och skickar data med ursprung utanför Kina till närmaste lokala domänkontrollant utanför Kina. Se [Prestandaoptimering för Kina](#china-performance-optimization) nedan.

## Prestandaoptimering för Kina

Tilläggspaketet för Kina-prestandaoptimering (RDC) är ett avgiftsbelagt tillägg till Adobe Analytics. Adobe Performance Optimization in Mainland China gör det möjligt för kunder med användare i Kina att skicka dessa data direkt till Adobe datainsamlingsservrar i Kina i stället för till andra platser globalt. Denna optimering förbättrar sidinläsningstiden och datakvaliteten jämfört med att skicka data till platser utanför Kina. Data överförs slutligen till ett av Adobe databearbetningscenter (DPC) utanför Kina. Kontakta din säljare på Adobe för mer information.

>[!NOTE]
>
>Det kinesiska RDC-tilläggspaketet stöds inte för [Web SDK](/help/implement/aep-edge/overview.md).

