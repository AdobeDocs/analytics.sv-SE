---
title: konto
description: Använd kontovariabeln för att bestämma till vilken rapportsserie data ska skickas.
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 1%

---

# konto

>[!IMPORTANT]
>
>Den här variabeln har tagits bort. Använd funktionen [`s.sa()`](../functions/sa-method.md) om implementeringen kräver att du ändrar rapportsvitens mål.

I tidigare versioner av Adobe Analytics bestämde variabeln `account` den rapportserie som du vill skicka data till. Du måste ange ett rapportsprogram-ID för att kunna skicka data till Adobe Analytics.

* Om du använder taggar i Adobe Experience Platform finns rapportsviter under dragspelet [!UICONTROL Library Management] när du konfigurerar Adobe Analytics-tillägget.
* Om du använder funktionen [`s_gi()`](../functions/s-gi.md) för att instansiera ett Analytics-spårningsobjekt finns rapportsvitens ID redan som ett obligatoriskt argument i funktionen.
