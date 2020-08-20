---
description: Klassificeringar används för att kategorisera värden i grupper och rapportera på gruppnivå. Du kan t.ex. klassificera alla betalsökningskampanjer i en kategori som popmusiktermer och rapportera hur framgångsrik den kategorin är i förhållande till mått som instanser (klickningar) och konvertering till lyckade händelser.
title: Konverteringsklassificeringar
translation-type: tm+mt
source-git-commit: de7dd41bba6907d6af7a59dc385ca6a185d503ae
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 4%

---


# Konverteringsklassificeringar

Klassificeringar används för att kategorisera värden i grupper och rapportera på gruppnivå. Du kan t.ex. klassificera alla betalsökningskampanjer i en kategori som *popmusiktermer* och rapportera om framgången i den kategorin i förhållande till mätvärden som instanser (klickningar) och konvertering till framgångshändelser.

Med konverteringsklassificeringar kan du klassificera konverteringsvariabler. När de har klassificerats kan alla rapporter som du kan generera med nyckeldata också genereras med hjälp av de associerade dataegenskaperna.

När du har aktiverat klassificeringar använder du [Klassificeringsimporteraren](/help/components/classifications/importer/c-working-with-saint.md) för att tilldela specifika värden till lämplig klassificering.

## Beskrivningar av konverteringsklassificeringar

| Element | Beskrivning |
| --- | --- |
| Namn | Klassificeringsnamnet |
| Aktiverat den (endast text) | Anger om textklassificeringen är ett datumintervall för kampanjvariabler. |
| Alternativ (endast text) | Skapar en lista över klassificeringsvärden som är tillgängliga för den här klassificeringen. Använd Alternativ med kampanjvariabler för att ge användarna en lista över värden som stöds för klassificeringen i Campaign Manager. |
| Nummertyp (endast numeriskt) | Anger siffertypen i den numeriska klassificeringen. Alternativen är Numeric, Percent och Currency. |

## Lägg till konverteringsklassificeringar

Steg som beskriver hur du lägger till konverteringsklassificeringar i Admin.

1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Välja en rapportsvit.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**.
1. I den **[!UICONTROL Select Classification Type]** nedrullningsbara listan väljer du variabeln där du vill lägga till en klassificering.

   ![Steginformation](../assets/sub_class_create.png)

1. För musen över **[!UICONTROL Edit Classification]** ikonen och markera sedan **[!UICONTROL Add Classification]**.
1. I **[!UICONTROL Select Type]** fältet väljer du vilken typ av klassificering du vill lägga till i variabeln.

   Alternativen är **[!UICONTROL Text]** och **[!UICONTROL Numeric]**. Mer information om klassificeringstyper finns i [Om klassificeringar](/help/components/classifications/c-classifications.md).
1. Konfigurera klassificeringen i **[!UICONTROL Text Classifications]** dialogrutan efter behov.

1. Lägg till eller ta bort alternativ i **[!UICONTROL Dropdown List]** dialogrutan.

   Med Alternativ för att lägga till skapas en lista med klassificeringsvärden som är tillgängliga för den här klassificeringen. Du kan använda det här alternativet med Campaign-variabler för att ge användarna en lista över värden som stöds för klassificeringen i Campaign Manager. Använd detta för klassificeringsdimensioner där du har ett litet antal tillåtna värden som sällan eller aldrig ändras. Du kan till exempel köra olika kampanjer som har olika kundlojalitetsnivåer: Silver, Gold och Platinum. Du kan sedan använda listrutan för att se till att de enda värden som är godkända är de som matchar dina tre nivåer. Om någon försöker använda ett annat värde, tas det bort.

1. Klicka på **[!UICONTROL Save]**.

## Ta bort en konverteringsklassificering

Ta bort en konverteringsklassificering när den inte längre behövs.

1. Öppna Report Suite Manager genom att klicka **[!UICONTROL Admin]**> **[!UICONTROL Report Suites]** i Suite-rubriken.
1. Välja en rapportsvit.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**.
1. I den **[!UICONTROL Select Classification Type]** nedrullningsbara listan väljer du variabeln där du vill ta bort en klassificering.
1. För musen över **[!UICONTROL Edit Classification]** ikonen och markera sedan **[!UICONTROL Delete Classification]**.
1. Klicka på i dialogrutan Ta bort klassificering **[!UICONTROL Delete]**.
