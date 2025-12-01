---
title: Klassificeringsuppsättningsregler
description: Lär dig hur du använder regler för klassificeringsuppsättningar för att definiera regler för klassificeringsdata.
feature: Classifications
hide: true
hidefromtoc: true
source-git-commit: bccb3409875336a092ab641ad69b866b43621984
workflow-type: tm+mt
source-wordcount: '1448'
ht-degree: 0%

---


# Klassificeringsuppsättningsregler

Du använder regler för att stödja automatiska klassificeringar i scenarier där nyckeldimensionen ständigt ändras. Uppdateringen av klassificeringar genom överföring eller automatisering blir en besvärlig process eller försenar en korrekt klassificering för nya dimensionsvärden. Exempel: interna kampanjer, spårningskoder eller SKU:er för produkter. Dimensionen måste innehålla värden som gör att du kan tillämpa en eller flera regler så att du kan härleda klassificeringsdata från värdena.

Du definierar regler inom ramen för en klassificeringsuppsättning, vilket innebär att regler tillämpas (när de aktiveras) på alla rapportsviter och nyckeldimensionskombinationer som prenumererar på klassificeringsuppsättningen. Den här implementeringen skiljer sig något från hur den äldre funktionen för att skapa klassificeringsregler fungerar. I klassregelmappen definierar du en eller flera regler som en del av en regeluppsättning separat och kopplar sedan regeluppsättningen till en eller flera rapportsviter. I det nya gränssnittet kallas reglerna i klassificeringsuppsättningen även för regeluppsättning, men definieras i samma gränssnitt där du konfigurerar andra attribut för klassificeringsuppsättningar.


Så här definierar du en regeluppsättning för en klassificeringsuppsättning:

1. Välj **[!UICONTROL Components]** i Adobe Analytics övre menyrad och välj sedan **[!UICONTROL Classification sets]**.
1. I **[!UICONTROL Classification Sets]** väljer du fliken **[!UICONTROL Classification Sets]**.
1. I hanteraren för **[!UICONTROL Classifications Sets]** väljer du den klassificeringsuppsättning som du vill definiera reglerna för.
1. Välj fliken **[!UICONTROL Classification Set: _i dialogrutan_]** klassificeringsuppsättningsnamn **[!UICONTROL Rules]**.

   * Om du använder gränssnittet **[!UICONTROL Rules]** för första gången för en klassificeringsuppsättning, eller om du hittills har beslutat att fortsätta använda det äldre gränssnittet för regelbyggaren, visas en dialogruta där du kan välja hur du vill komma igång. Alternativen är:

      * **Migrera befintliga regler**. Importera dina aktuella klassificeringsregler och fortsätt arbeta med dessa regler i det nya gränssnittet. De befintliga reglerna bevaras och konverteras till det nya formatet.
         * Välj **[!UICONTROL Migrate rules]** om du vill fortsätta.
         * Läs konsekvenserna av migreringen i dialogrutan **[!UICONTROL Confirm migration]**.
            * Välj **[!UICONTROL Migrate rules]** för att bekräfta migreringen. När migreringen är klar använder du gränssnittet [Regeluppsättning](#rule-set-interface) för att skapa nya regler och redigera dina befintliga migrerade regler.
            * Välj **[!UICONTROL Cancel]** om du vill avbryta migreringen

      * **Börja om**. Skapa nya klassificeringsregler från grunden med nya regelverktyget. Välj det här alternativet om du vill designa om klassificeringslogiken eller börja om från början med nya klassificeringsregler.
         * Välj **[!UICONTROL Create new rules]** om du vill fortsätta.
         * Läs vad en ny start innebär i dialogrutan **[!UICONTROL Confirm start fresh]**.
            * Välj **[!UICONTROL Start fresh]** om du vill konfigurera en ny start och ignorera befintliga regler. Använd gränssnittet [Regeluppsättning](#rule-set-interface) för att skapa nya regler.
            * Välj **[!UICONTROL Cancel]** om du vill avbryta.


      * **Använd det gamla gränssnittet**. Fortsätt att använda det tidigare gränssnittet för regelbyggaren. Du kan migrera till den nya upplevelsen när som helst när du är redo.
         * Välj **[!UICONTROL Go to legacy interface]** om du vill fortsätta. Du dirigeras till det gamla **[!UICONTROL Classification Rule Builder]**-gränssnittet.

   * Om du redan har migrerat regler eller skapat nya regler för en klassificeringsuppsättning hamnar du direkt i gränssnittet Regeluppsättning.



## Regeluppsättningsgränssnitt

När du skapar eller redigerar regler använder du gränssnittet Regeluppsättning.

![Gränssnitt för regeluppsättning](assets/rulesets-ui.png)

| | Namn | Beskrivning |
|---|---|---|
| 1 | **[!UICONTROL Functions]** | Du använder området **[!UICONTROL Functions]** för att markera och dra och släppa funktioner till regeluppsättningsverktyget. |
| 2 | **Regeluppsättningsverktyget** | Du skapar regeluppsättningen med en eller flera regler. En regel är implementeringen av en funktion och alltid associerad med bara en funktion. En funktion kan ha flera operatorer. Du skapar en regel genom att dra och släppa en funktion i regeluppsättningsverktyget. Funktionstypen definierar regelns gränssnitt. <br/>Mer information finns i [Regelgränssnittet](#rule-interface).<br/>Du kan infoga funktioner var som helst, och funktionerna körs i sekvens för att bestämma de slutliga värdena för klassificeringarna.<br/>Använd **[!UICONTROL Collapse all]** för att komprimera alla regler och använd **[!UICONTROL Expand all]** för att expandera alla regler. |
| 3 | **[!UICONTROL Status]** | Visa regeluppsättningens status och senaste ändringsdatum. <br/>Välj **[!UICONTROL Activate]** om du vill aktivera regeluppsättningen. <br/>Välj **[!UICONTROL Deactivate]** om du vill inaktivera regeluppsättningen. |
| 4 | **[!UICONTROL Lookback]** | Ange regeluppsättningens uppslagsfönster.<br/>Välj ett alternativ (från 1 månad till 6 månader) i listrutan.<br/>Välj **[!UICONTROL Perform lookback]** om du vill utföra en uppläsning med den valda uppslagsperioden. |
| 5 | **[!UICONTROL Test options]** | Använd samplingsnyckeldimensionsvärden för att testa klassificeringarna: <ul><li>Lägg till eller klistra in värden i textområdet **[!UICONTROL Sample keys]**.<br/>Kontrollera **[!UICONTROL Remember sample keys]** för att se till att exempelnycklarna finns kvar när regeluppsättningsgränssnittet används på olika sätt.</li><li>Välj **[!UICONTROL Test rule set]** om du vill testa regeluppsättningen.</li></ul> |


## Regelgränssnitt

Du definierar varje enskild regel i regeluppsättningen i regelgränssnittet. Gränssnittet består av följande element:

![Regelgränssnitt](assets/rule-ui.png)

| | Beskrivning |
|---|---|
| 1 | Namnet på den valda funktionen och de indata som har angetts för funktionen. |
| 2 | Indata för den valda funktionen. Indata beror på den valda funktionen. För funktionen Reguljärt uttryck är indata ett reguljärt uttryck och för funktionen Dela är indata en token. Ange lämplig inmatning för den specifika funktionen. `^(.+)\:(.+)\:(.+)$` för ett reguljärt uttryck som identifierar tre klassificeringar i en intern kampanjkod. |
| 3 | Varje åtgärd ställer in en specifik klassificering till ett värde. <br/>Välj en klassificering i listrutan **[!UICONTROL Set Classification]** och ange ett värde för **[!UICONTROL to]**. <br/>Använd ![CrossSize400](/help/assets/icons/CrossSize400.svg) om du vill ta bort en åtgärd från listan. |
| 4 | Välj ![Lägg till](/help/assets/icons/Add.svg) **[!UICONTROL Add operation]** om du vill lägga till ytterligare en åtgärd i funktionen. |
| 5 | Välj ![SparrrNed](/help/assets/icons2/ChevronDown.svg) om du vill komprimera regeln. Välj ![Sparrvänster](/help/assets/icons/ChevronLeft.svg) om du vill expandera regeln.<br/>Markera ![CrossSize400](/help/assets/icons/CrossSize400.svg) om du vill ta bort regeln. |

## Funktionsreferens

För varje funktion som stöds hittar du information nedan om obligatoriska indata- och exempelfall.


### Börjar med..

Ställer in en klassificering baserat på ett specifikt värde som nyckeldimensionen börjar med.

+++ Information 

#### Nödvändiga indata

Ange ett värde för **[!UICONTROL Starts With]**. Till exempel: `em`.

#### Använd skiftläge

Du vill definiera en regel som automatiskt tilldelar `Email` som ett värde till **[!UICONTROL Channel]**-klassificeringen när värdet för nyckeldimensionens interna kampanj börjar med `em` (till exempel: `em:FY2025:Summer Sale`).

![Regel - börjar med](assets/rule-startswith.png)

+++



### Slutar med...

Ställer in en klassificering baserat på ett specifikt värde som nyckeldimensionen avslutas med.

+++ Information 

#### Nödvändiga indata

Ange ett värde för **[!UICONTROL Ends With]**. Till exempel: `Sale`.

#### Använd skiftläge

Du vill definiera en regel som automatiskt tilldelar `Sale` som ett värde till **[!UICONTROL Type]**-klassificeringen när värdet för den interna nyckeldimensionen innehåller `Sale` (till exempel: `em:FY2025:Summer Sale`).

![Regel - slutar med](assets/rule-endswith.png)

+++


### Innehåller...

Ställer in en klassificering baserat på ett specifikt värde som nyckeldimensionen innehåller.

+++ Information 

#### Nödvändiga indata

Ange ett värde för **[!UICONTROL Contains]**. Till exempel: `2025`.

#### Använd skiftläge

Du vill definiera en regel som automatiskt tilldelar `2025` som ett värde till **[!UICONTROL Year]**-klassificeringen när värdet för nyckeldimensionens interna kampanj slutar med `2025` (till exempel: `em:FY2025:Summer Sale`).

![Regel - innehåller](assets/rule-contains.png)

+++


### Matcha

Ställer in en klassificering baserat på ett specifikt värde som nyckeldimensionens matchningar.

+++ Information 

#### Nödvändiga indata

Ange ett värde för **[!UICONTROL Match]**. Till exempel: `em:FY2025:Summer`.

#### Använd skiftläge

Du vill definiera en regel som automatiskt tilldelar `2025 Summer Email` som ett värde till **[!UICONTROL Type]**-klassificeringen när värdet för nyckeldimensionens interna kampanj matchar `em:FY2025:Summer`.

![Regel - träffar](assets/rule-match.png)

+++


### Reguljärt uttryck

Ställer in en eller flera klassificeringar baserat på ett reguljärt uttryck som används på nyckeldimensionsvärdet.

+++ Information 

#### Nödvändiga indata

Ange ett värde för **[!UICONTROL Regular Expression]**. Till exempel: `^(.+)\:(.+)\:(.+)$`.

#### Använd skiftläge

Du vill definiera en regel som automatiskt tilldelar värden till klassificeringarna **[!UICONTROL Channel]**, **[!UICONTROL Type]** och **[!UICONTROL Year]** genom att tillämpa det reguljära uttrycket `^(.+)\:(.+)\:(.+)$` och använda matchningsgrupper (`$1`, `$2` och `$3`) på värdena för nyckeldimensionens interna kampanj.

![Regel - reguljärt uttryck](assets/rule-regex.png)


#### Referenstabell {#section_0211DCB1760042099CCD3ED7A665D716}

| Reguljärt uttryck | Beskrivning |
|---|---|
| `(?ms)` | Matchar hela det reguljära uttrycket mot flerradiga indata, vilket tillåter . jokertecken som matchar alla radmatningstecken |
| `(?i)` | Gör hela det reguljära uttryckets skiftläge okänsligt |
| `[abc]` | Ett enda tecken: a, b eller c |
| `[^abc]` | Ett enda tecken förutom: a, b eller c |
| `[a-z]` | Ett enskilt tecken i intervallet a-z |
| `[a-zA-Z]` | Ett enskilt tecken i intervallet a-z eller A-Z |
| `^` | Radbörjan (matchar början av raden) |
| `$` | Matcha radens slut (eller före radmatningen i slutet) |
| `\A` | Strängstart |
| `\z` | Strängslut |
| `.` | Matcha alla tecken (utom en ny rad) |
| `\s` | Valfritt blankstegstecken |
| `\S` | Alla tecken som inte är blanksteg |
| `\d` | Alla siffror |
| `\D` | Alla icke-siffror |
| `\w` | Valfritt ordtecken (bokstav, siffra, understreck) |
| `\W` | Valfritt icke-ordtecken |
| `\b` | Valfri ordgräns |
| `(...)` | Fånga allt inneslutet |
| `(a\b)` | a eller b |
| `a?` | Noll eller en av |
| `a*` | Noll eller mer av en |
| `a+` | en eller flera av |
| `a{3}` | Exakt 3 av en |
| `a{3,}` | 3 eller fler av en |
| `a{3,6}` | Mellan 3 och 6 i en |

+++


## Regelprioritet

Om ett nyckeldimensionsvärde matchas mot flera regler, och regeluppsättningarna innehåller regler med samma Set Classification-åtgärd, bestämmer den sista regeln värdet för klassificeringen. Därför bör du rangordna den viktigaste åtgärden Ange klassificering som en del av den sista regeln i regeluppsättningen.

Om du skapar flera regler som inte delar samma Set Classification-åtgärd spelar bearbetningsordningen ingen roll.


### Exempel

Du vill klassificera med klassificeringen **[!UICONTROL Type]** hur användare söker efter en idrottare med söksträngen som nyckeldimension. Använd till exempel den här regeluppsättningen:

![Regelprioritet](assets/rule-priority.png)

* När en användare söker efter `Cowboys Fantasy Tony Romo` klassificeras `Romo` som **[!UICONTROL Type]**.
* När en användare söker efter `Cowboys Fantasy Tony Romeo` klassificeras `Fantasy` som **[!UICONTROL Type]**.
* När en användare söker efter `Cowboys vs. Broncos` klassificeras `Team` som **[!UICONTROL Type]**.

