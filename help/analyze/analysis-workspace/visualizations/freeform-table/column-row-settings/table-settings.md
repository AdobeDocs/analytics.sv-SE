---
description: Radinställningarna varierar beroende på vilken komponent du har dragit till tabellen.
title: Radinställningar
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
feature: Freeform Tables
role: User, Admin
exl-id: 9057e930-b4c6-439e-b82a-8ab9828de91d
source-git-commit: 3903387ac6cba1ceb45e1de35fbceb259151f4f8
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 2%

---

# Radinställningar

Radinställningarna varierar beroende på vilken komponent du har dragit till tabellen. Om du vill komma åt tabellradsinställningarna klickar du på inställningsikonen bredvid en dimension, ett segment, ett mått, en tidsperiod eller en uppdelning i var och en av dessa:

![](assets/row-settings.png)

| Inställning | Beskrivning |
|--- |--- |
| Justera datum | Det här är en inställning på tabellnivå som justerar datum från varje kolumn så att alla börjar på samma rad. Datumjustering är aktiverat som standard när en tidsdimension används i tabellraderna och olika datumintervall används i kolumnerna. I en daglig tabell där oktober och september tillämpas på kolumnerna börjar den vänstra kolumnen med 1 oktober och den högra kolumnen börjar med 1 september. |
| Uppdelning efter position | Som standard är den här inställningen inaktiverad och uppdelningar är fasta på statiska radobjekt. Låt oss till exempel säga att du har delat upp de tre viktigaste sidobjekten (startsida, sökresultat, utcheckning) efter marknadsföringskanal. Sedan lämnar du projektet och återvänder två veckor senare. När du öppnar projektet igen har de tre översta sidorna ändrats, och nu är startsidan, sökresultaten och utcheckningen de 4-6 översta sidorna istället. Som standard visas dina Marketing Channel-indelningar fortfarande under Hemsida, Sökresultat och Utcheckning, även om de nu finns på raderna 4-6. <br> I motsats till **Uppdelning efter position** kommer alltid att dela upp de tre främsta objekten, oavsett vad de är. När du öppnar ditt projekt på nytt, som en hänvisning till vårt exempel, kommer de tre främsta sidorna i tabellen att vara kopplade till Marketing Channel-uppdelningarna, inte till Hemsida, Sökresultat och Utcheckning, som nu finns på raderna 4-6. |
| Procenttal | **Beräkna procentandelar per kolumn** är standardinställningen, de procentsatser som visas i en kolumn beräknas utifrån kolumnsumman. <br>**Beräkna procentandelar per rad** tvingar friformstabellen att beräkna cellprocenten över raden i stället för nedåt i kolumnen, med totalsumman som nämnare. Detta är särskilt användbart för att hantera procentsatser. Den här inställningen är aktiverad som standard när du använder ikonen Visa. |
| Kolumnsummor | De här inställningarna är bara tillgängliga för [statiska rader](manual-vs-dynamic-rows.md). <br> **Visa som summan av aktuella rader** visar en summa av raderna i tabellen på klientsidan, vilket innebär att summan *not* avduplicera mätvärden som besök eller besökare. <br> **Visa totalsumma** visar en serversidessumma vilket innebär att summan kommer att dubblera måtten. |

## Ändra radantal

Så här ändrar du antalet rader som visas:

1. Klicka på siffran bredvid [!UICONTROL Rows] längst upp på bordet.

   ![](assets/row-number.png)

1. I listrutan väljer du det antal rader som du vill att tabellen ska visa.

## Videor

Här är en kort video om&quot;Procent av rad&quot;:

>[!VIDEO](https://video.tv.adobe.com/v/23134/?quality=12)
