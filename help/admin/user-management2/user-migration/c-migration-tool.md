---
description: Det ni behöver veta om migreringen av användar-ID:n för Analytics till Admin Console i Adobe Experience Cloud.
title: Migrering av Analytics-användare till Admin Console
uuid: 7d020713-693b-4945-aa52-3669a631aacb
translation-type: tm+mt
source-git-commit: 3db8481434f3db43732f0b54a58c6d4a29bce652

---


# Migrering av Analytics-användare till Admin Console{#analytics-user-migration-to-the-admin-console}

Det ni behöver veta om migreringen av användar-ID:n för Analytics till Admin Console i Adobe Experience Cloud.

Allmän hjälp om ämnen som rör Admin Console (som inte rör Analytics-migrering) finns i Användarhandbok [för](https://helpx.adobe.com/enterprise/administering/user-guide.html)Admin Console.

När du har migrerat kan du [hantera Experience Cloud-användare och -produkter](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) på Admin Console.

## Vad är migreringen av Analytics-användar-ID:n? {#section-adbe49aba10c4e62afa836a97894107c}

Med migreringen av användar-ID:n i Analytics kan administratörer enkelt migrera användarkonton i Analytics-användarhantering till Adobe Admin Console. När användarna har migrerats får de tillgång till de lösningar och bastjänster som finns i Experience Cloud. Migreringen introduceras till kunderna i faser.

Fördelarna med att använda Admin Console är bland annat:

<table id="table_E4465796E224474680D750CAC5434ED3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fördelar </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Enkel inloggning </p> </td> 
   <td colname="col2"> <p>Analysanvändare kan logga in på Experience Cloud och alla lösningar med sitt Adobe ID eller Enterprise ID. Denna inloggning ger tillgång till integrerade lösningar och bastjänster i Experience Cloud. </p> <p>Efter migreringen omdirigeras användare som försöker logga in via äldre inloggningar (<span class="filepath"> my.omniture.com</span> och <span class="filepath"> sc.omniture.com</span>) till <span class="filepath"> experienceCloud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hantera användaridentitet och behörigheter </p> </td> 
   <td colname="col2"> <p>Analysadministratörer kan hantera användare och behörigheter exklusivt på <a href="http://adminconsole.adobe.com/enterprise/"> Admin Console</a> (http://adminconsole.adobe.com/enterprise/). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hantera produkter och bastjänster </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">Bjud in nya användare </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">Skapa produktprofiler </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">Ge användare behörighet till specifika produkter och tjänster </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">Få tillgång till <a href="https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html"> flerlösande bastjänster</a> som finns i Adobe Experience Cloud </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Vad du ska veta (och göra) innan du migrerar användar-ID:n (FAQ) {#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

Svar på frågor som du kan ha innan migreringen.

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fråga/uppgift </th> 
   <th colname="col2" class="entry"> Svar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Jag är Analytics-administratör och har fått ett e-postmeddelande före migreringen. Vad ska jag göra först? </p> </td> 
   <td colname="col2"> <p>Kontrollera att du har ett Adobe-ID och har tillgång till <a href="https://adminconsole.adobe.com/enterprise/"> Experience Cloud Admin Console</a>. </p> <p>Annars kontaktar du <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"> Adobes kundtjänst</a>. (Kontakta först system- eller produktadministratören som kan bjuda in dig till rätt organisation.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AEM-integreringar med Analytics </p> </td> 
   <td colname="col2"> <p> AEM-användare med en integrering i Analytics måste ändra konfigurationen för att kunna använda den delade Analytics-hemligheten i stället för lösenordet. </p> <p> Du bör göra detta innan migreringen aktiveras. När migreringen har inaktiverats blir det ursprungligen konfigurerade lösenordet inte längre giltigt. </p> <p><b>För att få reda på den delade hemligheten i Analytics</b> </p> <p> Den delade hemligheten kan hämtas från Analytics (<span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol"> User Management</span>) och skiljer sig åt för varje användare. </p> <p><b>Så här uppdaterar du din AEM-konfiguration med den delade hemligheten</b> </p> <p>Se Ansluta till Adobe Analytics och Skapa ramverk <a href="https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html"></a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uppdatera Report Builder </p> </td> 
   <td colname="col2"> <p> <p>Viktigt: Uppdatera installationen av <a href="https://marketing.adobe.com/resources/help/en_US/arb/t_install_arb.html"> Report Builder</a> till den senaste versionen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>När börjar migreringen? </p> </td> 
   <td colname="col2"> <p>Adobe meddelar Analytics-administratörer via e-post med instruktioner om när migreringen ska börja. </p> <p>Migreringar till Admin Console sker i vågor. På migreringsdagen meddelar Adobe Analytics-administratörer och ger dem tillgång till migreringsverktyget. När ett inloggningsföretag uppfyller kriterierna för varje migreringsvåg kommer Adobe att: </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">Ange start- och slutdatum för företagets migrering. </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">Skicka ett e-postmeddelande till företagets nuvarande Analytics-administratörer ungefär 30 dagar före migreringen. </li> 
     <li id="li_476265B24CE2404B995201170C75D674">Visa ett meddelande i produkten som informerar administratörerna om startdatumet för migreringen. </li> 
    </ul> <p> På migreringsdagen kopieras dina tidigare behörighetsgrupper automatiskt till Admin Console. Du kan inte längre bjuda in nya användare eller skapa nya grupper i administrationsverktygen för Analytics. </p> <p>Efter migreringen: </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">Administratörer använder Admin Console för att hantera sina Analytics-användare och behörigheter. (Du kommer inte längre att använda användarhanteringsgränssnittet i Analytics &gt; Admin &gt; User Management.) </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">Användare kommer åt Analytics via sina Adobe- eller Enterprise-id:n via Experience Cloud i stället för <span class="filepath"> my.omniture.com</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vad kommer att hända på startdatumet för migreringen? </p> </td> 
   <td colname="col2"> <p>Klockan 10.00 UTC på startdatumet för migreringen: </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">Befintliga behörighetsgrupper i Analytics replikeras automatiskt i Admin Console som produktprofiler, inklusive deras beskrivning och detaljerade behörigheter för rapportsviter, mätvärden, dimensioner, analyser och Report Suite-verktyg. </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">Om någon av dina nuvarande Analytics-användare har skapats i Admin Console (vilket innebär att de har ett länkat Adobe/Enterprise ID) läggs de till i rätt produktprofiler i Admin Console. </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">Avsnittet Användarhantering på fliken Admin i Analytics kommer att vara <span class="term"> skrivskyddat</span>. Du kommer inte längre att kunna skapa nya användare eller behörighetsgrupper här och du måste utföra båda dessa funktioner i Admin Console. Mer information finns i Analytics-funktioner som inte stöds i Admin Console <a href="/help/admin/user-management2/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56"></a> . </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">Som administratör får du åtkomst till [verktyget för migrering av användar-ID] (https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/t_migrate-users.html). Dessutom visas ett meddelande i produkten som innehåller slutdatumet för migreringen (vanligtvis 60 dagar i framtiden) utöver länkar till hjälpinnehåll och vanliga frågor. </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">Du får tillgång till fliken Behörigheter på Admin Console där du kan skapa produktprofiler med alla detaljerade alternativ du känner till i Analytics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hur migrerar jag användar-ID:n? </p> </td> 
   <td colname="col2"> <p> Klicka på <a href="/help/admin/user-management2/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migrera användar-ID</a> på sidan Admin under Användarhantering. Använd verktyget för att lägga till användare i produktprofiler på Admin Console (replikeras från behörighetsgrupper i Analytics). Du kan migrera användar-ID:n i din egen takt. </p> <p>Administrationsprivilegier krävs. När migreringen är klar kan den inte ångras. </p> <p>På slutdatumet för migreringen inaktiveras åtkomsten till <span class="filepath"> my.omniture.com</span> för användare i deras inloggningsföretag. Användare (inklusive de som ännu inte har migrerats) omdirigeras till inloggning via den nya Experience Cloud-URL:en (<span class="filepath"> experience.adobe.com</span>) </p> <p>Obs!  Adobe rekommenderar att du tar tillfället i akt att utföra en granskning av dina användare och grupper innan du migrerar. Ta bort gamla och oanvända konton, eller konton som inte längre ska ha tillgång till produkten (t.ex. anställda som inte längre ingår i organisationen). </p> <p>Relaterat ämne: <a href="/help/admin/user-management2/user-migration/migrate-enterprise.md"> Migrera Analytics-användarkonton för Enterprise ID och Federated ID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kommer migreringen att påverka min Analytics-implementering eller hur data samlas in? </p> </td> 
   <td colname="col2"> <p>Nej. </p> <p>Migreringsverktyget finns för att hjälpa dig att övergå användar-ID och behörigheter från användarhantering i Analytics till <a href="https://adminconsole.adobe.com/enterprise/"> Experience Cloud Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hur lång tid tar migreringsprocessen? </p> </td> 
   <td colname="col2"> <p>Alla aktuella Analytics-administratörer får ett e-postmeddelande före migreringen fyra veckor innan migreringen. (Det faktiska startdatumet visas i analysgränssnittet.) </p> <p>När migreringen påbörjas har administratörerna 60 dagar på sig att slutföra processen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kan jag påskynda min migrering? </p> </td> 
   <td colname="col2"> <p>Ja. Adobe rekommenderar dock att du använder tiden innan migreringen börjar: </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">Kontrollera att du är produktadministratör för Analytics i Admin Console. </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">Kommunicera till din användarbas om att deras inloggningsupplevelse kommer att ändras när migreringen börjar. </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">Granska aktuella användare och behörigheter och utför rensningsaktiviteter. </li> 
    </ul> <p>Kontakta din Customer Success Manager på <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"> Adobe Customer Care</a> och skicka en begäran om ett tidigare startdatum för att underlätta migreringen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Jag är Analytics-administratör utan tillgång till Admin Console. Vem kan hjälpa mig att få åtkomst till Admin Console? </p> </td> 
   <td colname="col2"> <p>Alla system- och produktadministratörer som har åtkomst till organisationens Admin Console kan ge dig åtkomst. Om du är osäker på vem i organisationen som har administratörsbehörighet i konsolen kontaktar du <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"> Adobes kundtjänst</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kan jag skjuta upp migreringens startdatum? </p> </td> 
   <td colname="col2"> <p>Ja. Kontakta <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"> Adobes kundtjänst</a>. </p> 
    <draft-comment> 
     <p>Nedan finns en beskrivning av ändringarna av din aktuella Analytics-hantering för användare och behörigheter på startdatumet. </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nu när mitt företag migrerar till Admin Console, var skapar jag nya användare och behörighetsgrupper före migreringens startdatum? </p> </td> 
   <td colname="col2"> <p>Före migreringens startdatum kan du skapa användare i Admin Console eller i Analytics &gt; User Management. </p> <p>När migreringen har påbörjats kan du bara skapa användare och behörighetsgrupper i Admin Console. </p> 
    <draft-comment> 
     <p>Se avsnittet Migrering nedan för mer information om vad som händer på migreringens startdatum). </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> När kan jag implementera enkel inloggning med Federated ID? </p> </td> 
   <td colname="col2"> <p> Ett verktyg kommer snart att vara tillgängligt i Admin Console där du kan ändra ID-typer från Adobe ID:n till Federated ID:n. Under migreringen kan du inte migrera användare som Federated ID:n. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vad du ska veta under migreringen (frågor och svar) {#section-d394524aa6d046d79025bbd7499792bc}

Viktig information om migreringsprocessen och hur den påverkar den aktuella användarhanteringen.

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fråga </th> 
   <th colname="col2" class="entry"> Svar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Hur replikeras behörighetsgrupper till Admin Console? Mina användare då? </p> </td> 
   <td colname="col2"> <p>En migrerad analysgrupp kallas en <i>produktprofil</i> i Admin Console. Behörighetsinställningar för den ursprungliga gruppen behålls i migreringen. De användare som är tilldelade gruppen migreras dock inte. När en användare som tillhör den gruppen migreras med migreringsverktyget tilldelas den användaren till produktprofilen. </p> <p>En behörighetsgrupp för West Coast Operations som ger medlemmarna rätt att arbeta i Report Builder och Analysis Workspace (med vissa rapportsviter, mätvärden, dimensioner) blir till exempel en produktprofil för West Coast Operations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kan jag delegera migreringsarbetet till en annan administratör? </p> </td> 
   <td colname="col2"> <p>När migreringen påbörjas kan alla administratörer som har åtkomst till din Analytics-instans via Experience Cloud använda migreringsverktyget för att börja (eller fortsätta) migrera användare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kan jag uppdatera medlemskap för behörighetsgrupp för användare som inte migrerats? </p> </td> 
   <td colname="col2"> <p>Ja. Du kan ändra gruppmedlemskap för ej migrerade användare i avsnittet Användarhantering i Analytics. </p> 
    <draft-comment> 
     <p>Väntar på klargöranden från Ashok om var det är gjort. </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kan jag skapa användare och behörighetsgrupper i Analytics när min migrering har påbörjats och sedan använda migreringsverktyget för att flytta dem till Admin Console? </p> </td> 
   <td colname="col2"> <p> Nej. När migreringen påbörjas måste alla nya användare och behörighetsgrupper (kallas produktprofiler i Admin Console) skapas i Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Skulle användare som jag migrerar med hjälp av migreringsverktyget få samma behörigheter som de hade i Analytics? </p> </td> 
   <td colname="col2"> <p>Ja. Användare som migreras med verktyget får de behörigheter de har i Analytics. Dessutom har de fortfarande tillgång till sina Analytics-resurser (som segment, projekt, beräknade värden och så vidare) när de får tillgång till Analytics via Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Har användare som jag migrerar till Admin Console fortfarande tillgång till Analytics via <span class="filepath"> my.omniture.com</span>? </p> </td> 
   <td colname="col2"> <p>Ja. Migrerade användare kan fortfarande komma åt Analytics med sitt befintliga användarnamn och lösenord via <span class="filepath"> my.omniture.com</span> fram till migreringens slutdatum, såvida du inte inaktiverar deras gamla inloggningsåtkomst via migreringsverktyget. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Två eller flera av mina användare har samma e-post-ID i sin Analytics-post. Vad händer om jag migrerar dem? </p> </td> 
   <td colname="col2"> <p>Eftersom användarkonton på Admin Console kräver unika e-post-ID:n, kommer du att stöta på felet Duplicera e-post-ID när du försöker migrera fler än en av dessa användare. Du kan uppdatera e-post-ID:n för användare som inte migrerats under avsnittet Användarhantering (äldre) innan du försöker migrera igen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Vad gör jag efter att jag har migrerat mina användare? </p> </td> 
   <td colname="col2"> <p>Inaktivera deras tidigare inloggningsåtkomst till <span class="filepath"> my.omniture.com</span>. Du kan inte inaktivera äldre inloggningar om de inte har migrerats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kan jag spåra migreringsprocessen? </p> </td> 
   <td colname="col2"> <p>Migreringsverktyget innehåller en kontrollpanel som visar hur många av dina användare som har migrerats och hur många som har inaktiverat sin tidigare inloggning. </p> <p> Helst har du migrerat ditt inloggningsföretag till Admin Console när 100 % av dina användare har slutfört migreringen och har inaktiverat sina tidigare inloggningar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Jag måste hantera användare och behörigheter under migreringen. Vilket verktyg kan jag använda för att utföra den här uppgiften? </p> </td> 
   <td colname="col2"> <p>När migreringen har påbörjats använder du Admin Console för att skapa och hantera nya användare och produktprofiler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vad händer när jag migrerar dem med verktyget? </p> </td> 
   <td colname="col2"> <p>De får ett välkomstmejl adresserat till e-post-ID:t i användarposten för Analytics, som meddelar dem om deras nya sätt att få tillgång till Analytics via Experience Cloud. Om de inte har något befintligt Adobe-ID uppmanas de att skapa ett, varefter de får tillgång till lösningen med sitt Adobe-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kan jag använda API:er för att migrera mina användare i stället för att använda migreringsverktyget? </p> </td> 
   <td colname="col2"> <p>Nej. Du måste använda migreringsverktyget för att se till att alla dina befintliga användare migreras till Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vilka funktioner för användarhantering i Analytics finns inte på Admin Console? </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">Överföring av tillgångar </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">Användarens förfallodatum </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">Användarloggar </li> 
    </ul> <p>Dessa förblir tillgängliga för er i användarhanteringen i Analytics. </p> <p>Mer information finns i Analytics-funktioner som inte stöds i Admin Console <a href="/help/admin/user-management2/user-migration/c-migration-tool.md"></a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vi skapade flera konfigurationer i Admin Console och mappade dem till behörighetsgrupperna Analytics. Vad händer med dessa konfigurationer när migreringen börjar? </p> </td> 
   <td colname="col2"> <p>Behörighetsgrupper för analyser återskapas i Admin Console som produktprofiler, precis som alla andra grupper. Det innebär att du kommer att se två produktprofiler i konsolen som i princip har duplicerade behörigheter. Du kan ta bort duplicerade produktprofiler från Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vad är nästa steg efter att jag har migrerat en användare? </p> </td> 
   <td colname="col2"> <p>När du har migrerat användaren eller en uppsättning användare är nästa steg att inaktivera den gamla inloggningen via <span class="filepath"> my.omniture.com</span>. Du kan göra det genom att markera de här användarna i migreringsverktyget och klicka på det sammanhangsberoende alternativet Inaktivera äldre inloggning som visas längst upp på skärmen. Observera att det här alternativet bara är synligt när du väljer en användare eller en uppsättning användare som har migrerats till Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vad händer på migreringens slutdatum? </p> </td> 
   <td colname="col2"> <p>Efter migreringens slutdatum (60 dagar efter migreringens början) omdirigeras alla användare i ditt inloggningsföretag till inloggning via inloggningssidan för Experience Cloud med sina Adobe ID:n. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Jag har inte kunnat migrera alla mina användare vid migreringens slutdatum. Skulle icke-migrerade användare förlora åtkomsten till Analytics? </p> </td> 
   <td colname="col2"> <p>Användare som inte har migrerats vid slutdatumet omdirigeras till inloggningssidan för Experience Cloud (experienceCloud.adobe.com) och kan inte komma åt Analytics. Du har dock fortfarande tillgång till migreringsverktyget så att du kan hitta och migrera dem för att återställa deras åtkomst. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vad du ska veta efter migreringen (frågor och svar) {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fråga/Problem </th> 
   <th colname="col2" class="entry"> Svar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ta bort användare från Admin Console </p> </td> 
   <td colname="col2"> <p> I Analytics anges en borttagen användare som <span class="term"> utgången</span>, men kontot finns fortfarande. Om du bevarar kontot aktiveras överföringen av tillgångar, som segment, beräknade värden, schemalagda rapporter, projekt och så vidare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utgångsdatum för konto </p> </td> 
   <td colname="col2"> <p> Du kan ange ett kontots förfallodatum manuellt i Analytics i Admin Tools. När förfallodatumet är uppfyllt kommer användaren inte att kunna komma åt Analytics, utan själva Experience Cloud-användarkontot (till exempel Adobe ID, Enterprise ID, Federated ID) går inte ut. De kan fortfarande logga in på Experience Cloud, de kommer bara inte att kunna klicka in i Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Analysfunktioner som inte stöds i Admin Console {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>Granska följande problem som kan gälla dig under migreringen.

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fråga/Problem </th> 
   <th colname="col2" class="entry"> Svar </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Logga in som </p> </td> 
   <td colname="col2"> <p> Administratörer som migrerar till Admin Console kan inte längre använda funktionen"Logga in som" för att komma åt icke-administratörskonton som har migrerats till Admin Console. Den här funktionen har tagits bort från Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Användarens förfallodatum och överföring av tillgångar </p> </td> 
   <td colname="col2"> <p> Admin Console har inte stöd för förfallodatum eller överföring av resurser. Administratörer använder avsnittet Analysanvändare och resurser under Administratörsverktyg i Analytics för båda funktionerna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Senaste åtkomst (senaste inloggning) </p> </td> 
   <td colname="col2"> <p> Information om en användares senaste inloggningsdatum och -tid finns på länken Analytics Users and Assets (Användare och resurser) och inte på Admin Console. Det senaste inloggningsdatumet i Analytics är specifikt för när användare faktiskt använde Analytics inifrån Experience Cloud och inte för att återspegla datumet/tiden när de loggade in på Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>API:er för användarhantering som stöds av <a href="https://helpx.adobe.com/enterprise/help/identity.html"> Adobe</a> </p> </td> 
   <td colname="col2"> <p> Administratörer som migrerar till Admin Console bör konfigurera<a href="https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html"> de API:er</a> för användarhantering som finns i Adobe I/O för programmatisk åtkomst till användarkonton i Admin Console. </p> <p>API:erna för Analytics-behörighet kommer att stängas av när du har aktiverat för migreringen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autentiseringsuppgifter för webbtjänst </p> </td> 
   <td colname="col2"> <p> Användarens inloggningsuppgifter för webbtjänsten (och deras delade hemlighet) är inte tillgängliga i Admin Console och kan nås genom att klicka på den specifika användaren i avsnittet Analytics-användare och -resurser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enkel inloggning </p> </td> 
   <td colname="col2"> <p> Konfigurationer för enkel inloggning i Analytics tas bort när du har slutfört migreringen. De kommer att förbli aktiva under migreringen. Kunder som använder enkel inloggning med Analytics bör uppgradera till <a href="https://helpx.adobe.com/enterprise/help/identity.html"> Adobe Federated ID</a>. </p> <p>Analytics rekommenderar att du migrerar dina användare som Adobe ID:n först för att enkelt skapa Experience Cloud-konton och sedan konvertera dessa konton till Federated single sign-användare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hämtar behörighetsgrupper </p> </td> 
   <td colname="col2"> <p> Hämtning av behörighetsgruppsinformation stöds inte längre i administrationsverktygen för analyser eller i Adobe Admin Console. Kunder bör använda API:erna för användarhantering i adobe.io för att få gruppinformation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Skapad av konto </p> </td> 
   <td colname="col2"> <p>Information om datum när kontot skapades stöds inte längre i Analytics Admin Tools eller Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Massutskick </p> </td> 
   <td colname="col2"> <p>E-post som skickas satsvis till användare stöds inte längre i Admin Console för analyser eller i Adobe Admin Console. Kunder kan exportera användarnas e-postadresser i grupp från Adobe Admin Console och skicka ett e-postmeddelande med valfri e-postklient. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Så här meddelar du användarna om migreringen {#section-f3b25f672a3a4d03b0559656fd99d20a}

Du kanske vill förmedla migreringsplanen proaktivt till dina nuvarande användare. Här är en mall som du kan anpassa för att skicka alla era nuvarande Analytics-användare:

Om du vill skicka e-post till alla användare går du till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** > [E-postanvändare](https://marketing.adobe.com/resources/help/en_US/reference/t_email_users.html).

**Ämne:** Kommer snart - ett nytt sätt att logga in på Adobe Analytics och Adobe Experience Cloud.

**Brödtext:** Hej Adobe Analytics-användare!

Vårt företag börjar migrera alla Adobe Analytics-konton från [!DNL https://my.omniture.com/login/] till Adobe Experience Cloud ([experience.adobe.com](http://experiencecloud.adobe.com/)). Med den här migreringen kommer ditt Adobe Analytics-konto att uppgraderas för att ge tillgång till Analytics via Adobe Experience Cloud. Metoden för åtkomst till Analytics ändras, men alla dina befintliga behörigheter till rapportsviterna och verktygen bevaras.

**Nästa steg:** Vi börjar migrera användare från och med **INSERT DATE**. Håll utkik efter ett välkomstmeddelande med din nya inloggning adresserad till e-post-ID:t som listas under ditt analyskonto. Om du inte har konfigurerat ett [Adobe-ID](https://helpx.adobe.com/x-productkb/global/adobe-id-account-change.html) som är länkat till din e-postadress ombeds du att skapa ett konto.

**Användbara resurser:**

[Logga in och hantera dina profilinställningar](https://marketing.adobe.com/resources/help/en_US/mcloud/getting-started-experience-cloud.html).

[Om moln, bastjänster och lösningar](https://marketing.adobe.com/resources/help/en_US/mcloud/solutions_capability_names.html) i Experience Cloud

Kontakta era Analytics-administratörer om ni har några frågor eller problem.

Bästa,

Analysadministratör
