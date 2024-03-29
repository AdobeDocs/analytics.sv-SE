---
description: En omfattande lista med beskrivningar av konfigurationsvariabler, HTTP-huvuden och datasignaler i vidarebefordringsanrop på serversidan.
title: Vidarebefordra data och kodreferenser på serversidan
feature: Server-Side Forwarding
exl-id: 6ab7bbb6-0709-427b-b9fa-a179dbe55fc9
role: Admin
source-git-commit: def7d071de1765acf524a638a8f8d13ae69e1a1f
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 1%

---

# Vidarebefordra data och kodreferenser på serversidan

En omfattande lista med beskrivningar av konfigurationsvariabler, HTTP-huvuden och datasignaler i vidarebefordringsanrop på serversidan.

## Konfigurationsvarabler {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Parametrar med prefix `d_*` identifiera nyckelvärdepar på systemnivå som används av vår [datainsamlingsservrar](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html) (DCS) Se även [Attribut som stöds för DCS API-anrop](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html).

| Parameter | Beskrivning |
|--- |--- |
| `d_rs` | (Hämtar med äldre/spårningsserverbaserad vidarebefordran på serversidan) <br>Anges till de rapportsviter som skickades in med träffen till Analytics. |
| `d_dst_filter` | (Hämtar med rapportsvitbaserad vidarebefordran på serversidan)  <br>Ange till rapportsvitens ID:n som skickades med träffen till Analytics. |
| `d_dst` | Ange `d_dst=1`  <br>om begäran till Analytics förväntar att innehåll om målet ska skickas tillbaka till klienten. |
| `d_mid` | Experience Cloud-ID:t skickades till Analytics. |

## HTTP-huvuden {#section_0549705E76004F9585224AEF872066C0}

Dessa rubriker är fält som innehåller information som förfrågningar om data och svar i ett HTTP-anrop.

| HTTP-huvud | Beskrivning | h_key accepterad av Audience Manager |
| --- | --- | --- |
| Värd | Detta ställs in på klientens specifika värdnamn för datainsamling som anges i konfigurationsfilen för analysvärden. Det ser ut som `host name .demdex.net`. Se [Förstå anrop till Demdex-domänen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html). | `h_host` |
| Användaragent | Ange användaragenthuvudet som skickas till Analytics. | `h_user-agent` |
| Acceptera språk | Ange till  `Accept-Language`  har skickats till Analytics. | `h_accept-language` |
| Referent | Ange som sidans URL som skickas till Analytics (Analyser) eller som samlats in från `Referer` har skickats till Analytics. | `h_referer` |
| Referent | Ange som sidans URL som skickas till Analytics (Analyser) eller som samlats in från `Referrer` har skickats till Analytics. | `h_referrer` |
| Datum | Ange till `Date` har skickats till Analytics. | `h_date` |

Dessutom har `h_ip` signalen genereras från IP-adressen för värddatorn som skickar begäran till DCS.

## Kunddefinierade signaler {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Parametrar med prefix `c_` identifiera kunddefinierade variabler. Se även [Attribut som stöds för DCS API-anrop](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html).

| Signal | Beskrivning |
| --- |--- |
| `c_browserWidth`  och `c_browserHeight` | Bredd och höjd på webbläsarfönstret. |
| `c_campaign` | Ange efter `s.campaign`. |
| `c_channel` | Ange efter `s.channel`. |
| `c_clientDateTime` | Tidsstämpel formaterad som `dd/mm/yyy hh:mm:ss  W TZ` . `TZ` är i minuter och matchar returen av `Date.getTimezoneOffset` -metod. |
| `c_colorDepth` | Anges som 16- eller 32-bitars färg. |
| `c_connectionType` | Anger anslutningstyp. Alternativen är:<ul><li>modem</li><li>lan</li></ul> |
| `c_contextData.*` | Exempel:<ul><li>AppMeasurement: `s.contextData`</li><li>[&quot;category&quot;] = &quot;news&quot;;</li><li>Signal: `c_contextData.category=news`</li></ul> |
| `c_cookiesEnabled` | Anger om cookies kan aktiveras. Alternativ: ja, nej, okänd |
| `c_currencyCode` | Typ av valuta som används för transaktionen. |
| `c_evar#` | Egna evar |
| `c_events` | Ange efter `s.events`. |
| `c_hier#` | Anpassade hierarkivariabler. |
| `c_javaEnabled` | Anger om Java kan aktiveras. Alternativ: ja, nej, okänd |
| `c_javaScriptVersion` | Version av JavaScript stöds av en webbläsare. |
| `c_latitude` | Numerisk latitud |
| `c_linkClick` | Alternativ: anpassad, nedladdningsavslutning |
| `c_linkCustomName` | Det anpassade namn (om det finns något) som anges för länken. |
| `c_linkDownloadURL` | URL:en för nedladdningslänkar. |
| `c_linkExitURL` | URL:en för avslutningslänken. |
| `c_list#` | Egna listvariabler. |
| `c_longitude` | Numerisk longitud. |
| `c_mediaPlayerType` | För begäranden om spårning av medieströmmar. Alternativ: annan, primetime |
| `c_pageName` | Sidnamnet (om det har angetts). |
| `c_pageURL` | Adressen till sidan i webbläsarens adressfält. |
| `c_products` | Produktsträngen (anges av `s.products`). |
| `c_prop` | Egna proppar. |
| `c_purchaseID` | Ett unikt ID för köpet. |
| `c_referrer` | Sidan före den aktuella sidan. |
| `c_screenResolution` | Skärmbredd och -höjd (i pixlar). |
| `c_server` | Webbservernamn (anges av `s.server`). |
| `c_state` | Geografisk region (anges av `s.state`). |
| `c_timezone` | Tidsförskjutning (i timmar). |
| `c_transactionID` | Ett unikt ID för en transaktion. |
| `c_zip` | Postnummer (anges av `s.zip`). |
