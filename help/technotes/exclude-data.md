---
title: Uteslut data i Adobe Analytics
description: Lär dig olika metoder för att exkludera data både före och efter datainsamling.
exl-id: dee5bf3b-8bb3-48eb-908d-b4a981f17bfb
feature: Data Configuration and Collection
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Uteslut data i Adobe Analytics

Att exkludera data används ofta för att förhindra att organisationens testarbete fyller i produktionsdata eller för att förhindra att oönskade data genererar felaktiga rapporter. Använd någon av följande metoder för att exkludera data från Adobe Analytics beroende på hur du använder dem.

## Uteslut datainsamling efter data

Följande metoder är ett sätt att utesluta data i analysrapporter när Adobe datainsamlingsservrar tar emot bildbegäranden. Data som utelämnats med dessa metoder räknas fortfarande in i fakturerbara serveranrop.

* **Exkludera med IP**: Adobe Analytics tillhandahåller grundläggande funktioner för att exkludera data för IP-adresser eller intervall i en rapportserie. Se [Uteslut av IP](/help/admin/tools/exclude-ip.md) i användarhandboken för Admin.
* **Punktregler**: Punktregler tar trafik från kända båda användaragentsträngar och exkluderar dem från analysrapporter. Data som utesluts via båda reglerna placeras i Bots-rapporten. Anpassade robotregler kan skapas för att exkludera ytterligare data. Se [Punktregler](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) i användarhandboken för Admin.
* **VISTA-regler**: Beroende på organisationens behov skickas träffar som matchar dina krav till en annan rapportsvit som är dedikerad till att ta emot exkluderade data. VISTA-regler används ofta mot IP-adresser, men är inte begränsade till dem. Du kan använda vilken dimension som helst för att inkludera eller exkludera data i rapportsviter. Ytterligare kostnader kan tillkomma för VISTA-reglerna. Kontakta Adobe Account Team för mer information.
* **Avanmäl cookies**: Alla besökare på webbplatsen kan frivilligt avanmäla sig från spårning i Adobe Analytics genom att besöka en sida som är specifik för spårningsservern. Se [Implementera länkar för avanmälan](/help/implement/js/opt-out.md) i användarhandboken för implementering.

>[!TIP]
>
>Bearbetningsregler kan inte utesluta data eller skicka data till en annan rapportserie. Vissa variabler kan dock ställas in villkorligt och ett segment kan användas för att utesluta data från rapporteringen.

## Uteslut datainsamling före datainsamling

Använd variabeln [`abort`](/help/implement/vars/config-vars/abort.md) om du vill förhindra att vissa träffar når datainsamlingsservrar för Analytics. Den här flaggan förhindrar att bildbegäran skickas. Fakturerbara serveranrop ökas inte för avbrutna bildbegäranden eftersom de inte når Adobe datainsamlingsservrar.
