---
description: Så här lägger du till, redigerar, tillämpar och filtrerar Adobe Analytics-segment i Report Builder.
title: Hantera segment (Report Builder)
feature: Report Builder
role: User, Admin
exl-id: c4ad89e0-91c9-47e1-a226-69d82fdb8918
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 0%

---

# Hantera segment

Så här lägger du till, redigerar, tillämpar och filtrerar Adobe Analytics-segment i Report Builder.

Report Builder har en segmenteringspanel i steg 1 i begärandeguiden där du kan skapa och hantera segment.

![](assets/seg_dialog.png)

## Lägga till eller redigera segment {#section_B2BC136F9A53498D90C7C2ECC5DB892B}

>[!NOTE]
>
>Om du vill lägga till eller redigera segment startar segmentgränssnittet i Report Builder segmentet segmentverktyget i Analytics i ett fönster i Microsoft Internet Explorer. Din Report Builder-session förblir aktiv. Andra webbläsare än Internet Explorer stöds inte för den här åtgärden.

1. Klicka på i segmentpanelen i steg 1 i begärandeguiden **[!UICONTROL Add]**.
1. Ett Internet Explorer-fönster öppnas som öppnar gränssnittet i segmentbyggaren i Analytics. Mer information om hur du skapar segment finns i [Analyssegmentering](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html).
1. När du har definierat och sparat segmentet går du tillbaka till Begärandeguiden.
1. Klicka på ikonen Uppdatera för att uppdatera segmentlistan.

>[!IMPORTANT]
>
>Den här listan cachelagras och det segment du skapade visas inte om du inte uppdaterar.

## Skapa sammanhangsberoende segment {#section_6DD2C663B2854469AA1075438F907678}

Du kan ha specifika kombinationer av rapportdimensioner som du vill omvandla till ett segment. Du kan skapa de här segmenten från Report Builder-gränssnittet. Välj till exempel några sidor från en sidförfrågan och skapa ett segment baserat på dessa värden.

1. Markera de rapportutdataobjekt som du vill omvandla till ett segment.
1. Högerklicka för att markera **[!UICONTROL Create In-Context Segment in]** och ange rätt behållare (träffar-behållare, besöksbehållare, besöksbehållare).

   ![](assets/seg_in_context.png)

   Mer information om behållare finns i [Segmenteringshandbok](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html).

1. Segment Builder-gränssnittet kommer nu att startas i Internet Explorer. Användargränssnittet för segmentbyggaren initieras med den behållare och det filter som du angav.
1. När du har lagt till ett namn och en beskrivning i segmentet sparar du det.
1. Gå tillbaka till Report builder och klicka på ikonen Uppdatera för att uppdatera listan med segment.
1. Du kan nu använda det här segmentet.

## Söka efter och använda segment {#section_CACA269B48E94CFD91C2D5A15E9C77B7}

Alla segment som har skapats i Rapporter och analyser, Report Builder eller Data warehouse visas i den här segmentlistan. Om du vill uppdatera listan klickar du på ikonen Uppdatera ( ![](assets/refresh_icon.png).

Du kan tillämpa ett eller flera segment på en viss begäran. Detta inkluderar sekventiella segment.

1. Gå till **[!UICONTROL Segment]** nedrullningsbar lista och klicka på den lilla nedåtpilen i **[!UICONTROL Choose Segment]** om du vill visa alla segment.

   ![](assets/seg_list.png)

1. Kontrollera vilka segment du vill använda.

>[!NOTE]
>
>Oavsett om du är administratör eller icke-administratör kan du i Report Builder bara se de segment som du äger och de som har delats med dig. (I användargränssnittet Marketing Reports &amp; Analytics kan administratören se alla segment i organisationen.)

## Filtrera segment {#section_376E986D3E684999A7CDB08E53854159}

**Filter** segment genom att klicka på filterikonen:  ![](assets/segment_filter.png)

Tillgängliga filter:

| Filternamn | Beskrivning |
|---|---|
| Taggar | Gör att du kan filtrera segment med specifika taggar. Observera att taggfilter använder operatorn AND. Om du markerar två taggar visas de segment i den högra rutan som har taggats med **båda** -taggar. |
| Ägare | Gör att du kan filtrera segment efter ägare. Observera att ägarfilter använder operatorn OR. Om du markerar två ägare visar den högra rutan segment som ägs av **antingen** ägare. |
| Andra filter > Endast *rapportsvitens namn* | Om du använder Endast *rapportsvitens namn*&quot; i Segment Builder i [!DNL marketing reports & analytics]och sedan visa det avancerade filtret i [!DNL report builder]visas bara segmentet för den valda rapportsviten. |
| Andra filter > Mitt | Visar alla segment som du äger. |
| Andra filter > Delat med mig | Visar alla segment som andra delar med dig. |
| Andra filter > Favoriter | Visar alla segment som du har markerat som Favoriter. |
| Andra filter > Godkänt | Visar alla officiellt godkända segment. |

## Lägga till en segmentkontroll i en arbetsbok {#section_E3E5149A8464441FA5445A98DBD520AC}

Genom att lägga till en segmentkontroll kan du växla segment från en arbetsbok i stället för att behöva gå till Begärandeguiden.

1. Klicka på ikonen Kontroll ( ![](assets/control_icon.png)) bredvid segmentlistrutan.

   ![](assets/seg_control.png)

1. Markera alla segment som du vill ska visas i segmentkontrollen eller markera **[!UICONTROL Select All]**.
1. Lägg märke till alternativet **[!UICONTROL Automatically refresh linked requests upon item selection]**.

   * Om det här alternativet är markerat uppdateras alla begäranden som använder den här kontrollen.
   * Om den inte är markerad uppdateras de associerade parametrarna för begäran, men förfrågningarna uppdateras inte.

1. Ange segmentkontrollens övre vänstra cellplacering.
1. Klicka **[!UICONTROL OK]** och segmentkontrollen visas på den angivna platsen.

   ![](assets/seg_control2.png)

## Uppdatera listan med segment {#section_22E4A86789444B4A998532396B476EFB}

När du vill lägga till ett nytt segment eller redigera ett befintligt bör du klicka på ikonen Uppdatera ( ![](assets/refresh_icon.png) om du vill uppdatera den cachelagrade listan med segment.

## Hantera segment över förfrågningar {#section_C3D63FCBE1A94369A319243313B03C93}

Före v5.4 kan Report Builder ändra segment vid flera förfrågningar. Den här processen ersätter dock alltid de befintliga segmenten. Användare som vill lägga till ett nytt segment i varje begäran kunde inte göra detta eftersom den tidigare uppsättningen segment som redan tilldelats varje begäran skulle tas bort om segmentet lades till.

Med Report Builder 5.4 kan du lägga till, ta bort, ersätta och ersätta alla segment i flera begäranden:

1. Markera flera begäranden i en arbetsbok.
1. Högerklicka och välj **[!UICONTROL Edit Requests]** > **[!UICONTROL By Segment]**.

   ![](assets/edit_by_segment.png)

1. I dialogrutan Redigera grupp väljer du ett av de fyra alternativen:

   | Alternativ | Beskrivning |
   |---|---|
   | Lägg till segment | Gör att du kan välja ett eller flera segment att lägga till i listan över aktuella segment. |
   | Ersätt segment | Här kan du välja vilka segment som ska ersättas med ett eller flera segment. |
   | Ersätt alla segment med | Gör att du kan välja ett eller flera segment att ersätta det aktuella segmentet/de aktuella segmenten med. |
   | Ta bort segment | Gör att du kan ta bort segment från begäranden. |
