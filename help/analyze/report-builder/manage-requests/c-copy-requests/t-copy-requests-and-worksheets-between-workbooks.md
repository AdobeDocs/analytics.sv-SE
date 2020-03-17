---
description: Kopiera ett helt kalkylblad i en källarbetsbok till ett kalkylblad i en eller flera målarbetsböcker.
title: Kopiera begäranden och kalkylblad mellan arbetsböcker
topic: Report builder
uuid: 6b2c4259-d8cb-430e-819f-38e213dd2661
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Kopiera begäranden och kalkylblad mellan arbetsböcker

Kopiera ett helt kalkylblad i en källarbetsbok till ett kalkylblad i en eller flera målarbetsböcker.

För att kunna göra detta måste du ha minst två arbetsböcker öppna i samma instans av Excel: den första källarbetsboken innehåller ett kalkylblad (kalkylblad) med begäranden som mappas till celler, medan målarbetsböckerna är mål. För varje ny målarbetsbok bör du logga in på samma rapportprogramsvit som källarbetsboken innan du kan klistra in kalkylblad som innehåller begäranden.
1. Högerklicka på kalkylbladet i källarbetsboken och välj **[!UICONTROL Copy Worksheet w/Requests]**.
1. Högerklicka på kalkylbladet i målarbetsboken och välj **[!UICONTROL Paste Worksheet w/Requests]**.

   Samma instans av Excel innebär att det bara körs en Excel-process ( [!DNL excel.exe]) i taget på datorn. Om du startar två instanser av Excel och försöker kopiera ett kalkylblad från en arbetsbok i den första instansen av Excel till en arbetsbok i den andra instansen av Excel, kan du inte använda rapportverktyget för att klistra in ett kalkylblad på snabbmenyn i den andra instansen av Excel.

   Om du loggar in på käll- och målarbetsböckerna med olika rapportsviter är det enda resultat som du ser av inklistringsåtgärden de som påverkar formateringen i målarbetsboken. I Report Builder visas ett meddelande om att informationen för begäranden som härleds från en angiven rapportsserie (i källarbetsboken) inte är tillgänglig i målarbetsboken. Om du vill visa de begäranden som klistras in i målarbetsboken måste du logga in i målarbetsboken med samma rapportserie som källarbetsboken.

   Du kan kopiera och klistra in en eller flera begäranden från ett kalkylblad i en arbetsbok till ett kalkylblad i en annan arbetsbok, så länge som den andra arbetsboken är öppen som ett annat dokument i samma instans av Excel. Förfrågningarna i båda arbetsböckerna måste skapas med samma rapportsvitsinloggning.
