---
description: När du schemalägger en rapport kan du välja en publiceringslista som ska användas för distribution.
title: Tillåt åsidosättning av publiceringslista
feature: Report Builder
role: User, Admin
exl-id: a7bd6cdb-397a-45ba-88ff-c3b3c7062005
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# Tillåt åsidosättning av publiceringslista

När du schemalägger en rapport kan du välja en publiceringslista som ska användas för distribution.

Publiceringslistor konfigureras i verktygen för Analytics Admin.

Se [Publiceringslisthanteraren](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/publishing-list.html) i Analytics Reference.

Om du vill aktivera den här funktionen går du till [!UICONTROL Request Wizard: Step 1] -fönstret.

Om du aktiverar [!UICONTROL Allow Publishing List Override]ersätter rapportsviten som tilldelats varje mottagare i publiceringslistan rapportsviten för denna begäran. Om arbetsboken innehåller flera rapportsviter används dessutom det rapportsviter-ID som är kopplat till publiceringslistan.

Det här alternativet är inte tillgängligt för rapportsviter som du markerar i celler.

>[!NOTE]
>
>Om du skickar den schemalagda rapporten till flera publiceringslistor körs rapporten en gång för varje lista. Variabla rapportsviter ersätts med rapportsviten som tilldelats publiceringslistan.
