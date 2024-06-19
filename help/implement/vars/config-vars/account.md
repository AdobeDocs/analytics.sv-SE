---
title: konto
description: (Pensionerat) Fastställ rapportsviten dit data skickas.
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 0%

---

# konto

>[!IMPORTANT]
>
>Den här variabeln har tagits bort. Använd [`s.sa()`](../functions/sa-method.md) om implementeringen kräver att du ändrar rapportsvitens mål.

I tidigare versioner av Adobe Analytics `account` variabeln bestämmer vilken rapportserie du vill skicka data till. Du måste ange ett rapportsprogram-ID för att kunna skicka data till Adobe Analytics.

* Om du använder Web SDK finns rapportsviterna i de Adobe Analytics-tjänstinställningar i datastream som Web SDK skickar data till.
* Om du använder Adobe Analytics-tillägget finns rapportsviterna under [!UICONTROL Library Management] när du konfigurerar Adobe Analytics-tillägget.
* Om du använder [`s_gi()`](../functions/s-gi.md) för att instansiera ett Analytics-spårningsobjekt finns det redan ett eller flera ID:n för rapportsviten som ett obligatoriskt argument i funktionen.
