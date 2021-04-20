---
description: Kopiera en enkel begäran i stället för en referensbegäran. En enkel begäran är en begäran som inte innehåller några referenser till en annan begäran eller innehållet i en cell.
title: Kopiera enkla förfrågningar
uuid: ff20560a-01ee-47e7-8bd1-b73edb010456
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 1%

---


# Kopiera enkla förfrågningar

Kopiera en enkel begäran i stället för en referensbegäran. En enkel begäran är en begäran som inte innehåller några referenser till en annan begäran eller innehållet i en cell.

En [referensbegäran](/help/analyze/report-builder/manage-requests/c-copy-requests/t-copy-referential-requests.md) använder värden från celler som indata för parametrar, till exempel ett datafilter eller relationsfilter. Dessa filter använder antingen matchning eller trending och baseras på resultatet från en tidigare begäran eller på det innehåll som användaren anger i en cell, som kallas indatacell.
1. Skapa en giltig begäran.
1. Högerklicka på en av cellerna där förfrågan har mappats, eller markera ett område med celler som innehåller förfrågningar.

   Var konsekvent när du väljer en cell att kopiera från i gruppen med celler som omfattas av begäran. Det bästa alternativet är den översta och vänstra cellen i den uppsättning celler som omfattas av begäran och fungerar från vänster till höger. Det beror på att Excel-kalkylbladet har hundratals kolumner och tusentals rader tillgängliga för utökning åt åt höger och nedåt. Om du bestämmer dig för att starta en begärandekopia från cellen längst till höger eller längst ned i en uppsättning celler som är kopplade till en begäran, kan du inte klistra in begäran om cellerna som ska klistras in sträcker sig utanför den vänstra eller övre kanten av kalkylbladet.
1. Välj **[!UICONTROL Copy Request]**.
1. I en annan del av kalkylbladet högerklickar du på en tom cell (en cell som inte innehåller någon begäran).

   Du kan inte klistra in celler som innehåller förfrågningar i celler som är mappade med förfrågningar för att förhindra att förfrågningar som du redan har skapat går förlorade eller skadas. Om du kopierar eller klipper ut celler som innehåller förfrågningar blir alternativet [!UICONTROL Paste Requests] inte tillgängligt på snabbmenyn när du högerklickar på celler (eller celluppsättningen) som innehåller förfrågningar. Du måste markera en annan cell som mål för inklistringsåtgärden så att förfrågningar inte överlappar varandra. Detta gäller oavsett om du markerar en enskild cell med en begäran om att klistra in eller ett område med celler som innehåller begäranden.
1. Klicka på **[!UICONTROL Paste Request]**.

   En kopia av den ursprungliga begäran placeras i cellen/cellerna på en eller flera platser i förhållande till den ursprungliga begäran.

   >[!NOTE]
   >
   >Endast begäranden kopieras, inte innehållet i cellerna. Om du har annan information som inte baseras på begäranden, men som är relevant för att förstå data som visas i cellerna (t.ex. kolumnrubriker i tabeller eller radidentifierare), använder du Excel-standardkommandona Kopiera och Klistra in.

   Eftersom Excel använder olika urklipp för kopiering av cellinnehåll och kopieringsbegäranden, kan du kopiera både cellinnehåll som inte efterfrågas och sedan förfrågningar genom att utföra en begäran om kopiera/klistra in och kopiera begäranden/klistra in i serie. Om du formaterar begäranden i kalkylbladet och sedan kopierar och klistrar in, återger Report builder den ursprungliga formateringen (till exempel kantlinjer, teckensnitt) i inklistringsområdet.

   Om du ändrar en begäran som du har kopierat eller klippt ut till Urklipp innan du klistrar in begäran tas begäran bort från Urklipp. Därför bör du inte ändra en begäran mellan den tidpunkt då du kopierar den och den tidpunkt då du klistrar in den, om du vill behålla den i ursprungligt skick.
