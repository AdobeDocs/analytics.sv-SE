---
description: Med interaktiva kontroller kan du redigera segment och datumintervall för en eller flera begäranden direkt från kalkylbladet. Detta ger större flexibilitet vid uppdatering av förfrågningar från Report Builder.
title: Interaktiva kontroller
feature: Report Builder
role: User, Admin
exl-id: 2340ff31-1478-4a54-a4c3-c51e73c39109
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 0%

---

# Interaktiva kontroller

Med interaktiva kontroller kan du redigera segment och datumintervall för en eller flera begäranden direkt från kalkylbladet. Detta ger större flexibilitet vid uppdatering av förfrågningar från Report Builder.

Interaktiva kontroller skapades som svar på ett gemensamt arbetsflöde där analytiker skapar arbetsböcker och delar dessa arbetsböcker med marknadsföringsorganisationen. Med interaktiva kontroller kan marknadsförarna ändra och uppdatera förfrågningar utan att behöva ha djupgående kunskaper om hur Report Builder fungerar. (Observera att arbetsbokens mottagare måste vara en Report Builder-användare för att en begäran ska kunna uppdateras.) Dessa kontroller fungerar inuti schemalagda arbetsböcker. Det finns för närvarande två typer av interaktiva kontroller:

* Rullande datumintervall
* Segment

>[!IMPORTANT]
>
>Du måste ha Report Builder v5.0 installerat för att de interaktiva kontrollerna ska fungera. >
>* Om du kör Microsoft Excel i Windows men kör en äldre version av Report Builder, eller om du inte har Report Builder installerat: Du kan ändra värdet i den interaktiva kontrollen, men den associerade begäran uppdateras inte eller så uppdateras förfrågningens associerade parametrar.
>* Om du kör Excel på Mac och ändrar värdet i kontrollen visas följande meddelande: &quot;Det går inte att hitta makrot &quot;Adobe.ReportBuilder.Bridge.FormControlClick.Event&quot;.&quot;
>

>[!WARNING]
>
>Manipulera inte med namnet på kontrollen. (Om du vill se namnet anger du fokus på kontrollen så visas kontrollnamnet precis ovanför Excel-stödrastret i det övre vänstra hörnet.)

## Implementera interaktiv kontroll för datumintervall {#section_39B228F2D2C44985863D31424C953280}

1. I steg 1 i begärandeguiden väljer du till exempel rapporten **[!UICONTROL Page]**.
1. Klicka på ikonen **[!UICONTROL Control Settings]** bredvid listrutan **[!UICONTROL Commonly Used Dates]**:

   ![Skärmbild av begärandeguiden Steg 1 som markerar ikonen Kontrollinställningar. ](assets/date_range_control.png)

1. I dialogrutan Kontrollinställningar markerar du alla datumintervallobjekt som du vill ska visas i den interaktiva kontrollen. Ange dessutom kontrollens placering i den övre vänstra cellen.

   ![Skärmbild som visar de valda datumintervallobjekten och cellplatsen i det övre vänstra hörnet.](assets/control_settings.png)

1. Observera alternativet &quot;Uppdatera länkade begäranden automatiskt när objekt väljs&quot;.

   * Om det här alternativet är markerat uppdateras alla begäranden som använder den här kontrollen.
   * Om den inte är markerad uppdateras de associerade parametrarna för begäran, men begäran uppdateras inte.

1. Klicka på **[!UICONTROL OK]**. Kontrollen visas på den cellplats som du har angett:

1. Du kan nu ändra datumintervallet och begäran uppdateras med det datumintervallet.

   ![Skärmbild som visar det valda datumintervallet.](assets/date_range_control_interactive.png)

1. Du kan också kopiera begäran och högerklicka för att använda ett av två alternativ för Klistra in begäran:

   * **[!UICONTROL Paste Request]** > **[!UICONTROL Use Absolute Input Cell]**. Det innebär att den kopierade begäran pekar på samma interaktiva datumintervallkontroll som den ursprungliga begäran.

   * **[!UICONTROL Paste Request]**> **[!UICONTROL Use Relative input Cell]**. Det innebär att den kopierade begäran pekar på sin egen kontroll.

     >[!NOTE]
     >
     >Du kan använda den inbyggda funktionen Klipp ut/Kopiera/Klistra in i Microsoft Excel. Report builder känner automatiskt igen de nya kontrollerna.

## Implementera interaktiv segmentkontroll {#section_5003D3F724644280BF1BCD6E1B0CB784}

Att implementera den interaktiva segmentkontrollen liknar att implementera datumintervallkontrollen.

1. I steg 1 i guiden Begäran, bredvid listrutan **[!UICONTROL Segment]**, väljer du ikonen Inställningar för segmentkontroll:

   ![Skärmbild av ikonen Inställningar för segmentkontroll.](assets/segment_interactive_1.png)

1. I dialogrutan Inställningar för segmentkontroll markerar du de segment som du vill ta med i listrutan. Ange dessutom kontrollens placering i den övre vänstra cellen.

   ![Skärmbild som visar inställningar för segmentkontroll med valda segment och cellplacering.](assets/segment_drop_down_properties.png)

1. Den nya interaktiva kontrollen visas nu i arbetsboken:

   ![Skärmbild med den nya interaktiva kontrollen markerad.](assets/segment_interactive_3.png)
