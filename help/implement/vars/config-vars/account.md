---
title: konto
description: (Pensionerat) Fastställ rapportsviten dit data skickas.
feature: Appmeasurement Implementation
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 0%

---

# konto

>[!IMPORTANT]
>
>Den här variabeln har tagits bort. Använd funktionen [`s.sa()`](../functions/sa-method.md) om implementeringen kräver att du ändrar rapportsvitens mål.

I tidigare versioner av Adobe Analytics fastställde variabeln `account` vilken rapportserie du vill skicka data till. Du måste ange ett rapportsprogram-ID för att kunna skicka data till Adobe Analytics.

* Om du använder Web SDK finns rapportsviterna i de Adobe Analytics-tjänstinställningar i det dataflöde som Web SDK skickar data till.
* Om du använder Adobe Analytics-tillägget finns rapportsviterna under dragspelsfliken [!UICONTROL Library Management] när du konfigurerar Adobe Analytics-tillägget.
* Om du använder funktionen [`s_gi()`](../functions/s-gi.md) för att instansiera ett Analytics-spårningsobjekt finns rapportsvitens ID:n redan som ett obligatoriskt argument i funktionen.
