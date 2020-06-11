---
title: Senaste beröringskanaldetalj
description: Information om den senaste marknadsföringskanalen inom besökarens förfallotid för engagemang.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---


# Senaste beröringskanaldetalj

Dimensionen&quot;Senaste beröringskanaldetalj&quot; visar information om den senaste marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard). Denna dimension är värdefull för att förstå vad som har bidragit till träffmatchningen av en marknadsföringskanal. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.

## Fyll den här dimensionen med data

Den här dimensionen kopierar värden från andra variabler. Variabeln som används refererar till kanalvärdet inom varje [regel](/help/admin/admin/marketing-channels-admin.md)för bearbetning av marknadsföringskanaler. När en träff matchar en regel för hantering av marknadsföringskanal ställs dimensionen för den [sista beröringskanalen](last-touch-channel.md) in på kanalnamnet, och den här dimensionen ställs in på kanalvärdet som anges i regeln.

Om du vill ställa in dimensionen på ett specifikt värde måste du utföra följande steg:

* Kontrollera att det önskade dimensionsvärdet finns i ett träffattribut eller en anpassad variabel.
* Ange en bearbetningsregel för marknadsföringskanal som innehåller de önskade villkoren för träffen.
* Välj önskat listrutevärde under [!UICONTROL Set the channel's value] bearbetningsregeln för marknadsföringskanal.
* Besökarens träff på webbplatsen måste matcha de villkor som anges i regeln för bearbetning av marknadsföringskanal.

## Dimensionsvärden

Dimensionsvärdena beror på kanalvärdets listruta. Om du t.ex. anger kanalens värde som &quot;Sidadress&quot;, inkluderar dimensionsvärdena sidadresser på webbplatsen. Om du anger kanalens värde till Referensdomän inkluderar dimensionsvärdena domäner som besökarna klickade igenom för att komma till din webbplats. Denna dimension samlar alla detaljdimensionsvärden, oavsett vilken kanal de finns i.

Adobe rekommenderar att du ställer in kanalvärden för marknadsföringskanalen för att få information om kanaldetaljer.
