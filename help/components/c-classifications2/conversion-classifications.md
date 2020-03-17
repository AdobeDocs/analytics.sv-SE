---
description: Klassificeringar används för att kategorisera värden i grupper och rapportera på gruppnivå. Du kan t.ex. klassificera alla betalsökningskampanjer i en kategori som popmusiktermer och rapportera hur framgångsrik den kategorin är i förhållande till mått som instanser (klickningar) och konvertering till lyckade händelser.
subtopic: Classifications
title: Konverteringsklassificeringar
topic: Admin tools
uuid: 4c8726c9-f527-44e1-be01-8c7b3b5c20f0
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Konverteringsklassificeringar

Klassificeringar används för att kategorisera värden i grupper och rapportera på gruppnivå. Du kan t.ex. klassificera alla betalsökningskampanjer i en kategori som popmusiktermer och rapportera hur framgångsrik den kategorin är i förhållande till mått som instanser (klickningar) och konvertering till lyckade händelser.

## Konverteringsklassificeringar {#concept_B4B1478A8CB540599AC9D4A58CA4B6FE}

Klassificeringar används för att kategorisera värden i grupper och rapportera på gruppnivå. Du kan t.ex. klassificera alla betalsökningskampanjer i en kategori som *popmusiktermer* och rapportera om framgången i den kategorin i förhållande till mätvärden som instanser (klickningar) och konvertering till framgångshändelser.

Med konverteringsklassificeringar kan du klassificera konverteringsvariabler. När de har klassificerats kan alla rapporter som du kan generera med nyckeldata också genereras med hjälp av de associerade dataegenskaperna.

När du har aktiverat klassificeringar använder du [Klassificeringsimporteraren](/help/components/c-classifications2/c-classifications-importer/c-working-with-saint.md) för att tilldela specifika värden till lämplig klassificering.

## Beskrivningar av konverteringsklassificeringar {#section_4A98DD5F5C314B9DAEE710AEE4EE51D4}

<table id="table_0B72C485467348E2A34BF913441F4AF5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Namn</span> </td> 
   <td colname="col2"> Klassificeringsnamnet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Aktiverat den (endast text)</span> </td> 
   <td colname="col2"> <p>Anger om textklassificeringen är ett datumintervall för kampanjvariabler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Alternativ (endast text)</span> </td> 
   <td colname="col2">Skapar en lista över klassificeringsvärden som är tillgängliga för den här klassificeringen. Använd <span class="wintitle"> Alternativ</span> med kampanjvariabler för att ge användarna en lista över värden som stöds för klassificeringen i <span class="wintitle"> Campaign Manager</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Nummertyp (endast numeriskt)</span> </td> 
   <td colname="col2">Anger siffertypen i den numeriska klassificeringen. Alternativen är <span class="wintitle"> Numeric</span>, <span class="wintitle"> Percent</span>och <span class="wintitle"> Currency</span>. </td> 
  </tr> 
 </tbody> 
</table>

## Lägg till konverteringsklassificeringar {#task_D535D09E3EAF4CD1A15A6B93C0BB1BB5}

<!-- 

t_classification_conversion.xml

 -->

Steg som beskriver hur du lägger till konverteringsklassificeringar i Admin.

1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Välj en rapportsvit.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**.
1. I den **[!UICONTROL Select Classification Type]** nedrullningsbara listan väljer du variabeln där du vill lägga till en klassificering.

   ![Steginformation](assets/sub_class_create.png)

1. För musen över **[!UICONTROL Edit Classification]** ikonen och markera sedan **[!UICONTROL Add Classification]**.
1. I **[!UICONTROL Select Type]** fältet väljer du vilken typ av klassificering du vill lägga till i variabeln.

   Alternativen är **[!UICONTROL Text]** och **[!UICONTROL Numeric]**. Mer information om klassificeringstyper finns i [Om klassificeringar](/help/components/c-classifications2/c-classifications.md).
1. Konfigurera klassificeringen i **[!UICONTROL Text Classifications]** dialogrutan efter behov.

   Mer information om de här elementen finns i Beskrivningar av [konverteringsklassificeringar](/help/components/c-classifications2/conversion-classifications.md#section_4A98DD5F5C314B9DAEE710AEE4EE51D4) .

1. Lägg till eller ta bort alternativ i **[!UICONTROL Dropdown List]** dialogrutan.

   Med Alternativ för att lägga till skapas en lista med klassificeringsvärden som är tillgängliga för den här klassificeringen. Du kan använda det här alternativet med Campaign-variabler för att ge användarna en lista över värden som stöds för klassificeringen i Campaign Manager. Använd detta för klassificeringsdimensioner där du har ett litet antal tillåtna värden som sällan eller aldrig ändras. Du kan till exempel köra olika kampanjer som har olika kundlojalitetsnivåer: Silver, Gold och Platinum. Du kan sedan använda listrutan för att se till att de enda värden som är godkända är de som matchar dina tre nivåer. Om någon försöker använda ett annat värde, tas det bort.
1. Klicka på **[!UICONTROL Save]**.

## Ta bort en konverteringsklassificering {#task_566651BC245944618A6A833E58211FDE}

<!-- 

t_classification_delete_conversion.xml

 -->

Ta bort en konverteringsklassificering när den inte längre behövs.

1. Öppna Report Suite Manager genom att klicka **[!UICONTROL Admin]**> **[!UICONTROL Report Suites]** i Suite-rubriken.
1. Välj en rapportsvit.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**.
1. I den **[!UICONTROL Select Classification Type]** nedrullningsbara listan väljer du variabeln där du vill ta bort en klassificering.
1. För musen över **[!UICONTROL Edit Classification]** ikonen och markera sedan **[!UICONTROL Delete Classification]**.
1. Klicka på i dialogrutan Ta bort klassificering **[!UICONTROL Delete]**.
