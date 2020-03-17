---
description: Importmallsfilen är avsedd att hjälpa dig att komma igång med importen.
subtopic: Data sources
title: Generera en importfilsmall
topic: Developer and implementation
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Generera en importfilsmall

Importmallsfilen är avsedd att hjälpa dig att komma igång med importen.

Du är inte begränsad till kolumnerna som definieras i mallen. Du kan lägga till ytterligare kolumner efter behov, förutsatt att det finns stöd för mått och definitioner för den valda databehandlingstypen. Du kan visa mått och dimensioner som stöds för varje typ i följande avsnitt: [Webblogg](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md), [trafik](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md), [konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md), [transaktions-ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md), [besökar-ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)[](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md), Full Processing¥). För en trafikdatatyp kan du till exempel lägga till en kolumn för alla mått och mått som anges i [Trafik](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md).

När du har skapat mallen kan du hämta den, ange dina data i mallen och sedan överföra data till FTP-webbplatsen för datakällor. När de har bearbetats av datakällservern är importerade data tillgängliga för användning i dina Analytics-rapporter.

Mallen Datakälla är en .txt-fil som du kan öppna med valfri textredigerare. Det är dock enklast att arbeta med mallen i Microsoft Excel eller något annat kalkylprogram. Mallinnehållet varierar beroende på dina val i guiden Aktivering av datakälla.

Mer information finns i [Importera filreferens](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md) .

1. Logga in på Analytics.
1. Välj **[!UICONTROL Admin]** > **[!UICONTROL Data Sources]** i Suite-rubriken.
1. Välj en mallkategori och malltyp på **[!UICONTROL Data Sources Create]** fliken.
1. Granska aktiveringsinstruktionerna/informationen och klicka sedan på **[!UICONTROL Activate]**.

   Stegresultat 1. Välj alternativ för mallgenerering i guiden Aktivering av datakälla.

   | Guiden Sida | Fält | Beskrivning |
   |--- |--- |--- |
   | 1 | Namn | Mallnamnet som visas i Analytics (Hanteraren för datakällor). |
   | 1 | E-post | E-postadressen som tar emot alla meddelanden som rör användningen av den här datakällmallen. |
   | 1 | Kryssruta för associerade avgifter | Markera kryssrutan för att ange att du godkänner avgifterna som är kopplade till användningen av den här datakällmallen. |
   | 2 | Välj mått | Välj de mätvärden som ska importeras med den här datakällan. Analyser rekommenderar vissa mått baserade på datakällkategorin och typen som valts i steg 3.  Om du vill ange ett annat mått skriver du namnet i ett tomt fält och markerar kryssrutan för att aktivera måttet. |
   | 3 | Mappningsmått | Välj en analyshändelse som ska ta emot varje importerat mätvärde som valts på guidesidan 2.  Dessa ska vara nya, ej tilldelade händelser som du tidigare har tilldelat namn som motsvarar de importerade mätdata som de får via datakällor.  Om en eVar-, Product- eller Tracking Code-variabel är en målvariabel och de överförda värdena matchar befintliga hämtade värden, lägger de överförda händelserna i princip till mått i befintliga värden. Du kan t.ex. skapa ett offlineordermått med en produktdatdimension som redan har produktvyer, utcheckningar och beställningar som befintliga mätvärden. |
   | 4 | Välj datadimensioner | Välj de datamått som ska användas för att dela upp importerade mätvärden från den här datakällan. Analytics rekommenderar vissa datamått baserade på den datakälltyp som valts i steg 3.  Om du vill ange en annan datamängd anger du dess namn i ett tomt fält och markerar sedan kryssrutan för att aktivera datamätningen. |
   | 5 | Mappa datamått | Välj en standardrapport eller eVar för att ta emot varje importerad datamängd som valts på guidesidan 4. |

1. När mallen har genererats kopierar du data till rätt kolumner i datakällmallen och ser till att du följer det dataformat som krävs för den datakolumnen.

   Stegresultat 1. Spara datakällfilen med valfritt namngivningskonvention. Adobe rekommenderar att du använder en konsekvent namnkonvention för alla datakällfiler. Använd ett vanligt filtillägg som .txt eller .tsv (eller använd inte något tillägg).

