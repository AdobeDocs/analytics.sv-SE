---
description: Vad du behöver veta om migreringen av användar-ID:n för Analytics till Admin Console i Adobe Experience Cloud.
title: Migrering av Analytics-användare till Admin Console
feature: Admin Tools
exl-id: f4bc0e92-af53-40db-8138-44d29e4b25fe
source-git-commit: dc9cd6bb45af0c992c37ffe20ea22eab67789ec5
workflow-type: tm+mt
source-wordcount: '3108'
ht-degree: 0%

---

# Migrering av Analytics-användare till Admin Console{#analytics-user-migration-to-the-admin-console}

Vad du behöver veta om migreringen av användar-ID:n för Analytics till Admin Console i Adobe Experience Cloud.

Allmän hjälp om Admin Console-ämnen (som inte hör till Analytics-migreringen) finns i [Användarhandbok för Admin Console](https://helpx.adobe.com/enterprise/administering/user-guide.html).

När du har migrerat kan du [hantera användare och produkter av Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) i Admin Console.

## Vad är migreringen av Analytics-användar-ID:n? {#section-adbe49aba10c4e62afa836a97894107c}

Med migreringen av användar-ID:n i Analytics kan administratörer enkelt migrera användarkonton i Analytics-användarhantering till Adobe Admin Console. När användarna har migrerats får de tillgång till de lösningar och bastjänster som är tillgängliga i Experience Cloud. Migreringen introduceras till kunderna i faser.

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
   <td colname="col2"> <p>Analysanvändare kan logga in på Experience Cloud och alla lösningar med sina Adobe ID eller Enterprise ID. Denna inloggning ger tillgång till integrerade lösningar och bastjänster i Experience Cloud. </p> <p>Efter migreringen försöker användare logga in via äldre inloggningar (<span class="filepath"> my.omniture.com</span> och <span class="filepath"> sc.omniture.com</span>) omdirigeras till <span class="filepath"> experience.loud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hantera användaridentitet och behörigheter </p> </td> 
   <td colname="col2"> <p>Analysadministratörer kan hantera användare och behörigheter exklusivt i <a href="https://adminconsole.adobe.com/enterprise/"> Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hantera produkter och bastjänster </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">Bjud in nya användare </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">Skapa produktprofiler </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">Ge användare behörighet till specifika produkter och tjänster </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">Få åtkomst till <a href="https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html"> kärntjänster med flera lösningar</a> finns i Adobe Experience Cloud </li> 
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
   <td colname="col2"> <p>Kontrollera att du har en Adobe ID och har tillgång till <a href="https://adminconsole.adobe.com/enterprise/"> Experience Cloud Admin Console</a>. </p> <p>Om inte, kontakta <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"> Adobe kundtjänst</a>. (Kontakta först system- eller produktadministratören som kan bjuda in dig till rätt organisation.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AEM integreringar med Analytics </p> </td> 
   <td colname="col2"> <p> AEM användare som är integrerade med Analytics måste ändra konfigurationen för att kunna använda den delade Analytics-hemligheten i stället för lösenordet. </p> <p> Du bör göra detta innan migreringen aktiveras. När migreringen har inaktiverats blir det ursprungligen konfigurerade lösenordet inte längre giltigt. </p> <p><b>För att få reda på den delade hemligheten i Analytics</b> </p> <p> Den delade hemligheten kan hämtas från Analytics (<span class="uicontrol"> Analyser</span> &gt; <span class="uicontrol"> Användarhantering</span>) och skiljer sig åt för varje användare. </p> <p><b>Så här uppdaterar du AEM med den delade hemligheten</b> </p> <p>Se <a href="https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html"> Ansluta till Adobe Analytics och skapa ramverk</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uppdatera Report Builder </p> </td> 
   <td colname="col2"> <p> <p>Viktigt: Uppdatera installationen av <a href="https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/report-builder-setup/t-install-arb.html"> Report Builder</a> till den senaste versionen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>När börjar migreringen? </p> </td> 
   <td colname="col2"> <p>Adobe kommer att via e-post meddela Analytics-administratörer om när migreringen kommer att börja. </p> <p>Migreringar till Admin Console sker i vågor. På migreringsdagen meddelar Adobe Analytics-administratörer och ger dem tillgång till migreringsverktyget. När ett inloggningsföretag uppfyller kriterierna för varje migreringsvåg kommer Adobe att: </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">Ange start- och slutdatum för företagets migrering. </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">Skicka ett e-postmeddelande till företagets nuvarande Analytics-administratörer ungefär 30 dagar före migreringen. </li> 
     <li id="li_476265B24CE2404B995201170C75D674">Visa ett meddelande i produkten som informerar administratörerna om startdatumet för migreringen. </li> 
    </ul> <p> På migreringsdagen kopieras dina tidigare behörighetsgrupper automatiskt till Admin Console. Du kan inte längre bjuda in nya användare eller skapa nya grupper i administrationsverktygen för Analytics. </p> <p>Efter migreringen: </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">Administratörer använder Admin Console för att hantera sina Analytics-användare och behörigheter. (Du kommer inte längre att använda användarhanteringsgränssnittet i Analytics &gt; Admin &gt; User Management.) </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">Användarna kommer åt Analytics via Adobe eller Enterprise ID via Experience Cloud istället för <span class="filepath"> my.omniture.com</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vad kommer att hända på startdatumet för migreringen? </p> </td> 
   <td colname="col2"> <p>Klockan 10.00 UTC på startdatumet för migreringen: </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">Dina befintliga behörighetsgrupper i Analytics replikeras automatiskt i Admin Console som produktprofiler, inklusive deras beskrivning och detaljerade behörigheter i rapportsviter, mått, analyser och rapportsviter. </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">Om någon av dina nuvarande Analytics-användare har skapats i Admin Console (vilket innebär att de har ett länkat Adobe/Enterprise ID) läggs de till i rätt produktprofiler i Admin Console. </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">Avsnittet Användarhantering på fliken Admin i Analytics är inställt på <span class="term"> skrivskyddad</span>. Du kommer inte längre att kunna skapa nya användare eller behörighetsgrupper här och du måste utföra båda funktionerna i Admin Console. Se <a href="/help/admin/admin-console/user-management2/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56"> Analysfunktionerna i Admin Console stöds inte</a> för mer information. </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">Som administratör får du åtkomst till <a href="https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/t-migrate-users.html">Migreringsverktyg för användar-ID</a>. Dessutom visas ett meddelande i produkten som innehåller slutdatumet för migreringen (vanligtvis 60 dagar i framtiden) utöver länkar till hjälpinnehåll och vanliga frågor. </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">Du får åtkomst till fliken Behörigheter i Admin Console som gör att du kan skapa produktprofiler med alla detaljerade alternativ som du känner till i Analytics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hur migrerar jag användar-ID:n? </p> </td> 
   <td colname="col2"> <p> Klicka <a href="/help/admin/admin-console/user-management2/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migrera användar-ID:n</a> på sidan Admin, under Användarhantering. Använd verktyget för att lägga till användare i produktprofiler på Admin Console (replikerade från behörighetsgrupper i Analytics). Du kan migrera användar-ID:n i din egen takt. </p> <p>Administrationsprivilegier krävs. När migreringen är klar kan den inte ångras. </p> <p>Vid migreringens slutdatum <span class="filepath"> my.omniture.com</span> åtkomst inaktiveras för användare i deras inloggningsföretag. Användare (även de som ännu inte har migrerats) omdirigeras till inloggning via den nya Experience Cloud-URL:en (<span class="filepath"> experience.loud.adobe.com</span>) </p> <p>Obs! Adobe rekommenderar att du tar tillfället i akt att utföra en granskning av dina användare och grupper innan du migrerar. Ta bort gamla och oanvända konton, eller konton som inte längre ska ha tillgång till produkten (t.ex. anställda som inte längre ingår i organisationen). </p> <p>Relaterat ämne: <a href="/help/admin/admin-console/user-management2/user-migration/migrate-enterprise.md"> Migrera Analytics-användarkonton för Enterprise ID och Federated ID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kommer migreringen att påverka min Analytics-implementering eller hur data samlas in? </p> </td> 
   <td colname="col2"> <p>Nej. </p> <p>Migreringsverktyget finns för att hjälpa dig att övergå användar-ID:n och behörigheter från användarhantering i Analytics till <a href="https://adminconsole.adobe.com/enterprise/"> Experience Cloud Admin Console</a>. </p> </td> 
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
    </ul> <p>Kontakta din Customer Success Manager på <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"> Adobe kundtjänst</a> och skicka en begäran om ett tidigare startdatum. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Jag är Analytics-administratör utan tillgång till Admin Console. Vem kan hjälpa mig att få tillgång till Admin Console? </p> </td> 
   <td colname="col2"> <p>Alla system- och produktadministratörer som har tillgång till din organisations Admin Console kan ge dig åtkomst. Om du är osäker på vem i organisationen som har administratörsbehörighet i konsolen kontaktar du <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"> Adobe kundtjänst</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kan jag skjuta upp migreringens startdatum? </p> </td> 
   <td colname="col2"> <p>Ja. Kontakt <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html"> Adobe kundtjänst</a>. </p><p>Nedan finns en beskrivning av ändringarna av din aktuella Analytics-hantering för användare och behörigheter på startdatumet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nu när mitt företag migrerar till Admin Console, var skapar jag nya användare och behörighetsgrupper före migreringens startdatum? </p> </td> 
   <td colname="col2"> <p>Före migreringens startdatum kan du skapa användare i Admin Console eller i Analytics &gt; User Management. </p> <p>När migreringen har påbörjats kan du bara skapa användare och behörighetsgrupper i Admin Console. </p><p>Se avsnittet Migrering nedan för mer information om vad som händer på migreringens startdatum. </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> När kan jag implementera enkel inloggning med Federated ID? </p> </td> 
   <td colname="col2"> <p> Ett verktyg kommer snart att vara tillgängligt i Admin Console som gör att du kan ändra ID-typer från Adobe ID till Federated ID. Under migreringen kan du inte migrera användare som Federated ID:n. </p> </td> 
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
   <td colname="col2"> <p>En migrerad Analytics-grupp kallas en <i>Produktprofil</i> i Admin Console. Behörighetsinställningar för den ursprungliga gruppen behålls i migreringen. De användare som är tilldelade gruppen migreras dock inte. När en användare som tillhör den gruppen migreras med migreringsverktyget tilldelas den användaren till produktprofilen. </p> <p>En behörighetsgrupp för West Coast Operations som ger medlemmarna rätt till Report Builder och Analysis Workspace (med vissa rapportsviter, mätvärden, dimensioner) kommer till exempel att bli en produktprofil för West Coast Operations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kan jag delegera migreringsarbetet till en annan administratör? </p> </td> 
   <td colname="col2"> <p>När migreringen påbörjas kan alla administratörer som har åtkomst till din Analytics-instans via Experience Cloud använda migreringsverktyget för att börja (eller fortsätta) migrera användare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kan jag uppdatera medlemskap för behörighetsgrupp för användare som inte migrerats? </p> </td> 
   <td colname="col2"> <p>Ja. Du kan ändra gruppmedlemskap för ej migrerade användare i avsnittet Användarhantering i Analytics. </p><p>Väntar på klargöranden från Ashok om var det är gjort. </p>
   </td> 
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
   <td colname="col1"> <p>Har de användare jag migrerar till Admin Console fortfarande tillgång till Analytics med <span class="filepath"> my.omniture.com</span>? </p> </td> 
   <td colname="col2"> <p>Ja. Migrerade användare kan fortfarande komma åt Analytics via sitt befintliga användarnamn och lösenord via <span class="filepath"> my.omniture.com</span> fram till slutdatumet för migreringen, såvida du inte inaktiverar deras tidigare inloggningsåtkomst via migreringsverktyget. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Två eller flera av mina användare har samma e-post-ID i sin Analytics-post. Vad händer om jag migrerar dem? </p> </td> 
   <td colname="col2"> <p>Eftersom användarkonton i Admin Console kräver unika e-post-ID:n, kommer du att stöta på felet Duplicera e-post-ID när du försöker migrera fler än en av dessa användare. Du kan uppdatera e-post-ID:n för användare som inte migrerats under avsnittet Användarhantering (äldre) innan du försöker migrera igen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Vad gör jag efter att jag har migrerat mina användare? </p> </td> 
   <td colname="col2"> <p>Inaktivera deras tidigare inloggningsåtkomst till <span class="filepath"> my.omniture.com</span>. Du kan inte inaktivera äldre inloggningar om de inte har migrerats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kan jag spåra migreringsprocessen? </p> </td> 
   <td colname="col2"> <p>Migreringsverktyget innehåller en kontrollpanel som visar hur många av dina användare som har migrerats och hur många som har inaktiverat sin tidigare inloggning. </p> <p> I idealfallet har du migrerat ditt inloggningsföretag till Admin Console när 100 % av dina användare har slutfört migreringen och har inaktiverat sina äldre inloggningar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Jag måste hantera användare och behörigheter under migreringen. Vilket verktyg kan jag använda för att utföra den här uppgiften? </p> </td> 
   <td colname="col2"> <p>När migreringen har påbörjats använder du Admin Console för att skapa och hantera nya användare och produktprofiler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vad händer när jag migrerar dem med verktyget? </p> </td> 
   <td colname="col2"> <p>De får ett välkomstmejl adresserat till e-post-ID:t i användarposten för Analytics, som meddelar dem om deras nya sätt att komma åt Analytics via Experience Cloud. Om de inte har någon befintlig Adobe ID uppmanas de att skapa en, varefter de får tillgång till lösningen med sin Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kan jag använda API:er för att migrera mina användare i stället för att använda migreringsverktyget? </p> </td> 
   <td colname="col2"> <p>Nej. Du måste använda migreringsverktyget för att se till att alla dina befintliga användare migreras till Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vilka funktioner för användarhantering i Analytics finns inte i Admin Console? </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">Överföring av tillgångar </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">Användarens förfallodatum </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">Användarloggar </li> 
    </ul> <p>Dessa förblir tillgängliga för er i användarhanteringen i Analytics. </p> <p>Se <a href="/help/admin/admin-console/user-management2/user-migration/c-migration-tool.md"> Analysfunktionerna i Admin Console stöds inte</a> för mer information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vi skapade flera konfigurationer i Admin Console och mappade dem till behörighetsgrupperna i Analytics. Vad händer med dessa konfigurationer när migreringen börjar? </p> </td> 
   <td colname="col2"> <p>Behörighetsgrupper för analyser återskapas i Admin Console som produktprofiler, precis som alla andra grupper. Det innebär att du kommer att se två produktprofiler i konsolen som i princip har duplicerade behörigheter. Du kan ta bort duplicerade produktprofiler från Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vad är nästa steg efter att jag har migrerat en användare? </p> </td> 
   <td colname="col2"> <p>När du har migrerat en användare eller en uppsättning användare är nästa steg att inaktivera den gamla inloggningen via <span class="filepath"> my.omniture.com</span>. Du kan göra det genom att markera de här användarna i migreringsverktyget och klicka på det sammanhangsberoende alternativet Inaktivera äldre inloggning som visas längst upp på skärmen. Observera att det här alternativet bara är synligt när du väljer en användare eller uppsättning användare som har migrerats till Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vad händer på migreringens slutdatum? </p> </td> 
   <td colname="col2"> <p>Efter migreringens slutdatum (60 dagar efter migreringens början) omdirigeras alla användare i ditt inloggningsföretag till inloggning via inloggningssidan för Experience Cloud med hjälp av deras Adobe-ID:n. </p> </td> 
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
   <td colname="col2"> <p> I Analytics anges en borttagen användare som <span class="term"> utgången</span>men kontot finns fortfarande. Om du bevarar kontot aktiveras överföringen av tillgångar, som segment, beräknade värden, schemalagda rapporter, projekt och så vidare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utgångsdatum för konto </p> </td> 
   <td colname="col2"> <p> Du kan ange ett kontots förfallodatum manuellt i Analytics i Admin Tools. När förfallodatumet är uppfyllt kommer användaren inte att kunna komma åt Analytics, utan själva Experience Cloud-användarkontot (t.ex. Adobe ID, Enterprise ID, Federated ID osv.) går inte ut. De kan fortfarande logga in på Experience Cloud, de kan bara inte klicka in i Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Analysfunktionerna i Admin Console stöds inte {#section-928ffba27a0446e0af575b720434ef56}

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
   <td colname="col2"> <p> Administratörer som migrerar till Admin Console kommer inte längre att kunna använda funktionen "Logga in som" för att få åtkomst till icke-administratörskonton som har migrerats till Admin Console. Den här funktionen har tagits bort från Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Användarens förfallodatum och överföring av tillgångar </p> </td> 
   <td colname="col2"> <p> Admin Console stöder inte användarens förfallodatum eller överföring av resurser. Administratörer använder avsnittet Analysanvändare och resurser under Administratörsverktyg i Analytics för båda funktionerna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Senaste åtkomst (senaste inloggning) </p> </td> 
   <td colname="col2"> <p> Information om en användares senaste inloggningsdatum och -tid finns på länken Analytics Users and Assets (Användare och resurser), inte Admin Console. Det sista inloggningsdatumet i Analytics är specifikt för när användare faktiskt kom åt Analytics inifrån Experience Cloud och det återspeglar inte datumet/tiden när de loggade in i Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>API:er för användarhantering <a href="https://helpx.adobe.com/enterprise/help/identity.html"> Identitetstyper som stöds av Adobe</a> </p> </td> 
   <td colname="col2"> <p> Administratörer som migrerar till Admin Console bör konfigurera<a href="https://developer.adobe.com/UMAPI/"> API:er för användarhantering</a> som erbjuds på Adobe Developer för programmatisk åtkomst till användarkonton i Admin Console. </p> <p>API:erna för Analytics-behörighet kommer att stängas av när du har aktiverat för migreringen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autentiseringsuppgifter för webbtjänst </p> </td> 
   <td colname="col2"> <p> Användarens inloggningsuppgifter för webbtjänsten (och deras delade hemlighet) är inte tillgängliga i Admin Console och kan nås genom att klicka på den specifika användaren i avsnittet Analytics-användare och -resurser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enkel inloggning </p> </td> 
   <td colname="col2"> <p> Konfigurationer för enkel inloggning i Analytics tas bort när du har slutfört migreringen. De kommer att förbli aktiva under migreringen. Kunder som använder enkel inloggning med Analytics bör uppgradera till <a href="https://helpx.adobe.com/enterprise/help/identity.html"> Federated ID Adobe</a>. </p> <p>Analytics rekommenderar att du migrerar dina användare som Adobe ID:n först för att enkelt skapa Experience Cloud-konton och sedan konvertera dessa konton till Federated single sign-användare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hämtar behörighetsgrupper </p> </td> 
   <td colname="col2"> <p> Hämtning av behörighetsgruppsinformation stöds inte längre i administrationsverktygen för Analytics eller Adobe Admin Console. Kunder bör använda API:erna för användarhantering i adobe.io för att få gruppinformation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Skapad av konto </p> </td> 
   <td colname="col2"> <p>Information om datum när kontot skapades stöds inte längre i Analytics Admin Tools eller Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Massutskick </p> </td> 
   <td colname="col2"> <p>E-post som skickas satsvis till användare stöds inte längre i Analytics Admin Console eller Adobe Admin Console. Kunderna kan exportera användarnas e-postadresser i grupp från Adobe Admin Console och skicka ett e-postmeddelande med valfri e-postklient. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Så här meddelar du användarna om migreringen {#section-f3b25f672a3a4d03b0559656fd99d20a}

Du kanske vill förmedla migreringsplanen proaktivt till dina nuvarande användare. Här är en mall som du kan anpassa för att skicka alla era nuvarande Analytics-användare:

Om du vill skicka e-post till alla användare går du till **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]** > [E-postanvändare](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/t-email-users.html).

**Ämne:** Kommer snart - ett nytt sätt att logga in på Adobe Analytics och Adobe Experience Cloud.

**Brödtext:** Hej Adobe Analytics!

Vårt företag börjar migrera alla Adobe Analytics-konton från [!DNL https://my.omniture.com/login/] till Adobe Experience Cloud ([experience.loud.adobe.com](https://experiencecloud.adobe.com/)). Med den här migreringen kommer ditt Adobe Analytics-konto att uppgraderas för att ge åtkomst till Analytics via Adobe Experience Cloud. Metoden för åtkomst till Analytics ändras, men alla dina befintliga behörigheter till rapportsviterna och verktygen bevaras.

**Nästa steg:** Vi börjar migrera användare från **INFOGA DATUM**. Håll utkik efter ett välkomstmeddelande med din nya inloggning adresserad till e-post-ID:t som listas under ditt analyskonto. Om du inte har konfigurerat [Adobe ID](https://helpx.adobe.com/x-productkb/global/adobe-id-account-change.html) länkad till din e-postadress uppmanas du att skapa ett konto.

**Användbara resurser:**

[Logga in och hantera dina profilinställningar](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-products.ug.html).

Kontakta era Analytics-administratörer om ni har några frågor eller problem.

Bästa,

Analysadministratör
