---
title: Export av klassificeringsdata via FTP
description: FTP-export ger större flexibilitet vid nedladdning av datauppsättningar, inklusive nedladdning av data från flera rapportsviter och nedladdning av datauppsättningsfiler som är större än 50 000 datarader
feature: Classifications
exl-id: 6f97f0b2-1a04-407f-9df9-8715da52037d
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 0%

---

# Export av klassificeringsdata via FTP

FTP-alternativet ger större flexibilitet vid nedladdning av datauppsättningar, inklusive möjligheten att hämta data från flera rapportsviter och att hämta datauppsättningsfiler som är större än 50 000 datarader. Skapa ett FTP-konto innan du hämtar klassificeringsdata via FTP.

Tänk på följande när du tillämpar datafilter:

* Du kan använda jokertecken när du definierar datafiltret. Använd en asterisk `*` för att matcha noll eller flera tecken och ett frågetecken `?` för att matcha exakt ett tecken. Använd `?*` för att matcha ett eller flera tecken.
* När du använder båda typerna av datafilter på en hämtning hämtas vanligtvis bara rader som matchar båda reglerna. Följande undantag gäller dock:
   * Om rader med tom kolumn = Alla kolumner kontrolleras alla kolumner utom den kolumn som anges i den första regeln för tomhet. Detta undantag säkerställer att verktyget hämtar alla rader med en kolumn som matchar den första regeln som också har alla andra kolumner tomma.
   * När du hämtar datarader som baseras på tomma kolumner kontrolleras alla kolumner utom de som anges i den första regeln för tomhet.
   * Om samma kolumn anges för båda filterreglerna (det är nästan omöjligt att uppfylla båda villkoren) hämtas bara rader som matchar den första regeln.
   * FTP-exporter har en begränsning på 30 kolumner.

## Exportera klassificeringar med FTP

De här stegen beskriver hur du exporterar (hämtar) klassificeringar från Adobe Analytics med hjälp av FTP.

1. Skapa ett FTP-konto.
1. Gå till [!UICONTROL Admin] > [!UICONTROL Classification Importer].
1. Klicka på **[!UICONTROL FTP Import]** -fliken.
1. Konfigurera fält för FTP-export.
1. Klicka på **[!UICONTROL Export File]**.
1. Spara datauppsättningen i ditt lokala system.

## Fältbeskrivningar

| Element | Beskrivningar |
| --- | --- |
| [!UICONTROL Select Report Suite] | Välj den rapportsvit som du vill exportera rapportdata från. |
| [!UICONTROL Data Set to be classified] | Välj den datauppsättning som du vill klassificera i listrutan. |
| [!UICONTROL Select Number of Rows] | Ange hur många rader med data som ska exporteras.<ul><li>Välj **[!UICONTROL All]** för att ladda ned alla rapportdata.</li><li>Välj **[!UICONTROL Limit Data Rows To]** om du vill ange ett visst antal rader som ska hämtas.</li></ul> |
| [!UICONTROL Filter by Date Received] | (Valfritt) Filtrera data efter det datum då de togs emot. Ange datumintervallet som du vill hämta data för. |
| [!UICONTROL Apply Data Filter] | (Valfritt) Filtrera datauppsättningen efter datavillkor. Du kan filtrera nedladdningen så att den innehåller datarader som innehåller ett visst värde eller datarader med otilldelade kolumnvärden (klassificerings-). |
| [!UICONTROL Date Filter] | (Valfritt) Filtrera data efter kampanjdata.Du kan bara hämta data från aktiva kampanjer, eller välja kampanjer som börjar (eller slutar) inom ett visst datumintervall. |
| [!UICONTROL Export Numeric 2] | Du kan importera Numeric 2-klassificeringar till systemet med hjälp av importeraren. Numeriska 2-klassificeringar är användbara för variabler som ändras över tid för olika objekt, till exempel kostnad- och budgetvärden för Marketing Channel-rapporten. |
| [!UICONTROL FTP Account] | Ange den FTP-serverinformation där du vill att Adobe ska hämta datafilen, inklusive värdnamn och port, sökväg till målkatalogen, användarnamn och lösenord. |
| [!UICONTROL Notification] | Ange den e-postadress som du vill ska få meddelanden om den här FTP-hämtningen. |
| [!UICONTROL Encoding] | Välj teckenkodning för datafilen. Standardkodningsformatet är antingen UTF-8 eller ISO-8859-1, baserat på den kodning som överfördes för klassificeringen. UTF-8 till UTF-16 konverterar dina UTF-8-kodade klassificeringar till UTF-16-kodning. ISO-8859-1 till UTF-16 konverterar dina ISO-8859-1-kodade klassificeringar till UTF-16-kodning.<br>**Obs!** Om du väljer att konvertera till UTF-16 måste källkodningen matcha kodningen för den ursprungliga överföringen, annars kan oväntade resultat uppstå. Vi rekommenderar att du kodar alla överförda filer i UTF-8 utan BOM. |
