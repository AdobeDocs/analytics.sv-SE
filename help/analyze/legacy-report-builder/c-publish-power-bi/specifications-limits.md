---
description: Begränsningar när du använder Report Builder och Microsoft Power BI.
title: Begränsningar och specifikationer
feature: Report Builder
role: User, Admin
exl-id: 4bbeec5b-64bc-4285-9f13-33b223b88834
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 0%

---

# Begränsningar och specifikationer

{{legacy-arb}}

## Power BI publiceringsbegränsningar {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>Dessa begränsningar gäller endast alternativet&quot;Publish Report Builder Requests as Power BI Dataset Tables&quot;.

* Högst 100 Report Builder-begäranden kan exporteras till Power BI per arbetsbok.
* Schemaläggningsprocessen avbryter exporten av begäranden när den 101:e begäran nås.
* Endast de första 10 000 raderna i Analytics-data skickas till Power BI per Report Builder-begäran. De återstående raderna ignoreras.

## Redigera en Report Builder-begäran efter publicering till Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>Specifikationen gäller alternativen&quot;Publish All Report Builder Requests as Power BI Dataset Tables&quot; och&quot;Publish All Formatted Tables in the Workbook as Power BI Dataset Tables&quot;.

Om du redigerar en Report Builder-begäran efter att ha publicerat den på Power BI kan det orsaka problem.

* **Fall 1**: Du publicerar en arbetsbok på Power BI och skapar en visualisering baserat på dess data. Därefter gör du ändringar i arbetsboken, vilket gör att en av kolumnerna i datauppsättningen som refereras till försvinner. Sedan publicerar du igen. Detta bryter visualiseringen i Power BI.

  **Här är ett exempel på hur visualiseringen bryts:**

   1. I Report Builder skapar du en arbetsbok med en begäran med måtten Siddimension och Sidvisning.
   2. Schemalägg den här begäran för publicering på Power BI.
   3. I Power BI skapar du en visualisering för sid- och sidvyer.
   4. Redigera nu arbetsboken genom att ta bort sidvyer från begäran.
   5. Redigera schemat med den uppdaterade arbetsboken och återpublicera begäran till Power BI.
   6. När den nya arbetsboken har skickats till Power BI

      1. Kontrollera att den har skrivit över den befintliga datauppsättningen som skapades när du först publicerade den.
      2. Kontrollera att tabellen page_1 är korrekt uppdaterad med kolumnerna Sida och Besök.
      3. Kontrollera att visualiseringen är bruten eftersom den refererar till kolumnen Sidvyer som inte längre finns i tabellen page_1.

  **Här följer ett exempel på hur visualiseringen INTE bryts:**

   1. I Report Builder skapar du en arbetsbok med en begäran med måtten Siddimension och Sidvisning.
   2. Schemalägg den här begäran för publicering på Power BI.
   3. I Power BI skapar du en visualisering för sid- och sidvyer.
   4. Redigera nu arbetsboken i Report Builder och lägg till besöksmåtten samtidigt som du behåller sid- och sidvyerna.
   5. Redigera schemat med den uppdaterade arbetsboken och återpublicera begäran till Power BI.
   6. När den nya arbetsboken har skickats till Power BI

      1. Kontrollera att den har skrivit över den befintliga datauppsättningen som skapades när du först publicerade den.
      2. Kontrollera att tabellen page_1 är korrekt uppdaterad med kolumnerna Sida, Sidvyer och Besök.
      3. Kontrollera att visualiseringen fortsätter att fungera som den ska eftersom den refererar till två kolumner som fortfarande finns i tabellen page_1.

* **Fall 2**: Du fäster ett avsnitt i arbetsboken på en instrumentpanel i Power BI och du tar senare bort det fästa avsnittet (till exempel ett diagram eller en tabell) från arbetsboken. Det här kommer att bryta visualiseringen.

## Ändra namnet på en Power BI-rapport {#section_2E7893A78B914EBFACB2B08CBD9E472E}

Som standard fylls namnet i från arbetsbokens filnamn (utan filtillägget .xlsx), förutom att blanksteg ersätts med understreck.

Kom ihåg

* Etiketten kan inte vara en kombination av bokstäver och siffror som kan vara felaktiga för en rad- och kolumnadress. A100 kan till exempel inte vara en etikett eftersom det är adressen till en cell i ett kalkylblad.
* Följande tecken är inte giltiga etiketttecken: `'#', '@', '!', '$', '^', '&', '&#42;', '` och `'~', ' '`. De ersätts med ett understreck.
* När du anger ett ogiltigt namn visas ett varningsmeddelande som föreslår ett automatiskt genererat namn. Om du klickar på **[!UICONTROL Yes]** används det här namnet. Om du klickar på **[!UICONTROL No]** kan du ange det nya namnet med hjälp av gränssnittet för den avancerade guiden.
