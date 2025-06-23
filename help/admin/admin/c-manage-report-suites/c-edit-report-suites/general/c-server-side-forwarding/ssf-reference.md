---
description: En omfattande lista med beskrivningar av konfigurationsvariabler, HTTP-huvuden och datasignaler i vidarebefordringsanrop på serversidan.
title: Vidarebefordra data och kodreferenser på serversidan
feature: Report Suite Settings
exl-id: 6ab7bbb6-0709-427b-b9fa-a179dbe55fc9
role: Admin
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 1%

---

# Vidarebefordra data och kodreferenser på serversidan

En omfattande lista med beskrivningar av konfigurationsvariabler, HTTP-huvuden och datasignaler i vidarebefordringsanrop på serversidan.

## Konfigurationsvarabler {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Parametrar som har prefixats med `d_*` identifierar nyckelvärdepar på systemnivå som används av våra [datainsamlingsservrar](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html?lang=sv-SE) (DCS). Se även [Attribut som stöds för DCS API-anrop](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=sv-SE).

| Parameter | Beskrivning |
|--- |--- |
| `d_rs` | (Hämtas med äldre/spårningsserverbaserad vidarebefordring på serversidan) <br>Ange till rapportsviterna som skickades med träffen till Analytics. |
| `d_dst_filter` | (Hämtas med rapportsvitbaserad vidarebefordring på serversidan) <br>Ange rapportsvitens ID som skickades med träffen till Analytics. |
| `d_dst` | Ange `d_dst=1` <br>om Analytics-begäran förväntar att innehåll om målet ska skickas tillbaka till klienten. |
| `d_mid` | Experience Cloud-id:t skickades till Analytics. |

## HTTP-huvuden {#section_0549705E76004F9585224AEF872066C0}

Dessa rubriker är fält som innehåller information som förfrågningar om data och svar i ett HTTP-anrop.

| HTTP-huvud | Beskrivning | h_key accepterad av Audience Manager |
| --- | --- | --- |
| Värd | Detta ställs in på klientens specifika värdnamn för datainsamling som anges i konfigurationsfilen för analysvärden. Det visas som `host name .demdex.net`. Se [Förstå anrop till Demdex-domänen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=sv-SE). | `h_host` |
| Användaragent | Ange användaragenthuvudet som skickas till Analytics. | `h_user-agent` |
| Acceptera språk | Ange till huvudet `Accept-Language` som skickades till Analytics. | `h_accept-language` |
| Referent | Ange till den sid-URL som skickades till Analytics (Analys) eller som samlats in från huvudet `Referer` som skickades till Analytics (Analys). | `h_referer` |
| Referent | Ange till den sid-URL som skickades till Analytics (Analys) eller som samlats in från huvudet `Referrer` som skickades till Analytics (Analys). | `h_referrer` |
| Datum | Ange till huvudet `Date` som skickades till Analytics. | `h_date` |

Dessutom genereras en `h_ip`-signal från IP-adressen för värddatorn som skickar begäran till DCS.

## Kunddefinierade signaler {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Parametrar som har prefixats med `c_` identifierar kunddefinierade variabler. Se även [Attribut som stöds för DCS API-anrop](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=sv-SE).

| Signal | Beskrivning |
| --- |--- |
| `c_browserWidth` och `c_browserHeight` | Bredd och höjd på webbläsarfönstret. |
| `c_campaign` | Inställd av `s.campaign`. |
| `c_channel` | Inställd av `s.channel`. |
| `c_clientDateTime` | Tidsstämpeln har formaterats som `dd/mm/yyy hh:mm:ss  W TZ`. `TZ` är i minuter och matchar returvärdet för metoden `Date.getTimezoneOffset`. |
| `c_colorDepth` | Anges som 16- eller 32-bitars färg. |
| `c_connectionType` | Anger anslutningstyp. Alternativen är:<ul><li>modem</li><li>lan</li></ul> |
| `c_contextData.*` | Exempel:<ul><li>AppMeasurement: `s.contextData`</li><li>[&quot;category&quot;] = &quot;news&quot;;</li><li>Signal: `c_contextData.category=news`</li></ul> |
| `c_cookiesEnabled` | Anger om cookies kan aktiveras. Alternativ: ja, nej, okänd |
| `c_currencyCode` | Typ av valuta som används för transaktionen. |
| `c_evar#` | Egna evar |
| `c_events` | Inställd av `s.events`. |
| `c_hier#` | Anpassade hierarkivariabler. |
| `c_javaEnabled` | Anger om Java kan aktiveras. Alternativ: ja, nej, okänd |
| `c_javaScriptVersion` | Den version av JavaScript som stöds av en webbläsare. |
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
