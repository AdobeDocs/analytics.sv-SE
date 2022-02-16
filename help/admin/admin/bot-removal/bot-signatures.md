---
title: Vanliga robotsignaturer
description: Identifiera vanliga identifierare för botar.
feature: Admin Tools
exl-id: 57622af6-c1d3-4ef1-b3e6-10c14f04a55c
source-git-commit: ee56267979979f8e03b1c6a0d849ccf994599024
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 0%

---

# Vanliga robotsignaturer

När du identifierar botar i en datauppsättning är det olika beroende på miljön, men det finns några vanliga sätt att identifiera botar.

## Ett stort antal sidvisningar per besök

Du kan hämta en Data warehouse-rapport med IP-adress, sidvisningar och unika besökare. Skapa sedan en &#x200B; i Excel för att se hur sidorna ser ut vid varje besök och sortera från högst upp till lägst. Bots har vanligtvis ett mycket stort antal sidvisningar per besök (flera hundra till tusentals). Du kommer att se en kraftig nedgång när du övergår till faktisk trafik.

## Ingen referent

Bots har vanligtvis ingen hänvisande URL. I segmentering kan detta filtreras som `Referring Domain equals Typed/Bookmarked`.

## Konstiga användaragenter

Bok använder ofta anpassade användaragenter som inte är klassificerade i webbläsardimensionen eller visas som en `unknown` version av en standardwebbläsare. Okänd Safari och okänd Opera har en extremt hög sannolikhet för att vara botar.

## Linux eller&quot;Ej specificerad&quot; operativsystem

Vi vill inte misskreditera det fantastiska Linux-operativsystemet med öppen källkod, men det verkar som om det är att sätta det som operativsystem. Var dock försiktig med att utesluta legitim trafik från Linux-användare. Bots gillar också att inte ställa in ett operativsystem, som kan segmenteras som `Operating System &#x200B;equals Not Specified`.

## Sidvyer = besök = unika besökare

Detta gäller särskilt användaragentrapporten. Som du ser i skärmbilden nedan har den&quot;okända versionen&quot; av dessa webbläsare nästan samma antal besökare som unika besökare (och nästan samma antal sidvisningar). Detta kan isoleras i segmenteringen genom att man bygger upp en [!UICONTROL Include] behållare för `Single Page Visits equals Enabled` eller `Hit Depth is less than 2`.

![](assets/bots-browsers-unknown.png)

## Besök nummer 1

Bots får vanligtvis ett nytt besökar-ID varje gång de genomför ett besök och all trafik består av besöksnumret 1.

## Lägre skärmupplösningar

Moderna användare har mycket högre upplösningsskärmar än tidigare. Träffar med följande upplösningar verkar vara mycket populära för bots:

* 1024 x 768 &#x200B; &#x200B;
* 1 366 x 768
* 1 600 x 864
* 800 x 600
* 1600 x 1200
* Ej angivet
* 1024 x 667

## Land + tidszon matchar inte

Det skulle finnas en felmatchning mellan det ursprungliga landet och tidszonen. Platsen kan till exempel vara USA men tidszonen kan vara GMT.

![](assets/bots-country-time-zone.png)

## Inte inloggad

Användaren loggar inte in på något ställe under sitt besök och användaridentifierings-eVars finns inte kvar från tidigare besök. Vissa botar kan konfigureras för att autentiseras, men majoriteten är inte så smarta.

## Inga nyckeltal finns på besök

Bok lägger vanligtvis inte till produkter i en kundvagn eller checkar ut. Oftast skickar de inte in blanketter för leads eller andra framgångshändelser, men vissa av dem skickar enkla HTML-blanketter. &#x200B;

## Specifik frågesträng finns

Ibland försöker bots att bust cache-lagra eller på annat sätt bryta webbplatser genom att trycka på felformaterade URL:er eller URL:er som inte finns (som vanliga LAMP- eller Wordpress-administratörssidor) eller genom att lägga till specifika frågesträngar.

## IP-adresser som härstammar från distribuerade datorplattformar

Webbhotell som Amazon Web Services eller Google Cloud kan missbrukas som båda gårdar. De här IP-adresserna löper stor risk att bli botar: &#x200B;
* [Google Cloud](https://cloud.google.com/compute/): IP-adressen börjar med `&#x200B;35.199` eller `35.194&#x200B;`
