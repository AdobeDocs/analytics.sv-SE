---
description: När du schemalägger en rapport kan du välja en publiceringslista som ska användas för distribution.
title: Tillåt åsidosättning av publiceringslista
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
feature: Report Builder
role: Affärsledare, administratör
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 1%

---


# Tillåt åsidosättning av publiceringslista

När du schemalägger en rapport kan du välja en publiceringslista som ska användas för distribution.

Publiceringslistor konfigureras i verktygen för Analytics Admin.

Se [Publiceringslisthanteraren](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/publishing-list.html) i Analytics Reference.

Om du vill aktivera den här funktionen går du till fönstret [!UICONTROL Request Wizard: Step 1].

Om du aktiverar [!UICONTROL Allow Publishing List Override] ersätter rapportsviten som tilldelats varje mottagare i publiceringslistan rapportsviten för denna begäran. Om arbetsboken innehåller flera rapportsviter används dessutom det rapportsviter-ID som är kopplat till publiceringslistan.

Det här alternativet är inte tillgängligt för rapportsviter som du markerar i celler.

>[!NOTE]
>
>Om du skickar den schemalagda rapporten till flera publiceringslistor körs rapporten en gång för varje lista. Variabla rapportsviter ersätts med rapportsviten som tilldelats publiceringslistan.

