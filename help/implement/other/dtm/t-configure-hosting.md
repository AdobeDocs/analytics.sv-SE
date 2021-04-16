---
description: Du kan distribuera dynamisk tagghantering med ett eller flera av de tillgängliga värdalternativen.
keywords: Analysimplementering;implementeringsmetod;dynamisk tagghantering;dtm;hosting;hosting options;akamai;self hosting;self hosting;ftp delivery;ftp hosting;library download
title: Konfigurera värdalternativ
topic-fix: Developer and implementation
uuid: 04268f2d-e76f-4fe4-8fcc-f0db3a016502
exl-id: cef5205e-bb21-4d8d-862b-33dc800e1118
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 1%

---

# Konfigurera värdalternativ

Du kan distribuera [!UICONTROL Dynamic Tag Management] med ett eller flera av de tillgängliga värdalternativen.

[!UICONTROL Dynamic Tag Management] innehåller ett antal alternativ för att hantera de JavaScript-filer som behövs.

Mer information om värdtjänster finns i [Bädda in kod och värdalternativ](https://docs.adobe.com/content/help/en/dtm/using/client-side/client-side-information.html) i [!UICONTROL Dynamic Tag Management] produktdokumentation.

Välj ett värdalternativ på fliken Bädda in.

<table id="table_229298207DB64838B6F2477DFFAE073F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Värdalternativ </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Implementering </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Akamai </p> </td> 
   <td colname="col2"> <p> Det enklaste värdalternativet att implementera. </p> <p>Globalt distribuerat leveransnätverk. </p> <p>Lägger till ytterligare infrastrukturberoenden från tredje part (DNS-sökning, Akamai-tillgänglighet). </p> <p>Mer detaljerad information finns i <a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/deployment.html#concept_722B01555D0441ACBB052BC34DC5B67D"> Akamai</a> i produktdokumentationen för Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_EF148EF091A645B3962B084963B3C0B0"> 
     <li id="li_7ECE0C331EEE4907A563D581DF1DFEFE">Dynamic Tag Management genererar anpassade JavaScript-bibliotek. </li> 
     <li id="li_8E2C858290EF4665B2F45ACAFA121CB3">Dynamic Tag Management exporterar de anpassade JavaScript-biblioteken till Akamai. </li> 
     <li id="li_CE88B10B6E844A56BBB8C575A9363BA9">Målwebbplatsen refererar till Akamai-värdbaserade bibliotek för dynamisk tagghantering direkt på sidnivå. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Självvärdande: FTP-leverans </td> 
   <td colname="col2"> <p>En <span class="term"> push</span>-metod, där Dynamic Tag Management exporterar anpassade JavaScript-bibliotek direkt till webbinnehållsserverns värd via FTP-protokollet. </p> <p>Den här lösningen kräver att en FTP-server och autentiseringsuppgifter är tillgängliga på webbinnehållsservern för att kunna publicera ändringar i de anpassade biblioteken för dynamisk tagghantering. </p> <p>Mer detaljerad information finns i <a href="https://docs.adobe.com/help/en/dtm/using/client-side/deployment.html#task_A7B37CB2C89941A4A4D1F9AF06FC493D"> FTP</a> i produktdokumentationen för Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_60348F9C991D4F2B9457006B0F98C834"> 
     <li id="li_24A141C3C7074BF9897C022A22CAE78C">Dynamic Tag Management genererar anpassade JavaScript-bibliotek. </li> 
     <li id="li_E1E0843060F7447E853EA416A0B033BE">Dynamic Tag Management exporterar de anpassade JavaScript-biblioteken till värdservern via FTP. </li> 
     <li id="li_EAF5D2ABD03B4911A0CFA464AD8791CE">Målwebbplatsen refererar lokalt till de anpassade biblioteken för dynamisk tagghantering. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Självvärdande: Bibliotekshämtning </td> 
   <td colname="col2"> <p>En <span class="term"> pull</span>-metod, där programmet exporterar anpassade JavaScript-bibliotek
     <!-- to Amazon S3-->. Där kan biblioteken nås via en serverprocess. </p> <p>Dessutom är biblioteken tillgängliga via webbnedladdning direkt från gränssnittet för dynamisk tagghantering. </p> <p>Lösningen kräver antingen manuell hämtning och publicering av Dynamic Tag Management-biblioteken eller skapande av en automatiserad process som hämtar biblioteken från Akamai till webbinnehållsservern. </p> <p>Det här arbetssättet tar mest tid att skapa, men är också det säkraste och mest flexibla alternativet. </p> <p>Om du vill kontrollera om det finns referenser till den senaste versionen av biblioteksfilen använder du kommandot </p> <p>Mer information finns i<a href="https://docs.adobe.com/content/help/en/dtm/using/client-side/deployment.html#task_B7A42F3B1D3E4B71B0BADD17C181F22A"> Library Download</a> i produktdokumentationen för Dynamic Tag Management. </p> </td> 
   <td colname="col3"> 
    <ol id="ol_F40B721306FE473496BD657262DFD585"> 
     <li id="li_4EA4D6B555CE4E9CA476C7550C18C061">Dynamic Tag Management genererar anpassade JavaScript-bibliotek. </li> 
     <li id="li_BA40EBD7AD1546F29D8A209034D06477">Dynamic Tag Management exporterar de anpassade JavaScript-biblioteken till Akamai. </li> 
     <li id="li_E107E69E386A40F3B067F9991C2979AF">Anpassade bibliotek för dynamisk tagghantering flyttas manuellt eller via programmering till webbinnehållsservern. </li> 
     <li id="li_0809038453B544168A20CE09D7E5AC59">Målwebbplatsen refererar lokalt till de anpassade biblioteken för dynamisk tagghantering. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

Du kan använda flera värdalternativ. Du kan till exempel lagra dina mellanlagrade filer med Akamai, men vara värd för din produktionsplats. Observera att varje värdtyp har sin egen inbäddningskod, och bara en inbäddningskod kan läggas till på en sida.
