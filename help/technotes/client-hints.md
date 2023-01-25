---
title: Klienttips
description: Lär dig mer om hur klienttips gradvis ersätter användaragenten som källa för enhetsinformation.
exl-id: e0a74daa-12a2-4999-9920-2636b061dcc8
source-git-commit: cb15ba22fc9817583c6ded8fe12af5a115c1ea43
workflow-type: tm+mt
source-wordcount: '1230'
ht-degree: 1%

---

# Översikt över kundtips och vanliga frågor

Klienttips är individuell information om en användares enhet. De tillhandahålls av Chromium-webbläsare som Google Chrome och Microsoft Edge. För dessa webbläsare kommer klienttipsen gradvis att ersätta användaragenten som källa för enhetsinformation. Adobe Analytics uppdaterar sin enhetssökningsprocess så att den använder klienttips utöver användaragenten för att fastställa enhetsinformation.

Google delar upp klienttips för User-Agent i två kategorier: Tips för låg entropi och hög entropi.

* **Tips för låg entropi** innehåller mer allmän information om enheter. Dessa tips tillhandahålls automatiskt av Chromium-webbläsare.

* **Hög entropi** Tipsen innehåller mer detaljerad information. Tipsen är bara tillgängliga på begäran. Både AppMeasurement och Web SDK kan konfigureras för att begära tips för hög entropi. Som standard gör båda biblioteken **not** begär tips för entropi.

>[!NOTE]
>
>Klienttips kommer att införlivas i sökprocessen efter enheter i Analytics från och med den 15 februari 2023. Både AppMeasurement och Web SDK stöder för närvarande insamling av tipsdata, men kommer inte att användas i enhetssökning förrän i mitten av februari. Så som anges nedan var operativsystemsversionen fryst från och med oktober men på grund av en gradvis utrullning och det faktum att många användaragenter redan har en fryst OS-version (se mer [här](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)) uppskattar vi att detta påverkar &lt;3 % av Chrome-besökarna.

>[!NOTE]
>
>Från och med oktober 2022 började nya versioner av Chromium-webbläsare&quot;frysa&quot; operativsystemversionen som representerades i användaragentsträngen. Operativsystemsversionen är ett tips för hög entropi, så för att operativsystemsversionen ska vara korrekt i din rapportering måste du konfigurera ditt samlingsbibliotek så att du kan samla in dessa tips för hög entropi. Med tiden kommer annan enhetsinformation för användaragenten att frysas, vilket kräver att klienttipsen upprätthåller enhetens rapporteringsnoggrannhet.

>[!NOTE]
>
> Från och med januari 2023 är vissa versioner av Mac och Windows felaktigt representerade i användaragenten, men korrekt representerade i klienttips med hög entropi. Se [Operativsystem](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) för mer information.

>[!NOTE]
>
>AAM kräver att hög entropi-tips samlas in för att bevara alla funktioner. Om du använder [vidarebefordran på serversidan till AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) kan du aktivera en samling med höga entropi-tips.

## Frågor och svar

+++**Var kan jag läsa mer om kundtips?**

Detta [Google blogginlägg](https://web.dev/user-agent-client-hints/) är en bra referens och utgångspunkt.

+++

+++**Hur aktiverar jag samlingen med klienttips?**

Tips om låg entropi tillhandahålls automatiskt av webbläsaren och hämtas för att ta fram information om enheter och webbläsare. Nyare versioner av Web SDK (från och med 2.12.0) och AppMeasurement (från och med 2.23.0) kan konfigureras för att samla in tips med hög entropi via respektive taggtillägg eller direkt via ett konfigurationsalternativ. Se vägbeskrivningar för [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html#enabling-high-entropy-client-hints) och [AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/collecthighentropyuseragenthints.html).

För båda biblioteken är samlingen med höga entropytips **inaktiverad som standard**.

För data som skickas via API, till exempel via [API för datainfogning](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) eller [API för massdatainmatning](https://experienceleague.adobe.com/docs/analytics/import/bulk-data-insert.html?lang=en), måste tips uttryckligen inkluderas i nyttolasten. Mer information finns i respektive dokumentation.

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

Höga entropittips samlas in via JavaScript-anrop och skickas via frågeparametrar

+++

+++**Kommer enhetsrapporteringen att ändras i Analytics?**

De enhetsfält som är tillgängliga för rapportering ändras inte. De data som hämtas för dessa fält kan ändras beroende på vilket fält och hur du har konfigurerat samlingen för klienttips.

+++

+++**Vilka analysrapporteringsfält kommer från användaragenten?**

Dessa fält härleds direkt från användaragenten, men användaragenten kan användas för att härleda värden för andra enhetsrelaterade fält, beroende på enhetsinformationen.

* [Webbläsare](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html)
* [Typ av webbläsare](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html)
* [Operativsystem](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html)
* [Operativsystemstyper](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html)
* [Mobil enhet och mobilenhetstyp](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html)

+++

+++**Vilka delar av användaragenten &quot;fryses&quot; och när?**

Se [tidslinje som publicerats av Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Detta kan komma att ändras.

+++

+++**På vilka sätt är Analytics beroende av användaragenten?**

Enhetsinformation i rapporter hämtas från användaragenten. Vi har uppdaterat våra processer så att vi kan använda både användaragenten och klienttips där det finns tillgängliga.

Återställnings-ID ([s_fd](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-ids.html?lang=en)) härleds från användaragenten och IP-adressen. Detta ID används endast om en cookie inte kan anges så används inte i någon större utsträckning

+++

+++**Vilka analysrapporteringsfält härleds från värden som lagras i höga entropitups?**

Detta ändras med tiden eftersom Google fryser fler delar av användaragenten. Det första fältet som ska påverkas direkt är&quot;operativsystem&quot;, som innehåller operativsystemversionen Enligt Google publicerade tidslinje för&quot;frysning&quot; av användaragenttips, kommer operativsystemsversionen att frysas från slutet av oktober 2022 med Chromium version 107. Då blir operativsystemversionen i användaragenten i vissa fall felaktig.

Se [tidslinje som publicerats av Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) om du vill se tidpunkten för frysning av andra delar av användaragenten.

+++

+++**Hur använder Adobe klienttips för att hämta enhetsinformation?**

Adobe använder en tredje part, Device Atlas, som kommer att använda både klienttips och User-Agent för att hämta enhetsinformation.

+++

+++**Vilka webbläsare påverkas av klienttipsen?**

Klienttips gäller endast för Chromium-webbläsare som Google Chrome och Microsoft Edge. Data från andra webbläsare eller mobilappar ändras inte.

+++

+++**Stöds klienttips över osäkra anslutningar?**

Nej. Klienttips kan bara samlas in via en säker HTTP-anslutning, till exempel HTTPS.

+++

+++**Hur tar jag med data för klienttips när jag skickar API?**

Se dokumentationen för att inkludera dessa via [API för massdatainmatning](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/file-format/).

+++

+++**Kommer klienttips att vara tillgängliga i data som skickas till AEP och CJA via Adobe Source Connector?**

Adobe planerar att inkludera klienttips i data via Adobe Source Connector under första halvåret 2023.

+++

+++**Hur visas klienttips i XDM?**

Se [schemadokumentation](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) i Adobe Experience Platform.

+++

+++**Kommer AAM att stödja klienttips för vidarebefordran på serversidan?**

Ja. Klienttips inkluderas i de data som skickas till AAM. Observera att AAM kräver att högentropi-tips samlas in för att bevara alla funktioner. Om du använder [vidarebefordran på serversidan till AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) kan du aktivera en samling med tips för entropi.

+++
