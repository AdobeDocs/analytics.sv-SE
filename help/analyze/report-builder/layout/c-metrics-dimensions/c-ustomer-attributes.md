---
description: Kundattribut lagras i en ny typ av element som kallas VisAttr, som kan konfigureras som en dimension eller ett mått.
title: Kundattribut
feature: Report Builder
role: User, Admin
exl-id: b5855ce0-6d17-4690-a2c2-366b66ab8e83
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 15%

---

# Kundattribut

Kundattribut lagras i en ny typ av element som kallas VisAttr, som kan konfigureras som en dimension eller ett mått.

Mer detaljerad information om hur du överför kundattribut finns i [hjälpen för Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html).

* Om den är konfigurerad som ett mått visas VisAttr både som&quot;dimension&quot; och som mått.

   ![](assets/ca_metrics.png) ![](assets/ca_dimension.png)

* Den stöder samma uppdelning som en eVar (allt kan delas upp efter vad som helst).
* VisAttr stöder alla eVar.
* VisAttr som ett mätresultat har stöd för &quot;bucketization&quot; (som Time Spent on Site: 0 till 30, 31 till 60, ...)
* VisAttr finns som segmenteringsdimension.
