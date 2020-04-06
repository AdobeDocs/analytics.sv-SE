---
title: Paketanalysatorer
description: Med paketanalyserare kan du visa data som skickas av implementeringen till Adobes datainsamlingsservrar.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Paketanalysatorer

Med paketanalyserare kan du visa data som skickas av implementeringen till Adobes datainsamlingsservrar.

På samma sätt som felsökaren för Adobe Experience Cloud visar en paketskärm vilka dataparametrar som skickas i en bildbegäran. paketskärmar har dock fler funktioner:

* Visa bildbegäran för anpassad länkspårning
* Visa bildbegäranden med andra implementeringsmetoder än JavaScript, till exempel hårdkodade bildbegäranden eller [!DNL Appmeasurement]

Om du vill visa Analytics-begäranden filtrerar du utgående begäranden med&quot;b/ss&quot;.

I mycket sällsynta fall rapporterar felsökaren en bildförfrågan, men ingen begäran gör den till Adobes [!DNL Analytics] bearbetningsservrar. Att använda en paketbildskärm är ett bra sätt att vara helt säker på att en viss bildbegäran kan utlösas.

Även om Adobe inte har någon officiell paketövervakare finns det många sådana på internet. Här följer några exempel på paketskärmar som andra tycker är användbara.

>[!NOTE] Dessa listor är inte avsedda att vara heltäckande, utan snarare information om ofta använda bildskärmar. Om du har en paketskärm som du använder och tycker är användbar kan du ge feedback med knappen till höger i det här fönstret. [!UICONTROL Feedback]

| Firefox | Internet Explorer | Krom | Fristående program |
|---|---|---|---|
| [Observera punkt](https://www.observepoint.com/product#plugin) (taggvisningsprogram) | [HttpWatch](https://www.httpwatch.com/) | [Observera punkt](https://www.observepoint.com/product#plugin) (taggvisningsprogram) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Verktyg för Chrome Developer](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Manipuleringsdata](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE] Adobe ger INTE support för eller felsökning av eventuella problem som du kan råka ut för med dessa paketskärmar. Mer information om hur du får hjälp finns på paketskärmens ursprungliga webbplats.

## NS_BINDING_ABORTED i svarskoder

Det här felet inträffar eftersom bildbegäran för länkspårning är utformad för att webbläsaren ska kunna fortsätta till nästa sida innan den väntar på ett svar från Adobes datainsamlingsservrar.

Adobes svar på bildbegäran är helt enkelt en tom 1x1-genomskinlig bild som inte är relevant för sidans innehåll. Om du ser ett linjeobjekt på din paketskärm från Adobe, antingen med ett **[!UICONTROL 200 OK]** svar eller ett **[!UICONTROL NS_BINDING_ABORTED]** svar, har data nått våra servrar. Sidan behöver inte vänta längre.

Packet Monitor som är integrerade som plugin-program ser sällan det fullständiga svaret. De brukar se begäran som avbruten eftersom det fullständiga svaret inte togs emot. Dessa övervakare skiljer dessutom sällan åt mellan om det var begäran eller svaret som avbröts. En fristående paketövervakare har vanligtvis mer detaljerade meddelanden och rapporterar statusen mer korrekt. En användare kan till exempel få ett meddelande i *Charles* som säger&quot;Klienten stängde anslutningen innan hela svaret tas emot&quot;. Detta innebär att data nådde våra servrar, bara webbläsaren gick vidare till nästa sida innan pixeln 1x1 togs emot.

Om en extern paketfragmenterare rapporterar att datainsamlingsbegäran har avbrutits, i stället för att svara, är detta en orsak till oro. Adobe [!DNL Customer Care] kan hjälpa till vid felsökning.
