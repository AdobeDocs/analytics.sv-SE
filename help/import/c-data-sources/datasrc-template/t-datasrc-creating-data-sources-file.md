---
description: Importmallsfilen är avsedd att hjälpa dig att komma igång med importen.
subtopic: Data sources
title: Generera en importfilsmall
topic-fix: Developer and implementation
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
exl-id: c2717936-a011-4224-8a9e-94753abbcb33
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 3%

---

# Generera en importfilsmall

Importmallsfilen är avsedd att hjälpa dig att komma igång med importen.

Du är inte begränsad till kolumnerna som definieras i mallen. Du kan lägga till ytterligare kolumner efter behov, förutsatt att det finns stöd för mått och definitioner för den valda databehandlingstypen. Du kan visa mått och dimensioner som stöds för varje typ i följande avsnitt: [Webblogg](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md), [trafik](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md), [Konvertering](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md), [Transaktions-ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md), [Besökar-ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md), [Fullständig bearbetning](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)). För en trafikdatatyp kan du till exempel lägga till en kolumn för alla mått och mått som anges i [Trafik](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md).

När du har skapat mallen kan du hämta den, ange dina data i mallen och sedan överföra data till FTP-webbplatsen för datakällor. När de har bearbetats av datakällservern är importerade data tillgängliga för användning i dina Analytics-rapporter.

Mallen Datakälla är en .txt-fil som du kan öppna med valfri textredigerare. Det är dock enklast att arbeta med mallen i Microsoft Excel eller något annat kalkylprogram. Mallinnehållet varierar beroende på dina val i guiden Aktivering av datakälla.

Mer information finns i [Importera filreferens](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md).

1. Logga in på Analytics.
1. Välj **[!UICONTROL Admin]** > **[!UICONTROL Data Sources]** i Suite-huvudet.
1. Välj en mallkategori och typ på fliken **[!UICONTROL Data Sources Create]**.
1. Granska aktiveringsinstruktionerna/informationen och klicka sedan på **[!UICONTROL Activate]**.

   Stegresultat 1. Välj alternativ för mallgenerering i guiden Aktivering av datakälla.

   | Guiden Sida | Fält | Beskrivning |
   |--- |--- |--- |
   | 3 | Namn | Mallnamnet som visas i Analytics (Hanteraren för datakällor). |
   | 1 | E-post | E-postadressen som tar emot alla meddelanden som rör användningen av den här datakällmallen. |
   | 3 | Kryssruta för associerade avgifter | Markera kryssrutan för att ange att du godkänner avgifterna som är kopplade till användningen av den här datakällmallen. |
   | 2 | Välj mått | Välj de mätvärden som ska importeras med den här datakällan. Analyser rekommenderar vissa mått baserade på datakällkategorin och typen som valts i steg 3.  Om du vill ange ett annat mått skriver du namnet i ett tomt fält och markerar kryssrutan för att aktivera måttet. |
   | 3 | Mappningsmått | Välj en analyshändelse som ska ta emot varje importerat mätvärde som valts på guidesidan 2.  Dessa ska vara nya, ej tilldelade händelser som du tidigare har tilldelat namn som motsvarar de importerade mätdata som de får via datakällor.  Om en variabel för eVar, produkt eller spårningskod är en målvariabel, och de överförda värdena matchar befintliga hämtade värden, lägger de överförda händelserna i princip till mått i befintliga värden. Du kan t.ex. skapa ett offlineordermått med en produktdatdimension som redan har produktvyer, utcheckningar och beställningar som befintliga mätvärden. |
   | 4 | Välj Dimensioner | Välj de datamått som ska användas för att dela upp importerade mätvärden från den här datakällan. Analyser rekommenderar vissa datamått baserade på den datakälltyp som valts i steg 3.  Om du vill ange en annan datamängd anger du dess namn i ett tomt fält och markerar sedan kryssrutan för att aktivera datamätningen. |
   | 5 | Dimensioner för kartdata | Markera en standardrapport eller eVar som ska ta emot varje importerad datamängd som valts på guidesidan 4. |

1. När mallen har genererats kopierar du data till rätt kolumner i datakällmallen och ser till att du följer det dataformat som krävs för den datakolumnen.

   Stegresultat 1. Spara datakällfilen med valfritt namngivningskonvention. Adobe rekommenderar att du använder en konsekvent namnkonvention för alla datakällfiler. Använd ett vanligt filtillägg som .txt eller .tsv (eller använd inte något tillägg).
