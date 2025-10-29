---
title: Första beröringskanaldetalj
description: Information om den första marknadsföringskanalen inom besökarens förfallotid för engagemang.
feature: Dimensions
exl-id: a155182d-7bc0-4c7d-9de7-680bfe2d6432
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Första beröringskanaldetalj

Den första beröringskanalinformationen [dimension](overview.md) rapporterar detaljer runt den första marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard). Denna dimension är värdefull för att förstå vad som har bidragit till träffmatchningen av en marknadsföringskanal. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.

## Fyll den här dimensionen med data

Den här dimensionen kopierar värden från andra variabler. Variabeln som används refererar till kanalvärdet inom varje [regel för bearbetning av marknadsföringskanal](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md). När en träff matchar en regel för bearbetning av marknadsföringskanal ställs dimensionen [Senaste beröringskanal](last-touch-channel.md) in på kanalnamnet, och den här dimensionen ställs in på kanalvärdet som angetts i regeln.

Om du vill ställa in dimensionen på ett specifikt värde måste du utföra följande steg:

* Kontrollera att önskat dimensionsobjekt finns i ett träffattribut eller en anpassad variabel.
* Ange en bearbetningsregel för marknadsföringskanal som innehåller de önskade villkoren för träffen.
* Välj önskat värde i listrutan under [!UICONTROL Set the channel's value] i regeln för bearbetning av marknadsföringskanal.
* Besökarens träff på din webbplats måste matcha de villkor som anges i regeln _för bearbetning av marknadsföringskanal och_ måste vara det första värdet i marknadsföringskanalen för att göra det under besökarens interaktionsperiod.

Om en efterföljande träff matchar kriterier under en annan marknadsföringskanal skrivs denna dimension inte över med den nya marknadsföringskanalen.

## Dimension-objekt

Dimension-objekt beror på vilket kanalvärde som anges i listrutan för den tillämpliga regeln för hantering av marknadsföringskanaler. Om du t.ex. anger kanalens värde som &quot;Sidadress&quot;, inkluderar dimensionsobjekten sidadresser på din webbplats. Om du anger kanalens värde till Referensdomän inkluderar dimensionsobjekten domäner som besökare klickade igenom för att komma till din webbplats. Denna dimension samlar alla detaljdimensionsobjekt, oavsett vilken kanal de finns i.

Adobe rekommenderar att du ställer in kanalvärden för marknadsföringskanalen för att få information om kanaldetaljer.
