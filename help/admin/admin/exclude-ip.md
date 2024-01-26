---
title: Exkludera efter IP-adress
description: Förhindra att data som genereras av vissa IP-adresser visas i rapporter.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Exkludera efter IP-adress

Du kan undanta data från specifika IP-adresser, som interna webbplatsaktiviteter, platstestning och personalanvändning, från dina rapporter. Om du exkluderar data förbättras rapportens exakthet genom att IP-adressdata utesluts. Dessutom kan du ta bort data från denial of service eller andra skadliga händelser som kan förvränga rapportdata. Du kan konfigurera undantag eller använda brandväggen.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Exclude by IP]**

>[!NOTE]
>
>Träffar som exkluderats av IP-adressen faktureras som [serveranrop](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html).

Du kan använda jokertecken (&#42;) för att exkludera ett adressintervall. Till exempel: `[!DNL 0.0.*.0]` utelämnar alla IP-adresser mellan `[!DNL 0.0.0.0]` och `[!DNL 0.0.255.0]`. Du kan utesluta upp till 50 olika IP-adresser.

>[!TIP]
>
>Privata IP-adresser behöver inte uteslutas. Endast externa IP-adresser når datainsamlingsservrar i Adobe. Privata adresser innehåller `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*`och `169.254.*.*`.

## Inverkan av IP-missbruk {#section_51B7529FFF16449CA016FDC51D87E2CA}

Om IP-förfalskning är aktiverat inträffar IP-uteslutning innan IP-adressen döljs, så kunderna behöver inte ändra någonting när de aktiverar IP-förfalskning.

Om den sista oktetten tas bort, görs det före IP-filtrering. Den sista oktetten ersätts med 0, och reglerna för IP-undantag måste uppdateras för att matcha IP-adresser med en nolla på slutet. Matchande &#42; ska matcha 0.
