---
description: När du schemalägger en rapport kan du välja en publiceringslista som ska användas för distribution.
title: Tillåt åsidosättning av publiceringslista
topic: Report builder
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tillåt åsidosättning av publiceringslista

När du schemalägger en rapport kan du välja en publiceringslista som ska användas för distribution.

Publiceringslistor konfigureras i verktygen för Analytics Admin.

Se [Publiceringslisthanteraren](https://marketing.adobe.com/resources/help/en_US/reference/publishing_list.html) i Analytics Reference.

Navigera till [!UICONTROL Request Wizard: Step 1] fönstret om du vill aktivera den här funktionen.

Om du aktiverar [!UICONTROL Allow Publishing List Override]ersätter rapportsviten som tilldelats varje mottagare i publiceringslistan rapportsviten för denna begäran. Om arbetsboken innehåller flera rapportsviter används dessutom det rapportsviter-ID som är kopplat till publiceringslistan.

Det här alternativet är inte tillgängligt för rapportsviter som du markerar i celler.

> [!NOTE] Om du skickar den schemalagda rapporten till flera publiceringslistor körs rapporten en gång för varje lista. Variabla rapportsviter ersätts med rapportsviten som tilldelats publiceringslistan.

