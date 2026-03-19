---
title: Exkludera efter IP-adress
description: Förhindra att data som genereras av vissa IP-adresser visas i rapporter.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: 4b4febd839682d88164b2f505245441d18ef2543
workflow-type: tm+mt
source-wordcount: '312'
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
>* Träffar som exkluderats av IP-adressen faktureras som [serveranrop](/help/technotes/terms.md).
>* Privata IP-adresser behöver inte uteslutas. Endast externa IP-adresser når Adobe datainsamlingsservrar. Privata adresser omfattar `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*` och `169.254.*.*`.
>* Du kan använda jokertecken (&#42;) för att exkludera ett adressintervall. `[!DNL 0.0.*.0]` skulle till exempel exkludera alla IP-adresser mellan `[!DNL 0.0.0.0]` och `[!DNL 0.0.255.0]`. Du kan utesluta upp till 50 olika IP-adresser.
>* Data från en utelämnad IP-adress utelämnas för nya träffar som kommer in i systemet inom 5 minuter efter det att undantaget har angetts.
>* Data för träffar som fångats in före den tidpunkt då IP-adressen ändrades påverkas inte. IP-undantag gäller endast data som flyttas framåt.
>* Exkluderade träffar visas fortfarande i [Dataflöden](/help/export/analytics-data-feed/data-feed-overview.md) (flaggade som `exclude_hit = 4`).

Så här konfigurerar du undantag efter IP-adress:

1. I Adobe Analytics väljer du **[!UICONTROL Admin]** > **[!UICONTROL All admin]**.

1. Välj **[!UICONTROL Exclude by IP]** på administratörssidan.

## Inverkan av att använda IP-missbruk med IP-undantag

Effekten av att använda [IP-döljning](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) tillsammans med IP-exkludering beror på varje rapportsvits inställning för IP-döljning:

* **IP-förvrängning (senaste oktett)**: IP-adressen är delvis okomplicerad INNAN IP-undantaget körs. Kontrollera att IP-exkluderingsreglerna alltid förväntar sig `0` som den sista oktetten (jokertecken är giltiga eftersom de innehåller `0`).
* **IP-förfalskning (ta bort IP)**: IP är fullständigt dolt EFTER att IP-undantag har körts. Det behövs inga alternativ för IP-exkluderingsregler.
