---
description: Beskrivningar av rapporttyper och jämförelse av globala rapportsviter och sammanfattningsrapportsviter.
title: Rapportera metoder för programsvit
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '875'
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

  Om du vill använda virtuella rapportsviter implementerar du en global rapportsvit och tolkar sedan data för att skapa virtuella rapportsviter med specifika segment och med specifika gruppbehörigheter. Du kan skapa virtuella rapportsviter i Virtual Report Suites-hanteraren ([!UICONTROL Components] > [!UICONTROL Virtual report suites]). Se &quot;[Arbetsflöde för virtuella rapportsviter](/help/components/vrs/c-workflow-vrs/vrs-workflow.md)&quot; för mer information.

Att använda virtuella rapportsviter i stället för taggning i flera sviter är ofta en bra metod, men virtuella rapportsviter har vissa begränsningar. Se &quot;[Virtuella rapportsviter och taggar för flera programsviter](/help/components/vrs/vrs-considerations.md)&quot; för att avgöra vilken rapportsviter som är det bästa valet för era affärsbehov. En detaljerad jämförelse av virtuella rapportsviter och taggningsfunktioner för flera sviter finns i &quot;[Virtuella rapportsviter jämfört med märkning för flera programsviter](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78).&quot;

## Sammanslagningsrapporter

>[!NOTE]
>
>[!DNL Reports & Analytics] är det enda verktyg som stöder sammanslagningsrapporter. Rapporter och analyser upphörde den 17 januari 2024.

### Begränsningar för sammanslagningsrapporter {#limitations-rollups}

* Sammanslagningar ger totaldata, men de rapporterar inte enskilda värden i rapporter. EVar1-värden inkluderas till exempel inte, men deras sammanlagda summa kan vara det.
* Data dedupliceras inte när sammanslagningen kombinerar data mellan olika rapportsviter.
* Upprullningar går nattetid vid midnatt.
* När du lägger till en rapportserie i en befintlig sammanslagning inkluderas inte historiska data i sammanslagningen.
* Alla underordnade rapportsviter måste ha data i dem för att en sammanslagning ska fungera. Om nya rapportsviter ingår i en sammanslagning måste du skicka minst en sidvy till var och en av dessa rapportsviter.
* Sammanslagningsrapportsviter kan innehålla maximalt 40 underordnade rapportsviter.
* Sammanslagningsrapportsviter kan innehålla maximalt 100 händelser.
* Data i sammanslagningsrapportsviter stöder inte uppdelningar eller segment.
* Sidrapporten ersätts med rapporten Most Popular Sites (Populära platser), som rapporterar mått på underordnad svitnivå.

## Jämförelse av funktionerna i Global Report Suite och Sammanslagningsrapport

**Sekundära serveranrop**: Vid sammanslagning uppstår inga ytterligare serveranrop utöver vad en enskild rapportserie samlar in. Om din organisation använder taggar för flera programsviter görs sekundära serveranrop för varje extra rapportsvit som ingår i en bildbegäran.

>[!TIP]
>
>Om du bara använder en global rapportserie med [virtuella rapportsviter](/help/components/vrs/vrs-considerations.md)behövs inga sekundära serveranrop.

**Implementeringsändringar**: Vid sammanslagning krävs inga implementeringsändringar, medan globala rapportsviter kräver att du inkluderar det globala rapportsvitens ID i implementeringen.

**Duplicering**: Globala rapportsviter dubblerar unika besökare, men inte sammanslagningar. Om en användare till exempel besöker tre av dina domäner under samma dag, kommer sammanslagningar att räkna tre unika besökare per dag. Global rapportserie registrerar en unik besökare.

**Tidsram**: Samlingar behandlas endast vid midnatt varje kväll, medan globala rapportsviter rapporterar data med standardfördröjning.

**Bredd**: Samlingar kan inte kommunicera mellan rapportsviter. Globala rapportsviter kan attribuera konverteringar till konverteringsvariabler mellan olika rapportsviter och tillhandahålla sökvägar mellan rapportsviter.

**Historiska data**: Samlingar kan samla in historiska data, medan globala rapportsviter bara rapporterar data från den punkt de implementerades.

**Rapporter**: Globala rapportsviter innehåller data om alla dimensioner; sammanslagningar tillhandahåller aggregerade data på enbart högnivårapporter.

**Produkter som stöds**: Samlingar kan bara användas i rapporter och analyser. De stöds inte i Analysis Workspace eller Data Warehouse. Globala rapportsviter kan användas för alla produkter.

**Antal aggregerade rapportsviter**: Samlingar stöder endast maximalt 40 underordnade rapportsviter. Globala rapportsviter kan implementeras på valfritt antal domäner eller appar som du äger.
