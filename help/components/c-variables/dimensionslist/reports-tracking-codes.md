---
description: Mäter hur olika annonseringsspårningskoder påverkar olika konverteringshändelser på din webbplats. Den här rapporten kan användas för att mäta vilka specifika kampanjer som fungerar bättre för olika framgångshändelser eller för att se hur kampanjer hjälper till eller hämmar webbplatsens initiativ, till exempel vilka kampanjer som genererar störst intäkter.
title: Spårningskoder
topic: Reports
uuid: c893d592-10fd-4b40-84b3-8c8949a67b25
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Spårningskoder

Mäter hur olika annonseringsspårningskoder påverkar olika konverteringshändelser på din webbplats. Den här rapporten kan användas för att mäta vilka specifika kampanjer som fungerar bättre för olika framgångshändelser eller för att se hur kampanjer hjälper till eller hämmar webbplatsens initiativ, till exempel vilka kampanjer som genererar störst intäkter.

**Allmänna egenskaper**

* Den här rapporten refererar till data direkt från [s.campaign](/help/implement/vars/page-vars/campaign.md)
* Variabeln som rapporten baseras på är en [konverteringsvariabel](/help/admin/admin/conversion-var-admin/conversion-var-admin.md). Det innebär att det kan finnas kvar utanför sidvyn och associeras med mätvärden inom den angivna förfallotiden.
* Rapportens standardmått är Intäkter. Du kan ändra det här standardvärdet i [!UICONTROL Report Suite Manager] i [!UICONTROL Admin Tools]. ( **[!UICONTROL Edit Settings]** > **[!UICONTROL Individual Report Settings]** > **[!UICONTROL Default Metrics]**.)

* Den här rapporten kan visas i både trand- och rankningsformat.
* Den här rapporten kan använda ett sökfilter för att hitta specifika radobjekt.
* Rapporterna [!UICONTROL Campaigns] och [!UICONTROL Creative Elements] rapporterna är klassificeringar som baseras på den här rapporten och skapas automatiskt med varje rapportserie.

* Du kan använda SAINT Classifications i den här rapporten för att byta namn på och konsolidera radobjekt.
* Du kan dela upp den här rapporten med följande rapporter (beroende på inställningar för organisation och rapportsviten):

   * Tid per besök
   * Rapporter om sidor och webbplatsavsnitt, med alla relaterade klassificeringar
   * Siddjup, anmälningssidor och ursprungliga anmälningssidor
   * De flesta trafikkällor rapporterar
   * Besök nummer och kundlojalitet
   * Många besökarprofiler och tekniska rapporter, förutom GeoSegmentation
   * Alla anpassade konverteringsvariabler

* Följande mätvärden kan användas i den här rapporten (beroende på inställningar för organisation och rapportsviten):

   * Klickfunktioner: antalet gånger som *`s.campaign`* variabeln definieras
   * Alla standardvärden för e-handel: Intäkter, beställningar, enheter, kundvagnar, kundvagnsvyer, utcheckningar, kundvagnstillägg, kundvagnsborttagningar.
   * Alla anpassade händelser: Händelser 1-80 och händelser 81-100 om H22-kod eller högre används
   * Besök och besökare: tillgängligheten är beroende av organisation och rapportserie. Kontakta kontohanteraren om du vill ha mer information.

**Rapporter och analysegenskaper**

* Klicka **[!UICONTROL Conversion]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Tracking Code]** om du vill hitta rapporten, såvida inte menyn är anpassad.

* Den här rapporten kan också delas upp efter alla [listvariabler](https://marketing.adobe.com/resources/help/en_US/sc/implement/list_var.html).
* Sidvyer, besök och unika besökare är tillgängliga som mått.
* Den här rapporten kan använda segment.

**Ad hoc-analysegenskaper**

* Förutom de flesta färdiga konverteringsvariabler kan du bryta ned Tracking Code-rapporten från alla andra rapporter i rapportgränssnittet.
* Förutom e-handel och anpassade händelser kan ni använda alla konverterings- och trafikvärden, samt använda olika allokeringar för alla konverteringsvärden.
* Den här rapporten kan använda avancerade segment.

