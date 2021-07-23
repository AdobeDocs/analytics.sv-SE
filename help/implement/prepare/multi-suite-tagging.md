---
description: Lär dig hur du implementerar märkning för flera programsviter för att skicka bildförfrågningar till flera rapportsviter.
title: Implementera märkning för flera programsviter
exl-id: null
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---


# Implementera märkning för flera programsviter

[Med ](/help/admin/c-manage-report-suites/rollup-report-suite.md) taggning för flera programsviter kan du skicka bildbegäranden inte bara till en global rapportsvit utan även till enskilda underordnade rapportsviter, så att du kan tillhandahålla delmängder av företagets globala rapportsviter till olika slutanvändare.

Om du vill implementera taggning för flera programsviter måste du inkludera Report Suite-ID (RSID) för den globala rapportsviten och även RSID:n för de underordnade rapportsviterna i spårningskoden för dina webbsidor och appar.

* För implementeringar av Adobe Experience Platform-taggar anger du var och en av rapportsviterna för [[!DNL Analytics] tillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html).

* För äldre JavaScript- och mobil-SDK-implementeringar skiljer du RSID:erna med kommatecken och utan blanksteg (`rsid1,rsid2,rsid3` och så vidare).

* För andra implementeringstyper använder du den syntax som krävs för att lista flera RSID.

>[!TIP]
>
> Det bästa sättet är att först lista den globala rapportsviten eller rapportsvitens-ID.

Taggar för flera programsviter medför flera serveranrop för varje bildbegäran: ett primärt anrop till den globala rapportsviten och ett sekundärt anrop för varje underordnad rapportsvit.

>[!NOTE]
>
> [Virtuella rapportsviter](/help/components/vrs/vrs-about.md), som även gör det möjligt att tillhandahålla deluppsättningar av företagets globala rapportsvitsdata till olika slutanvändare, kräver inte sekundära serveranrop.

## Ska jag implementera märkning av flera programsviter eller virtuella rapportsviter?

Att använda virtuella rapportsviter i stället för taggning i flera programsviter är ofta en bra metod, men ditt företags behov avgör vilket rapporteringsprogram som passar bäst för din organisation.

Om du vill veta om virtuella rapportsviter är det bästa sättet ska du läsa &quot;[Virtual Report suites and multi-suite tagging Consider](/help/components/vrs/vrs-considerations.md).&quot; Se även &quot;[Virtual Report Suites vs. Multisuite Tagging](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot; för en jämförelse av flersuite-taggning och funktioner för virtuella rapportsviter.
