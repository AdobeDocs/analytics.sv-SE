---
title: Klienttips
description: Lär dig mer om hur klienttips gradvis ersätter användaragenten som källa för enhetsinformation.
exl-id: e0a74daa-12a2-4999-9920-2636b061dcc8
feature: Data Configuration and Collection
role: Admin
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '1184'
ht-degree: 0%

---

# Översikt över kundtips och vanliga frågor

Klienttips är individuell information om en användares enhet. De tillhandahålls av Chromium-webbläsare som Google Chrome och Microsoft Edge. För dessa webbläsare kommer klienttipsen gradvis att ersätta användaragenten som källa för enhetsinformation. Adobe Analytics uppdaterar sin enhetssökningsprocess så att den använder klienttips utöver användaragenten för att fastställa enhetsinformation.

## Klienttips för låg entropi och hög entropi

Google delar upp klienttips för användaragenter i två kategorier: tips för låg entropi och hög entropi.

* **Tips för låg entropi** innehåller mer allmän information om enheter. Dessa tips tillhandahålls automatiskt av Chromium-webbläsare.

* **Tips för hög entropi** innehåller mer detaljerad information. Tipsen är bara tillgängliga på begäran. Både AppMeasurement och Web SDK kan konfigureras för att begära tips för hög entropi. Som standard begär båda biblioteken **inte** tips för hög entropi.

Från och med oktober 2022 började nya versioner av Chromium-webbläsare&quot;frysa&quot; operativsystemversionen som representerades i användaragentsträngen. Operativsystemsversionen är ett tips för hög entropi, så för att operativsystemsversionen ska vara korrekt i din rapportering måste du konfigurera ditt samlingsbibliotek så att du kan samla in dessa tips för hög entropi. Med tiden kommer annan enhetsinformation för användaragenten att frysas, vilket kräver att klienttipsen upprätthåller enhetens rapporteringsnoggrannhet.

Klienttips kommer att införlivas i processen för sökning efter enheter i Analytics från och med den 27 februari 2023 och avslutas den 2 mars 2023. Både AppMeasurement och Web SDK stöder för närvarande insamling av tipsdata, men kommer inte att användas i enhetssökning förrän i mitten av februari. Som anges nedan var operativsystemsversionen fryst från och med oktober, men på grund av en gradvis utrullning och det faktum att många användaragenter redan har en fryst OS-version (se mer [här](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html)), uppskattar vi att detta påverkar &lt;3 % av Chrome-besökarna.

>[!NOTE]
>
> Från och med januari 2023 är vissa versioner av Mac och Windows felaktigt representerade i användaragenten, men korrekt representerade i klienttips med hög entropi. Mer information finns i [Operativsystem](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html).

Adobe Audience Manager kräver att högentropi-tips samlas in för att bevara alla funktioner. Om du använder [vidarebefordran på serversidan till Adobe Audience Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) kanske du vill aktivera en samling med tips för hög entropi.

## Frågor och svar

+++**Var kan jag läsa mer om kundtips?**

Det här [Google-blogginlägget](https://web.dev/user-agent-client-hints/) är en bra referens och utgångspunkt.

+++

+++**Hur aktiverar jag samlingen med klienttips?**

Tips om låg entropi tillhandahålls automatiskt av webbläsaren och hämtas för att ta fram information om enheter och webbläsare. Nyare versioner av Web SDK (från och med 2.12.0) och AppMeasurement (från och med 2.23.0) kan konfigureras för att samla in tips med hög entropi via respektive taggtillägg eller direkt via ett konfigurationsalternativ. Se instruktionerna för [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html#enabling-high-entropy-client-hints) och [AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/collecthighentropyuseragenthints.html).

För båda biblioteken är samlingen med höga entropytips **inaktiverad som standard**.

För data som skickas via API, t.ex. via [API för datainmatning](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) eller [API för datainmatning i grupp](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/), måste tips uttryckligen inkluderas i nyttolasten. Mer information finns i respektive dokumentation.

+++

+++**Kan jag välja vilka entropiton jag ska samla in?**

Inte just nu. Du kan välja att samla in alla högentropiska tips eller inga.

Observera att fullVersionList för närvarande inte samlas in eftersom webbläsarhuvudversionen fångas in som ett tips om låg entropi.

+++

+++**Vilka är de olika tipsvärdena för klienten?**

Tabellen nedan beskriver klienttipsen från oktober 2022.

| Tips | Beskrivning | Hög eller låg Entropi | Exempel |
| --- | --- | --- | --- | 
| Sec-CH-UA | Webbläsare och signifikant version | Låg | `"Google Chrome 84"` |
| Sec-CH-UA-Mobile | Mobil enhet (true eller false) | Låg | `true` |
| Sec-CH-UA-Platform | Operativsystem/plattform | Låg | `"Android"` |
| arkitektur | Arkitektur för webbplatsen | Hög | `"arm"` |
| bitterhet | Arkitekturbitenhet | Hög | `"64"` |
| fullVersionList | Lista över varumärken med deras version | Hög | `"Not A;Brand";v="99", "Chromium";v="98", "Google Chrome";v="98"` |
| modell | Enhetsmodell | Hög | `"Pixel 3"` |
| platformVersion | Operativsystem/plattformsversion | Hög | `"10"` |

* Tips om låg entropi samlas in via begärandehuvudet.
* High-entropy-tips samlas in via JavaScript och skickas via frågesträngsparametervärden. Frågesträngsparametrarna använder `h.` som prefix i bildbegäran. Observera att fullVersionList för närvarande inte samlas in eftersom webbläsarhuvudversionen fångas in som ett lågt entropittips.

Höga entropitextipsen samlas in via JavaScript-anrop och skickas via frågeparametrar

+++

+++**Kommer enhetsrapportering att ändras i Analytics?**

De enhetsfält som är tillgängliga för rapportering ändras inte. De data som hämtas för dessa fält kan ändras beroende på vilket fält och hur du har konfigurerat samlingen för klienttips.

+++

+++**Vilka analysrapporteringsfält kommer från användaragenten?**

Dessa fält härleds direkt från användaragenten, men användaragenten kan användas för att härleda värden för andra enhetsrelaterade fält, beroende på enhetsinformationen.

* [Webbläsare](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html)
* [Webbläsartyp](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html)
* [Operativsystem](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html)
* [Operativsystemstyper](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html)
* [Mobil enhet och typ av mobil enhet](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html)

+++

+++**Vilka delar av användaragenten &quot;fryses&quot; och när?**

Se tidslinjen [som publicerats av Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Detta kan komma att ändras.

+++

+++**På vilka sätt är Analytics beroende av användaragenten?**

Enhetsinformation i rapporter hämtas från användaragenten. Vi har uppdaterat våra processer så att vi kan använda både användaragenten och klienttips där det finns tillgängliga.

Återställnings-ID ([s_fid](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-ids.html)) härleds från användaragenten och IP-adressen. Detta ID används endast om en cookie inte kan anges så används inte i någon större utsträckning

+++

+++**Vilka analysrapporteringsfält härleds från värden som lagras i tips för hög entropi?**

Detta ändras med tiden eftersom Google fryser fler delar av användaragenten. Det första fältet som ska påverkas direkt är&quot;operativsystem&quot;, som innehåller operativsystemversionen Enligt Google publicerade tidslinje för&quot;frysning&quot; av användaragenttips, kommer operativsystemsversionen att frysas från slutet av oktober 2022 med Chromium version 107. Då kommer operativsystemversionen i användaragenten att vara felaktig i vissa fall.

Se tidslinjen [som publicerats av Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) för att se när andra delar av användaragenten har frysts.

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

+++**Hur inkluderar jag klienttipsdata när jag använder API-överföring?**

Se dokumentationen för att inkludera dessa via [API för datainfogning i grupp](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/file-format/).

+++

+++**Kommer klienttips att vara tillgängliga i data som skickas till Adobe Experience Platform och Customer Journey Analytics via Adobe Source Connector?**

Adobe planerar att inkludera kundtips i data via Adobe Source Connector under första halvåret 2023.

+++

+++**Hur visas klienttips i XDM?**

Se [schemadokumentationen](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) i Adobe Experience Platform.

+++

+++**Kommer Adobe Audience Manager klienttips för vidarebefordran på serversidan att stödjas?**

Ja. Klienttips inkluderas i de data som skickas till Adobe Audience Manager. Observera att Adobe Audience Manager kräver att högentropiska tips samlas in för att bevara alla funktioner. Om du använder [vidarebefordran på serversidan till Adobe Audience Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) kanske du vill aktivera en samling med tips för hög entropi.

+++
