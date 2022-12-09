---
title: Senaste beröringskanaldetalj
description: Information om den senaste marknadsföringskanalen inom besökarens förfallotid för engagemang.
feature: Dimensions
exl-id: def03267-f3e5-4772-a707-5678c45eba6d
source-git-commit: ab0f0c80c13b9064b40511b59d03d9d899d20df1
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---

# Senaste beröringskanaldetalj

Dimensionen&quot;Senaste beröringskanaldetalj&quot; visar information om den senaste marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard). Denna dimension är värdefull för att förstå vad som har bidragit till träffmatchningen av en marknadsföringskanal. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.

## Fyll den här dimensionen med data

Den här dimensionen kopierar värden från andra variabler. Variabeln som används refererar till kanalvärdet inom varje [Bearbetningsregel för marknadsföringskanal](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels-admin.md). När en träff matchar en regel för hantering av marknadsföringskanaler [Senaste pekkanal](last-touch-channel.md) dimensionen är inställd på kanalnamnet och den här dimensionen är inställd på kanalvärdet som är angivet i regeln.

Om du vill ställa in dimensionen på ett specifikt värde måste du utföra följande steg:

* Kontrollera att önskat dimensionsobjekt finns i ett träffattribut eller en anpassad variabel.
* Ange en bearbetningsregel för marknadsföringskanal som innehåller de önskade villkoren för träffen.
* Välj önskat listrutevärde under [!UICONTROL Set the channel's value] inom marknadsföringskanalens bearbetningsregel.
* Besökarens träff på webbplatsen måste matcha de villkor som anges i regeln för bearbetning av marknadsföringskanal.

## Dimensioner

Dimensionen beror på kanalvärdets listruta. Om du t.ex. anger kanalens värde som &quot;Sidadress&quot;, inkluderar dimensionsobjekten sidadresser på din webbplats. Om du anger kanalens värde till Referensdomän inkluderar dimensionsobjekten domäner som besökare klickade igenom för att komma till din webbplats. Denna dimension samlar alla detaljdimensionsobjekt, oavsett vilken kanal de finns i.

Adobe rekommenderar att kanalvärden för marknadsföringskanalen ställs in för att få kunskap om kanaldetaljer.
