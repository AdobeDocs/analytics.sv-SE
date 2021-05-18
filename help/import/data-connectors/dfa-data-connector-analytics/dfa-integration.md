---
description: 'När du konfigurerar DFA-integrering utförs följande uppgifter '
keywords: DFA
title: DFA-integrering
feature: Data Connectors
uuid: 972a9d62-24fd-4463-a34c-5ec0b926e81e
exl-id: 27eb7789-30a5-4f4a-8b23-06e3625996ec
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '2592'
ht-degree: 0%

---

# DFA-integrering{#dfa-integration}

När du konfigurerar DFA-integreringen ingår följande uppgifter:

## Konfigurera DFA-integrering{#configure-the-dfa-integration}

Gå igenom DFA Data Connectors Integration.

Konfigurationssidorna ger en översikt över integreringen, tillsammans med praktiska länkar för mer information. Det finns både Adobe- och DoubleClick-avgifter för den här integreringen. Kontakta en säljare för båda organisationerna och se till att du förstår avgiftsstrukturen.

1. Logga in på [!DNL Adobe Analytics].
1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data connectors]**.

   ![](assets/data_connectors.png)

1. Leta reda på **[!UICONTROL DoubleClick DFA]** och klicka sedan på **[!UICONTROL Add New]**.

   ![Stegresultat](assets/wizard-01.png)

   På varje sida i integreringsguiden anger du den information som krävs och klickar sedan på **[!UICONTROL Next]**. I följande tabell förklaras den information du behöver för att slutföra integreringen med guiden.

<table id="table_8F6F7F304C36431DA5FD6E5D54F60FC0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Guiden Sidnummer </th> 
   <th colname="col2" class="entry"> Fält </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Integrationsnamn </td> 
   <td colname="col3"> Det integrationsnamn som Genesis visas i rapportsvitens lista över aktiv integrering. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> E-postadress för integrering </td> 
   <td colname="col3"> E-postadressen som tar emot alla meddelanden som rör den här integreringen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Användarnamn </td> 
   <td colname="col3"> DFA API-användarnamnet som ska användas med den här integreringen. Om du vill aktivera en användare för API-inloggning kontrollerar du API-attributet i DFA-gränssnittet. När du har aktiverat API-inloggning visas ett lösenordsfält som anger ett lösenord för användaren. Lösenordet anges tillsammans med användarnamnet i guiden för att autentisera. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Lösenord </td> 
   <td colname="col3"> DFA API-lösenordet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Annonsörs-ID </td> 
   <td colname="col3"> <p>DFA-annonserings-ID eller överordnat Floodlight Configuration ID. Data Connectors använder det här ID:t för att identifiera DFA Advertiser för att spåra (version 1.5 av integreringen). Det här Advertiser-ID:t används inte i version 2.0 av integreringen - det överordnade konfigurations-ID:t för Floodlight kommer att slås upp och användas. Se instruktionerna på skärmen </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> DFA-annonsvariabel </td> 
   <td colname="col3"> Den Analytics-eVar som tar emot DFA-kampanjattribut, visningar och klickdata. Vanligtvis är det här eVar för spårningskod ( <span class="varname"> s.campaign </span>), men du kan välja vilken eVar som helst. Data Connectors lägger även till följande DFA-relaterade klassificeringar i den valda eVar: <p><b>Kampanjer</b>: En samling annonser som betjänas av flera webbplatser med vanliga meddelanden. </p> <p><b>Platsnamn</b>: Webbplatsen där annonsen tjänstgjordes. </p> <p><b>Annonsnamn</b>: Annonsnamnet, enligt definition i ditt DFA-konto. </p> <p><b>Platsplaceringsnamn</b>: Webbplatsen och sidan där annonsen fanns. </p> <p><b>Leveransverktyg</b>: Dubbelklicka för annonsörer. </p> <p><b>Kanal</b>: Banderollannons </p> <p><b>Kostnadsstruktur</b>: CPM, CPC eller Fixed, baserat på annonsens kostnadsstruktur. </p> <p><b>Kreativt namn</b>: Namnet på den som är kopplad till ett annons-/placerings-/kreativt ID. </p> <p><b>DFA &gt; SearchCenter Deduplicering</b>: Anger att DFA ska placera värden i SearchCenter-variabler när DFA-klickningar eller Vyer sker.  </a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Impressions </td> 
   <td colname="col3"> Den anpassade händelse som tar emot DFA-komprimeringsmåttdata. Impressions anger hur många gånger annonsen betjänades. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Klickningar </td> 
   <td colname="col3"> Välj den anpassade händelse som tar emot DFA-klickningsdata. Klickningar anger antalet gånger besökarna klickat på annonsen enligt DFA:s omdirigering. Klickmåttet korrelerar med analysens klickningsmått. <p>Obs!  DFA Click and Analytics Click-through kanske inte matchar exakt på grund av skillnader i hur data samlas in.  </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Direktvariabel </td> 
   <td colname="col3"> <p>Analytics-eVar som tar emot DFA-vydata. Med variabeln Visa-genom kan du se hur genomsiktningen påverkar konverteringsgraden på din webbplats. </p> <p>Data Connectors lägger till samma DFA-relaterade klassificeringar i den här eVar som i DFA Ad Variable (se ovan). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Tid sedan senaste vy (variabel för hela tidsintervall för visning) </td> 
   <td colname="col3"> Analytics-eVar som tar emot DFA-tidsdata sedan senaste vy. Tid sedan senaste vy visar hur lång tid som har gått sedan den senaste annonsvyn. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Visa-Över </td> 
   <td colname="col3"> Den anpassade händelse som tar emot DFA-vyvärden. Använd händelsen Visa-Över med vyvariabeln för att se vilka kampanjer som inte påverkade en direkt klickfrekvens, men som kan ha spelat en roll när det gäller att köra trafik till webbplatsen vid ett senare tillfälle. <p>Dataanslutningar byter namn på den valda anpassade händelsen till "Visa genomslag". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> DFA-frågefel </td> 
   <td colname="col3"> (Valfritt) Den Analytics-eVar som tar emot eventuella rapporterade felmeddelandekoder för DFA-frågor. Möjliga DFA-meddelandekoder är: 
    <ul id="ul_85FC7FB19F7F4ADF83ABCA6DDB44CE19"> 
     <li id="li_0A3181DED5A149588A0D3F1584E2FE8B"><b>nc</b>: Ingen DoubleClick-cookie. </li> 
     <li id="li_D397AA73AD5E4086A18B87F271E4EC14"><b>oo</b>: Användaren har avanmält sig. </li> 
     <li id="li_5AC1D0C8049340B4AD857D88E275CBD6"><b>nh</b>: Ingen kampanjhistorik. </li> 
     <li id="li_73A8C5E905C54E2BB531A1FCDBC6AA1A"><b>qe</b>: Frågefel (timeout, server ned osv.) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Timeout-händelse </td> 
   <td colname="col3"> <p>Räknarhändelsen för analys som ökar varje gång timern <span class="varname"> s.maxDelay </span> förfaller, och inget svar togs emot från DFA-servrarna. Använd den här händelsen om du vill konfigurera variabeln <span class="varname"> s.maxDelay </span> Tuning s.maxDelay </a>.) </p> </td> 
  </tr> 
 </tbody> 
</table>

## Webbplatsuppdateringar för DFA-integrering{#web-site-updates-for-the-dfa-integration}

När Genesis har konfigurerat din Analytics-rapportsserie för DFA-integrering måste du göra följande för att konfigurera din webbplats och DFA-miljö så att den stöder integreringen:

### Verifiera cookie-utrymme på domänen{#verify-cookie-space-on-the-domain}

Integreringen av Data Connectors för DFA kräver att du anger en cookie på sidans domän.

Även om detta är sällsynt har vissa domäner nått maximal cookie-kapacitet för vissa webbläsare. Om du vill undvika att en besökares surfupplevelse på din webbplats påverkas, bör du rådfråga ditt nätverks-, utvecklings- eller konstruktionsgrupp för att kontrollera att det inte påverkar användarupplevelsen om du lägger till en annan cookie i domänen för de sidor som används för DFA-integreringen. Du måste också ange ett namn för cookien.

### Uppdatera DFA-frågesträngsparameter{#update-your-dfa-query-string-parameter}

Om du redan har spårat annonskampanjer med Adobe Analytics innan DFA-integreringen är det möjligt att alla kampanjer (e-post, sökning eller banderoll) använder samma frågesträngsparameter för att identifiera det refererande kampanj-ID:t på landningssidan.

För att förstå när ni ska begära genomskinlighets- och klickningsdata från DFA-data för era DFA-annonskampanjer måste Data Connectors identifiera när en besökare har klickat på en DFA-kampanjannons. För att detta ska vara möjligt måste du lägga till en differentierad frågesträngsparameter i DFA Ad-kampanjens startsid-URL så att Data Connectors kan skilja mellan DFA Ad-kampanjsidor och andra annonskampanjsidor som du kan ha på din webbplats. `dfa_overrideParam` i JavaScript-plugin-programmet som används för DFA.

>[!CAUTION]
>
>Även om Campaign-variabeln kan användas för andra kampanjer ska du inte använda den för DFA-kampanjer. Om du ställer in Campaign-variabeln på en DFA-kampanjstartsida kan Adobe inte knyta visningar och klickningar till DFA-kampanjklickningar. Vid varje besök kontrollerar Adobe-samlingsservrar DFA-servrar för en tidigare klicknings- eller genomsiktsprocess. Därför bör du bara inkludera DFA-pluginkoden på vanliga landningssidor för att undvika onödiga omdirigeringar som kan göra sidinläsningen långsammare, särskilt för användare med långsammare Internet-anslutningar.

## Uppdatera din webbplats kod för datainsamling{#update-your-web-site-s-data-collection-code}

Integreringen av DFA med Genesis utnyttjar DFA Floodlight Configuration ID (dfa_SPOTID), vilket förbättrar rapportens enhetlighet mellan DFA och Adobe datainsamlingssystemet.

>[!NOTE]
>
>Termen Spotlight ändrades till Floodlight i en nyligen släppt version av Google DFA. JavaScript-parametern `dfa_SPOTID` namngavs baserat på Spotlight-terminologin, men används för båda versionerna.

Om du vill aktivera DFA-integreringen på din webbplats måste du uppdatera din JavaScript-kod för datainsamling genom att lägga till följande:

* Integrera modul för DFA
* Tillägg till din samlingskod

### Integrera modul för DFA {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

DFA-integreringen utnyttjar Adobe Experience Cloud Integrate Module, som lägger till funktioner i JavaScript-koden för datainsamling ( `s_code.js`). Integrate-modulen ingår i ZIP-filen när du hämtar AppMeasurement for Javascript-koden från Code Manager. Kontakta din Adobe-konsult endast om du behöver mer hjälp med att hitta den.

Infoga integrate Module-koden i `Modules`-avsnittet i webbplatsens `s_code.js`-fil.

### Tillägg till din samlingskod {#section-8f98c727f1ba414fb8b4f02d696b8791}

Baserat på dina val när du aktiverar DFA-integreringen i Integreringsguiden, genererar och skickar Data Connectors ett anpassat tillägg till din JavaScript-kod för datainsamling. Infoga den här koden i huvudavsnittet av filen `s_code.js` (inte i funktionen `doPlugins` eller någon annan funktion).

Den exempelkod som visas nedan är endast avsedd som illustration. använd den kod som har skickats till dig via e-post när du har slutfört integreringsguiden för Data Connectors.

Samlingskoden består av följande komponenter:

* DFA-integrationsinställningar
* Insticksprogram som krävs för integrering

**DFA-integrationsinställningar**

```
/************************** DFA VARIABLES **************************/ 
var dfaConfig = { 
   CSID:              "1234567", 
   SPOTID:            "29876543", 
   tEvar:             "eVar17", 
   errorEvar:         "eVar59", 
   timeoutEvent:      "event76", 
   requestURL:         "http://fls.doubleclick.net/ 
json?spot=[SPOTID]&src=[CSID]&var=[VAR]&host=integrate.112.2o7.net%2 
Fdfa_echo%3Fvar%3D[VAR]%26AQE%3D1%26A2S%3D1&ord=[RAND]", 
 
   maxDelay:          "1500", 
   visitCookie:       "s_dfa", 
   clickThroughParam: "CID", 
   searchCenterParam: "s_kwcid", 
   newRsidsProp:      undefined 
}; 
/************************ END DFA Variables ************************/ 
```

DFA Integrate Settings Block anger variabler som krävs för DFA-integreringen. Värdena för var och en av dessa variabler kommer från följande källor:

**CSID**: Klientsidans ID. Skapas av DFA när du har slutfört integreringsguiden. Data Connectors fyller i variabeln i förväg med ditt DFA CS ID och skickar även det här värdet i e-postmeddelandet om konfiguration när du har slutfört Integreringsguiden. Den här variabeln krävs inte om avancerad annonsvisning är aktiverat på ditt konto.

**SPOTID**: Konfiguration av flytande ljus (kallades tidigare Spotlight-ID). Data Connectors förifyller den här variabeln med ditt DFA Floodlight Configuration ID, baserat på den DFA-kontoinformation som du angav i Integreringsguiden.

**Evar**: Överföringsvariabel. Data Connectors fyller i variabeln i förväg med det Analytics-variabelnamn som du angav för View-Through-variabeln i Integreringsguiden. Ändra inte det här värdet utan noggrann samordning med Adobe Engineering eller Engineering Services.

**errorEvar**: Felvariabel. Datakopplingar fyller i den här variabeln i förväg med det analysvariabelnamn du angav för DFA-frågefelsvariabeln i Integreringsguiden.

**timeoutEvent**: Timeout-händelse. Datakopplingar fyller i den här variabeln i förväg med det analysvariabelnamn som du angav för Timeout-händelsevariabeln i Integreringsguiden.

**requestURL**: DFA-fjärrvärden som ska fråga efter annonsinformation. Ändra inte det här värdet om inte Adobe anger det.

**maxDelay**: Anger hur lång tid JavaScript-datainsamlingskoden väntar på ett svar från DFA-servern för Floodlight, i millisekunder. Adobe rekommenderar att du experimenterar med det här värdet för att hitta det optimala värdet baserat på webbplatsens trafik. Om du till exempel ökar det här värdet samlas mer DFA-data in, men det ökar risken för att grundläggande besöksdata förloras om besökaren lämnar platsen under fördröjningsperioden. Om du minskar det här värdet minskar risken för dataförlust, men det kan minska mängden DFA-data som skickas med träffdata för Adobe.

**besökCookie**: Namnet på den cookie som används för att begränsa DFA-anrop till en gång per besök.

**clickThroughParam**: En frågesträng, som vanligtvis finns på alla annonser, som meddelar integreringsmodulen att ett klick har inträffat. Förekomsten av den här parametern i frågesträngen gör att begäran görs till DFA Floodlight-servrar oavsett om besökaren redan har frågats under de senaste 30 minuterna.

**newRsidsProp**: (Valfritt) Mappas till en oanvänd Traffic-egenskapsvariabel. DFA-integreringen samlar in och lagrar det här värdet i besöks-cookien för att identifiera de rapportsviter som samlar in data för en viss besökare. Den här egenskapen behövs bara för anpassade implementeringar med Adobe Engineering-tjänster.

**Insticksprogram som krävs för integrering**

Collection Code innehåller ytterligare plugin-program som förbättrar DFA-integreringen:

* Begränsar DFA-frågor till en gång per besök
* Ger flexibilitet för cookie-namn. Även om de flesta organisationer använder s_dfa kan du använda valfritt giltigt cookie-namn för DFA-integreringen.
* Eliminerar onödiga omdirigeringar. Eftersom genomskinliga data samlas in i realtid kan Adobe-samlingsservrar och DFA utbyta data på varje sidvy. Plugin-programmet blockerar dessa datautbyten när informationen inte behövs.

>[!CAUTION]
>
>En av de mekanismer som plugin-programmet använder för att eliminera onödiga DFA-frågor är en domänbaserad cookie för besök. En integreringsrapportsserie som spänner över flera domäner blåser upp klicknings- och genomskinlighetsdata när besökare korsar domäner efter en DFA-påverkad genomgång eller klickning.

## Bekräfta en lyckad DFA-integrering{#confirming-a-successful-dfa-integration}

När du har gjort alla nödvändiga webbplatsuppdateringar kan du använda ett nätverkstrafikvisningsprogram, som Charles*, Chrome Developer Tools eller Firebug*, för att bekräfta att DFA kommunicerar med Adobe-samlingsservrar.

När du har distribuerat den DFA-aktiverade `s_code.js`-filen kan du använda nätverkstrafikvisningsprogrammet för att visa begäranden mellan DFA- och Adobe datainsamlingsservrar och leta efter följande:

* En begäran till DFA:s `fls.doubleclick.net/json`-tjänst. Tjänsten kan svara på olika sätt beroende på vilken version av DFA du använder. Med DFA-integrering version 1.5:

   * En HTTP 302-omdirigering till [!DNL ad.doubleclick.net]. Detta skickar en plats: -taggen i svaret som innehåller information om annonsbesökaren.
   * Den här platstaggen leder till en omdirigering till [!DNL integrate.112.2o7.net/dfa_echo]. Den här tjänsten översätter informationen om annonsbesökaren till en JSON-kodad sträng (JavaScript Object Notati on). Dessa data returneras med ett 200 OK HTTP-svar.

* Med DFA-integrering version 2.0 (Advanced Ad Serving enabled):

   * [!DNL fls.doubleclick.net] kommer att svara direkt med 200 OK.

I båda fallen kommer en lyckad begäran att resultera i en begäran till datainsamlingsservrarna i Adobe som innehåller parametern vX, där X är eVar View-Through. Det här parametervärdet har följande format: DFA-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX. Strängen innehåller data om den senaste klickningen och det senaste intrycket för den aktuella besökaren.

## Justerar s.maxDelay{#tuning-s-maxdelay}

För att uppnå en lyckad DFA-implementering måste du optimera s.maxDelay för just din plats.

I allmänhet innebär beslutet att höja eller sänka *`s.maxDelay`* en kompromiss mellan att få fram fler DFA-besöksuppgifter och att samla in besöksdata från Adobe äventyras. Om du ökar *`s.maxDelay`* hämtas fler DFA-besöksdata, men (placeras för högt) kan det äventyra insamlingen av besöksdata från Adobe. Genom att minska s.maxDelay säkerställs att besöksdata från Adobe samlas in, men DFA-besöksdata kan gå förlorade.

*`s.maxDelay`* inkapslar mer än bara tiden i nätverkskommunikation för att kontakta DFA, det innebär också webbläsarfördröjningar att utlösa och utvärderar det JavaScript som kommunikationen baseras på. Detta beror på att modulen Integrera börjar med timern *`s.maxDelay`* efter att HTML-elementet har infogats i DOM som hämtar data från DFA-servern för Floodlight. Hur lång tid det tar för webbläsaren att initiera HTTP-begäran baserat på det nya HTML-elementet varierar beroende på andra bilder eller JavaScript-filer som läses in samtidigt, hastigheten på besökarens dator och specifika webbläsarimplementeringar. Dessutom måste JavaScript utvärderas av webbläsaren när JSON-data hämtas från DFA Floodlight-servern. Detta styrs helt och hållet av webbläsaren och kan fördröjas om det finns stora mängder JavaScript-kod som körs samtidigt eller många asynkrona JavaScript-begäranden.

Med detta i åtanke måste *`s.maxDelay`* ställas in beroende på landningssidans komplexitet plus mängden nätverksfördröjning med DFA. På vissa webbplatser är det möjligt att minska komplexiteten genom att utlösa samlingskoden för Adobe tidigt under sidinläsningen, så att det inte är så mycket som sker i webbläsaren när Floodlight-servern begärs.

Timeout-variabeln är absolut nödvändig vid justering av *`s.maxDelay`*, eftersom den ökas varje gång s.maxDelay-timeout uppnås. När vi beslutar om vi ska öka eller minska *`s.maxDelay`* rekommenderar vi att du följer den här processen:

1. Samla in flera dagar med data med *`s.maxDelay`* inställt på ett visst värde.
1. Kör en [!DNL Daily Unique Visitors Report] för tidsintervallet.
1. Kör [!DNL Timeout Event Report] för att kontrollera antalet timeout som inträffar. Kom ihåg att en timeout bara samlas in en gång per besökare.

Nu när vi har bilderna i handen, beräknar

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

Observera att timeoutprocenten faktiskt tar hänsyn till alla besökare på webbplatsen. En del av besökarna hade inte varit bundna till DFA alls, och timeoutvärdet är missvisande. För att förbättra den här beräkningen kan en annan analys endast beakta unika besökare på sidor med `clickThroughParam`-uppsättningen (till exempel `?CID=1`). Detta ger större precision.

Om tidsgränsen är mycket låg bör du minska *`s.maxDelay`*. Om den är mycket hög ökar du *`s.maxDelay`*. När du minskar *`s.maxDelay`* måste du köra [!DNL Timeout Report] igen för att vara säker på att tidsgränserna inte har ökat dramatiskt. När du ökar *`s.maxDelay`* måste du köra en [!DNL Page Views Report] för att vara säker på att sidvyerna inte faller bort på grund av förlorade data. Varje gång *`s.maxDelay`* ändras bör du observera data under flera dagar för att vara säker på att data representerar en trend och inte bara en daglig fluktuation.

Den optimala inställningen för *`s.maxDelay`* är den punkt där timeout-procentandelen minimeras medan sidvyer inte tas bort.

Timeout förväntas minska när du går över till version 2.0 av integreringen på grund av elimineringen av 302 omdirigeringar. Inledande fynd hos betatestare har visat en konsekvent minskning av tidsgränsen, vilket innebär att fler DFA-data samlas in
