---
title: maxDelay
description: Fastställ den maximala tid som AppMeasurement väntar på ett svar från DFA innan en bildbegäran skickas.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# maxDelay

Variabeln `s.maxDelay` används i DFA-datakopplingen för att bestämma timeoutperioden när DFA-värden kontaktas. Om Adobe inte får något svar från DFA:s servrar inom den angivna perioden som anges i den här variabeln, bryts anslutningen och data bearbetas normalt. Inkludera den här variabeln i implementeringen om du är intresserad av DFA:s svarstid på varje sida. Adobe rekommenderar att du experimenterar med det här värdet för att fastställa den optimala tidsgränsen.

Den här variabeln används bara i implementeringar med DFA-datakopplingen. Även med implementeringar med DFA är variabeln valfri.

## Maximal fördröjning i Adobe Experience Platform Launch

Det finns inget dedikerat fält i Launch som kan använda den här variabeln. Använd den anpassade kodredigeraren efter AppMeasurement-syntax.

## s.maxDelay in AppMeasurement and Launch custom code editor

Variabeln är ett heltal som representerar antalet millisekunder som AppMeasurement väntar på ett svar från DFA. `s.maxDelay` Om AppMeasurement inte får något svar från DFA i tid skickas en bildbegäran till Adobe utan DFA-data.

```js
s.maxDelay = 750;
```

## Egenskaper

* Om du ökar väntetiden samlas fler DFA-data in, men det ökar också risken för att Analytics-träffdata går förlorade. Förlorade träffdata i Analytics inträffar när användaren navigerar bort från sidan under `s.maxDelay` perioden.
* Genom att minska väntetiden minskar risken för att förlora träffdata i Analytics, men det kan minska mängden DFA-data som skickas med träffdata.
* DFA-integreringsdata går förlorade när perioden inte räcker till för att DFA-värden ska kunna svara. `s.maxDelay`

> [!NOTE] Adobe har ingen kontroll över DFA:s svarstid. Om du får konsekventa problem även efter att ha ökat den maximala fördröjningsperioden till en rimlig tidsperiod, kontaktar du din organisations DFA-kontoadministratör.
