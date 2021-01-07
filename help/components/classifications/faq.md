---
title: Vanliga frågor om klassificeringar
description: Frågor och svar om hur du använder klassificeringar.
translation-type: tm+mt
source-git-commit: a63b8ae3948ffd9a37058696aa1b1d4c923709ba
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---


# Vanliga frågor om klassificeringar

Frågor och svar om hur du använder klassificeringar.

## Hur klassificerar jag dimensionsobjektet &quot;0&quot;?

Klassificeringsfiler som överförts med antingen ett nyckelvärde eller ett klassificeringsvärde på noll (`0`) resulterar i ett fel. Den innehåller alla värden som bara innehåller nollor (`00`, `000` och så vidare). Det finns flera sätt att lösa det här problemet:

* **Implementera alternativa värden**: Att använda ett annat textvärde än  `"0"` är det bästa och enklaste sättet att lösa det här problemet. Ändra till exempel `s.campaign = "0";` i implementeringen till `s.campaign = "Zero";`.

* **Använd bearbetningsregler**: Du kan ändra dimensionsobjekt mellan datainsamling och deras lagring i en rapportserie. Skapa följande bearbetningsregel:

   *Om  [] dimensionerna är lika  `0`skriver du över  [] dimensionens värde med det anpassade värdet  `Zero`.*

* **Begär en VISTA-regel**: En konsult inom Engineering Services skapar en regel för er på serversidan till en extra kostnad. Kontakta er organisations Account Manager för att begära en VISTA-regel.

## Kan jag använda klassificeringsimporteraren för att klassificera dimensionsobjekt som inte finns än?

Ja, *Om du gör det räknas varje dimensionsobjekt som ett fakturerbart serversamtal.*

* Dimensioner som redan finns medför inte någon extra kostnad.
* Om du använder funktionen för att skapa klassificeringsregler klassificeras inte objekt som inte finns och medför därför inte någon extra kostnad.

## Hur klassificerar jag värden som innehåller specialtecken?

Att använda specialtecken som kommatecken eller dubbla citattecken i rapporter rekommenderas vanligtvis inte. I vissa fall är det dock nödvändigt att använda dem. Om dina rapportvärden innehåller tecken som du väljer att klassificera gör du så här:

1. Logga in på Adobe Analytics och navigera sedan till **[!UICONTROL Admin]** > **[!UICONTROL Classification importer]**.
2. Klicka på fliken **[!UICONTROL Browser export]**.
3. Konfigurera exportinställningar och kontrollera att offertutdata INTE är markerat.
4. Klicka på **[!UICONTROL Export File]** och öppna den hämtade filen i en kalkylbladsredigerare.
5. På rad 1 söker du efter cell C1 som innehåller värdet `v:2.0`. Ändra värdet till `v:2.1` och använd de önskade klassificeringarna i arbetsboken.
6. Överför filen på samma sätt som andra klassificeringar.

## Vad är Numeric 2-klassificeringar?

Numeriska 2-klassificeringar gör att du kan klassificera dimensionsobjekt som tidsbaserade värden. De togs bort från Adobe Analytics användargränssnitt i juli 2019.
