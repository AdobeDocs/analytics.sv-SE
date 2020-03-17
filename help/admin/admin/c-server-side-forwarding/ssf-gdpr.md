---
description: 'null'
title: GDPR/ePrivacy compliance och vidarebefordran på serversidan
uuid: 1b90c567-3321-4dbd-a699-38c04e809fa4
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# GDPR/ePrivacy compliance och vidarebefordran på serversidan

I det här avsnittet förklaras de senaste förbättringarna av vidarebefordran på serversidan som togs fram av [EU:s regler](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm)för efterlevnad av cookies, som trädde i kraft den 30 september 2017.

Vidarebefordran på serversidan används för att dela data från Adobe Analytics med andra [!DNL Experience Cloud Solutions], till exempel Audience Manager, i realtid. När det här alternativet är aktiverat kan Analytics även överföra data till andra Experience Cloud-lösningar och för att dessa lösningar ska skicka data till Analytics under datainsamlingsprocessen.

Fram tills nyligen har vidarebefordring på serversidan inte kunnat avgöra om det fanns händelser/träffar för samtycke och för förhandsgodkännande. Från och med den 1 november 2018 har du som datakontroll (Adobe Analytics-kund) möjlighet att begränsa förhandsgodkännande av data till Adobe Analytics och förhindra att de vidarebefordras till AAM. Med en ny sammanhangsvariabel för implementering kan du flagga träffar där samtycke inte har tagits emot. När variabeln är inställd hindras dessa träffar från att skickas till AAM tills samtycke har erhållits.

När den nya kontextvariabeln `cm.ssf=1`finns i en träff flaggas den här träffen och serversidan vidarebefordras inte till AAM. Om den här strängen inte visas i en träff vidarebefordras träffen till AAM.

Vidarebefordran på serversidan är dubbelriktad, vilket innebär att när den tillämpas på en träff och den träffen vidarebefordras till AAM, tar Audience Analytics emot segmentinformation för träffen från AAM och skickar tillbaka den till Analytics. Därför kommer träffar som inte vidarebefordras från Analytics till AAM på serversidan inte att berikas med listan över segment-ID:n från AAM. Det kommer därför att finnas en delmängd av trafik/träffar som inte kommer att få information om segment-ID från AAM.

## Implementeringsinformation {#section_FFA8B66085BF469FAB5365C944FE38F7}

Följ de här stegen beroende på vilken implementeringsmetod du använder.

| Implementeringsmetod | Steg |
|--- |--- |
| Adobe Experience Platform Launch | Förutsatt att du har Adobe Analytics-tillägget installerat lägger du till följande kontextdatavariabeldefinition i den anpassade kodredigeraren i åtgärdskonfigurationen för en regel: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` Obs! <br/>Obs!  Definiera kontextdatavariabeln och ange den till 1 om kunden inte samtycker till riktad marknadsföring. Ställ in `contextdata` variabeln på *0* för kunder som samtyckte till riktad marknadsföring. |
| DTM | Lägg till variabeldefinitionen för kontextdata i redigeraren för anpassad sidkod: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` Obs! <br/>Obs!  Definiera kontextdatavariabeln och ange den till 1 om kunden inte samtycker till riktad marknadsföring. Ställ in kontextdatavariabeln på 0 för kunder som samtyckte till riktad marknadsföring. |
| AppMeasurement | Lägg till variabeldefinitionen för kontextdata i filen AppMeasurement.js:  <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` Obs! <br/>Obs!  Definiera kontextdatavariabeln och ange den till 1 om kunden inte samtycker till riktad marknadsföring. Ställ in kontextdatavariabeln på 0 för kunder som samtyckte till riktad marknadsföring. |

## Rapportering (valfritt) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Du kan använda Adobe Analytics för att rapportera hur mycket av er trafik som är sammandragsbaserad och som ett resultat av detta har vidarebefordrats på serversidan jämfört med hur mycket av er trafik som inte är sammandragsbaserad och som inte har vidarebefordrats till AAM.

Om du vill konfigurera den här typen av rapportering mappar du den nya kontextvariabeln till en anpassad trafikvariabel (prop) via bearbetningsregler. Gör så här

1. Implementera variabeln &quot;cm.ssf&quot; (som visas ovan).
1. [Aktivera säljaren.](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. Använd bearbetningsregler för att mappa kontextvariabeln till säljaren.

   1. Gå till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** och välj en rapportserie.
   1. Klicka på  **[!UICONTROL Edit Report Suite]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]** .
   1. Klicka på **[!UICONTROL Add Rule.]**
   1. Under **[!UICONTROL Always Execute]** skriver du över värdet för det uttryck som du aktiverat med kontextvariabeln &quot;cm.ssf(Context Data)&quot;.
   1. Klicka på **[!UICONTROL Save]**.

