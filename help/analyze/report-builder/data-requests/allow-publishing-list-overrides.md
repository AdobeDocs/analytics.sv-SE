---
description: När du schemalägger en rapport kan du välja en publiceringslista som ska användas för distribution.
title: Tillåt åsidosättning av publiceringslista
topic: Report builder
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---


# Tillåt åsidosättning av publiceringslista

När du schemalägger en rapport kan du välja en publiceringslista som ska användas för distribution.

Publiceringslistor konfigureras i Analytics Admin-verktygen.

Se [Publiceringslisthanteraren](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/publishing-list.html) i Analytics Reference.

Navigera till [!UICONTROL Request Wizard: Step 1] fönstret om du vill aktivera den här funktionen.

Om du aktiverar [!UICONTROL Allow Publishing List Override]ersätter rapportsviten som tilldelats varje mottagare i publiceringslistan rapportsviten för denna begäran. Om arbetsboken innehåller flera rapportsviter används dessutom det rapportsviter-ID som är kopplat till publiceringslistan.

Det här alternativet är inte tillgängligt för rapportsviter som du markerar i celler.

>[!NOTE]
>
>Om du skickar den schemalagda rapporten till flera publiceringslistor körs rapporten en gång för varje lista. Variabla rapportsviter ersätts med rapportsviten som tilldelats publiceringslistan.

