---
title: Regional datainsamling
description: Information om regional datainsamling
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 1%

---


# Regional datainsamling

Adobe Experience Cloud använder Regional Data Collection (RDC) så att interaktionen mellan slutanvändarna och Adobe Experience Cloud sker så nära slutanvändarna som möjligt. Detta förbättrar prestanda för er webbplats/app och säkerställer att data samlas in så snabbt som möjligt för att optimera slutanvändarens upplevelse. När data från dina digitala egenskaper samlas in lokalt på ett datainsamlingscenter (DCC) vidarebefordras de via en säker anslutning till ett datacenter där de bearbetas och görs tillgängliga för produkter i Adobe Experience Cloud.

>[!IMPORTANT]
>
>Det kinesiska paketet för prestandaoptimering (Kina Performance Optimization) är ett tilläggsprogram som kan debiteras Adobe Analytics. Adobe prestandaoptimering på det kinesiska fastlandet gör det möjligt för kunder i Kina att skicka data direkt till den kinesiska kantnoden i stället för till andra platser globalt. Detta förbättrar sidinläsningstiden och datakvaliteten jämfört med att skicka data till noder utanför Kina. Kontakta din säljare på Adobe för mer information.

Följande platser (kan ändras) ingår för närvarande i RDC:

## Insamling av data från tredje part och HTTP

| Typ av domänkontrollant | Datainsamlingscentral |
|---------------------|-------------------|
| Standard | Oregon, Virginia, Irland, Paris, Mumbai, Singapore, Tokyo, Sydney |

Obs! Om din Analytics-bildförfrågan skickas till `adobedc`slutpunkterna `2o7.net` eller `omtrdc.net` slutpunkterna har du en datainsamling från tredje part. Du kan avgöra detta om du ser någon av slutpunkterna i URL:en för dina förfrågningar.

## Insamling av HTTPS-data från första part

| Typ av domänkontrollant | Datainsamlingscentral |
|---------------------|-------------------|
| Global (standard) | Oregon, Virginia, Irland, Paris, Mumbai, Singapore, Tokyo, Sydney |
| Endast Amerika | Oregon, Virginia |
| Endast Europa | Irland, Paris |
| Endast Asien och Stillahavsområdet | Mumbai, Singapore, Tokyo, Sydney |

Obs! Experience Edge Global ger bästa prestanda för dina slutanvändare.  Om du vill använda en alternativ RDC-typ kontaktar du Adobe kundtjänst.

## Så här fungerar RDC

I följande lista beskrivs den datainsamlingsprocess som används av Adobe:

1. DNS löser automatiskt samlingens värdnamn till IP-adressen för datainsamlingscentret som finns närmast besökaren.
1. Besökaren skickar data till den platsen.
1. Uppgifterna vidarebefordras omedelbart via en säker anslutning till Data Processing Center, där de behandlas och görs tillgängliga för Adobe Experience Cloud-produkterna.
