---
description: Lär dig hur du kopierar referensbegäranden.
title: Så här kopierar du referensförfrågningar
uuid: b6f64630-868f-455b-8682-471ff9fc596e
feature: Report Builder
role: User, Admin
exl-id: 3cd77325-7461-4345-a672-64c03ea1ae5b
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# Kopiera referensförfrågningar

I en referensbegäran används värden från celler som indata för parametrar, till exempel ett datafilter eller relationsfilter.

Så här sprider eller kopierar och klistrar du in referensförfrågningar i kalkylbladet:
* Du måste skapa minst en giltig begäran i kalkylbladet.
* De data som tas fram av begäran måste innehålla en cell vars värde är beroende av antingen en begäran i en annan cell (med ett nedbrytnings- eller matchningsfilter) eller beroende av ett filter som hämtar indata från data som anges i en cell.

Du kan också skapa begäranden som refererar till indatafilter från begäranden i olika kalkylblad, men inte i olika arbetsböcker. En begäran i Sheet 2 kan t.ex. använda en rapportsvit från en viss cell i Sheet 1 och ett datumintervall från en cell i en begäran i Sheet 2. De nya utdata kan placeras antingen i ett blad eller i ett nytt blad i samma arbetsbok. När du klistrar in en relativ begäran, och ett indatafilter finns på ett kalkylblad som inte är det kalkylblad där den kopierade begäran finns, klistras filtret in som ett absolut filter.

>[!NOTE]
>
>Du kan inte skriva ut en enstaka begäran i flera kalkylblad. Dessutom kan systemet inte klistra in vissa av de kopierade begäranden i nya arbetsböcker eftersom förfrågningarna innehåller indatafilter från andra kalkylblad. Indatafiltren innehåller rapportsviter från celler, datumintervall från celler, filter från celler och andra relaterade parametrar.

**Så här kopierar du referensbegäranden**

1. Markera cellerna som innehåller förfrågningar som du vill kopiera, inklusive indatacellen eller refererad till cellen.
1. Högerklicka i de markerade cellerna och markera **[!UICONTROL Copy Requests]** på kortkommandomenyn.

   När du har markerat området där förfrågningar och indataceller finns markeras cellerna med dessa element.
1. Markera antingen en cell eller ett intervall med sammanhängande celler som ska fyllas med de inklistrade förfrågningarna.

   Kontrollera att cellen eller cellområdet som du markerar inte innehåller några andra data eller förfrågningar.
1. Högerklicka på den enskilda cellen eller den översta cellen längst till vänster i cellintervallet och välj **[!UICONTROL Paste Requests]**.

   När du klistrar in en begäran som innehåller en indatacell visas alternativen under [!UICONTROL Paste Requests] inkludera:

   **Använd absolut indatacell:** Klistrar in en kopia av den eller de förfrågningar och formateringar som är kopplade till de markerade cellerna i det inklistringsområde som du markerar. Indatacellen (cellen som refereras i en av de ursprungliga förfrågningarna) klistras inte in. I stället behåller indatacellen samma position som tidigare.

   **Använd relativ indatacell:** Klistrar in en kopia av förfrågningar och formatering som är kopplade till de markerade cellerna i det inklistringsområde som du markerade, inklusive en kopia av indatacellen. Det rumsliga förhållandet mellan begäran(en) och indatacellen är detsamma som i den/de ursprungliga begäran(en). Men även om de nyligen inklistrade cellerna nu har en kopia av förfrågningarna har de inget innehåll från början. Detta beror på att när indatacellen återskapas i inklistringsåtgärden associeras inga data med indatacellen. Om du vill visa data för den eller de nyligen inklistrade förfrågningarna måste du ange ett värde i indatacellen och sedan uppdatera förfrågningarna.
