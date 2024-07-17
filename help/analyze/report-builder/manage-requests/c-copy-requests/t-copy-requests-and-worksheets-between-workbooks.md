---
description: Lär dig hur du kopierar ett kalkylblad från en källarbetsbok till en eller flera målarbetsböcker.
title: Så här kopierar du begäranden och kalkylblad mellan arbetsböcker
uuid: 6b2c4259-d8cb-430e-819f-38e213dd2661
feature: Report Builder
role: User, Admin
exl-id: 1a2363da-603e-4d1d-aefa-14ce71554247
source-git-commit: d218d07ec16e981d7e148092b91fbbd5711e840f
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 0%

---

# Kopiera begäranden och kalkylblad mellan arbetsböcker

Kopiera ett helt kalkylblad i en källarbetsbok till ett kalkylblad i en eller flera målarbetsböcker. För att kunna göra detta måste du ha minst två arbetsböcker öppna i samma instans av Excel:
* Den första källarbetsboken innehåller ett kalkylblad (kalkylblad) med begäranden som mappas till celler.
* De ytterligare målarbetsböckerna är målen. För varje ny målarbetsbok bör du logga in på samma rapportprogramsvit som källarbetsboken innan du kan klistra in kalkylblad som innehåller begäranden.

>[!NOTE]
>
>Du måste logga in på målarbetsboken med samma rapportsserie som källarbetsboken. Förfrågningarna i båda arbetsböckerna måste skapas med samma rapportsvitsinloggning.

1. Högerklicka på kalkylbladet i källarbetsboken och välj **[!UICONTROL Copy Worksheet w/Requests]**.
1. Högerklicka på kalkylbladet i målarbetsboken och välj **[!UICONTROL Paste Worksheet w/Requests]**.

   Samma instans av Excel innebär att det bara körs en Excel-process ( [!DNL excel.exe]) åt gången på datorn. Om du startar två instanser av Excel och försöker kopiera ett kalkylblad från en arbetsbok i den första instansen av Excel till en arbetsbok i den andra instansen av Excel, har Report Builder inte möjlighet att klistra in ett kalkylblad på snabbmenyn i den andra instansen av Excel.

   Om du loggar in på käll- och målarbetsböckerna med olika rapportsviter är det enda resultat som du ser av inklistringsåtgärden de som påverkar formateringen i målarbetsboken. Report Builder visar ett meddelande om att informationen för begäranden som härleds från en angiven rapportsvit (i källarbetsboken) inte är tillgänglig i målarbetsboken. Om du vill visa de begäranden som klistras in i målarbetsboken måste du logga in i målarbetsboken med samma rapportserie som källarbetsboken.

   Du kan kopiera och klistra in en eller flera begäranden från ett kalkylblad i en arbetsbok till ett kalkylblad i en annan arbetsbok, så länge som den andra arbetsboken är öppen som ett annat dokument i samma instans av Excel. Förfrågningarna i båda arbetsböckerna måste skapas med samma rapportsvitsinloggning.
