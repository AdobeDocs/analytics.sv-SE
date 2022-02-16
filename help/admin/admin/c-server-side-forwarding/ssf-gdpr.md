---
description: Beskriver förbättringar av vidarebefordran på serversidan som har gjorts av EU:s regler för cookie-kompatibilitet.
title: GDPR/ePrivacy-efterlevnad och vidarebefordran på serversidan
feature: Server-Side Forwarding
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
source-git-commit: ee56267979979f8e03b1c6a0d849ccf994599024
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 3%

---

# GDPR/ePrivacy-efterlevnad och vidarebefordran på serversidan

I det här avsnittet förklaras de förbättringar av vidarebefordran på serversidan som uppmanades av [EU:s regler om överensstämmelse med cookies](https://wikis.ec.europa.eu/display/WEBGUIDE/04.+Cookies+and+similar+technologies), som trädde i kraft den 30 september 2017.

Vidarebefordran på serversidan används för att dela data från Adobe Analytics till andra [!DNL Experience Cloud Solutions], till exempel Audience Manager, i realtid. När det här alternativet är aktiverat kan Analytics även skicka data till andra Experience Cloud-lösningar och dessa lösningar skicka data till Analytics under datainsamlingsprocessen.

Tidigare hade vidarebefordran på serversidan inte något sätt att skilja mellan händelser/träffar för medgivande och förhandsmedgivande. Från och med den 1 november 2018 har du som personuppgiftsansvarig (Adobe Analytics-kund) möjlighet att begränsa förhandsgodkännande av data till Adobe Analytics och förhindra att de vidarebefordras till AAM. Med en ny sammanhangsvariabel för implementering kan du flagga träffar där samtycke inte har tagits emot. När variabeln är inställd förhindrar den att de här träffarna skickas till AAM tills samtycke har tagits emot.

När den nya kontextvariabeln `cm.ssf=1`, finns på en träff, den här träffen flaggas och serversidan vidarebefordras inte till AAM. Om den här strängen inte visas på en träff vidarebefordras träffen till AAM.

Vidarebefordran på serversidan är dubbelriktad, vilket innebär att när den tillämpas på en träff och den träffen vidarebefordras till AAM, får Audience Analytics segmentinformation för träffen från AAM och skickar tillbaka den till Analytics. Det innebär att träffar som inte vidarebefordras från Analytics till AAM på serversidan inte kommer att berikas med listan över segment-ID:n från AAM. Det kommer därför att finnas en delmängd av trafik/träffar som inte hämtar information om segment-ID från AAM.

## Implementeringsinformation {#section_FFA8B66085BF469FAB5365C944FE38F7}

Följ de här stegen beroende på vilken implementeringsmetod du använder.

| Implementeringsmetod | Steg |
|--- |--- |
| Taggar i Adobe Experience Platform | Om du har Adobe Analytics-tillägget installerat lägger du till följande kontextdatavariabeldefinition i den anpassade kodredigeraren i åtgärdskonfigurationen för en regel: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Obs! Definiera kontextdatavariabeln och ange den till 1 om kunden inte samtycker till riktad marknadsföring. Ange `contextdata` variabel till *0* för kunder som gått med på riktad marknadsföring. |
| AppMeasurement | Lägg till variabeldefinitionen för kontextdata i filen AppMeasurement.js:  <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Obs! Definiera kontextdatavariabeln och ange den till 1 om kunden inte samtycker till riktad marknadsföring. Ställ in kontextdatavariabeln på 0 för kunder som samtyckte till riktad marknadsföring. |

## Rapportering (valfritt) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Du kan använda Adobe Analytics för att rapportera hur mycket av er trafik som är samtyckesbaserad och som ett resultat av detta har vidarebefordrats på serversidan jämfört med hur mycket av er trafik som inte är medgivandebaserad och som inte har vidarebefordrats till AAM.

Om du vill konfigurera den här typen av rapportering mappar du den nya kontextvariabeln till en anpassad trafikvariabel (prop) via bearbetningsregler. Gör så här

1. Implementera variabeln &quot;cm.ssf&quot; (som visas ovan).
1. [Aktivera säljaren.](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. Använd bearbetningsregler för att mappa kontextvariabeln till säljaren.

   1. Gå till  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** väljer du sedan en rapportserie.
   1. Klicka på  **[!UICONTROL Edit Report Suite]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]** .
   1. Klicka på **[!UICONTROL Add Rule.]**
   1. Under **[!UICONTROL Always Execute]** skriver du över värdet för det uttryck du aktiverat med kontextvariabeln &quot;cm.ssf(Context Data)&quot;.
   1. Klicka på **[!UICONTROL Save]**.
