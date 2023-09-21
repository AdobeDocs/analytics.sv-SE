---
title: Mobila dimensioner
description: Dimensioner baserade på enhetens IP-adress.
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 0%

---

# Mobila dimensioner

*Den här sidan refererar till egenskaper för mobila enheter som använder webbplatsen. Om du vill spåra enheter i en mobilapp läser du [Implementera analyser för mobila enheter](/help/implement/mobile-device-sdk.md) i Implementeringshandboken.*

Mobil [dimensioner](overview.md) ge insikter om egenskaperna hos de mobila enheter som besöker er webbplats. Du kan använda de här dimensionerna för att förstå vilka funktioner en mobil enhet stöder.

## Fyll i dessa dimensioner med data

Dessa dimensioner hänvisar till uppslagsregler som är interna för Adobe. [!UICONTROL Mobile Carrier] sökningar bestäms av IP-adressen, med hjälp av data från NetAcuity (en Digital Elements-produkt).
Om du använder ett fotobibliotek (till exempel via taggar i Adobe Experience Platform) kommer alla mobildimensioner att fungera utan.

## Beskrivningar av mobildimension

>[!NOTE]
>
>Dimensioner med etiketter `"None"` är icke-mobila enheter. Om du vill ha en rapport som bara innehåller mobila enheter drar du dimensionen &quot;Mobil enhet&quot; till segmentområdet på arbetsytan.

* **Stöd för mobilljud**: Avgör vilka filformat som enheten kan spela upp. Exempelvärden innehåller `"MP3"`, `"AAC"`och `"MIDI Monophonic"`. Värden i den här dimensionen utesluter inte varandra. En enda träff kan attribuera till flera dimensionsobjekt.
* **Mobiloperatör**: Värdena för den här dimensionen fylls i genom att tredjepartsdata (Digital Elements) söks igenom baserat på de IP-adresser som analysdata har hämtat. Exempelvärden innehåller `"Reliance Jio"`, `"Airtel"`, `"Vodafone"`och `"Verizon"`.
* **Mobil färgdjup**: Den mobila enhetens färgdjup i bitar.
* **Stöd för Mobile cookie**: Avgör om den mobila enheten stöder cookies. Den här rapporten anger inte om webbläsaren accepterar cookies. Dimensionerna innehåller `"Supported"`, `"Not supported"`och `"Unknown"`.
* **Mobil enhet**: Den mobila enhet som besökaren använder. **Anteckning**: Digital Elements publicerar regelbundet uppdateringar för att identifiera nya/uppdaterade enheter.
* **Mobilenhetsnummer**: Avgör om den mobila enhetens nummer skickas. Dimensionerna innehåller `"Supported"`, `"Not supported"`och `"Unknown"`.
* **Typ av mobil enhet**: Typ av mobil enhet. Exempelvärden innehåller `"Mobile phone"`, `"Tablet"`, `"Media player"`och `"Gaming console"`.
* **Mobil DRM**: Den typ av DRM som den mobila enheten stöder. Exempelvärden innehåller `"DRM OMA forward"`, `"DRM OMA combined delivery"`och `"DRM OMA separate delivery"`.
* **Stöd för mobilbilder**: De typer av bilder som stöds av en mobil enhet. Exempelvärden innehåller `"PNG"`, `"JPEG"`och `"GIF 87"`. Värden i den här dimensionen utesluter inte varandra. En enda träff kan attribuera till flera dimensionsobjekt.
* **Mobilinformationstjänster**: De typer av nyhetstjänster som stöds av enheten. Senaste enheter rapporterar vanligtvis inte den här informationen.
* **Mobil Java VM**: De versioner av Java som enheten stöder.
* **E-postdekoration för mobiler**: Avgör om enheten stöder Decomail, en funktion som tidigare var populär på japanska enheter.
* **Mobil tillverkare**: Grupperar mobila enheter efter tillverkare. Exempelvärden innehåller `"Apple"`, `"Samsung"`, `"Huawei"`och `"Motorola"`.
* **Maximal bokmärkeslängd för mobil**: Det maximala antalet byte som mobilenheten stöder i bokmärkta URL:er. Nyligen använda enheter har vanligtvis ingen gräns.
* **Högsta URL-längd för mobil webbläsare**: Maximalt antal byte som den mobila enheten stöder i URL:er. Nyligen använda enheter har vanligtvis ingen gräns.
* **Maximal e-postlängd för mobil**: Maximalt antal byte som mobilenheten stöder i ett e-postmeddelande. Nyligen använda enheter har vanligtvis ingen gräns.
* **Mobila nätprotokoll**: De typer av protokoll som enheten stöder vid åtkomst till Internet. Exempelvärden innehåller `"EDGE"`, `"GPRS"`, `"UMTS"`och `"LTE"`.
* **Mobiloperativsystem (borttaget)**: Använd [Operativsystem](operating-systems.md) i stället.
* **Mobilt tryck för att prata**: Avgör om enheten har stöd för PTT (Push to talk), vilket gör att den mobila enheten kan uppträda som en tvåvägsradio. Senaste enheter rapporterar vanligtvis inte den här funktionen.
* **Höjd på mobilskärm**: Skärmens höjd i pixlar. Observera att iPhone alltid rapporterar `"480"` på grund av att det inte gick att avgöra vilken version av iPhone som användes. Se avsnittet nedan om hur du avgör vilken version av iPhone som är enhet.
* **Skärmstorlek för mobiler**: Den mobila enhetens fullständiga dimensioner i pixlar. Den rapporterade skärmstorleken anger inte enhetens orientering. Oavsett skärmorientering har varje enhet en fast skärmupplösning i rapporten. Storleken baseras på forskning som avgör vilken orientering som är mer sannolik. Du kan se storlekar som `"768x1024"` och `"1024x768"` i samma rapport där varje storlek representerar en eller flera olika enheter.
* **Bredd på mobilskärm**: Skärmens bredd i pixlar.
* **Stöd för mobilvideo**: De videofilformat och kodekar som den mobila enheten stöder. Det finns flera dimensionsobjekt för olika kodekar av MP4- och 3GPP-filer. Värden i den här dimensionen utesluter inte varandra. En enda träff kan attribuera till flera dimensionsobjekt.

## Separera iPhone efter modell eller version

Mobilenheter rapporterar sin firmware-version i användaragentsträngen, inte i enhetsversionen. En aktuell iPhone innehåller till exempel en identisk användaragent som den senaste generationen iPhone om de finns i samma firmware-version. Eftersom det inte går att avgöra vilken version av iPhone som används med JavaScript hör alla iPhone till samma hink. Mobildimensionerna baseras strikt på sökningar som refererar till användaragent, så du kommer att upptäcka att alla iPhone rapporterar en mobilskärmsstorlek på `320 x 480`.

Om du vill samla in en version av en iPhone-enhet kan du kringgå den här begränsningen på två sätt.

* **Använda iOS SDK**: Den mobila SDK:n innehåller dimensioner som visar enhetsversionen för rapportering. Den här metoden passar bättre för mobilappar än för webbplatser.
* **Använd andra variabler som är tillgängliga via JavaScript**: Vissa variabler, till exempel `screen.height` och `screen.width`, kan användas för att härleda en enhetsversion. Du kan till exempel använda följande kodfragment på din plats:

  ```js
  if (navigator.userAgent.indexOf('iPhone') > -1) {
    s.eVarXX = screen.width + "x" + screen.height;
    }
  ```

  Detta kodblock identifierar först om enheten är en iPhone. I så fall använder koden JavaScript för att hämta skärmupplösningen till en eVar. Med den här metoden kan du identifiera enhetsversionen om skärmupplösningarna är unika.
