---
title: Vanliga frågor om klassificeringar
description: Frågor och svar om hur du använder klassificeringar.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---


# Vanliga frågor om klassificeringar

Frågor och svar om hur du använder klassificeringar.

## Hur klassificerar jag dimensionsobjektet &quot;0&quot;?

Klassificeringsfiler som överförts med antingen ett nyckelvärde eller ett klassificeringsvärde på noll (`0`) resulterar i ett fel. Den innehåller alla värden som bara innehåller nollor (`00`, `000`och så vidare). Det finns flera sätt att lösa det här problemet:

* **Implementera alternativa värden**: Det bästa och enklaste sättet att lösa problemet är att använda ett annat textvärde än `"0"` . Ändra till exempel implementeringen `s.campaign = "0";` till `s.campaign = "Zero";`.

* **Använd bearbetningsregler**: Du kan ändra dimensionsobjekt mellan datainsamling och deras lagring i en rapportserie. Skapa följande bearbetningsregel:

   *Om[dimensionen]är lika med`0`skriver du över[dimensionens]värde med anpassat värde`Zero`.*

* **Begär en VISTA-regel**: En konsult inom Engineering Services skapar en regel för er på serversidan till en extra kostnad. Kontakta er organisations Account Manager för att begära en VISTA-regel.

## Kan jag använda uppladdaren för att klassificera dimensionsobjekt som inte finns än?

Ja, *men då räknas varje dimensionsobjekt som ett fakturerbart serversamtal.*

* Dimensioner som redan finns medför inte någon extra kostnad.
* Om du använder funktionen för att skapa klassificeringsregler klassificeras inte objekt som inte finns och medför därför inte någon extra kostnad.
