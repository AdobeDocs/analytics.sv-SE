---
title: Identifiering av besökare med hjälp av taggtillägget Web SDK
description: Identifiera besökare korrekt när du implementerar SDK-taggtillägget för webben.
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 0%

---

# Identifiering av besökare med hjälp av taggtillägget Web SDK

Med taggtillägget Web SDK i Adobe Experience Platform Data Collection kan man implementera Web SDK med hjälp av ett tagghanteringsgränssnitt. Avancerade scenarier som delning av domänöverskridande ID och migrering av besökarprofiler kan enkelt konfigureras via tilläggsregler och åtgärder. Med Web SDK framtidssäkrar du implementeringen och stöder en smidig uppgradering till Customer Journey Analytics.

Eftersom besökar-ID-tjänsten är inbyggd i taggtillägget, behöver du bara ange **[!UICONTROL Edge Domain]** till det önskade värdet. Om det här fältet är korrekt fungerar besökaridentifiering utan ytterligare konfiguration.

>[!NOTE]
>
>Inkludera inte besökar-ID-tjänstens taggtillägg om du använder Web SDK-taggtillägget. Tillägget för service tag-taggen för Visitor ID krävs bara om du använder [Adobe Analytics-tillägget](analytics-extension.md).
