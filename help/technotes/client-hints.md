---
title: Klienttips
description: Lär dig mer om hur klienttips gradvis ersätter användaragenten som källa för enhetsinformation.
source-git-commit: f2f1e64a62796b58c24e6ff652db93b21f750669
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 2%

---


# Översikt över kundtips och vanliga frågor

Klienttips är individuell information om en användares enhet. De tillhandahålls av Chromium-webbläsare som Google Chrome och Microsoft Edge. För dessa webbläsare kommer klienttipsen gradvis att ersätta användaragenten som källa för enhetsinformation. Adobe Analytics uppdaterar sin enhetssökningsprocess så att den använder klienttips utöver användaragenten för att fastställa enhetsinformation.

Google delar upp klienttips för User-Agent i två kategorier: Tips för låg entropi och hög entropi.

* **Tips för låg entropi** innehåller mer allmän information om enheter. Dessa tips tillhandahålls automatiskt av Chromium-webbläsare.

* **Hög entropi** Tipsen innehåller mer detaljerad information. Tipsen är bara tillgängliga på begäran. Både AppMeasurement och Web SDK [kan konfigureras](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) för att begära tips för entropi. Som standard gör båda biblioteken **not** begär tips för entropi.

>[!NOTE]
>
>Från och med oktober 2022 kommer nya versioner av Chromium-webbläsare att starta frysningen av operativsystemversionen som representeras i användaragentsträngen. När användare uppgraderar sina enheter ändras inte operativsystemet i användaragenten. Det innebär att den versionsinformation som visas i användaragenten blir mindre exakt över tiden. Operativsystemsversionen är ett tips för hög entropi, så för att operativsystemsversionen ska vara korrekt i din rapportering måste du konfigurera ditt samlingsbibliotek så att du kan samla in dessa tips för hög entropi. Med tiden kommer annan enhetsinformation för användaragenten att frysas, vilket kräver att klienttipsen upprätthåller enhetens rapporteringsnoggrannhet.

## Frågor och svar

+++**Var kan jag läsa mer om kundtips?**

Detta [Google blogginlägg](https://web.dev/user-agent-client-hints/) är en bra referens och utgångspunkt.

+++

+++**Hur aktiverar jag samlingen med klienttips?**

Tips om låg entropi tillhandahålls automatiskt av webbläsaren och ingår i Adobe-processen för att hämta information om enheter och webbläsare. Nyare versioner av AppMeasurement (från och med 2.23.0) och Web SDK (från och med 2.12.0) kan konfigureras för att samla in tips för hög entropi. För båda biblioteken är samlingen med höga entropytips **inaktiverad som standard**.

+++

+++**Hur fångar jag antydan?**

Högentropiska tips kan konfigureras med Web SDK- och AppMeasurement-biblioteken via respektive taggtillägg eller direkt med flaggan collectHighEntropyUserAgentHints.

+++

+++**Kan jag välja vilka högentropiska tips jag samlar in?**

Inte just nu. Du kan välja att samla in alla högentropiska tips eller inga.

+++

+++**Kommer enhetsrapporteringen att ändras i Analytics?**

De enhetsfält som är tillgängliga för rapportering ändras inte. De data som hämtas för dessa fält kan ändras beroende på vilket fält och hur du har konfigurerat samlingen för klienttips.

+++

+++**Vilka analysrapporteringsfält kommer från användaragenten?**

* [Webbläsare](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [Typ av webbläsare](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [Operativsystem](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [Operativsystemstyper](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [Mobil enhet och mobilenhetstyp](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)
* [Datafeeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en)

+++

+++**Vilka analysrapporteringsfält härleds från värden som lagras i höga entropitups?**

Från om med september 2022 indikerar Google publicerade tidslinje för&quot;frysning&quot; av användaragenttips att operativsystemets version kommer att sluta uppdateras från och med oktober 2022. När användare uppgraderar sitt operativsystem uppdateras inte operativsystemsversionen i användaragenten. Utan höga entropytips kommer exaktheten i operativsystemsversionen, som ingår i analysdimensionen &quot;Operativsystem&quot;, att gradvis försämras.

Se [tidslinje som publicerats av Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) om du vill se tidpunkten för frysning av andra delar av användaragenten.

+++

+++**Hur använder Adobe klienttips för att hämta enhetsinformation?**

Adobe använder en enhetskarta från en annan leverantör, Device Atlas, som kommer att använda både klienttips och användaragent för att hämta enhetsinformation.

+++

+++**Vilka webbläsare påverkas av klienttipsen?**

Klienttips gäller endast för Chromium-webbläsare som Google Chrome och Microsoft Edge. Data från andra webbläsare eller mobilappar ändras inte.

+++

++**Stöds klienttips över osäkra anslutningar?

Nej. Klienttips kan bara samlas in via en säker HTTP-anslutning, till exempel HTTPS.

+++

+++**Kommer klienttips att vara tillgängliga i data som skickas till AEP och CJA via Adobe Source Connector?**

Adobe planerar att inkludera klienttips i data via Adobe Source Connector under första halvåret 2023.

+++

+++**Hur visas klienttips i XDM?**

Se [schemadokumentation](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) i Adobe Experience Platform.

+++

+++**Vilka är de olika tipsfälten? Vilka påverkar enhetsrapporteringen?**

Tabellen nedan beskriver klienttipsen från september 2022.

| Tips | Beskrivning | Hög eller låg Entropi | Exempel |
| --- | --- | --- | --- | 
| Sec-CH-UA | Webbläsare och signifikant version | Låg | &quot;Google Chrome 84&quot; |
| Sec-CH-UA-Mobile | Mobil enhet (true eller false) | Låg | TRUE |
| Sec-CH-UA-Platform | Operativsystem/plattform | Låg | &quot;Android&quot; |
| Sec-CH-UA-Arch | Arkitektur för webbplatsen | Hög | &quot;arm&quot; |
| Avsn-CH-UA-bitness | Arkitekturbitars | Hög | &quot;64&quot; |
| Sec-CH-UA-Full-Version | Fullständig version av webbläsaren | Hög | &quot;84.0.4143.2&quot; |
| Sec-CH-UA-full-version-list | Lista över varumärken med deras version | Hög | &quot;Inte A;Varumärke&quot;;v=&quot;99&quot;, &quot;Krom&quot;;v=&quot;98&quot;, &quot;Google Chrome&quot;;v=&quot;98&quot; |
| Sec-CH-UA-Model | Enhetsmodell | Hög | &quot;Pixel 3&quot; |
| Sec-CH-UA-platform-version | Operativsystem/plattformsversion | Hög | &quot;10&quot; |

+++



+++**Vilka delar av användaragenten &quot;fryses&quot; och när?**

Se [tidslinje som publicerats av Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Detta kan komma att ändras.

+++
