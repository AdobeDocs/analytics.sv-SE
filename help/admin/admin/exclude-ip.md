---
title: Exkludera efter IP-adress
description: Förhindra att data som genereras av vissa IP-adresser visas i rapporter.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: d642bf8703d7c4c1545bfd9763c70ed8b1237eac
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---

# Exkludera efter IP-adress

Du kan undanta data från specifika IP-adresser, som interna webbplatsaktiviteter, platstestning och personalanvändning, från dina rapporter. Om du exkluderar data förbättras rapportens exakthet genom att IP-adressdata utesluts. Dessutom kan du ta bort data från denial of service eller andra skadliga händelser som kan förvränga rapportdata.

Om du vill exkludera data med IP-adress kan du konfigurera undantag enligt beskrivningen nedan eller [konfigurera brandväggen](/help/technotes/ip-addresses.md).

## Konfigurera undantag efter IP-adress

>[!NOTE]
>
>När du konfigurerar undantag efter IP-adress bör du tänka på följande:
>
>* Träffar som exkluderats av IP-adressen faktureras som [serveranrop](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=sv-SE).
>* Privata IP-adresser behöver inte uteslutas. Endast externa IP-adresser når Adobe datainsamlingsservrar. Privata adresser omfattar `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*` och `169.254.*.*`.
>* Du kan använda jokertecken (&#42;) för att exkludera ett adressintervall. `[!DNL 0.0.*.0]` skulle till exempel exkludera alla IP-adresser mellan `[!DNL 0.0.0.0]` och `[!DNL 0.0.255.0]`. Du kan utesluta upp till 50 olika IP-adresser.
>* Data från en utelämnad IP-adress utelämnas för nya träffar som kommer in i systemet inom 5 minuter efter det att undantaget har angetts.
>* Data för träffar som fångats in före den tidpunkt då IP-adressen ändrades påverkas inte.
>

Så här konfigurerar du undantag efter IP-adress:

1. I Adobe Analytics väljer du **[!UICONTROL Admin]** > **[!UICONTROL All admin]**.

1. Välj **[!UICONTROL Exclude by IP]** på administratörssidan.




## Inverkan av IP-missförstånd {#section_51B7529FFF16449CA016FDC51D87E2CA}

Om IP-förfalskning är aktiverat inträffar IP-uteslutning innan IP-adressen döljs, så kunderna behöver inte ändra någonting när de aktiverar IP-förfalskning.

Om den sista oktetten tas bort, görs det före IP-filtrering. Den sista oktetten ersätts med 0, och reglerna för IP-undantag måste uppdateras för att matcha IP-adresser med en nolla på slutet. Matchande &#42; ska matcha 0.
