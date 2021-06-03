---
description: När du schemalägger en rapport kan du välja en publiceringslista som ska användas för distribution.
title: Tillåt åsidosättning av publiceringslista
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
feature: Report Builder
role: Business Practitioner, Administrator
exl-id: a7bd6cdb-397a-45ba-88ff-c3b3c7062005
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---

# Tillåt åsidosättning av publiceringslista

När du schemalägger en rapport kan du välja en publiceringslista som ska användas för distribution.

Publiceringslistor konfigureras i verktygen för Analytics Admin.

Se [Publiceringslisthanteraren](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/publishing-list.html) i Analytics Reference.

Om du vill aktivera den här funktionen går du till fönstret [!UICONTROL Request Wizard: Step 1].

Om du aktiverar [!UICONTROL Allow Publishing List Override] ersätter rapportsviten som tilldelats varje mottagare i publiceringslistan rapportsviten för denna begäran. Om arbetsboken innehåller flera rapportsviter används dessutom det rapportsviter-ID som är kopplat till publiceringslistan.

Det här alternativet är inte tillgängligt för rapportsviter som du markerar i celler.

>[!NOTE]
>
>Om du skickar den schemalagda rapporten till flera publiceringslistor körs rapporten en gång för varje lista. Variabla rapportsviter ersätts med rapportsviten som tilldelats publiceringslistan.
