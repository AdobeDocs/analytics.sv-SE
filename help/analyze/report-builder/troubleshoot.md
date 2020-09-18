---
description: Olika sätt som du kan optimera leveransen av Report Builder och en lista över felmeddelanden som ibland kan förekomma.
title: Felsökning och bästa praxis för Report Builder
topic: Report builder
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 86%

---


# Felsökning och bästa praxis för Report Builder

Olika sätt som du kan optimera leveransen av Report Builder och en lista över felmeddelanden som ibland kan förekomma.

## Report Builder 5.0-användare och öppna 5.1-arbetsböcker {#section_C29898775999453FABB5FB0E098415C8}

Adobe ändrade avgränsaren mellan dimensioner och klassificeringar från ett understreck (_) till ||. Den här ändringen påverkar kompatibiliteten för en Report Builder 5.0-användare som öppnar en Report Builder v5.1-arbetsbok med klassificeringsbegäranden. Varje gång en arbetsbok öppnas från en version som är äldre än v5.1 konverteras alla serialiserade klassificeringsbegäranden till det här formatet.

Detta introducerar ett framåtkompatibilitetsproblem: Om en arbetsbok har konverterats till v5.1 och den delas med en användare i Report Builder v5.0, kan den användaren inte identifiera klassificeringsbegäran (den letar efter&quot;_&quot; men v5.1 serialiserade &quot;||&quot;).

Följande sidoeffekter uppstår när du öppnar en ARB v5.1-arbetsbok med en klassificeringsbegäran:

* När du öppnar arbetsboken visas följande varning: &quot;Den här arbetsboken sparades senast med Report Builder v5.1. Den här versionen innehåller funktioner som är inkompatibla med Report Builder-versionen som är installerad på den här datorn. Vi rekommenderar att du uppgraderar till den senaste versionen av Report Builder innan du uppdaterar den här arbetsboken.&quot;
* Om du högerklickar på en ARB-begäran med klassificering visas inte snabbmenyerna för Report Builder (redigera begäran, lägg till beroende begäran..).
* Om du uppdaterar alla genom att klicka på den tredje knappen eller genom att uppdatera en uppsättning begäranden från Request Manager-formuläret, körs klassificeringsbegäran utan fel. Klassificeringsvärdena skrivs dock inte ut.
* Du kan fortfarande redigera begäran genom att öppna Request Manager och sedan gå från rad till rad tills du når rätt begäran.
* Om du redigerar begäran och låter alla parametrar vara oförändrade och sedan klickar på Slutför skrivs svaret ut korrekt. Om du redigerar begäran löses problemet eftersom parametrarna för svarslayout återserialiseras. Det finns en lösning, men den är tidskrävande.

## Autentiseringsproblem i Report Builder {#section_FD79104DF1414FE2B36591606C963DE6}

Report Builder kräver autentisering för att skapa dataförfrågningar från dina rapportsviter. Ibland kan det vara problem med att logga in på Report Builder beroende på dina inställningar i [!DNL Analytics] eller nätverket.

* **Ogiltigt inloggningsföretag**: Det här felet inträffar oftast när inloggningsföretaget är felaktigt angivet eller om det finns nätverksaktivitetsproblem. Gör följande:
   * Kontrollera inloggningsföretagets stavning för att se till att där inte finns skrivfel eller felaktiga blanksteg.
   * Logga in på Analytics med samma inloggningsföretag för att säkerställa att det är korrekt. Om du inte kan logga in med dessa uppgifter kontaktar du någon av organisationens administratörer för att få rätt inloggningsföretag.
* **Brandvägg**: Report Builder använder portarna 80 och 443. Se till att portarna tillåts via organisationens brandvägg. Se även Adobes interna IP-adresser för ytterligare undantag för brandväggar.

## Rekommendationer för optimering av begäranden {#section_33EF919255BF46CD97105D8ACB43573F}

Följande faktorer kan göra begäran mer komplex och leda till långsammare bearbetning.

* **Faktorer som kan göra leveranser** långsammare: För många bokmärken, instrumentpaneler och arbetsböcker från Report Builder har schemalagts inom några timmar. Överväg också att alltför många Report Builder-arbetsböcker har schemalagts ungefär samtidigt. När detta inträffar blir rapport-API-kön eftersläpad.
* **Faktorer som kan göra arbetsbokens körtid långsammare**: Betydande ökning av klassificeringar eller ökning av datumintervallet för begäran över tid.
* **Orsaker till att arbetsboken inte kan levereras**: Komplexa Excel-formler i en arbetsbok, särskilt sådana som innehåller datum och tid.
* **Celler som returnerar 0s (inga värden)**: En apostrof eller ett enkelt citattecken i Excel-kalkylbladsnamnet gör att rapportbyggaren inte returnerar några värden. (Detta är en Microsoft Excel-begränsning.)
* **Prestanda för enskilda begäranden**: Bearbetningshastigheten kan påverkas av följande inställningar:

   | Inställning | Snabbare prestanda | Långsammare prestanda |
   |--- |--- |--- |
   | Uppdelningar och uppdelningsordning | Få | Många |
   |  | Exempel: Om du delar upp efter A-Z ska antalet objekt för A alltid vara mindre än antalet objekt för Z. Om det är motsatsen kan begärandetiden öka avsevärt. |
   | Datumintervall | Litet intervall | Stort intervall |
   | Filtrering | Specifik filtrering | Mest populära filtrering |
   | Kornighet | Sammanställd | Varje timme<ul><li>Dagligen</li><li>Veckovis</li><li>Månadsvis</li><li>Kvartalsvis</li><li>Årlig</li></ul> |
   | Antal poster | Liten datauppsättning | Stor datauppsättning |

* **Schemaläggningstid**: Sprid schemaläggning över en 24-timmarsperiod (se tabellen nedan). Befintliga bokmärken, kontrollpaneler och Report Builder-arbetsböcker som är schemalagda nära varandra kan orsaka förseningar. Schemalägg större och mer komplexa begäranden på morgonen för att möjliggöra manuella körningar och uppdateringar under arbetsdagen.

   | Schemaläggningstid | 01:00 - 02:00 | 02:00 - 07:00 | 07:00 - 18:00. | 18:00 - Midnatt |
   |--- |--- |--- |--- |--- |
   | Report Builder-användning | Tyst | Mycket upptagen | Användning på klientsidan.<br>Många användare som uppdaterar lokalt och begär att få skicka direkt.<br>Kontrollera också om API-kön är rensad när en tidsgräns för schemalagda arbetsböcker överskrids. | Inte upptagen |

* **Tidsgränser**: Tidsgräns för alla schemalagda rapporter träder i kraft efter fyra timmar. Systemet försöker schemalägga ytterligare tre gånger, vilket kan leda till ett fel. (I allmänhet tar det längre tid att köra datauppsättningen ju större den är.) Detta märks i [!DNL Analytics] rapportering och i Report Builder:

## Felmeddelandebeskrivningar {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

En lista med felmeddelanden som ibland kan visas när du använder Report Builder.

>[!NOTE]
>
>Detta är bara ett urval av felmeddelanden och inte en fullständig lista. Kontakta administratören om du vill ha mer information om hur du löser fel.

* **Den här funktionen kan bara användas på en öppen arbetsbok.**: Om inga arbetsböcker (kalkylbladsdokument) är öppna i Excel, och du klickar på en av ikonerna i verktygsfältet för Report Builder, visas det här meddelandet. Dessutom inaktiveras verktygsfältet tills du öppnar ett kalkylblad. Du kan dock klicka på ikonen för onlinehjälp medan verktygsfältet fortfarande är aktiverat utan att detta fel uppstår.
* **Du måste först avsluta [!UICONTROL Request Wizard] innan du aktiverar [!UICONTROL Request Manager].**: Eftersom [!UICONTROL Request Manager] och [!UICONTROL Request Wizard] är länkade till varandra kan du inte börja arbeta med [!UICONTROL Request Manager] innan du slutför eller avbryter åtgärder som vidtas i [!UICONTROL Request Wizard].
* **Det finns ingen begäran som är associerad med det här intervallet.**: Det här felmeddelandet visas om du klickar på knappen [!UICONTROL From Sheet] i [!UICONTROL Request Manager] när en cell i kalkylbladet inte innehåller några begäranden. Om du vill identifiera vilka celler i kalkylbladet som innehåller begäranden klickar du på de enskilda begärandena som visas i tabellen i [!UICONTROL Request Manager]. Om en begäran är kopplad till celler, visas cellerna som markerade när begäran är markerad i tabellen.
* **Det markerade intervallet är inte giltigt. Välj ett annat intervall.**: Om en cell i kalkylbladet är markerad och redan har en begäran mappad till sig, inträffar det här felet. Du kan antingen ta bort den begäran som är kopplad till cellerna eller välja ett annat cellintervall att mappa. När du vill ta bort celler är det viktigt att leta reda på celler som innehåller begäranden och ta bort begäran innan cellerna tas bort (rader eller kolumner tas bort).
* **Avsluta Excel-cellen med fokus innan du använder den här funktionen.**: Om du är i *redigeringsläge* i en Excel-cell och klickar på någon av Report Builder-ikonerna visas det här felmeddelandet. Redigeringsläget i en Excel-cell innebär att cellen är markerad och att markören visas inuti cellen. Du är också i redigeringsläge i en Excel-cell när du skriver direkt i fältet [!UICONTROL Formula] eller i [!UICONTROL Name Box] överst i Excel.
* **Det markerade intervallet överlappar en annan begärans intervall. Ändra ditt val.**: Om du redan har kopplat en uppsättning celler till kalkylbladet visas det här felet.
* **Reparationer av arbetsboken (Borttagna poster: Formel från /xl/calcChain.xml del)**: Ibland kan formler i en arbetsbok bli skadade när du sparar eller överför den. När filen öppnas försöker Excel köra formlerna och misslyckas. Du kan lösa problemet genom att ta bort `calcChain.xml` från kalkylbladet och tvinga Excel att uppdatera sina formelberäkningar.
   1. Byt namn på arbetsbokens filtillägg från `.xlsx` till `.zip`.
   2. Zippa upp innehållet och öppna `/xl/` mappen.
   3. Ta bort `calcChain.xml`.
   4. Zippa upp innehållet igen och ändra filnamnstillägget tillbaka till `.xlsx`.
   5. Öppna arbetsboken i Excel och uppdatera alla förfrågningar från Report Builder.
