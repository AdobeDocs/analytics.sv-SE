---
title: Mobila dimensioner
description: Dimensioner baserade på enhetens IP-adress.
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 0%

---

# Mobila dimensioner

*Den här sidan refererar till egenskaper för mobila enheter som använder webbplatsen. Om du vill spåra enheter i en mobilapp läser du [Implementera analys för mobila enheter](/help/implement/mobile-device-sdk.md) i Implementera användarhandboken.*

Mobila dimensioner ger insikter om egenskaperna hos de mobila enheter som besöker er webbplats. Du kan använda de här dimensionerna för att förstå vilka funktioner en mobil enhet har stöd för.

## Fyll i dessa dimensioner med data

Dessa dimensioner hänvisar till uppslagsregler som är interna för Adobe. [!UICONTROL Mobile Carrier] sökningar bestäms av IP-adressen, med hjälp av data från NetAcuity (en Digital Elements-produkt).
Om du använder ett AppMeasurement-bibliotek (till exempel via taggar i Adobe Experience Platform) kommer alla mobildimensioner att gå ur lådan.

## Beskrivningar av mobildimension

>[!NOTE]
>
>Dimensioner som är märkta `"None"` är inte mobila enheter. Om du vill ha en rapport som bara innehåller mobila enheter drar du dimensionen &quot;Mobil enhet&quot; till segmentområdet på arbetsytan.

* **Stöd** för mobilljud: Bestämmer vilka filformat som enheten kan spela upp. Exempelvärden är `"MP3"`, `"AAC"` och `"MIDI Monophonic"`. Värdena i denna dimension utesluter inte varandra. en enda träff kan attribuera till flera dimensionsobjekt.
* **Mobiloperatör**: Värdena för den här dimensionen fylls i genom att tredjepartsdata (Digital Elements) söks igenom baserat på de IP-adresser som analysdata har hämtat. Exempelvärden är `"Reliance Jio"`, `"Airtel"`, `"Vodafone"` och `"Verizon"`.
* **Mobil färgdjup**: Färgdjupet för den mobila enheten, i bitar.
* **Stöd** för Mobile cookie: Avgör om den mobila enheten stöder cookies. Den här rapporten anger inte om webbläsaren accepterar cookies. Bland Dimensionerna finns `"Supported"`, `"Not supported"` och `"Unknown"`.
* **Mobil enhet**: Den mobila enhet som besökaren använder.
* **Mobilenhetsnummer**: Avgör om den mobila enheten skickar numret. Bland Dimensionerna finns `"Supported"`, `"Not supported"` och `"Unknown"`.
* **Typ** av mobil enhet: Typ av mobil enhet. Exempelvärden är `"Mobile phone"`, `"Tablet"`, `"Media player"` och `"Gaming console"`.
* **Mobil DRM**: Den typ av DRM som den mobila enheten stöder. Exempelvärden är `"DRM OMA forward"`, `"DRM OMA combined delivery"` och `"DRM OMA separate delivery"`.
* **Stöd** för mobilbilder: De typer av bilder som stöds av en mobil enhet. Exempelvärden är `"PNG"`, `"JPEG"` och `"GIF 87"`. Värdena i denna dimension utesluter inte varandra. en enda träff kan attribuera till flera dimensionsobjekt.
* **Mobilinformationstjänster**: De typer av nyhetstjänster som stöds av enheten. Senaste enheter rapporterar vanligtvis inte den här informationen.
* **Mobil Java VM**: De versioner av Java som enheten stöder.
* **Dekoration** av mobilpost: Avgör om enheten stöder Decomail, en funktion som tidigare var populär på japanska enheter.
* **Mobiltillverkare**: Grupperar mobila enheter efter tillverkare. Exempelvärden är `"Apple"`, `"Samsung"`, `"Huawei"` och `"Motorola"`.
* **Högsta bokmärkeslängd för** mobiler: Det maximala antalet byte som mobilenheten stöder i bokmärkta URL:er. Nyligen använda enheter har vanligtvis ingen gräns.
* **Högsta URL-längd för** mobil webbläsare: Det maximala antalet byte som den mobila enheten stöder i URL:er. Nyligen använda enheter har vanligtvis ingen gräns.
* **Maximal e-postlängd** för mobilen: Det maximala antalet byte som mobilenheten stöder i ett e-postmeddelande. Nyligen använda enheter har vanligtvis ingen gräns.
* **Protokoll** för mobilnät: De typer av protokoll som enheten stöder vid åtkomst till Internet. Exempelvärden är `"EDGE"`, `"GPRS"`, `"UMTS"` och `"LTE"`.
* **Mobiloperativsystem (borttaget)**: Använd  [operativsystemdimensionen ](operating-systems.md) i stället.
* **Mobilt push för att prata**: Avgör om enheten stöder PTT (Push to talk), vilket gör att den mobila enheten kan uppträda som en tvåvägsradio. Senaste enheter rapporterar vanligtvis inte den här funktionen.
* **Höjd på** mobilskärm: Skärmens höjd i pixlar. Observera att iPhone alltid rapporterar `"480"` på grund av att det inte går att fastställa iPhone-enhetens version. Se avsnittet nedan om hur du avgör iPhone-enhetens version.
* **Skärmstorlek** för mobiler: Den mobila enhetens fullständiga dimensioner i pixlar. Den rapporterade skärmstorleken anger inte enhetens orientering. Oavsett skärmorientering har varje enhet en fast skärmupplösning i rapporten. Storleken baseras på forskning som avgör vilken orientering som är mer sannolik. Du kan se storlekar som `"768x1024"` och `"1024x768"` i samma rapport där varje storlek representerar en eller flera olika enheter.
* **Bredd** på mobilskärm: Skärmens bredd i pixlar.
* **Stöd** för mobilvideo: De videofilformat och kodekar som den mobila enheten stöder. Det finns flera dimensionsobjekt för olika kodekar av MP4- och 3GPP-filer. Värdena i denna dimension utesluter inte varandra. en enda träff kan attribuera till flera dimensionsobjekt.

## Separera iPhone efter modell eller version

Mobilenheter rapporterar sin firmware-version i användaragentsträngen, inte i enhetsversionen. En aktuell iPhone innehåller till exempel en identisk användaragent som den senaste generationen iPhone om de finns i samma version av den inbyggda programvaran. Eftersom det inte går att avgöra vilken iPhone-version som används med JavaScript, hör alla iPhone till samma hink. Mobildimensionerna baseras strikt på sökningar som refererar till användaragent, så du kommer att upptäcka att alla iPhone rapporterar en mobilskärmstorlek på `320 x 480`.

Om du vill samla in iPhone-enhetsversionen finns det två sätt som du kan kringgå den här begränsningen på.

* **Använd iOS SDK**: Den mobila SDK:n innehåller dimensioner som visar enhetsversionen för rapportering. Den här metoden är mer idealisk för mobilappar än för webbplatser.
* **Använd andra variabler som är tillgängliga via JavaScript**: Vissa variabler, till exempel  `screen.height` och  `screen.width`, kan användas för att härleda enhetsversionen. Du kan till exempel använda följande kodfragment på din plats:

   ```js
   if (navigator.userAgent.indexOf('iPhone') > -1) {
     s.eVarXX = screen.width + "x" + screen.height;
     }
   ```

   Detta kodblock identifierar först om enheten är en iPhone. I så fall använder koden JavaScript för att hämta skärmupplösningen till en eVar. Med den här metoden kan du identifiera enhetsversionen om skärmupplösningarna är unika.
