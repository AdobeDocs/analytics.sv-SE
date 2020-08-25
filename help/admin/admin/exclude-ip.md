---
title: Exkludera efter IP-adress
description: Förhindra att data som genereras av vissa IP-adresser visas i rapporter.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 3%

---


# Exkludera efter IP-adress

Du kan undanta data från specifika IP-adresser, som interna webbplatsaktiviteter, platstestning och personalanvändning, från dina rapporter. Om du exkluderar data förbättras rapportens exakthet genom att IP-adressdata utesluts. Dessutom kan du ta bort data från denial of service eller andra skadliga händelser som kan förvränga rapportdata. Du kan konfigurera undantag eller använda brandväggen.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Exclude by IP]**

>[!NOTE]
>
>Träffar som exkluderats av IP-adressen faktureras som [serversamtal](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html).

Du kan använda jokertecken (*) för att exkludera ett adressintervall. Till exempel `[!DNL 0.0.*.0]` skulle alla IP-adresser mellan `[!DNL 0.0.0.0]` och `[!DNL 0.0.255.0]`utelämnas. Du kan utesluta upp till 50 olika IP-adresser.

>[!TIP]
>
>Privata IP-adresser behöver inte uteslutas. Endast externa IP-adresser når datainsamlingsservrar i Adobe. Privata adresser inkluderar `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*`och `169.254.*.*`.

## Inverkan av IP-missbruk {#section_51B7529FFF16449CA016FDC51D87E2CA}

Om IP-förfalskning är aktiverat inträffar IP-uteslutning innan IP-adressen döljs, så kunderna behöver inte ändra någonting när de aktiverar IP-förfalskning.

Om den sista oktetten tas bort, görs det före IP-filtrering. Den sista oktetten ersätts med 0, och reglerna för IP-undantag måste uppdateras för att matcha IP-adresser med en nolla på slutet. Matchande * ska matcha 0.
