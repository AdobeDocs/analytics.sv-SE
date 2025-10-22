---
title: Identifiering av besökare med hjälp av taggtillägget Web SDK
description: Identifiera besökare korrekt när du implementerar SDK-taggtillägget för webben.
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# Identifiering av besökare med hjälp av taggtillägget Web SDK

Med taggtillägget Web SDK i Adobe Experience Platform Data Collection kan man implementera Web SDK med hjälp av ett tagghanteringsgränssnitt. Avancerade scenarier som delning av domänöverskridande ID och migrering av besökarprofiler kan enkelt konfigureras via tilläggsregler och åtgärder. Med Web SDK framtidssäkrar du implementeringen och stöder en smidig uppgradering till Customer Journey Analytics.

Identitetsdata kan utökas med stöd för anpassade ID:n och flera namnutrymmen med hjälp av XDM:s `identityMap`. Adobe rekommenderar att du använder Adobe Experience Cloud ID Service som primär identifierare för Analytics, och använder andra identitetshanteringsalternativ för avancerade scenarier.

Eftersom besökar-ID-tjänsten är inbyggd i taggtillägget, behöver du bara ange **[!UICONTROL Edge Domain]** till det önskade värdet. Om det här fältet är korrekt fungerar besökaridentifiering utan ytterligare konfiguration.

>[!NOTE]
>
>Inkludera inte besökar-ID-tjänstens taggtillägg om du använder Web SDK-taggtillägget. Tillägget för service tag-taggen för Visitor ID krävs bara om du använder [Adobe Analytics-tillägget](analytics-extension.md).
