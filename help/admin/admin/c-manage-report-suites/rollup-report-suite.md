---
description: Beskrivningar av rapporttyper och jämförelse av globala rapportsviter och sammanfattningsrapportsviter.
title: Rapportera metoder för programsvit
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '967'
ht-degree: 0%

---

# Rapportera metoder för programsvit

<!-- change filename since page name changed? -->

Du kan konfigurera dina rapportsviter som antingen *globala rapportsviter* eller *rapportsviter för sammanslagning*.

## Globala rapportsviter

En global rapportserie samlar in data från alla domäner och appar som organisationen äger. Implementeringen kräver att alla bildbegäranden skickas till en enda rapportserie.

Adobe rekommenderar att man i de flesta fall genomför en global rapportserie. Se &quot;[Överväganden för globala rapportsviter](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html)&quot; för fördelarna med att implementera en global rapportserie.

Du kan tillhandahålla delmängder av företagets globala rapportsvitsdata till olika slutanvändare med hjälp av *taggning för flera programsviter* och *virtuell rapportsvit* metoder:

* **Taggar för flera programsviter**: Med taggar för flera programsviter kan du skicka bildbegäranden inte bara till en global rapportsvit utan även till enskilda underordnade rapportsviter. De globala rapportdata dedupliceras i alla rapportsviter.

   Du kan till exempel samla in alla data i en global rapportserie och även skapa sekundära rapportsviter baserade på varumärke, region eller annan differentiator. De olika teamen i företaget kan sedan fokusera på data i de rapportsviter som är relevanta för dem.

   Om du vill använda flera svittaggar implementerar du underordnade rapportsviter och en global rapportserie som innehåller alla data från de underordnade. Spårningskoden för dina webbsidor och appar inkluderar Report Suite ID (RSID) för den globala rapportsviten och även RSID för de tillämpliga underordnande rapportsviterna.<!-- Wording/be more specific? And include any links? -->

   Ett separat serveranrop görs till varje rapportssvit i bildbegäran. Anropen till de underordnade rapportsviterna är sekundära anrop.

* **Virtuell rapportsvit**: A [virtuell rapportsvit](/help/components/vrs/vrs-about.md) är en fråga om angivna segment som samlats in i en global rapportserie och som är tillgängliga för angivna användargrupper. Med virtuella rapportsviter kan du strukturera rapportelement för olika slutanvändare utan att behöva använda flera svittaggar, vilket undviker sekundära serveranrop.

   Om du vill använda virtuella rapportsviter implementerar du en global rapportsvit och tolkar sedan data för att skapa virtuella rapportsviter med specifika segment och med specifika gruppbehörigheter. Du kan skapa virtuella rapportsviter i Virtual Report Suite Manager ([!UICONTROL Components] > [!UICONTROL Virtual Report Suites]). Se &quot;[Arbetsflöde för virtuella rapportsviter](/help/components/vrs/c-workflow-vrs/vrs-workflow.md)&quot; för mer information.

Att använda virtuella rapportsviter i stället för taggning i flera sviter är ofta en bra metod, men virtuella rapportsviter har vissa begränsningar. Se &quot;[Virtuella rapportsviter och taggar för flera programsviter](/help/components/vrs/vrs-considerations.md)&quot; för att avgöra vilken rapportsviter som är det bästa valet för era affärsbehov. En detaljerad jämförelse av virtuella rapportsviter och taggningsfunktioner för flera sviter finns i &quot;[Virtual Report Suites vs. Multisuite Taggning](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78).&quot;

## Sammanslagningsrapporter

>[!NOTE]
>
>[!DNL Reports & Analytics] är det enda verktyget som stöder sammanslagningsrapporter, och Adobe rekommenderar inte längre att du använder sammanslagningar. Överväg i stället att använda en global rapportserie med taggar för flera programsviter eller virtuella rapportsviter.

En sammanslagningsrapport är en enkel sammanställning av data från flera rapportsviter, utan borttagning av dubbletter eller någon segmentering eller datauppdelning. För sammanslagningar krävs ingen kodimplementering. Om du vill använda sammanslagningsrapporter [implementera underordnade rapportsviter](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) och sedan [kombinera dem i en sammanställningsrapport](/help/admin/admin/c-manage-report-suites/t-rollups.md) använda [!UICONTROL Admin Tools].

Sammanslagningsrapporter är kostnadsfria: den underordnade rapportsviten har egna serveranrop, men sammanslagningen medför inga ytterligare anrop. Sammanslagning är en äldre funktion och har många begränsningar.

### Begränsningar för sammanslagningsrapporter {#limitations-rollups}

* Sammanslagningar ger totaldata, men de rapporterar inte enskilda värden i rapporter. eVar1-värden inkluderas till exempel inte, men deras sammanlagda summa kan vara det.
* Data dedupliceras inte när sammanslagningen kombinerar data mellan olika rapportsviter.
* Upprullningar går nattetid vid midnatt.
* När du lägger till en rapportserie i en befintlig sammanslagning inkluderas inte historiska data i sammanslagningen.
* Alla underordnade rapportsviter måste ha data i dem för att en sammanslagning ska fungera. Om nya rapportsviter ingår i en sammanslagning måste du skicka minst en sidvy till var och en av dessa rapportsviter.
* Sammanslagningsrapportsviter kan innehålla maximalt 40 underordnade rapportsviter.
* Sammanslagningsrapportsviter kan innehålla maximalt 100 händelser.
* Data i sammanslagningsrapportsviter stöder inte uppdelningar eller segment.
* Sidrapporten ersätts med rapporten Most Popular Sites (Populära platser), som rapporterar mått på underordnad svitnivå.

## Jämförelse av funktionerna i Global Report Suite och Sammanslagningsrapport

**Sekundära serveranrop**: Vid sammanslagning uppstår inga ytterligare serveranrop utöver vad en enda rapportserie samlar in. Om din organisation använder taggar för flera programsviter görs sekundära serveranrop för varje extra rapportsvit som ingår i en bildbegäran.

>[!TIP]
>
>Om du bara använder en global rapportserie med [virtuella rapportsviter](/help/components/vrs/vrs-considerations.md)behövs inga sekundära serveranrop.

**Implementeringsändringar**: Vid sammanslagning krävs inga implementeringsändringar, medan globala rapportsviter kräver att du inkluderar det globala rapportsvitens ID i implementeringen.

**Duplicering**: Globala rapportsviter dubblerar unika besökare, men inte sammanslagningar. Om en användare till exempel besöker tre av dina domäner under samma dag, kommer sammanslagningar att räkna tre unika besökare per dag. Global rapportserie registrerar en unik besökare.

**Tidsram**: Samlingar behandlas endast vid midnatt varje kväll, medan globala rapportsviter rapporterar data med standardfördröjning.

**Bredd**: Uppsättningar kan inte kommunicera mellan rapportsviter. Globala rapportsviter kan attribuera konverteringar till konverteringsvariabler mellan olika rapportsviter och tillhandahålla sökvägar mellan rapportsviter.

**Historiska data**: Sammanslagningar kan samla in historiska data, medan globala rapportsviter bara rapporterar data från den punkt de implementerades.

**Rapporter**: Globala rapportsviter innehåller data om alla dimensioner. sammanslagningar tillhandahåller aggregerade data på enbart högnivårapporter.

**Produkter som stöds**: Samlingar kan bara användas i rapporter och analyser. De stöds inte i Analysis Workspace eller Data warehouse. Globala rapportsviter kan användas för alla produkter.

**Antal aggregerade rapportsviter**: Samlingar stöder endast maximalt 40 underordnade rapportsviter. Globala rapportsviter kan implementeras på valfritt antal domäner eller appar som du äger.
