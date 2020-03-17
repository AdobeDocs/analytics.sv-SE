---
description: Du kan undanta data från specifika IP-adresser, som interna webbplatsaktiviteter, platstestning och personalanvändning, från dina rapporter. Om du exkluderar data förbättras rapportens exakthet genom att IP-adressdata utesluts. Dessutom kan du ta bort data från denial of service eller andra skadliga händelser som kan förvränga rapportdata. Du kan konfigurera undantag eller använda brandväggen.
title: Exkludera efter IP-adress
topic: Admin tools
uuid: 1ed6105f-e7c5-4c4f-b8f4-e5f66d0824bb
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Exkludera efter IP-adress

Du kan undanta data från specifika IP-adresser, som interna webbplatsaktiviteter, platstestning och personalanvändning, från dina rapporter. Om du exkluderar data förbättras rapportens exakthet genom att IP-adressdata utesluts. Dessutom kan du ta bort data från denial of service eller andra skadliga händelser som kan förvränga rapportdata. Du kan konfigurera undantag eller använda brandväggen.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Exclude by IP]**

> [!NOTE] Träffar som exkluderats av IP-adressen faktureras som [serversamtal](https://marketing.adobe.com/resources/help/en_US/reference/primary_server_calls.html).

## Uteslut av cookie {#section_FB5A20AB5E514DA6BC596CC67F6A3A4C}

Gör att du kan utesluta att den här datorn spåras i ditt konto. Om du väljer att utesluta datorn räknas inga data som genereras från datorn.

Med den här funktionen kan du och dina kollegor besöka webbplatsen utan att behöva skeva dina trafikdata. Du kan använda den här funktionen om du inte har en statisk IP-adress (till exempel en uppringd Internet-anslutning via en tjänsteleverantör) och vill utesluta dig själv från dina kontodata.

| Element | Beskrivning |
|--- |--- |
| [!UICONTROL Add CNAME] | Skapar en länk för avanmälan som du kan använda för att utesluta din domän. Kontakta företagets användare om du behöver hjälp. <br>Din trafik kan uteslutas från rapporteringen i dina rapportsviter genom att besöka företagets avanmälningssida och välja att utesluta webbläsaren från mätningen. <br>Om implementeringen använder cookies från tredje part finns din avanmälningssida [här](https://democorp.112.2o7.net/optout.html?locale=en_US&popup=true). |

> [!NOTE] Uteslutning per dator fungerar endast om:
>
> * Du kommer åt din webbplats från samma arbetsstation.
> * Dina cookies är aktiverade i den webbläsare du använder.
> * Dina cookies tas inte bort. Om cookies tas bort måste du utesluta dig själv igen.


## Exkludera efter IP-adress {#section_609FB6461529409D840111A32FEF5C3D}

En IP-adress är en Internetadress. Alla internetanvändare tilldelas numeriska IP-adresser (vanligtvis via Internet-leverantörer) som fungerar effektivt som elektroniska identifierare.

Sidvisningar räknas och unika sidbesökare identifieras via IP-adresser. Genom att utesluta IP-adresser från räkningen kan du hindra Adobe från att spåra besökare som ofta är återkommande. Med den här funktionen kan du och dina kollegor besöka webbplatsen utan att behöva skeva dina trafikdata. Du kan utesluta upp till 50 olika IP-adresser.

Du kan använda jokertecken (*) för att exkludera ett adressintervall. Till exempel `[!DNL 0.0.*.0]` skulle alla IP-adresser mellan `[!DNL 0.0.0.0]` och `[!DNL 0.0.255.0]`utelämnas. Du kan utesluta upp till 50 olika IP-adresser.

## Exkludera via brandvägg {#section_3E7BFB71ADD941D39F923DB9557AD9CD}

Du kan även blockera datainsamling från specifika IP-adresser via en brandvägg.

Se [IP-adresserna som används i Experience Cloud](https://marketing.adobe.com/resources/help/en_US/home/index.html#kb-adobe-ip-addresses) -artikeln.

## Inverkan av IP-missbruk {#section_51B7529FFF16449CA016FDC51D87E2CA}

Om IP-förfalskning är aktiverat inträffar IP-uteslutning innan IP-adressen döljs, så kunderna behöver inte ändra någonting när de aktiverar IP-förfalskning.

Om den sista oktetten tas bort, görs det före IP-filtrering. Den sista oktetten ersätts med 0, och reglerna för IP-undantag måste uppdateras för att matcha IP-adresser med en nolla på slutet. Matchande * ska matcha 0.
