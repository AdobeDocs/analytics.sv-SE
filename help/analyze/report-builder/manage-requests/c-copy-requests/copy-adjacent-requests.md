---
description: På samma sätt som du kopierar och klistrar in begäranden kan du även flytta begäranden till en annan del av kalkylbladet genom att välja Klippbegäran på snabbmenyn.
title: Kopiera intilliggande begäranden
topic: Report builder
uuid: c8abec0d-6fbd-4a98-8672-ede81317487b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Kopiera intilliggande begäranden

På samma sätt som du kopierar och klistrar in begäranden kan du även flytta begäranden till en annan del av kalkylbladet genom att välja Klippbegäran på snabbmenyn.

När du klipper ut en begäran tas den bort från sin ursprungliga plats och placeras på den nya platsen när du har valt [!UICONTROL Paste Request]. Om du ångrar dig efter att ha klippt en viss begäran och beslutar dig för att kopiera eller klippa ut en annan begäran från en annan cell, lämnar Report Builder den första begäran i sin ursprungliga cell och agerar (antingen kopior eller klipp ut) den andra.

> [!NOTE] Report Builder stöder inte Excel-kommandot Ångra för att klippa ut eller klistra in begäranden. Var därför försiktig när du skär ned begäranden.

Du är inte begränsad till att kopiera och klistra in i samma blad i arbetsboken. Du kan kopiera en begäran i ett blad och klistra in den på en plats i ett annat blad i samma arbetsbok.

Du är inte begränsad till att kopiera och klistra in en begäran i taget. Du kan markera mer än en begäran i kalkylbladet och klistra in den i ett tomt område i kalkylbladet. Precis som när du kopierar och klistrar in en begäran, måste du se till att det inte finns några celler i det område som klistras in som ska ersättas av inklistringsåtgärden. Om systemet hittar att målområdet för klistra in redan innehåller en eller flera begäranden, visar Report Builder inte [!UICONTROL Paste Requests] menyn för kopierade eller urklippta begäranden. Du måste markera en annan cell som mål för inklistringsåtgärden så att förfrågningar inte överlappar varandra.
