---
description: Lär dig hur du kopierar en enkel begäran.
title: Så här kopierar du enkla begäranden
uuid: ff20560a-01ee-47e7-8bd1-b73edb010456
feature: Report Builder
role: User, Admin
exl-id: ceed28d5-cb7f-4343-96fd-2ce09f5a3515
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 0%

---

# Kopiera enkla förfrågningar

Kopiera en enkel begäran i stället för en referensbegäran. En enkel begäran är en begäran som inte innehåller några referenser till en annan begäran eller innehållet i en cell.

A [hänvisningsbegäran](/help/analyze/report-builder/manage-requests/c-copy-requests/t-copy-referential-requests.md) I används värden från celler som indata för parametrar, t.ex. ett datafilter eller relationsfilter. Dessa filter använder antingen matchning eller trendning och baseras på resultatet av en tidigare begäran eller på det innehåll som användaren har angett i en cell, som kallas indatacell.

Så här kopierar du en enkel begäran

1. Skapa en giltig begäran.
1. Högerklicka på en av cellerna där förfrågan har mappats, eller markera ett område med celler som innehåller förfrågningar.

   Var konsekvent när du väljer en cell att kopiera från i gruppen med celler som omfattas av begäran. Det bästa alternativet är den översta och vänstra cellen i den uppsättning celler som omfattas av begäran och fungerar från vänster till höger. Det beror på att Excel-kalkylbladet har hundratals kolumner och tusentals rader tillgängliga för utökning åt åt höger och nedåt. Om du bestämmer dig för att starta en begärandekopia från cellen längst till höger eller längst ned i en uppsättning celler som är kopplade till en begäran, kan du inte klistra in begäran om cellerna som ska klistras in sträcker sig utanför den vänstra eller övre kanten av kalkylbladet.
1. Välj **[!UICONTROL Copy Request]**.
1. I en annan del av kalkylbladet högerklickar du på en tom cell (en cell som inte innehåller någon begäran).

   Du kan inte klistra in celler som innehåller förfrågningar i celler som är mappade med förfrågningar för att förhindra att förfrågningar som du redan har skapat går förlorade eller skadas. Om du kopierar eller klipper ut celler som innehåller förfrågningar skapas inte genvägsmenyn [!UICONTROL Paste Requests] som är tillgängligt när du högerklickar på celler (eller celluppsättningen) som innehåller begäranden. Du måste markera en annan cell som mål för inklistringsåtgärden så att förfrågningar inte överlappar varandra. Detta gäller oavsett om du markerar en enskild cell med en begäran om att klistra in eller ett område med celler som innehåller begäranden.
1. Klicka på **[!UICONTROL Paste Request]**.

   En kopia av den ursprungliga begäran placeras i cellen/cellerna på en eller flera platser i förhållande till den ursprungliga begäran.

   >[!NOTE]
   >
   >Endast begäranden kopieras, inte innehållet i cellerna. Om du har annan information som inte baseras på begäranden, men som är relevant för att förstå data som visas i cellerna (t.ex. kolumnrubriker i tabeller eller radidentifierare), använder du Excel-standardkommandona Kopiera och Klistra in.

   Eftersom Excel använder olika urklipp för kopiering av cellinnehåll och kopieringsbegäranden, kan du kopiera både cellinnehåll som inte efterfrågas och sedan förfrågningar genom att utföra en begäran om kopiera/klistra in och kopiera begäranden/klistra in i serie. Om du formaterar begäranden i kalkylbladet och sedan kopierar och klistrar in, återger Report Builder den ursprungliga formateringen (till exempel kantlinjer, teckensnitt) i inklistringsområdet.

   Om du ändrar en begäran som du har kopierat eller klippt ut till Urklipp innan du klistrar in begäran tas begäran bort från Urklipp. Därför bör du inte ändra en begäran mellan den tidpunkt då du kopierar den och den tidpunkt då du klistrar in den, om du vill behålla den i ursprungligt skick.
