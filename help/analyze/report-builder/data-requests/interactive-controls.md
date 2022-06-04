---
description: Med interaktiva kontroller kan du redigera segment och datumintervall för en eller flera begäranden direkt från kalkylbladet. Detta ger större flexibilitet vid uppdatering av förfrågningar från Report builder.
title: Interaktiva kontroller
feature: Report Builder
role: User, Admin
exl-id: 2340ff31-1478-4a54-a4c3-c51e73c39109
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 1%

---

# Interaktiva kontroller

Med interaktiva kontroller kan du redigera segment och datumintervall för en eller flera begäranden direkt från kalkylbladet. Detta ger större flexibilitet vid uppdatering av förfrågningar från Report builder.

Interaktiva kontroller skapades som svar på ett gemensamt arbetsflöde där analytiker skapar arbetsböcker och delar dessa arbetsböcker med marknadsföringsorganisationen. Med interaktiva kontroller kan marknadsförarna ändra och uppdatera förfrågningar utan att behöva ha djupgående kunskaper om hur Report builder fungerar. (Observera att arbetsbokens mottagare måste vara en rapportskaparanvändare för att en begäran ska kunna uppdateras.) Dessa kontroller fungerar inuti schemalagda arbetsböcker. Det finns för närvarande två typer av interaktiva kontroller:

* Rullande datumintervall
* Segment

>[!IMPORTANT]
>
>Du måste ha Report Builder v5.0 installerat för att de interaktiva kontrollerna ska fungera. >
>* Om du kör Microsoft Excel i Windows men kör en äldre version av Report Builder, eller om du inte har Report Builder installerat: Du kan ändra värdet i den interaktiva kontrollen, men det kommer inte att uppdatera den associerade begäran eller uppdatera de associerade parametrarna för begäran.
>* Om du kör Excel på Mac och ändrar värdet i kontrollen visas följande meddelande: &quot;Det går inte att hitta makrot &quot;Adobe.ReportBuilder.Bridge.FormControlClick.Event&quot;.&quot;
>


>[!WARNING]
>
>Manipulera inte med namnet på kontrollen. (Om du vill se namnet anger du fokus på kontrollen så visas kontrollnamnet precis ovanför Excel-stödrastret i det övre vänstra hörnet.)

## Implementera interaktiv kontroll för datumintervall {#section_39B228F2D2C44985863D31424C953280}

1. I steg 1 i begärandeguiden väljer du till exempel **[!UICONTROL Page]** rapport.
1. Intill **[!UICONTROL Commonly Used Dates]** nedrullningsbar meny, klicka på **[!UICONTROL Control Settings]** ikon:

   ![](assets/date_range_control.png)

1. I dialogrutan Kontrollinställningar markerar du alla datumintervallobjekt som du vill ska visas i den interaktiva kontrollen. Ange dessutom kontrollens övre vänstra cellplacering.

   ![](assets/control_settings.png)

1. Observera alternativet &quot;Uppdatera länkade begäranden automatiskt när objekt väljs&quot;.

   * Om det här alternativet är markerat uppdateras alla begäranden som använder den här kontrollen.
   * Om den inte är markerad uppdateras de associerade parametrarna för begäran, men begäran uppdateras inte.

1. Klicka på **[!UICONTROL OK]**. Kontrollen visas på den cellplats som du har angett:

   ![](assets/date_range_control_interactive.png)

1. Du kan nu ändra datumintervallet och begäran uppdateras med det datumintervallet.
1. Du kan också kopiera begäran och högerklicka för att använda ett av två alternativ för Klistra in begäran:

   * **[!UICONTROL Paste Request]** > **[!UICONTROL Use Absolute Input Cell]**. Det innebär att den kopierade begäran pekar på samma interaktiva datumintervallkontroll som den ursprungliga begäran.

   * **[!UICONTROL Paste Request]**> **[!UICONTROL Use Relative input Cell]**. Det innebär att den kopierade begäran pekar på sin egen kontroll.

      >[!NOTE]
      >
      >Du kan använda den inbyggda funktionen Klipp ut/Kopiera/Klistra in i Microsoft Excel. Report builder känner automatiskt igen de nya kontrollerna.

## Implementera interaktiv segmentkontroll {#section_5003D3F724644280BF1BCD6E1B0CB784}

Att implementera den interaktiva segmentkontrollen liknar att implementera datumintervallkontrollen.

1. I steg 1 i begärandeguiden, bredvid **[!UICONTROL Segment]** väljer du ikonen Inställningar för segmentkontroll:

   ![](assets/segment_interactive_1.png)

1. I dialogrutan Inställningar för segmentkontroll markerar du de segment som du vill ta med i listrutan. Ange dessutom kontrollens övre vänstra cellplacering.

   ![](assets/segment_drop_down_properties.png)

1. Den nya interaktiva kontrollen visas nu i arbetsboken:

   ![](assets/segment_interactive_3.png)
