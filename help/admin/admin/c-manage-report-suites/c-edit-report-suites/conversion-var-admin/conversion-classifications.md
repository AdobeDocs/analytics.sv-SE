---
description: Klassificeringar används för att kategorisera värden i grupper och rapportera på gruppnivå. Du kan t.ex. klassificera alla betalsökningskampanjer i en kategori som popmusiktermer och rapportera hur framgångsrik den kategorin är i förhållande till mått som instanser (klickningar) och konvertering till lyckade händelser.
title: Konverteringsklassificeringar
feature: Classifications
role: Admin
exl-id: b4855000-adf3-4e3b-af36-f4803383126d
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 1%

---

# Konverteringsklassificeringar

Klassificeringar används för att kategorisera värden i grupper och rapportera på gruppnivå. Du kan t.ex. klassificera alla [!UICONTROL Paid Search] kampanjer i en kategori som *popmusiktermer* och rapportera om hur framgångsrik den kategorin är i förhållande till mätvärden som instanser (klickningar) och konvertering till lyckade händelser. Du kan lägga till upp till 255 klassificeringar i en variabel.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**

Med konverteringsklassificeringar kan du klassificera konverteringsvariabler. När de har klassificerats kan alla rapporter som du kan generera med nyckeldata också genereras med hjälp av de associerade dataegenskaperna.

När du har aktiverat klassificeringar använder du [Klassificeringsimporteraren](/help/components/classifications/importer/c-working-with-saint.md) för att tilldela specifika värden till lämplig klassificering.

>[!WARNING]
>
>Om du byter namn på en klassificering kan det orsaka problem med befintliga regler som har skapats i [klassificeringsregelbyggaren](/help/components/classifications/crb/classification-rule-builder.md). Om du byter namn på en klassificering som har klassificeringsregler måste du korrigera varje regel så att den pekar på den nya klassificeringen.

## Beskrivningar av konverteringsklassificeringar

| Element | Beskrivning |
| --- | --- |
| Namn | Klassificeringsnamnet |
| Aktiverat den (endast text) | Anger om textklassificeringen är ett datumintervall för kampanjvariabler. |
| Alternativ (endast text) | Skapar en lista över klassificeringsvärden som är tillgängliga för den här klassificeringen. Använd Alternativ med kampanjvariabler för att ge användarna en lista över värden som stöds för klassificeringen i Campaign Manager. |
| Nummertyp (endast numeriskt) | Anger siffertypen i den numeriska klassificeringen. Alternativen är Numeric, Percent och Currency. |

## Lägg till konverteringsklassificeringar

Så här lägger du till konverteringsklassificeringar i Admin:

1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Välj en rapportsvit.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**.
1. I listrutan **[!UICONTROL Select Classification Type]** väljer du variabeln där du vill lägga till en klassificering.

   ![Steginformation](/help/admin/admin/assets/sub_class_create.png)

1. För musen över ikonen **[!UICONTROL Edit Classification]** och välj sedan **[!UICONTROL Add Classification]**.
1. I fältet **[!UICONTROL Select Type]** väljer du den typ av klassificering som du vill lägga till i variabeln.

   Alternativen är **[!UICONTROL Text]** och **[!UICONTROL Numeric]**. Mer information om klassificeringstyper finns i [Om klassificeringar](/help/components/classifications/c-classifications.md).
1. Konfigurera klassificeringen i dialogrutan **[!UICONTROL Text Classifications]** efter behov.

1. Lägg till eller ta bort alternativ i listrutan.

   Med Alternativ för att lägga till skapas en lista med klassificeringsvärden som är tillgängliga för den här klassificeringen. Du kan använda det här alternativet med Campaign-variabler för att ge användarna en lista över värden som stöds för klassificeringen i Campaign Manager. Använd detta för klassificeringsdimensioner där du har ett litet antal tillåtna värden som sällan eller aldrig ändras. Du kan till exempel köra olika kampanjer som har olika kundlojalitetsnivåer: Silver, Gold och Platinum. Du kan sedan använda listrutan för att se till att de enda värden som är godkända är de som matchar dina tre nivåer. Om någon försöker använda ett annat värde, tas det bort.

1. Klicka på **[!UICONTROL Save]**.

## Ta bort en konverteringsklassificering

Ta bort en konverteringsklassificering när den inte längre behövs.

1. Öppna Report Suite-hanteraren genom att klicka på **[!UICONTROL Admin]**> **[!UICONTROL Report Suites]** i Suite-rubriken.
1. Välj en rapportsvit.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**.
1. I listrutan **[!UICONTROL Select Classification Type]** väljer du variabeln där du vill ta bort en klassificering.
1. För musen över ikonen **[!UICONTROL Edit Classification]** och välj sedan **[!UICONTROL Delete Classification]**.
1. Klicka på **[!UICONTROL Delete]** i dialogrutan Ta bort klassificering.
