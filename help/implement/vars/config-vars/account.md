---
title: konto
description: Använd kontovariabeln för att bestämma till vilken rapportsserie data ska skickas.
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '133'
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
