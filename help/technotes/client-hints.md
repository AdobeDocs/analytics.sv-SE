---
title: Klienttips
description: Läs mer om
source-git-commit: b99852f4b8e0a3034ea8965e5646b1ab2f1a8c4c
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 2%

---


# Översikt över kundtips och vanliga frågor

Klienttips är individuell information om en användares enhet. De tillhandahålls av Chromium-webbläsare som Google Chrome och Microsoft Edge. För dessa webbläsare kommer klienttipsen gradvis att ersätta användaragenten som källa för enhetsinformation. Adobe Analytics uppdaterar sin enhetssökningsprocess så att den använder klienttips utöver användaragenten för att fastställa enhetsinformation.

Google delar upp klienttips för användaragenten i två kategorier: Tips för låg entropi och hög entropi.

* Tips för låg entropi innehåller mer allmän information om enheter. Dessa tips tillhandahålls automatiskt av Chromium-webbläsare.

* Tips för avancerad entropi innehåller mer detaljerad information. Tipsen är bara tillgängliga på begäran. Både AppMeasurement och Web SDK kan konfigureras för att begära tips för hög entropi. Som standard gör båda biblioteken **not** begär tips för entropi.

>[!NOTE]
>
>Från och med oktober 2022 kommer nya versioner av Chromium-webbläsare att starta frysningen av operativsystemversionen som representeras i användaragentsträngen. Det innebär att den operativversionsinformation som representeras i användaragenten blir mindre exakt. Operativsystemsversionen är ett tips för hög entropi, så för att operativsystemsversionen ska vara korrekt i din rapportering måste du konfigurera ditt samlingsbibliotek så att du kan samla in dessa tips för hög entropi. Med tiden kommer annan enhetsinformation för användaragenten att frysas, vilket kräver att klienttipsen upprätthåller enhetens rapporteringsnoggrannhet.

## Frågor och svar

+++**Hur aktiverar jag samlingen med klienttips?**

Tips om låg entropi tillhandahålls automatiskt av webbläsaren och ingår i Adobe-processen för att få enhetsinformation. Nyare versioner av AppMeasurement (som startar TBD) och Web SDK (som startar TBD) kan konfigureras för att samla in tips för hög entropi. För båda biblioteken är samlingen med höga entropytips **inaktiverad som standard**. Här finns mer information om hur du implementerar detta.

+++**Kan jag välja vilka högentropiska tips jag samlar in?**

Inte just nu. Du kan välja att samla in alla högentropiska tips eller inga.

+++**Kommer enhetsrapporteringen att ändras i Analytics?**

De enhetsfält som är tillgängliga för rapportering ändras inte. De data som hämtas för dessa fält kan ändras beroende på vilket fält och hur du har konfigurerat samlingen för klienttips.

+++**Vilka analysrapporteringsfält kommer från användaragenten?**

* [Webbläsare](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [Typ av webbläsare](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [Operativsystem](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [Operativsystemstyper](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [Mobil enhet och mobilenhetstyp](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)?
* Dataflöden (Observera att användarna måste uppdatera för att kunna hämta dessa fält. Dessutom finns det ett beroende där vi inte kan visa mobilt ID tillsammans med enhetsinformation.)
* Källanslutning för analys (inte klar)

+++**Vilka analysrapporteringsfält härleds från värden som lagras i höga entropitups?**

Från om med september 2022 indikerar Google publicerade tidslinje för att frysa användaragenttips att operativsystemets version kommer att sluta uppdateras från och med oktober 2022. Utan höga entropintips kommer exaktheten i operativsystemsversionen, som ingår i analysdimensionen &quot;Operativsystem&quot;, att gradvis försämras.

Se [tidslinje som publicerats av Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) för att se tidpunkten för frysning av användaragenten.

+++**Vilka webbläsare påverkas av klienttipsen?**

Klienttips gäller endast för Chromium-webbläsare som Google Chrome och Microsoft Edge. Data från andra webbläsare eller mobilappar ändras inte.

+++**Hur använder Adobe klienttips för att hämta enhetsinformation?**

Adobe använder en enhetskarta från en annan leverantör, Device Atlas, som kommer att använda både klienttips och användaragent för att hämta enhetsinformation.

+++**Finns det klienttips i dataflöden?**

Ja. Se dokumentationen (som du följer).

+++**Kommer klienttips att vara tillgängliga i data som skickas till AEP och CJA via Adobe Source Connector?**

Vi planerar att inkludera kundtips i data via Adobe Source Connector under första halvåret 2023.

+++**Hur visas klienttips i XDM?**

Se [schemadokumentation](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) i Adobe Experience Platform.

+++**Var kan jag läsa mer om kundtips?**

Detta [Google blogginlägg](https://web.dev/user-agent-client-hints/) är en bra referens och utgångspunkt.

+++**Vilka är de olika tipsfälten? Vilka påverkar enhetsrapporteringen?**

Tabellen nedan beskriver klienttipsen från september 2022.

| Tips (rubrik) | Tips | Hög eller låg Entropi | Exempel | Rapporteringsfält för analyser |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | Webbläsare och signifikant version | Låg | Google Chrome 84 | [Webbläsare](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en) och [Typ av webbläsare](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en) |
| Sec-CH-UA-Mobile | Mobil enhet (true eller false) | Låg | TRUE | [Mobil enhet och mobilenhetstyp](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)? |
| Sec-CH-UA-Platform | Operativsystem/plattform | Låg | Android | [Operativsystem](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |
| Sec-CH-UA-Arch | Arkitektur för webbplatsen | Hög | &quot;arm&quot; | Ingen? |
| Avsn-CH-UA-bitness | Avsn-CH-UA-bitness | Hög |  | Ingen? |
| Sec-CH-UA-Full-Version | Fullständig version av webbläsaren | Hög | &quot;84.0.4143.2&quot; | Ingen? |
| Sec-CH-UA-full-version-list | ?? | Hög | ?? | Ingen? |
| Sec-CH-UA-Model | Enhetsmodell | Hög | &quot;Pixel 3&quot; | Ingen? |
| Sec-CH-UA-platform-version | Operativsystem/plattformsversion | Hög | &quot;10&quot; | [Operativsystem](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |

+++**Hur fångar jag antydan?**

Högentropytips kan konfigureras

* För AppMeasurement direkt [länk till flaggposten i implementeringshandboken]
* I tagganalystillägget
* I Web SDK.

+++**Vilka data tas bort från användaragenten och när?**

Se [tidslinje som publicerats av Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Detta kan komma att ändras.

+++