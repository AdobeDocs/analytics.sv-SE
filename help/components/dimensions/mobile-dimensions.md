---
title: Dimensioner för mobilsökning
description: Dimensioner baserade på enhetens IP-adress och användaragent.
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 0%

---

# Dimensioner för mobilsökning

*Den här sidan refererar till egenskaperna för mobila enheter som använder webbplatsen. Se [Dimensioner för mobil livscykel](lifecycle-dimensions.md) eller [Mätvärden för mobillivscykel](../metrics/lifecycle-metrics.md) för spårning i en mobilapp.*

Mobilsökning [dimensioner](overview.md) ge insikter om egenskaperna hos de mobila enheter som besöker er webbplats. Dessa egenskaper baseras på användaragenten och IP-adressen för träffen. Du kan använda de här dimensionerna för att förstå vilka funktioner en mobil enhet stöder.

## Fyll i dessa dimensioner med data

Dessa dimensioner hänvisar till uppslagsregler som är interna för Adobe.

* För [!UICONTROL Mobile Carrier] dimension, Adobe partners med [Digital Element](https://www.digitalelement.com/) använda NetAcuity för att upprätthålla sökningar mellan IP-adress och mobiloperatör.
* För alla andra mobildimensioner samarbetar Adobe med [DeviceAtlas](https://deviceatlas.com/) för att upprätthålla sökningar mellan användaragenten och respektive mobildimension.

Vilka dimensioner som är tillgängliga beror på implementeringstyp:

* När det gäller implementeringar av AppMeasurement fungerar de här måtten som standard.
* Aktivera för Web SDK-implementeringar [!UICONTROL Geo Lookup] (för mobiloperatör) eller [!UICONTROL Device Lookup] (för alla andra dimensioner) när [konfigurera ett datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Beskrivningar av mobildimension

>[!NOTE]
>
>Dimensioner med etiketter `"None"` är icke-mobila enheter. Om du vill ha en rapport som bara innehåller mobila enheter drar du dimensionen &quot;Mobil enhet&quot; till segmentområdet på arbetsytan.

* **[!UICONTROL Mobile audio support]**: Avgör vilka filformat som enheten kan spela upp. Exempelvärden innehåller `"MP3"`, `"AAC"`och `"MIDI Monophonic"`. Värden i den här dimensionen utesluter inte varandra. En enda träff kan attribuera till flera dimensionsobjekt.
* **[!UICONTROL Mobile carrier]**: Telefonen eller dataprovidern för enheten. Exempelvärden innehåller `"Reliance Jio"`, `"Airtel"`, `"Vodafone"`och `"Verizon"`.
* **[!UICONTROL Mobile color depth]**: Den mobila enhetens färgdjup i bitar.
* **[!UICONTROL Mobile cookie support]**: Avgör om den mobila enheten stöder cookies. Den här dimensionen anger inte om webbläsaren accepterar cookies. Dimensionerna innehåller `"Supported"`, `"Not supported"`och `"Unknown"`.
* **[!UICONTROL Mobile device]**: Den mobila enhet som besökaren använder.
* **[!UICONTROL Mobile device number]**: Avgör om den mobila enhetens nummer skickas. Denna dimension tillhandahåller inte själva mobilnumret. Dimensionerna innehåller `"Supported"`, `"Not supported"`och `"Unknown"`.
* **[!UICONTROL Mobile device type]**: Typ av mobil enhet. Exempelvärden innehåller `"Mobile phone"`, `"Tablet"`, `"Media player"`och `"Gaming console"`.
* **[!UICONTROL Mobile DRM]**: Den typ av DRM som den mobila enheten stöder. Exempelvärden innehåller `"DRM OMA forward"`, `"DRM OMA combined delivery"`och `"DRM OMA separate delivery"`.
* **[!UICONTROL Mobile image support]**: De typer av bilder som den mobila enheten stöder. Exempelvärden innehåller `"PNG"`, `"JPEG"`och `"GIF 87"`. Värden i den här dimensionen utesluter inte varandra. En enda träff kan attribuera till flera dimensionsobjekt.
* **[!UICONTROL Mobile information services]**: De typer av nyhetstjänster som stöds av enheten. Moderna enheter rapporterar vanligtvis inte den här informationen.
* **[!UICONTROL Mobile Java VM]**: De versioner av Java som enheten stöder.
* **[!UICONTROL Mobile mail decoration]**: Bestämmer om enheten stöder [Decome](https://en.wikipedia.org/wiki/Decome), en funktion som tidigare var populär på japanska enheter.
* **[!UICONTROL Mobile manufacturer]**: Klassificerar mobila enheter efter tillverkare. Exempelvärden innehåller `"Apple"`, `"Samsung"`, `"Huawei"`och `"Motorola"`.
* **[!UICONTROL Mobile max bookmark length]**: Det maximala antalet byte som mobilenheten stöder i bokmärkta URL:er. Moderna enheter har vanligtvis ingen gräns.
* **[!UICONTROL Mobile max browser URL length]**: Maximalt antal byte som den mobila enheten stöder i URL:er. Moderna enheter har vanligtvis ingen gräns.
* **[!UICONTROL Mobile max email length]**: Maximalt antal byte som mobilenheten stöder i ett e-postmeddelande. Moderna enheter har vanligtvis ingen gräns.
* **[!UICONTROL Mobile net protocols]**: De typer av protokoll som enheten stöder vid åtkomst till Internet. Exempelvärden innehåller `"EDGE"`, `"GPRS"`, `"UMTS"`och `"LTE"`.
* **[!UICONTROL Mobile operating system (deprecated)]**: Använd [Operativsystem](operating-systems.md) i stället.
* **[!UICONTROL Mobile push to talk]**: Avgör om enheten har stöd för PTT (Push to talk), vilket gör att den mobila enheten kan uppträda som en tvåvägsradio. Moderna enheter rapporterar vanligtvis inte den här funktionen.
* **[!UICONTROL Mobile screen height]**: Skärmens höjd i pixlar. Rapport alltid för iPhone `"480"` på grund av att det inte gick att avgöra vilken version av iPhone som användes. Se avsnittet nedan om hur du avgör vilken version iPhone-enheten har.
* **[!UICONTROL Mobile screen size]**: Den mobila enhetens fullständiga dimensioner i pixlar. Den rapporterade skärmstorleken anger inte enhetens orientering. Oavsett skärmorientering har varje enhet en fast skärmupplösning i rapporten. Storleken baseras på forskning som avgör vilken orientering som är mer sannolik. Du kan se storlekar som `"768x1024"` och `"1024x768"` i samma rapport där varje storlek representerar en eller flera olika enheter.
* **[!UICONTROL Mobile screen width]**: Skärmens bredd i pixlar.
* **[!UICONTROL Mobile video support]**: De videofilformat och kodekar som den mobila enheten stöder. Det finns flera dimensionsobjekt för olika kodekar av MP4- och 3GPP-filer. Värden i den här dimensionen utesluter inte varandra. En enda träff kan attribuera till flera dimensionsobjekt.

## Separera iPhone efter modell eller version

Mobilenheter rapporterar sin firmware-version i användaragentsträngen, inte i enhetsversionen. En aktuell iPhone innehåller till exempel en identisk användaragent som den senaste generationen iPhone om de finns i samma firmware-version. Eftersom det inte går att avgöra vilken version av iPhone som används med JavaScript hör alla iPhone till samma hink. Mobildimensionerna är strikt baserade på sökningar som refererar till användaragent, vilket resulterar i att alla iPhone-telefoner visar en mobilskärmsstorlek på `320 x 480`.

Om du vill samla in en version av iPhone finns det två sätt att kringgå den här begränsningen.

* **Använda Mobile SDK**: Mobile SDK innehåller dimensioner som visar enhetsversionen för rapportering. Den här metoden passar bättre för mobilappar än för webbplatser.
* **Använd andra variabler som är tillgängliga via JavaScript**: Vissa variabler, till exempel `screen.height` och `screen.width`, kan användas för att härleda en enhetsversion. Du kan till exempel använda följande kodfragment på din plats:

  ```js
  if (navigator.userAgent.indexOf('iPhone') > -1) {
    s.eVarXX = screen.width + "x" + screen.height;
    }
  ```

  Detta kodblock identifierar först om enheten är en iPhone. I så fall använder koden JavaScript för att hämta skärmupplösningen till en eVar. Med den här metoden kan du identifiera enhetsversionen om skärmupplösningarna är unika.
