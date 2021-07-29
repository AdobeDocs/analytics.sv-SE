---
title: maxDelay
description: Fastställ den maximala tid som AppMeasurement väntar på ett svar från DFA innan en bildbegäran skickas.
exl-id: 154f7e34-39e7-4390-ae36-d4fbc998787f
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---

# maxDelay

Variabeln `s.maxDelay` används i DFA-datakopplingen för att bestämma timeoutperioden när DFA-värden kontaktas. Om Adobe inte får något svar från DFA:s servrar inom den angivna perioden som anges i den här variabeln, bryts anslutningen och data bearbetas normalt. Inkludera den här variabeln i implementeringen om du är intresserad av DFA:s svarstid på varje sida. Adobe rekommenderar att du experimenterar med det här värdet för att fastställa den optimala tidsgränsen.

Den här variabeln används bara i implementeringar med DFA-datakopplingen. Även med implementeringar med DFA är variabeln valfri.

## Maximal fördröjning med taggar i Adobe Experience Platform

Det finns inget dedikerat fält i användargränssnittet för datainsamling som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.maxDelay i AppMeasurement och anpassad kodredigerare

Variabeln `s.maxDelay` är ett heltal som representerar antalet millisekunder AppMeasurement väntar på ett svar från DFA. Om AppMeasurement inte får något svar från DFA i tid skickas en bildbegäran till Adobe utan DFA-data.

```js
s.maxDelay = 750;
```

## Egenskaper

* Om du ökar väntetiden samlas fler DFA-data in, men det ökar också risken för att Analytics-träffdata går förlorade. Förlorade träffdata i Analytics inträffar när användaren navigerar bort från sidan under `s.maxDelay`-perioden.
* Genom att minska väntetiden minskar risken för att förlora träffdata i Analytics, men det kan minska mängden DFA-data som skickas med träffdata.
* DFA-integreringsdata går förlorade när `s.maxDelay`-perioden inte räcker till för att DFA-värden ska kunna svara.

>[!NOTE]
>
>Adobe har inte kontroll över DFA:s svarstid. Om du får konsekventa problem även efter att ha ökat den maximala fördröjningsperioden till en rimlig tidsperiod, kontaktar du din organisations DFA-kontoadministratör.
