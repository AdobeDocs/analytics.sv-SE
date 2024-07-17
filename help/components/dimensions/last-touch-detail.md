---
title: Senaste beröringskanaldetalj
description: Information om den senaste marknadsföringskanalen inom besökarens förfallotid för engagemang.
feature: Dimensions
exl-id: def03267-f3e5-4772-a707-5678c45eba6d
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 0%

---

# Senaste beröringskanaldetalj

[Dimension](overview.md) för den senaste beröringskanalen visar information om den senaste marknadsföringskanalen som besökaren matchar under besökarens engagemangsperiod (30 dagar som standard). Denna dimension är värdefull för att förstå vad som har bidragit till träffmatchningen av en marknadsföringskanal. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.

## Fyll den här dimensionen med data

Den här dimensionen kopierar värden från andra variabler. Variabeln som används refererar till kanalvärdet inom varje [regel för bearbetning av marknadsföringskanal](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md). När en träff matchar en regel för bearbetning av marknadsföringskanal ställs dimensionen [Senaste beröringskanal](last-touch-channel.md) in på kanalnamnet, och den här dimensionen ställs in på kanalvärdet som angetts i regeln.

Om du vill ställa in dimensionen på ett specifikt värde måste du utföra följande steg:

* Kontrollera att önskat dimensionsobjekt finns i ett träffattribut eller en anpassad variabel.
* Ange en bearbetningsregel för marknadsföringskanal som innehåller de önskade villkoren för träffen.
* Välj önskat värde i listrutan under [!UICONTROL Set the channel's value] i regeln för bearbetning av marknadsföringskanal.
* Besökarens träff på webbplatsen måste matcha de villkor som anges i regeln för bearbetning av marknadsföringskanal.

## Dimensioner

Dimensioner beror på vilket kanalvärde som anges i listrutan för den tillämpliga regeln för hantering av marknadsföringskanaler. Om du t.ex. anger kanalens värde som &quot;Sidadress&quot;, inkluderar dimensionsobjekten sidadresser på din webbplats. Om du anger kanalens värde till Referensdomän inkluderar dimensionsobjekten domäner som besökare klickade igenom för att komma till din webbplats. Denna dimension samlar alla detaljdimensionsobjekt, oavsett vilken kanal de finns i.

Adobe rekommenderar att kanalvärden för marknadsföringskanalen ställs in för att få kunskap om kanaldetaljer.
