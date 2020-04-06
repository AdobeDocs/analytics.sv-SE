---
description: Posterna anger hur många gånger ett givet värde hämtas som det första värdet vid ett besök. Tävlingsbidragen får endast förekomma en gång per besök. Men det är inte nödvändigtvis den första träffen om variabeln inte är definierad.
title: Poster
topic: Metrics
uuid: c4608b66-b70c-4e98-b7c6-9be5fbe4ec9c
translation-type: tm+mt
source-git-commit: e6aaf2754c6a5c33fbe3e093b4d7ca5a375c41e7

---


# Poster

&quot;Tävlingsbidrag&quot; representerar det antal gånger ett givet värde hämtas som det första värdet vid ett besök. Tävlingsbidragen får endast förekomma en gång per besök. Men det är inte nödvändigtvis den första träffen om variabeln inte är definierad.

I Analysis Workspace, från mars 2020, har vi ändrat hur värdet &quot;Ingen&quot; interagerar med poster/utträden.  Eftersom du nu kan aktivera och inaktivera &quot;Inga&quot; på arbetsytan för analyser, använder vi &quot;Inget&quot; efter att du skrivit in eller avslutat, medan (för vars) det tidigare användes.  Anta till exempel att den första träffen av ett besök inte har något värde för, till exempel eVar21, men att den andra träffen gör det. I Rapporter och analyser visas det som&quot;Ospecificerad&quot; för posten, men i Analysis Workspace visas det som värdet för den andra träffen.

Anmälningssidorna har en besöksuppdelad omfattning, vilket innebär att de finns kvar i alla träffar för ett besök. Mer information finns i [Behållare](https://marketing.adobe.com/resources/help/en_US/sc/user/c_Breakdown_and_segmentation_containers.html) för indelning och segmentering.
