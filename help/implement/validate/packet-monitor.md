---
title: Paketanalysatorer
description: Med paketanalyserare kan du visa data som skickas av implementeringen till datainsamlingsservrar i Adobe.
keywords: paketsniffer, http-status, 200, 302, charles
feature: Validation
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 0%

---

# Paketanalysatorer

Med paketanalyserare kan du visa data som skickas av implementeringen till datainsamlingsservrar i Adobe.

På samma sätt som för Adobe Experience Cloud felsökare visar en paketskärm vilka dataparametrar som skickas i en bildbegäran, men paketskärmar ger ytterligare funktioner:

* Visa bildbegäran för anpassad länkspårning
* Visa bildbegäranden med andra implementeringsmetoder än JavaScript, till exempel hårdkodade bildbegäranden eller [!DNL Appmeasurement]

Om du vill visa Analytics-begäranden filtrerar du utgående begäranden med&quot;b/ss&quot;.

I mycket sällsynta fall rapporterar felsökaren en bildbegäran, men ingen begäran gör den till Adobe [!DNL Analytics] bearbetningsservrar. Att använda en paketbildskärm är ett bra sätt att vara helt säker på att en viss bildbegäran kan utlösas.

Även om Adobe inte har någon officiell paketövervakare finns det många sådana på internet. Här följer några exempel på paketskärmar som andra tycker är användbara.

>[!TIP]
>
>Dessa listor är inte avsedda att vara heltäckande, utan snarare information om ofta använda bildskärmar.

| Firefox | Internet Explorer | Krom | Fristående program |
|---|---|---|---|
| [Observera punkt](https://www.observepoint.com/product#plugin) (taggläsare) | [HttpWatch](https://www.httpwatch.com/) | [Observera punkt](https://www.observepoint.com/product#plugin) (taggläsare) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Verktyg för Chrome Developer](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Manipuleringsdata](https://addons.mozilla.org/en-US/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/firebug-lite-for-google-c/ehemiojjcpldeipjhjkepfdaohajpbdo) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>Adobe stöder INTE eller felsöker problem som du upplever med dessa paketskärmar. Om du behöver hjälp kan du få hjälp på paketskärmens ursprungliga webbplats.

## Vanliga statuskoder för HTTP-svar

När AppMeasurementet skickar data till datainsamlingsservrar i Adobe svarar servrarna med en svarsstatuskod.

* **200 OK**: Det vanligaste svaret från datainsamlingsservrar. Bildbegäran togs emot och en genomskinlig bild returnerades.
* **302 HITTADES**: Det finns ett par möjliga skäl till att få detta svar:
   * Den första bildförfrågan från en besökare: En omdirigering sker om en användare besöker webbplatsen för första gången. Den här omdirigeringen är att få en besöks-cookie. Det påverkar inte datainsamlingen.
   * Integrering mellan Comscore och Adobe: Om din organisation använder en Comscore/Analytics-integrering ger varje bildförfrågan alltid ett 302-svar.
* **404 HITTADES INTE**: Detta svar innebär att bildbegäran inte hittades och att data inte skickas till datainsamlingsservrar i Adobe. Det här svaret är också möjligt när hårdkodade bildbegäranden inte är korrekt formaterade. Samarbeta med den person eller det team som implementerade Analytics för att lösa problemet.

## NS_BINDING_ABORTED i svarskoder

Det här meddelandet visas eftersom bildbegäran för länkspårning är utformad för att webbläsaren ska kunna fortsätta till nästa sida innan den väntar på ett svar från Adobe datainsamlingsservrar.

Adobe-svar på bildbegäran är helt enkelt en tom 1x1-genomskinlig bild som inte är relevant för sidans innehåll. Om du ser ett linjeobjekt på paketskärmen från Adobe, antingen med en **[!UICONTROL 200 OK]** eller en **[!UICONTROL NS_BINDING_ABORTED]** har data nått Adobe servrar. Sidan behöver inte vänta längre.

Packet Monitor som är integrerade som plugin-program ser sällan det fullständiga svaret. De brukar se begäran som avbruten eftersom det fullständiga svaret inte togs emot. Dessa övervakare skiljer dessutom sällan åt mellan om det var begäran eller svaret som avbröts. En fristående paketövervakare har vanligtvis mer detaljerade meddelanden och rapporterar statusen mer korrekt. En användare kan till exempel få ett meddelande i *Charles* som säger&quot;Klienten stängde anslutningen innan hela svaret togs emot.&quot; Detta innebär att data nådde våra servrar, bara webbläsaren gick vidare till nästa sida innan pixeln 1x1 togs emot.

Om en extern paketövervakare rapporterar att datainsamlingsbegäran har avbrutits, i stället för att svara, är detta en orsak till oro. Adobe [!DNL Customer Care] kan ge hjälp vid felsökning.
