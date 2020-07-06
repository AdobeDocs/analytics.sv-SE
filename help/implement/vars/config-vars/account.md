---
title: konto
description: Använd kontovariabeln för att bestämma till vilken rapportsserie data ska skickas.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 1%

---


# konto

>[!IMPORTANT]
>
>Den här variabeln har tagits bort. Använd [`s.sa()`](../functions/sa-method.md) funktionen om implementeringen kräver att du ändrar rapportsvitens mål.

I tidigare versioner av Adobe Analytics fastställde variabeln den rapportserie som du vill skicka data till `account` . Du måste ha ett rapportsprogram-ID för att kunna skicka data till Adobe Analytics.

* Om du använder Adobe Experience Platform Launch ligger rapportsviterna under dragspelsfliken [!UICONTROL Library Management] när du konfigurerar Adobe Analytics-tillägget.
* Om du använder funktionen för att [`s_gi()`](../functions/s-gi.md) instansiera ett Analytics-spårningsobjekt finns rapportsvitens ID redan som ett obligatoriskt argument i funktionen.
