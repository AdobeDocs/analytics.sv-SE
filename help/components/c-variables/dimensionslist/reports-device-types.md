---
description: Grupperar mobila enheter i mobiltelefoner, surfplattor, e-läsare, spelkonsoler, tv-apparater, digitalboxar, mediespelare och andra högnivåkategorier så att du kan se distributionen mellan olika typer av mobila enheter.
title: Enhetstyper
topic: Reports
uuid: e1224769-9a94-4cad-a1ed-e285d60d23f3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Enhetstyper

Grupperar mobila enheter i mobiltelefoner, surfplattor, e-läsare, spelkonsoler, tv-apparater, digitalboxar, mediespelare och andra högnivåkategorier så att du kan se distributionen mellan olika typer av mobila enheter.

Den här dimensionen är också användbar när du vill definiera segment för telefon- och surfplatteanvändare genom att segmentera där mobilenhetstypen är lika med&quot;enhetstyp&quot;.

**Dynamiska enhetsdata**

Den här dimensionen använder dynamiska enhetsdata som uppdateras kontinuerligt när nya enheter släpps och identifieras. En ny surfplatta som släpps under den aktuella månaden kanske inte identifieras eftersom den ännu inte finns i enhetsdatabasen. När enhetsdatabasen uppdateras med den nya enheten tillämpas eventuella ändringar som ett resultat av detta på alla framtida rapportdatum (inte på historiska data). Därför kan du se små variationer av den här rapporten för historiska datum över tiden. Den mest aktuella rapporten kommer som regel att ha de mest korrekta uppgifterna för varje rapporteringsperiod.

Data för den här rapporten fylls i med besökarens användaragentsträng.

>[!Note]
>Endast ändringar som görs i ett befintligt mobilt ID är retroaktiva. Om enheten är ny och inte har något mobil-ID än, startar den enda information som kommer att kopplas till den här enheten det datum då ett ID läggs till i enhetsdatabasen.
