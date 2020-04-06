---
title: konto
description: Använd kontovariabeln för att bestämma till vilken rapportsserie data ska skickas.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# konto

>[!IMPORTANT] Den här variabeln har tagits bort. Använd [`s.sa()`](../functions/sa-method.md) funktionen om implementeringen kräver att du ändrar rapportsvitens mål.

I tidigare versioner av Adobe Analytics fastställde variabeln den rapportserie som du vill skicka data till `account` . Du måste ha ett rapportsprogram-ID för att kunna skicka data till Adobe Analytics.

* Om du använder Adobe Experience Platform Launch ligger rapportsviterna under [!UICONTROL Library Management] dragspelspanelen när du konfigurerar Adobe Analytics-tillägget.
* Om du använder funktionen för att [`s_gi()`](../functions/s-gi.md) instansiera ett Analytics-spårningsobjekt finns rapportsvitens ID redan som ett obligatoriskt argument i funktionen.
