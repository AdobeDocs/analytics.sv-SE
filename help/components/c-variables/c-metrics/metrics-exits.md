---
description: Antalet gånger ett givet värde hämtas som det sista värdet vid ett besök. Utträden kan bara göras en gång per besök.
title: Avslutar
topic: Metrics
uuid: cd5436ef-65d3-431b-a24f-aceff8542c50
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Avslutar

Antalet gånger ett givet värde hämtas som det sista värdet vid ett besök. Utträden kan bara göras en gång per besök.

Avsluta sidor har en besöksuppdelad omfattning, vilket innebär att de finns kvar i alla träffar för ett besök. Mer information finns i [Behållare](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-overview.html) för indelning och segmentering.

När utträde tillämpas på en dimension räknas utträden som det sista värdet av ett besök, vilket kan inträffa vid en träff under besöket. Om det inte finns något värde för den senaste träffen, kommer Exit att tilldelas det senaste värdet.

Om ett utträde inträffar utanför rapporteringsintervallet för ett besök inom rapporteringsintervallet, inkluderas det så länge det inte ligger längs en månadsgräns (inuti datauppsättningen).
