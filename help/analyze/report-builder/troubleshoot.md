---
description: Lär dig hur du kan optimera leveransen till Report Builder och en lista över felmeddelanden som kan visas.
title: Felsökning och bästa praxis för Report Builder
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
feature: Report Builder
role: User, Admin
exl-id: 41a640ce-2316-439b-b3ba-f0bace9af268
source-git-commit: d218d07ec16e981d7e148092b91fbbd5711e840f
workflow-type: tm+mt
source-wordcount: '1403'
ht-degree: 54%

---

# Felsökning och bästa praxis för Report Builder

I den här artikeln beskrivs felsökning och de bästa metoder du kan använda för att optimera Report Builder. Den innehåller även en lista med felmeddelanden som kan visas.

## Report Builder 5.0-användare och 5.1-arbetsböcker {#section_C29898775999453FABB5FB0E098415C8}

Adobe ändrade avgränsaren mellan dimensioner och klassificeringar från ett understreck (_) till ||. Den här ändringen påverkar kompatibiliteten för en Report Builder 5.0-användare som öppnar en Report Builder v5.1-arbetsbok med klassificeringsbegäranden. Varje gång en arbetsbok öppnas från en version som är äldre än v5.1 konverteras alla serialiserade klassificeringsbegäranden till det här formatet.

Detta introducerar ett framåtkompatibilitetsproblem: Om en arbetsbok har konverterats till v5.1 och den delas med en användare i Report Builder v5.0, kan den användaren inte identifiera klassificeringsbegäran (den letar efter&quot;_&quot; men v5.1 serialiserade &quot;||&quot;).

Följande sidoeffekter uppstår när du öppnar en ARB v5.1-arbetsbok med en klassificeringsbegäran:

* När du öppnar arbetsboken visas följande varning: &quot;Den här arbetsboken sparades senast med Report Builder v5.1. Den här versionen innehåller funktioner som är inkompatibla med Report Builder-versionen som är installerad på den här datorn. Vi rekommenderar att du uppgraderar till den senaste versionen av Report Builder innan du uppdaterar den här arbetsboken.&quot;
* Om du högerklickar på en ARB-begäran med klassificering visas inte snabbmenyerna för Report Builder (redigera begäran, lägg till beroende begäran..).
* Om du uppdaterar alla genom att klicka på den tredje knappen eller genom att uppdatera en uppsättning begäranden från Request Manager-formuläret, körs klassificeringsbegäran utan fel. Klassificeringsvärdena skrivs dock inte ut.
* Du kan fortfarande redigera begäran genom att öppna Request Manager och sedan gå från rad till rad tills du når rätt begäran.
* Om du redigerar begäran och låter alla parametrar vara oförändrade och sedan klickar på Slutför skrivs svaret ut korrekt. Om du redigerar begäran löses problemet eftersom parametrarna för svarslayout återserialiseras. Det finns en lösning, men den är tidskrävande.

## Autentiseringsproblem i Report Builder {#section_FD79104DF1414FE2B36591606C963DE6}

Report Builder kräver autentisering för att skapa dataförfrågningar från dina rapportsviter. Ibland kan det vara problem med att logga in på Report Builder beroende på dina inställningar i [!DNL Analytics] eller ditt nätverk.

* **Ogiltigt inloggningsföretag**: Det här felet inträffar oftast när inloggningsföretaget är felaktigt angivet eller om det uppstår nätverksaktivitetsproblem. Gör följande:
   * Kontrollera inloggningsföretagets stavning för att se till att där inte finns skrivfel eller felaktiga blanksteg.
   * Logga in på Analytics med samma inloggningsföretag för att säkerställa att det är korrekt. Om du inte kan logga in med dessa uppgifter kontaktar du någon av organisationens administratörer för att få rätt inloggningsföretag.
* **Brandvägg**: Report Builder använder portarna 80 och 443. Se till att portarna tillåts via organisationens brandvägg. Se även Adobes interna IP-adresser för ytterligare undantag för brandväggar.

## Recommendations för optimering av begäranden {#section_33EF919255BF46CD97105D8ACB43573F}

Följande faktorer kan göra begäran mer komplex och leda till långsammare behandling.

* **Faktorer som kan göra leveranser långsammare**: För många bokmärken, instrumentpaneler och arbetsböcker från Report Builder har schemalagts inom några timmar. Överväg också att alltför många Report Builder-arbetsböcker har schemalagts ungefär samtidigt. När detta inträffar blir rapport-API-kön eftersläpad.
* **Faktorer som kan göra arbetsbokens körningsmiljö långsammare**: Betydande ökning av klassificeringar eller ökning av datumintervallet för begäran över tid.
* **Orsaker som orsakar leveransfel för arbetsböcker**: Komplexa Excel-formler i en arbetsbok, särskilt sådana som innehåller datum och tid.
* **Celler som returnerar 0s (inga värden)**: En apostrof eller ett enkelt citattecken i Excel-kalkylbladsnamnet gör att Report Builder inte returnerar några värden. (Detta är en Microsoft Excel-begränsning.)
* **Prestanda för enskild begäran**: Bearbetningshastigheten kan påverkas av följande inställningar:

  | Inställning | Snabbare prestanda | Långsammare prestanda |
  |--- |--- |--- |
  | Uppdelningar och uppdelningsordning | Få | Många |
  |  | Exempel: Om du delar upp efter A-Z ska antalet objekt för A alltid vara mindre än antalet objekt för Z. Om det är motsatsen kan begärandetiden öka avsevärt. |
  | Datumintervall | Litet intervall | Stort intervall |
  | Filtrering | Specifik filtrering | Mest populära filtrering |
  | Kornighet | Sammanställd | Varje timme<ul><li>Dagligen</li><li>Veckovis</li><li>Månadsvis</li><li>Kvartalsvis</li><li>Årlig</li></ul> |
  | Antal poster | Liten datauppsättning | Stor datauppsättning |

* **Schemaläggningstid**: Starkare schemaläggning över en 24-timmarsperiod (se tabellen nedan). Befintliga bokmärken, instrumentpaneler och arbetsböcker i Report Builder som är schemalagda att avslutas kan orsaka förseningar. Schemalägg större och mer komplexa begäranden på morgonen för att möjliggöra manuella körningar och uppdateringar under arbetsdagen.

  | Schemaläggningstid | 01:00 - 02:00 | 02:00 - 07:00 | 07:00 - 18:00. | 18:00 - Midnatt |
  |--- |--- |--- |--- |--- |
  | Report Builder-användning | Tyst | Mycket upptagen | Användning på klientsidan.<br>Många användare som uppdaterar lokalt och begär att få skicka direkt.<br>Kontrollera också om API-kön är rensad när en tidsgräns för schemalagda arbetsböcker överskrids. | Inte upptagen |

* **Timeout**: Alla schemalagda rapporter inträffar efter fyra timmar. Systemet försöker schemalägga ytterligare tre gånger, vilket kan leda till ett fel. (I allmänhet tar det längre tid att köra datauppsättningen ju större den är.) Detta märks i [!DNL Analytics] rapportering och i Report Builder:

## Exempel på felmeddelandebeskrivningar {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

I det här avsnittet finns ett exempel på en lista med felmeddelanden som kan visas när du använder Report Builder.

>[!NOTE]
>
>Detta är ett exempel på felmeddelanden och inte en fullständig lista. Kontakta administratören om du vill ha mer information om hur du löser fel.

* **Den här funktionen kan bara användas på en öppen arbetsbok.**: Om inga arbetsböcker (kalkylbladsdokument) är öppna i Excel och du klickar på en av ikonerna i verktygsfältet Report Builder visas det här meddelandet. Dessutom inaktiveras verktygsfältet tills du öppnar ett kalkylblad. Du kan dock klicka på ikonen för onlinehjälp medan verktygsfältet fortfarande är aktiverat utan att detta fel uppstår.
* **Du måste först avsluta [!UICONTROL Request Wizard] innan du aktiverar [!UICONTROL Request Manager].**: När [!UICONTROL Request Manager] och [!UICONTROL Request Wizard] är länkade funktionellt går det inte att börja arbeta med [!UICONTROL Request Manager] innan åtgärder som har vidtagits i [!UICONTROL Request Wizard] har slutförts eller avbrutits.
* **Det finns ingen begäran associerad med det här intervallet.**: Det här felmeddelandet visas om du klickar på knappen [!UICONTROL From Sheet] i [!UICONTROL Request Manager] när en cell i kalkylbladet inte innehåller några begäranden. Om du vill identifiera vilka celler i kalkylbladet som innehåller begäranden klickar du på de enskilda begärandena som visas i tabellen i [!UICONTROL Request Manager]. Om en begäran är kopplad till celler, visas cellerna som markerade när begäran är markerad i tabellen.
* **Det markerade intervallet är inte giltigt. Välj ett annat intervall.**: Om en cell i kalkylbladet är markerad och redan har en begäran mappad till den, inträffar det här felet. Du kan antingen ta bort den begäran som är kopplad till cellerna eller välja ett annat cellintervall att mappa. När du vill ta bort celler är det viktigt att leta reda på celler som innehåller begäranden och ta bort begäran innan cellerna tas bort (rader eller kolumner tas bort).
* **Avsluta Excel-cellen med fokus innan du använder den här funktionen.**: Om du är i *redigeringsläge* i en Excel-cell och klickar på någon av Report Builder-ikonerna visas det här felmeddelandet. Redigeringsläget i en Excel-cell innebär att cellen är markerad och att markören visas inuti cellen. Du är också i redigeringsläge i en Excel-cell när du skriver direkt i fältet [!UICONTROL Formula] eller i [!UICONTROL Name Box] överst i Excel.
* **Det markerade intervallet överlappar en annan begärans intervall. Ändra ditt val.**: Om du redan har mappat en uppsättning celler till kalkylbladet visas det här felet.
* **Reparationer av arbetsboken (Borttagna poster: Formel från /xl/calcChain.xml del)**: Ibland skadas formler i en arbetsbok när den sparas eller överförs. När filen öppnas försöker Excel köra formlerna och misslyckas. Du kan lösa det här problemet genom att ta bort `calcChain.xml` från kalkylbladet och tvinga Excel att uppdatera sina formelberäkningar.
   1. Byt namn på arbetsbokens filtillägg från `.xlsx` till `.zip`.
   2. Zippa upp innehållet och öppna mappen `/xl/`.
   3. Ta bort `calcChain.xml`.
   4. Zippa upp innehållet igen och ändra filnamnstillägget tillbaka till `.xlsx`.
   5. Öppna arbetsboken i Excel och uppdatera alla förfrågningar från Report Builder.
* **Excel-celler som är associerade med indatafilter eller utdataområde kan ha tagits bort**: Report Builder använder Excel-namn för att bifoga dataförfrågningar till celler. Om du tar bort Excel-namn från Names Manager visas det här felet. Begäranden kan inte återställas om Excel-namn tas bort. Om arbetsboken har schemalagts kan du antingen hämta en kopia från schemaläggningshanteraren eller öppna tidigare levererade kopior av arbetsboken.
