---
title: Klienttips
description: Lär dig mer om hur klienttips gradvis ersätter användaragenten som källa för enhetsinformation.
source-git-commit: 55747b79851696fd1bff8fb7cb4849dc8c813fc0
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Översikt över kundtips och vanliga frågor

Klienttips är individuell information om en användares enhet. De tillhandahålls av Chromium-webbläsare som Google Chrome och Microsoft Edge. För dessa webbläsare kommer klienttipsen gradvis att ersätta användaragenten som källa för enhetsinformation. Adobe Analytics uppdaterar sin enhetssökningsprocess så att den använder klienttips utöver användaragenten för att fastställa enhetsinformation.

Google delar upp klienttips för User-Agent i två kategorier: Tips för låg entropi och hög entropi.

* **Tips för låg entropi** innehåller mer allmän information om enheter. Dessa tips tillhandahålls automatiskt av Chromium-webbläsare.

* **Hög entropi** Tipsen innehåller mer detaljerad information. Tipsen är bara tillgängliga på begäran. Både AppMeasurement och Web SDK [kan konfigureras](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) för att begära tips för entropi. Som standard gör båda biblioteken **not** begär tips för entropi.

>[!NOTE]
>
>Från och med oktober 2022 kommer nya versioner av Chromium-webbläsare att starta frysningen av operativsystemversionen som representeras i användaragentsträngen. Operativsystemsversionen är ett tips för hög entropi, så för att operativsystemsversionen ska vara korrekt i din rapportering måste du konfigurera ditt samlingsbibliotek så att du kan samla in dessa tips för hög entropi. Med tiden kommer annan enhetsinformation för användaragenten att frysas, vilket kräver att klienttipsen upprätthåller enhetens rapporteringsnoggrannhet.

>[!NOTE]
>
>AAM kräver att hög entropi-tips samlas in för att bevara alla funktioner. Om du använder [vidarebefordran på serversidan till AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) kan du aktivera en samling med höga entropi-tips.

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

+++**Vilka är de olika tipsvärdena för klienten?**

Tabellen nedan beskriver klienttipsen från oktober 2022.

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

+++**Kommer enhetsrapporteringen att ändras i Analytics?**

De enhetsfält som är tillgängliga för rapportering ändras inte. De data som hämtas för dessa fält kan ändras beroende på vilket fält och hur du har konfigurerat samlingen för klienttips.

+++

+++**Vilka analysrapporteringsfält kommer från användaragenten?**

Dessa fält härleds direkt från användaragenten, men användaragenten kan användas för att härleda värden för andra enhetsrelaterade fält, beroende på enhetsinformationen.

* [Webbläsare](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [Typ av webbläsare](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [Operativsystem](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [Operativsystemstyper](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [Mobil enhet och mobilenhetstyp](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)

+++

+++**Vilka analysrapporteringsfält härleds från värden som lagras i höga entropitups?**

Detta ändras med tiden eftersom Google fryser fler delar av användaragenten. Det första fältet som ska påverkas direkt är&quot;operativsystem&quot;, som innehåller operativsystemversionen Enligt Google publicerade tidslinje för&quot;frysning&quot; av användaragenttips, kommer operativsystemsversionen att frysas från slutet av oktober 2022 med Chromium version 107. Då blir operativsystemversionen i användaragenten i vissa fall felaktig.

Se [tidslinje som publicerats av Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) om du vill se tidpunkten för frysning av andra delar av användaragenten.

+++

+++**Hur använder Adobe klienttips för att hämta enhetsinformation?**

Adobe använder en enhetskarta från en annan leverantör, Device Atlas, som kommer att använda både klienttips och användaragent för att hämta enhetsinformation.

+++

+++**Vilka webbläsare påverkas av klienttipsen?**

Klienttips gäller endast för Chromium-webbläsare som Google Chrome och Microsoft Edge. Data från andra webbläsare eller mobilappar ändras inte.

+++

+++**Stöds klienttips över osäkra anslutningar?**

Nej. Klienttips kan bara samlas in via en säker HTTP-anslutning, till exempel HTTPS.

+++

+++**Kommer klienttips att vara tillgängliga i data som skickas till AEP och CJA via Adobe Source Connector?**

Adobe planerar att inkludera klienttips i data via Adobe Source Connector under första halvåret 2023.

+++

+++**Hur visas klienttips i XDM?**

Se [schemadokumentation](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) i Adobe Experience Platform.

+++

+++**Vilka delar av användaragenten &quot;fryses&quot; och när?**

Se [tidslinje som publicerats av Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Detta kan komma att ändras.

+++

+++**Kommer AAM att stödja klienttips för vidarebefordran på serversidan?**

Ja. Klienttips inkluderas i de data som skickas till AAM. Observera att AAM kräver att högentropi-tips samlas in för att bevara alla funktioner. Om du använder [vidarebefordran på serversidan till AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) kan du aktivera en samling med tips för entropi.

+++

