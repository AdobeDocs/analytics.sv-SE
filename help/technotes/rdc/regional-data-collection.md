---
title: Regional datainsamling
description: Information om regional datainsamling
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: e2fd69043e198d855dddd316b04215fde9f52cad
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 1%

---

# Regional datainsamling

Adobe Experience Cloud använder Regional Data Collection (RDC) så att interaktionen mellan slutanvändarna och Adobe Experience Cloud sker så nära slutanvändarna som möjligt. Detta förbättrar prestanda för er webbplats/app och säkerställer att data samlas in så snabbt som möjligt för att optimera slutanvändarens upplevelse. När data från dina digitala egenskaper samlas in lokalt på ett datainsamlingscenter (DCC) vidarebefordras de via en säker anslutning till ett datacenter där de bearbetas och görs tillgängliga för produkter i Adobe Experience Cloud.

>[!IMPORTANT]
>
>Det kinesiska paketet för prestandaoptimering (Kina Performance Optimization) är ett tilläggsprogram som kan debiteras Adobe Analytics. Adobe prestandaoptimering på det kinesiska fastlandet gör det möjligt för kunder med användare i Kina att få dessa data skickade direkt till den kinesiska kantnoden i stället för till andra platser globalt. Detta förbättrar sidinläsningstiden och datakvaliteten jämfört med att skicka data till noder utanför Kina. Kontakta din säljare på Adobe för mer information.

Följande platser (kan ändras) ingår för närvarande i RDC:

## Insamling av data från tredje part och HTTP

| Typ av domänkontrollant | Datainsamlingscentral |
|---------------------|-------------------|
| Standard | Oregon, Virginia, Irland, Paris, Mumbai, Singapore, Tokyo, Sydney, Kina* |

*China RDC kräver China Add-On-paketet. Se&quot;Viktigt&quot;-texten ovan.

>[!NOTE]
>
>Om din Analytics-bildförfrågan skickas till `adobedc`, `2o7.net` eller `omtrdc.net` slutpunkter, och sedan har du datainsamling från tredje part. Du kan avgöra detta om du ser någon av slutpunkterna i URL:en för dina förfrågningar.

## Insamling av HTTPS-data från första part

| Typ av domänkontrollant | Datainsamlingscentral |
|---------------------|-------------------|
| Global (standard) | Oregon, Virginia, Irland, Paris, Mumbai, Singapore, Tokyo, Sydney |
| Global + Kina* | Kina*, Oregon, Virginia, Irland, Paris, Mumbai, Singapore, Tokyo, Sydney |
| Endast Amerika | Oregon, Virginia |
| Endast Europa | Irland, Paris |
| Endast Asien och Stillahavsområdet | Mumbai, Singapore, Tokyo, Sydney |
| Endast Kina* | Beijing |

*Endast Kina och Global + China RDC-typer kräver paketet China Add-On. Se&quot;Viktigt&quot;-texten ovan. Global + Kina kommer att dirigera data med ursprung i Kina till vår kinesiska lokala domänkontrollant medan data med ursprung utanför Kina slussas vidare till närmaste lokala domänkontrollant utanför Kina.

>[!NOTE]
>
>Experience Edge Global ger bästa prestanda för dina slutanvändare.  Om du vill använda en alternativ RDC-typ kontaktar du Adobe kundtjänst för att få hjälp.

## Fördelar med RDC

| Fördelar | Beskrivning |
| --- | --- |
| Prestanda | Med RDC kan besökarna ansluta till närmaste DCC. Detta ger den snabbaste svarstiden, vilket ger mer exakt spårning och snabbare laddningstider. |
| Redundans | Om kommunikationen mellan DCC och din DPC avbryts, sparar Adobe RDC-infrastruktur data lokalt och vidarebefordrar den sedan till DPC när kommunikationen återställs. |

## Så här fungerar RDC

I följande lista beskrivs den datainsamlingsprocess som används av Adobe:

1. DNS löser automatiskt samlingens värdnamn till IP-adressen för datainsamlingscentret som finns närmast besökaren.
1. Besökaren skickar data till den platsen.
1. Uppgifterna vidarebefordras omedelbart via en säker anslutning till Data Processing Center, där de behandlas och görs tillgängliga för Adobe Experience Cloud-produkterna.
