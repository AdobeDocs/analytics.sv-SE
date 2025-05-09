---
description: Lär dig hur du kopierar, klistrar in och flyttar begäranden till en annan del av kalkylbladet.
title: Så här kopierar du närliggande begäranden
uuid: c8abec0d-6fbd-4a98-8672-ede81317487b
feature: Report Builder
role: User, Admin
exl-id: 99476ec5-f1f0-49f5-a2d8-354cec63c6b1
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---

# Kopiera intilliggande begäranden

{{legacy-arb}}

På samma sätt som du kopierar och klistrar in begäranden kan du även flytta begäranden till en annan del av kalkylbladet genom att välja [!UICONTROL Cut Request] på snabbmenyn.

Om du klipper ut en begäran tas den bort från sin ursprungliga plats och placeras på den nya platsen när du har valt [!UICONTROL Paste Request]. Om du ångrar dig efter att ha klippt en viss begäran och beslutar dig för att kopiera eller klippa ut en annan begäran från en annan cell, lämnar Report Builder den första begäran i sin ursprungliga cell och agerar (antingen kopior eller klipp ut) den andra.

>[!NOTE]
>
>Report Builder stöder inte Excel-kommandot Ångra för att klippa ut eller klistra in begäranden.

Du är inte begränsad till att kopiera och klistra in i samma blad i arbetsboken. Du kan kopiera en begäran i ett blad och klistra in den på en plats i ett annat blad i samma arbetsbok.

Du är inte begränsad till att kopiera och klistra in en begäran i taget. Du kan markera flera begäranden i kalkylbladet och klistra in dem i ett tomt område i kalkylbladet. Precis som när du kopierar och klistrar in en begäran, måste du se till att det inte finns några celler i det område som klistras in som ska ersättas av inklistringsåtgärden. Om systemet hittar att målområdet för klistra in redan innehåller en eller flera begäranden, visar inte Report Builder [!UICONTROL Paste Requests]-menyn för kopierade eller urklippta begäranden. Du måste markera en annan cell som mål för inklistringsåtgärden så att förfrågningar inte överlappar varandra.
