---
description: Variabler för sekretessrapportering i dataintegritet.
title: Variabler för sekretessrapportering
topic: Admin tools
translation-type: tm+mt
source-git-commit: ddbd724231850c816e7b2b2e56dc139d31276d0c

---


# Variabler för sekretessrapportering

Om du vill få mer hjälp med att hantera sekretessdata finns det en uppsättning reserverade variabler som kan användas tillsammans med specifika kontextdatavariabler.
Dessa variabler för sekretessrapportering utgör ett lättanvänt ramverk för att samla in sekretessstatus för varje analyssession.

## Variabler

* Medgivandehantering avanmäl dig
   * Reserverad variabel: List Prop
   * Typ: Kommaavgränsad sträng
   * Innehåller:
      * `contextData.['cm.ssf']=1` visas som SSF
      * `contextData.['opt.dmp']=N` visas som DMP
      * `contextData.['opt.sell']=N` visas som SELL

* Medgivandehantering avanmäl dig
   * Reserverad variabel: List Prop
   * Typ: Kommaavgränsad sträng
   * Innehåller:
      * `contextData.['opt.dmp']=Y` visas som DMP
      * `contextData.['opt.sell']=Y` visas som SELL

## Rapportering

Du kan aktivera variablerna för sekretesrapportering via en ny sekretessinställning som är tillgänglig på Admin Console för Analytics.

Varje rapportsvit kan konfigureras på följande sätt:
1. Klicka på Rapporter och analyser **[!UICONTROL Admin > Report Suites]**.
1. Markera de rapportsviter där du samlar in mediedata och klicka på **[!UICONTROL Edit Settings > Privacy Management]**.

   ![](assets/rsm-privacy-select.png)

1. Klicka på **[!UICONTROL Enable Data Privacy Reports]** knappen.

   > [!NOTE] När variablerna har aktiverats kan de inte stängas av.

   ![](assets/rsm-privacy-enable.png)

1. När du har aktiverat visas ett bekräftelsemeddelande.

   ![](assets/rsm-privacy-config.png)

1. De reserverade variablerna är nu tillgängliga för analys i Rapporter och analyser samt på arbetsytan. Se Medgivandehantering avanmälan och Medgivandehantering avanmäl dig.

   ![](assets/consent-management.png)

## Implementering

Tre kontextdatavariabler har fördefinierats för att fungera med reserverade variabler för hantering av sekretessrapportering.  Det är respektive implementeringstekniker som bestämmer hur dessa variabler ska hanteras och sparas.

Se [Kontextdatavariabler](https://docs.adobe.com/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/context-data-variables.html) för allmän vägledning om hur du implementerar kontextdatavariabler.

### SSF

* Kontextdata: `contextData.['cm.ssf']`
* Godkända värden:
   * 1 - När du skickar värdet &quot;1&quot; innebär det att vidarebefordran på serversidan är i ett avanmälningsläge. Värdet 1 i kombination med den här variabeln blockerar delningen av träffen med Adobe Audience Manager. Se [AAM ePrivacy Compliance](https://docs.adobe.com/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/ssf-gdpr.html).
   * 0 - Valfritt. Använd värdet&quot;0&quot; för kunder som samtyckte till riktad marknadsföring. Om du inte anger variabeln får du också samma resultat.

### DMP

* Kontextdata: `contextData.['opt.dmp']`
* Godkända värden:
   * N - När värdet&quot;N&quot; skickas betyder det att konsumenten väljer att inte dela till datahanteringsplattformar.  **Obs**: Från och med den 15 januari 2020 blockeras delning på serversidan av den här träffen till AAM om variabeln anges som&quot;N&quot;.
   * Y - När värdet&quot;Y&quot; skickas indikerar det att konsumenten väljer att dela till datahanteringsplattformar.

### SÄLJNING

* Kontextdata: `contextData.['opt.sell']`
* Godkända värden:
   * N - När värdet&quot;N&quot; skickas betyder det att konsumenten väljer att inte dela eller sälja uppgifterna till tredje part.
   * Y - När värdet&quot;Y&quot; skickas betyder det att konsumenten väljer att dela eller sälja data till tredje part.
