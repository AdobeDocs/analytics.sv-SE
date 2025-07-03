---
description: Lär dig hur du kan skapa segment från en kontaktyta, lägga till segment som kontaktyta och jämföra viktiga arbetsflöden mellan olika segment i en utfallsanalys i Analysis Workspace.
keywords: utfall och segmentering;segment i utfallsanalys;jämför segment i utfall
title: Använd segment i bortfallsanalys
feature: Visualizations
role: User, Admin
exl-id: 2177cd09-5a27-4295-8414-580cf53062cb
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# Använd segment i utfallsanalys

Du kan skapa segment från en kontaktyta, lägga till segment som kontaktyta och jämföra viktiga arbetsflöden mellan olika segment i Analysis Workspace.

>[!IMPORTANT]
>
>Segment som används som kontrollpunkter i utfall måste använda en behållare som är på en lägre nivå än den övergripande kontexten för utfallsvisualiseringen. Med en besökarkontextutvikning måste segment som används som kontrollpunkter vara besök eller träffbaserade segment. Med en utvikning för besökskontext måste segment som används som kontrollpunkt vara träffbaserade segment. Om du använder en ogiltig kombination blir utfallet 100 %. En varning visas i Utfallsvisualiseringen när du lägger till ett inkompatibelt segment som kontaktyta. Vissa ogiltiga kombinationer av segmentbehållare leder till ogiltiga utfallsdiagram, som:
>
>* Använda ett besöksbaserat segment som kontaktyta inuti en besökarsammanhangsbaserad utfallsvisualisering.
>* Använda ett besöksbaserat segment som kontaktyta i en snabbutfallsvisualisering.
>* Använda ett besöksbaserat segment som kontaktyta i en snabbutfallsvisualisering.
>

## Skapa ett segment från en kontaktyta

1. Skapa ett segment från en viss kontaktyta som du är särskilt intresserad av och som kan vara användbar för andra rapporter. Det gör du genom att högerklicka på kontaktytan och välja **[!UICONTROL Create segment from touchpoint]**.

   ![](assets/fallout-createsegment.png)

   Segmentbyggaren öppnas, ifyllt med det fördefinierade sekventiella segmentet som matchar den kontaktyta du valde:

   ![](assets/fallout-definesegment.png)

1. Ge segmentet en rubrik och beskrivning och spara det.

   Du kan nu använda det här segmentet i vilket projekt som helst.

## Lägga till ett segment som kontaktyta

Om du till exempel vill se hur mobilappen når trenden och påverkar utfallet drar du bara segmentet för mobilappträffar till utfallet:

![](assets/segment-touchpoint.png)

Du kan också skapa en AND-kontaktyta genom att dra segmentet för mobilappsträffar till en annan kontrollpunkt.

## Jämför segment i utfall

Du kan jämföra ett obegränsat antal segment i utfallsvisualiseringen. (Observera att det i videon nedan står att du kan jämföra upp till tre segment, vilket är fel.)


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Jämför segment i en utfallsvisualisering](https://video.tv.adobe.com/v/24046?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


1. Markera de segment som du vill jämföra på panelen [!UICONTROL Segment] till vänster. I exemplet I exemplet är två segment markerade: **[!UICONTROL iOS]** och **[!UICONTROL Android]**.
1. Du drar de tre segmenten till segmentsläppzonen högst upp i visualiseringen.

   ![](assets/segment-compare.png)

1. Valfritt: Du kan behålla *Alla personer* som standardbehållare eller ta bort behållaren.

1. Du kan nu jämföra utfallet för de tre segmenten, till exempel var ett segment presterar bättre än ett annat, eller andra insikter.
