---
title: Uteslut data i Adobe Analytics
description: Lär dig olika metoder för att exkludera data både före och efter datainsamling.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---


# Uteslut data i Adobe Analytics

Att exkludera data används ofta för att förhindra att organisationens testarbete fyller i produktionsdata eller för att förhindra att oönskade data genererar felaktiga rapporter. Använd någon av följande metoder för att exkludera data från Adobe Analytics beroende på hur du använder dem.

## Uteslut datainsamling efter data

Följande metoder är ett sätt att utesluta data i analysrapporter efter att datainsamlingsservrarna i Adobe har tagit emot bildbegäranden. Data som utelämnats med dessa metoder räknas fortfarande in i fakturerbara serveranrop.

* **Exkludera via IP**: Adobe Analytics tillhandahåller grundläggande funktioner för att exkludera data för IP-adresser eller intervall i en rapportserie. Se [Uteslut via IP](/help/admin/admin/exclude-ip.md) i användarhandboken för Admin.
* **Punktregler**: Punktregler tar trafik från kända båda användaragentsträngar och utesluter dem från analysrapporter. Data som utesluts via båda reglerna placeras i Bots-rapporten. Anpassade robotregler kan skapas för att exkludera ytterligare data. Se [Punktregler](/help/admin/admin/bot-removal/bot-rules.md) i användarhandboken för Admin.
* **VISTA-regler**: Beroende på organisationens behov skickas träffar som matchar dina krav till en annan rapportsvit som är dedikerad till att ta emot exkluderade data. VISTA-regler används ofta mot IP-adresser, men är inte begränsade till dem. Du kan använda vilken dimension som helst för att inkludera eller exkludera data i rapportsviter. VISTA-reglerna är kostnadsbelagda. kontakta din organisations kontoansvarige för mer information.
* **Avanmäl cookies**: Alla besökare på webbplatsen kan frivilligt välja att inte spåra i Adobe Analytics genom att gå till en sida som är specifik för din spårningsserver. Se [Implementera avanmälningslänkar](/help/implement/js/opt-out.md) i Implementera användarhandbok.

>[!TIP]
>
>Bearbetningsregler kan inte utesluta data eller skicka data till en annan rapportserie. Vissa variabler kan dock ställas in villkorligt och ett segment kan användas för att utesluta data från rapporteringen.

## Uteslut datainsamling före datainsamling

Om du vill förhindra att vissa träffar når datainsamlingsservrarna för Analytics ska du använda [`abort`](/help/implement/vars/config-vars/abort.md) variabeln. Den här flaggan förhindrar att bildbegäran skickas. Fakturerbara serveranrop ökas inte för avbrutna bildbegäranden eftersom de inte når datainsamlingsservrar i Adobe.
