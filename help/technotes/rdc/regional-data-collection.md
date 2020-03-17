---
title: Regional datainsamling
description: Information om regional datainsamling
translation-type: tm+mt
source-git-commit: 449a64e361523d7a68514d60541c443a4f696c9d

---


# Regional datainsamling

Adobe Experience Cloud använder regional datainsamling (RDC) så att interaktionen mellan slutanvändarna och Adobe Experience Cloud sker så nära slutanvändarna som möjligt. Detta förbättrar prestanda för er webbplats/app och säkerställer att data samlas in så snabbt som möjligt för att optimera slutanvändarens upplevelse. När data från dina digitala egenskaper samlas in lokalt på ett datainsamlingscenter (DCC) vidarebefordras de via en säker anslutning till ett datacenter (DPC) där de bearbetas och görs tillgängliga för produkter i Adobe Experience Cloud.

Följande platser (kan ändras) ingår för närvarande i RDC:

## Insamling av data från tredje part och HTTP

| Typ av domänkontrollant | Datainsamlingscentral |
|---------------------|-------------------|
| Standard | Oregon, Virginia, Irland, Paris, Mumbai, Singapore, Tokyo, Sydney |

Obs! Om din Analytics-bildförfrågan skickas till `2o7.net` - eller `omtdrc.net` slutpunkterna har du en datainsamling från tredje part. Du kan avgöra detta om du ser någon av slutpunkterna i URL:en för dina förfrågningar.

## Insamling av HTTPS-data från första part

| Typ av domänkontrollant | Datainsamlingscentral |
|---------------------|-------------------|
| Global (standard) | Oregon, Virginia, Irland, Paris, Mumbai, Singapore, Tokyo, Sydney |
| Endast Amerika | Oregon, Virginia |
| Endast Europa | Irland, Paris |
| Endast Asien och Stillahavsområdet | Mumbai, Singapore, Tokyo, Sydney |

Obs! Experience Edge Global ger bästa prestanda för dina slutanvändare.  Om du vill använda en alternativ RDC-typ kontaktar du Adobes kundtjänst.

## Så här fungerar RDC

I följande lista beskrivs den datainsamlingsprocess som används av Adobe:

1. DNS löser automatiskt samlingens värdnamn till IP-adressen för datainsamlingscentret som finns närmast besökaren.
1. Besökaren skickar data till den platsen.
1. Informationen vidarebefordras omedelbart via en säker anslutning till Data Processing Center, där den behandlas och görs tillgänglig för produkterna i Adobe Experience Cloud.

## Fördelar med RDC

| Fördelar | Beskrivning |
|---------|-----------|
| Prestanda | Med RDC ansluter besökarna till närmaste DCC. Det innebär att svarstiderna på sidan minskar (lägre är bättre), vilket ger mer exakt spårning och snabbare laddningstider. |
| Redundans | Om kommunikationen med en DCC avbryts dirigeras datainsamlingen automatiskt till nästa närmaste DCC för att säkerställa tjänstens kontinuitet. |
| Redundans | Om kommunikationen mellan DCC och din DPC avbryts, sparar Adobes RDC-infrastruktur data lokalt och vidarebefordrar den sedan till DPC när kommunikationen återställs. |

## Versionshistorik för dokumentation

| Uppdatera | Beskrivning |
|--------|---------|
| 4 februari 2020 | Uppdatera RDC-platser |
| 20 februari 2019 | Fullständig omskrivning. Tillagd information om RDC-nätverk. |
