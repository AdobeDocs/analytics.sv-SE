---
title: konto
description: Använd kontovariabeln för att bestämma till vilken rapportsserie data ska skickas.
translation-type: tm+mt
source-git-commit: f179292abae9cf7986d61da89a86e3e88111943e

---


# konto

> [!IMPORTANT] Den här variabeln har tagits bort. Använd [`s.sa()`](../functions/sa-method.md) funktionen om implementeringen kräver att du ändrar rapportsvitens mål.

I tidigare versioner av Adobe Analytics fastställde variabeln den rapportserie som du vill skicka data till `account` . Du måste ha ett rapportsprogram-ID för att kunna skicka data till Adobe Analytics.

* Om du använder Adobe Experience Platform Launch ligger rapportsviterna under [!UICONTROL Library Management] dragspelspanelen när du konfigurerar Adobe Analytics-tillägget.
* Om du använder funktionen för att `s_gi()` instansiera ett Analytics-spårningsobjekt finns rapportsvitens ID redan som ett obligatoriskt argument i funktionen.
