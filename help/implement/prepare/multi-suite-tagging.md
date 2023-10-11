---
description: Lär dig hur du implementerar märkning för flera programsviter för att skicka bildförfrågningar till flera rapportsviter.
title: Implementera märkning för flera programsviter
feature: Implementation Basics
exl-id: c7fb0478-97e1-4367-8742-e7539f6f82e7
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---

# Implementera märkning för flera programsviter

[Taggar för flera programsviter](/help/admin/admin/c-manage-report-suites/rollup-report-suite.md) Med kan du skicka bildbegäranden inte bara till en global rapportserie utan även till enskilda underordnade rapportsviter så att du kan tillhandahålla delmängder av företagets globala rapportserie till olika slutanvändare.

Om du vill implementera taggning för flera programsviter måste du inkludera Report Suite-ID (RSID) för den globala rapportsviten och även RSID:n för de underordnade rapportsviterna i spårningskoden för dina webbsidor och appar.

* För implementering av Adobe Experience Platform-taggar anger du var och en av rapportsviterna för [[!DNL Analytics] extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html).

* För äldre JavaScript- och mobil SDK-implementeringar ska RSID-värdena separeras med kommatecken och utan blanksteg (`rsid1,rsid2,rsid3` och så vidare).

* För andra implementeringstyper använder du den syntax som krävs för att lista flera RSID:er.

>[!TIP]
>
> Det bästa sättet är att först lista den globala rapportsviten eller rapportsvitens-ID.

Taggar för flera programsviter innebär flera serveranrop för varje bildbegäran: ett primärt anrop till den globala rapportsviten och ett sekundärt anrop för varje underordnad rapportsvit.

>[!NOTE]
>
> [Virtuella rapportsviter](/help/components/vrs/vrs-about.md), som också gör det möjligt att tillhandahålla delmängder av företagets globala rapportsvitdata till olika slutanvändare, medför inte sekundära serveranrop.

## Ska jag implementera märkning av flera programsviter eller virtuella rapportsviter?

Att använda virtuella rapportsviter i stället för taggning i flera programsviter är ofta en bra metod, men ditt företags behov avgör vilket rapporteringsprogram som passar bäst för din organisation.

Om du vill veta om virtuella rapportsviter är ditt bästa tillvägagångssätt kan du läsa &quot;[Virtuella rapportsviter och taggar för flera programsviter](/help/components/vrs/vrs-considerations.md).&quot; Se även &quot;[Virtuella rapportsviter jämfört med taggar för flera programsviter](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot; för en jämförelse av taggning i flera programsviter och funktioner i virtuella rapportsviter.
