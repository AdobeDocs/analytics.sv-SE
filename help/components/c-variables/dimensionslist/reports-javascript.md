---
description: Visar mått baserat på om enheten har JavaScript aktiverat, inaktiverat eller om den räknas som "oidentifierad".
title: Stöd för JavaScript
topic: Reports
uuid: 7b95001a-cd35-478a-8b24-54d30666110d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Stöd för JavaScript

Visar mått baserat på om enheten har JavaScript aktiverat, inaktiverat eller om den räknas som &quot;oidentifierad&quot;.

> [!NOTE] I början av november 2016 planerar vi att ta bort begränsningarna där JavaScript alltid finns med som *`disabled / unidentified`* för mobila enheter.

JavaScript-rapporten motsvarar kolumnen javascript i raw-data.

javascript är ett besöksnivåfält, så det behåller värdet från första träffen i besöket. Kolumnen javascript baseras på det första värdet som finns i kolumnen j_jscript (som en visit_reference kommer endast att finnas kvar vid besökets första referent).

j_jscript fylls i från parametern j från Adobe Analytics-bildbegäran.

Här är ett exempel:

| Träff | j_jscript | javascript |
|---|---|---|
| 1 |  | 0 |
| 2 | 1.6 | 0 |
| 3 | 1.6 | 0 |

Därför spelar det ingen roll om du hade en javascript-version angiven någon gång under besöket. Den kommer alltid att visas som inte Javascript eftersom den första träffen inte innehöll något värde för j_jscript.
