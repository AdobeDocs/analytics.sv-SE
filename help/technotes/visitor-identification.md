---
description: Adobe använder en cookie för att spåra unika webbläsare/enheter.
keywords: Analytics Implementation
subtopic: Visitors
title: Identifiera unika besökare
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# Identifiera unika besökare

Adobe använder en cookie för att spåra unika webbläsare/enheter.

## Analysbesökarens ID-ordning {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics har flera sätt att identifiera besökare. I följande tabell visas de olika sätt som en besökare kan identifieras på i Analytics (i prioritetsordning):

| Använd order | Frågeparameter (samlingsmetod) | Presentera när |
|---|---|---|
| 1 | vid (s.visitorID) | s.visitorID har angetts |
| 2 | hjälp (s_vi cookie) | Besökaren hade en befintlig s_vi-cookie innan du distribuerade Visitor ID-tjänsten, eller så har du konfigurerat en respitperiod för besökar-ID. |
| 3 | mitten (AMCV_ cookie inställd av tjänsten Experience Cloud Visitor ID) | Besökarens webbläsare accepterar cookies (första part) |
| 4 | fid (fallback cookie) | Besökarens webbläsare accepterar cookies (första part) |
| 5 | IP-adress, användaragent, gateway-IP-adress | Besökarens webbläsare accepterar inte cookies. |

I många scenarier kan du se två eller tre olika ID:n för ett samtal, men i Analytics används det första ID:t som finns i föregående tabell som det officiella besökar-ID:t. Om du till exempel anger ett anpassat besökar-ID (som ingår i frågeparametern&quot;vid&quot;) kommer detta ID att användas före andra ID:n som kan finnas i samma träff.

> [!NOTE] Varje besökar-ID för Analytics är kopplat till en besökarprofil på Adobes servrar. Besökarprofiler tas bort efter minst 13 månaders inaktivitet, oavsett om en cookie-fil för besöks-ID har gått ut eller inte.

## Anpassat besökar-ID

Du kan implementera en anpassad metod för att identifiera besökare genom att ange variabeln s.visitorID.

Ett anpassat besökar-ID kan användas på webbplatser där du har ett unikt sätt att identifiera besökare. Ett exempel på detta är ett ID som genereras när en användare loggar in på webbplatsen med ett användarnamn och lösenord.

Om du har möjlighet att härleda och hantera [!UICONTROL visitor IDs] användarnas resurser kan du använda följande metoder för att ange ID:t:

| Metod | Beskrivning |
|---|---|
| [s.visitorID](../implement/vars/config-vars/visitorid.md) -variabel | Om JavaScript används i webbläsaren, eller om du använder något annat AppMeasurement-bibliotek, kan du ange besökar-ID i en datainsamlingsvariabel. |
| Frågesträngsparameter i bildbegäran | Detta gör att du kan skicka filen [!UICONTROL visitor ID] till Adobe via [!UICONTROL vid query string] parametern för en hårdkodad bildbegäran. |
| API för datainfogning | På enheter som använder trådlösa protokoll som inte accepterar JavaScript kan du skicka ett XML-inlägg som innehåller `<visitorid/>` XML-elementet till Adobes samlingsservrar från dina servrar. |
| Skriv om URL och VISTA | Vissa distributionsarkitekturer har stöd för att använda URL-omskrivning för att behålla sessionstillstånd när en cookie inte kan anges. I sådana fall kan Adobes tekniska tjänster implementera en [!DNL VISTA] regel som söker efter sessionsvärdet i sidans URL och sedan formatera och placera i [!UICONTROL visid] värdena. |
>[!CAUTION]
>**Anpassade besökar-ID:n måste vara tillräckligt detaljerade/unika **: En ogiltig implementering av anpassade besökar-ID:n kan leda till felaktiga data och dålig rapportprestanda. Om det anpassade besökar-ID:t inte är unikt eller tillräckligt detaljerat, eller felaktigt har angetts till ett gemensamt standardvärde som strängen &quot;NULL&quot; eller &quot;0&quot;, kommer träffar från många olika besökare att ses av Adobe Analytics som en enda besökare. Den här situationen resulterar i felaktiga data, där antalet besökare är för lågt och segmenten inte fungerar som de ska för besökaren. Ett otillräckligt detaljerat anpassat besökar-ID förhindrar också att data sprids korrekt över noder i rapportklustret för Analytics. I den här situationen blir en nod överbelastad och kan inte behandla begäranden i tid. Till slut kommer all rapportering för rapportsviten att misslyckas.<br>Dåligt implementerade anpassade besökar-ID:n kanske inte omedelbart påverkar rapportens prestanda eftersom analyser ofta kan hantera flera månaders obalanserade data. Med tiden kan emellertid ett dåligt implementerat anpassat besökar-ID bli problematiskt, så att Analytics måste inaktivera bearbetning för de berörda rapportsviterna.</br><br>Implementerare bör följa riktlinjen att ett enda anpassat besökar-ID aldrig ska tillgodoräknas för mer än 1 % av trafiken i rapportsviten. Även om riktlinjen på 1 % räcker för de flesta rapportsviter kan den faktiska gränsen som kan påverka rapportens prestanda vara lägre än 1 % för mycket stora rapportsviter.</br>

## Analysbesökar-ID

När en användare besöker din webbplats anges en beständig cookie av Adobes webbserver genom att den inkluderas i HTTP-svaret till webbläsaren. Den här cookien har angetts för den angivna datainsamlingsdomänen.

När en begäran skickas till Adobe datainsamlingsserver kontrolleras rubriken för besökar-ID-cookie ( `s_vi`). Om denna cookie finns i begäran används den för att identifiera besökaren. Om cookien inte finns i begäran genererar servern ett unikt besökar-ID, anger den som en cookie i HTTP-svarshuvudet och skickar tillbaka den med begäran. Cookien lagras i webbläsaren och skickas tillbaka till datainsamlingsservern vid efterföljande besök på webbplatsen, vilket gör att besökaren kan identifieras vid olika besök.

### Cookies och CNAME-poster från tredje part {#section_61BA46E131004BB2B75929C1E1C93139}

Vissa webbläsare, till exempel Apple Safari, lagrar inte längre cookies som har angetts i HTTP-huvudet från domäner som inte matchar domänen för den aktuella webbplatsen (detta är en cookie som används i en tredjepartskontext eller en cookie från tredje part). Om du till exempel är på `mysite.com` och datainsamlingsservern är `mysite.omtrdc.net`det kan den cookie som returneras i HTTP-huvudet från `mysite.omtrdc.net` avvisas av webbläsaren.

För att undvika detta har många kunder implementerat CNAME-poster för sina datainsamlingsservrar som en del av en [förstapartscookie-implementering](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/). Om en CNAME-post har konfigurerats för att mappa ett värdnamn på kundens domän till datainsamlingsservern (till exempel mappning `metrics.mysite.com` till `mysite.omtrdc.net`), lagras besökar-ID-cookien eftersom datainsamlingsdomänen nu matchar webbplatsens domän. Detta ökar sannolikheten för att besökar-ID-cookien ska lagras, men medför en viss belastning när du behöver konfigurera CNAME-poster och underhålla SSL-certifikat för datainsamlingsservrar.

### Cookies på mobila enheter {#section_7D05AE259E024F73A95C48BD1E419851}

När mobilenheter spåras med hjälp av cookies finns det vissa inställningar som du kan använda för att ändra hur mätningen utförs. Cookie-standardlivslängden är 5 år, men du kan använda CL-frågeparametervariabeln ( `s.cookieLifetime`) för att ändra detta standardvärde. Om du vill ange cookie-plats för namnimplementeringar använder du CDP-frågesträngen `s.cookieDomainPeriods`. Standardvärdet är 2 om inget värde anges. och standardplatsen är domain.com. För implementeringar som inte använder CNAME är platsen för besökar-ID-cookie på domänen 207.net.

## Identitetstjänst

Identitetstjänsten ersätter den gamla ID-mekanismen för Analytics-besökare och krävs av [!UICONTROL Heartbeat] videomätning, Analytics for Target och framtida bastjänster och integreringar i Experience Cloud.

Mer information om den här tjänsten finns i [Identitetstjänsten](https://marketing.adobe.com/resources/help/en_US/mcvid/) .

## Identifiera mobila enheter

De flesta mobila enheter kan hantera webbläsarcookies. Om enheter inte accepterar cookies används dock en annan metod för att unikt identifiera trådlösa enheter.

Adobe har identifierat ett antal rubriker för HTTP-prenumerations-ID som unikt identifierar de flesta mobila enheter. Dessa rubriker innehåller ofta enhetens telefonnummer (eller en hashad version av numret) eller andra identifierare. De flesta aktuella enheter har en eller flera av de huvuden som unikt identifierar enheten, och alla Adobe datainsamlingsservrar använder automatiskt dessa huvuden i stället för ett besökar-ID.

I en typisk bildbegäran gör &quot;1&quot; i sökvägen ( `/b/ss/rsid/1`) att Adobe-servrar returnerar en gif-bild och försöker ange en beständig [!UICONTROL visitor ID] cookie ( `AMCV_` eller `s_vi`). Om enheten identifieras som en mobil enhet som baseras på HTTP-rubriker skickas dock &quot;5&quot; i stället för &quot;1&quot;, vilket anger att en wbmp-formatbild ska returneras och att vår lista över godkända trådlösa rubriker (inte en cookie) ska användas för att identifiera enheten.

I följande tabell visas ordningen för de ID-metoder som används baserat på det returnerade bildtypsvärdet (&#39;1&#39; eller &#39;5&#39;) i sökvägen:

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Inställning </th> 
   <th colname="col2" class="entry"> ID-metodordning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>Standard: </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">Anpassat besökar-ID </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">Rubrik för prenumerations-ID </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> IP-adress-AnvändareAgent-Gateway IP-adress </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>Enheten identifierades som en trådlös enhet eller <code> /5/</code> skickades manuellt i bildbegäran: </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">Anpassat besökar-ID </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">Rubrik för prenumerations-ID </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">IP-adress-användare-agent-gateway IP-adress </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Du kan också skicka en &quot;1&quot; eller &quot;5&quot; i manuella bildbegäranden, men tänk på att dessa koder utesluter varandra, och därför påverkas inte cookie när den stöds om du alltid skickar &quot;5&quot;. Du kan använda en egen mekanism för att avgöra om en enhet stöder cookies, och i så fall skicka ett &quot;1&quot; i bilden i stället för &quot;5&quot;. Noggrannheten i denna situation är begränsad till antalet mobila enheter som stöder cookies.

### Rubriker för prenumerations-ID {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

Metoden för prenumerations-ID är vanligtvis mer tillförlitlig än en cookie för användaridentifiering på grund av problem med borttagning av cookies, accepterande av cookies och hantering av gateway-cookies.

Du kan förbättra ändringen av identifieringen av en besökare genom att läggas till i den vita listan för den operatör som era mobilbesökare använder. Om du vill få åtkomst till transportörens besökar-ID kontaktar du transportören för att lägga till din domän i deras vitlista. Om du är med i en transportörs lista har du även tillgång till prenumerant-ID-rubriker som du annars kanske inte kan komma åt.

Följande lista med rubriker används för att identifiera trådlösa enheter. Algoritmen för bearbetning av rubriker är att

1. extrahera HTTP-huvudnyckeln (rubrikens namn, till exempel&quot;X-Up-Calling-Line-ID&quot;)
1. rensa bort alla tecken som inte är alfa (A-Z och a-z)
1. konvertera sidhuvudnyckeln till gemener
1. jämför slutet av nyckeln med de i följande tabell för att hitta en matchning:

| Sidhuvud | Typ | Exempel |
|---|---|---|
| callinglineid | ID | X-Up-Calling-Line-ID: 8613802423312 |
| subno | ID | x-up-subno: swm_10448371100_vmag.mycingular.net |
| klientid | ID | Klient-ID: eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid: a2V4Eh21XQH9ECNN |
| klippa | ID | X-Hts_clid: 595961714786 |
| deviceid | ID | rim-device-id: 200522ae |
| vidarebefordra | ID eller IP-adress | X-Forwarded-For: 127.0.0.1 |
| msisdn | ID eller IP-adress | X-Wap-msisdn: 8032618185 |
| klientium | IP-adress | Klient-ip: 10.9.41.2 |
| wapipaddr | IP-adress | X-WAPIPADDR: 10.48.213.162 |
| huaweinasip | IP-adress | x-huawei-NASIP: 211.139.172.70 |
| userip | IP-adress | Användar-IP: 70.214.81.241 |
| ipaddress | IP-adress | X-Nokia-ipaddress: 212.97.227.125 |
| subscriberinfo | IP-adress | X-SUBSCRIBER-INFO: IP=10.103.132.128 |

&quot;callinglineid&quot; matchar till exempel &quot;X-Up-Calling-Line-ID&quot; och &quot;nokia-callinglineid&quot;. Rubriktypen anger vad som ska förväntas i rubriken. Prioritetsordningen för sidhuvuden anges här (om det finns en rubrik för &quot;callinglineid&quot; används den i stället för &quot;subno&quot;).

Du kan använda [dynamiska variabler](../implement/vars/page-vars/dynamic-variables.md) för att extrahera specifika värden från en rubrik.

## Metoder för reserv-ID

Om andra besökar-ID-metoder misslyckas anger Adobe en reservcookie eller använder en kombination av IP-adress och användaragent för att identifiera besökaren.

### Identifieringsmetod för reservbesökare {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement för JavaScript 1.x och JavaScript H.25.3 (släppt i januari 2013) innehåller en ny identifieringsmetod för reservbesökare vars webbläsare blockerar den cookie som anges av Adobes datainsamlingsservrar (kallas `s_vi`). Tidigare identifierades besökare med en kombination av IP-adressen och användaragentsträngen under datainsamlingen om det inte gick att ange en cookie.

Om den här uppdateringen inte är tillgänglig skapas en reservcookie på webbplatsens domän med ett slumpmässigt genererat unikt ID. `s_vi` Denna cookie, med namnet `s_fid`, har en tvåårig förfallotid och används som identifieringsmetod för reservlösningar. Denna ändring bör leda till större noggrannhet i besöks- och besöksantal i situationer där den primära cookien ( `AMCV_` eller `s_vi`) inte kan ställas in.

Totalt antal besök omfattar alla besökare som identifieras av `s_vi` cookien eller genom att använda en reservmetod.

### IP-adress, användaragent, gateway-IP-adress {#section_104819D74C594ECE879144FCC5DEF4BF}

. Om det inte går att ange `AMCV_` eller `s_vi` och `s_fid` cookies identifieras besökarna med en kombination av IP-adress och användaragent.
