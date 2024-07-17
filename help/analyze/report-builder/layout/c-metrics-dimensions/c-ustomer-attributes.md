---
description: Kundattribut lagras i en ny typ av element som kallas VisAttr, som kan konfigureras som en dimension eller ett mått.
title: Kundattribut
feature: Report Builder
role: User, Admin
exl-id: b5855ce0-6d17-4690-a2c2-366b66ab8e83
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 11%

---

# Kundattribut

Kundattribut lagras i en ny typ av element som kallas VisAttr, som kan konfigureras som en dimension eller ett mått.

Mer detaljerad information om hur du överför kundattribut finns i [hjälpen för Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html).

* Om den är konfigurerad som ett mått visas VisAttr både som mått och&quot;dimension&quot;.

  ![Skärmbild som visar mått och dimensionskundattribut.](assets/ca_metrics.png) ![](assets/ca_dimension.png)

* Det har stöd för samma uppdelning som en eVar (allt kan delas upp efter vad som helst).
* VisAttr har stöd för alla eVar-mått.
* VisAttr som ett mätvärde stöder&quot;buffring&quot; (som Time Spent on Site: 0 to 30, 31 to 60, ...)
* VisAttr finns som segmenteringsdimension.
