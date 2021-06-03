---
description: En omfattande lista med beskrivningar av konfigurationsvariabler, HTTP-huvuden och datasignaler i vidarebefordringsanrop på serversidan.
title: Vidarebefordra data och kodreferenser på serversidan
uuid: 3eb3ea0f-a530-448d-bba5-6408b2490dc8
exl-id: 6ab7bbb6-0709-427b-b9fa-a179dbe55fc9
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 2%

---

# Vidarebefordra data och kodreferenser på serversidan

En omfattande lista med beskrivningar av konfigurationsvariabler, HTTP-huvuden och datasignaler i vidarebefordringsanrop på serversidan.

## Konfigurationsvariabler {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Parametrar som har prefixats med `d_*` identifierar speciella nyckelvärdepar på systemnivå som används av våra [datainsamlingsservrar](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html) (DCS). Se även [Attribut som stöds för DCS API-anrop](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html).

| Parameter | Beskrivning |
|--- |--- |
| d_rs | (Hämtas med äldre/spårningsserverbaserad vidarebefordring på serversidan) <br>Ange till rapportsviterna som skickades med träffen till Analytics. |
| d_dst_filter | (Hämtas med rapportsvitbaserad vidarebefordring på serversidan) <br>Ange till rapportsvitens ID som skickades med träffen till Analytics. |
| d_dst | Ange d_dst=1 <br>om Analytics-begäran förväntar att innehåll om målet ska skickas tillbaka till klienten. |
| d_mitt | Experience Cloud-ID:t skickades till Analytics. |

## HTTP-huvuden {#section_0549705E76004F9585224AEF872066C0}

Dessa rubriker är fält som innehåller information som förfrågningar om data och svar i ett HTTP-anrop.

<!-- Meike, missing link in table below: "See Understanding Calls to the Demdex Domain" -->

| HTTP-huvud | Beskrivning |
|--- |--- |
| Värd | Detta ställs in på klientens specifika värdnamn för datainsamling som anges i konfigurationsfilen för analysvärden. Det ser ut som   `host name .demdex.net` .  Se Förstå anrop till Demdex-domänen. |
| Användaragent | Ange användaragenthuvudet som skickas till Analytics. |
| X-Original-User-Agent | Ange bara om en alternativ användaragent har angetts av någon av dessa rubriker: </br>`X-Device-User-Agent\ ` </br>`X-Original-User-Agent\`   </br>`X-OperaMini-Phone-UA\`   </br>`X-Skyfire-Phone\`    </br>`X-Bolt-Phone-UA\` |
| X-Forwarded-For | Ange till IP-adressen för den begärande klienten. Analyserna har redan tolkat det inkommande `X-Forwarded-For`-huvudet och fastställt den korrekta IP-adressen som ska användas. |
| Acceptera språk | Ange till rubriken `Accept-Language` som skickas till Analytics. |
| Referent | Ange till den sid-URL som skickas till Analytics (Analyser) eller som samlats in från det referenshuvud som skickades till Analytics (Analyser). |

## Kunddefinierade signaler {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Parametrar som har `c_` som prefix identifierar kunddefinierade variabler. Se även [Attribut som stöds för DCS API-anrop](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html).

| Signal | Beskrivning |
|--- |--- |
| c_browserWidth och c_browserHeight | Bredd och höjd på webbläsarfönstret. |
| c_campaign | Anges av s.campaign . |
| c_channel | Anges av s.channel . |
| c_clientDateTime | Tidsstämpel formaterad som   dd/mm/yyy hh:mm:ss W TZ .    TZ är i minuter och matchar returvärdet för metoden Date.getTimezoneOffset. |
| c_colorDepth | Anges som 16- eller 32-bitars färg. |
| c_connectionType | Anger anslutningstyp. Alternativen är:<ul><li>modem</li><li>lan</li></ul> |
| c_contextData.* | Exempel:<ul><li>AppMeasurement: s.contextData</li><li>[&quot;category&quot;] = &quot;news&quot;;</li><li>Signal:  c_contextData.category=news</li></ul> |
| c_cookiesEnabled | Anger om cookies kan aktiveras. Alternativen är: ja, nej, okänd |
| c_currencyCode | Typ av valuta som används för transaktionen. |
| c_evar# | Egna evar |
| c_events | Anges av s.events . |
| c_hier# | Anpassade hierarkivariabler. |
| c_javaEnabled | Anger om Java kan aktiveras. Alternativen är: ja, nej, okänd |
| c_javaScriptVersion | Den version av JavaScript som stöds av en webbläsare. |
| c_latitude | Numerisk latitud |
| c_linkClick | Alternativen är: anpassad nedladdning avsluta |
| c_linkCustomName | Det anpassade namn (om det finns något) som anges för länken. |
| c_linkDownloadURL | URL för nedladdningslänkar. |
| c_linkExitURL | URL:en för avslutningslänken. |
| c_list# | Egna listvariabler. |
| c_longitude | Numerisk longitud. |
| c_mediaPlayerType | För begäranden om spårning av medieströmmar. Alternativen är:  annan, primetime |
| c_pageName | Sidnamnet (om det har angetts). |
| c_pageURL | Adressen till sidan i webbläsarens adressfält. |
| c_products | Produktsträngen (anges med s.products ). |
| c_prop | Egna proppar. |
| c_purchaseID | Ett unikt ID för köpet. |
| c_reference | Sidan före den aktuella sidan. |
| c_screenResolution | Skärmbredd och -höjd (i pixlar). |
| c_server | Webbservernamn (anges av s.server). |
| c_state | Geografisk region (anges med s.state). |
| c_timezone | Tidsförskjutning (i timmar). |
| c_transactionID | Ett unikt ID för en transaktion. |
| c_zip | Postnummer (anges med s.zip). |
