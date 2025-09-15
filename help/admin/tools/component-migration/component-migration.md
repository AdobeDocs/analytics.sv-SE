---
description: Beskriver hur du migrerar komponenter och projekt från Adobe Analytics till Customer Journey Analytics.
title: Migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics
feature: Admin Tools
exl-id: 49c7e47a-464b-4465-9b30-d77f886ca6dc
source-git-commit: ec4475cdd8f0c3e89f528bd60155caa1ca3f0645
workflow-type: tm+mt
source-wordcount: '1635'
ht-degree: 0%

---

# Migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics

Adobe Analytics-administratörer kan migrera Adobe Analytics-projekt och tillhörande komponenter till Customer Journey Analytics.

Migreringsprocessen omfattar:

* Återskapa Adobe Analytics-projekt i Customer Journey Analytics.

* Mappa mått och mätvärden från Adobe Analytics rapporteringsprogram till mått och mätvärden i Customer Journey Analytics datavyer.

  Vissa dimensioner och mätvärden mappas automatiskt, andra måste du manuellt mappa som en del av migreringsprocessen. Segment migreras också, men de behöver inte mappas som en del av migreringsprocessen.

  Alla migrerade komponenter visas i migreringssammanfattningen när migreringen är klar.

>[!NOTE]
>
>Informationen på den här sidan beskriver hur du migrerar projekt och deras associerade komponenter till användargränssnittet.
>
>Du kan också utföra migreringen med API:erna. Mer information finns i [Adobe Analytics API:er](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Analytics%202.0%20APIs). Alla API-definitioner är tillgängliga i listrutan **[!UICONTROL Select a definition]**.


## Förbereda för migrering

Innan du migrerar projekt till Customer Journey Analytics bör du läsa mer om hur du migrerar projekt i [Förbered för att migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics](/help/admin/tools/component-migration/prepare-component-migration.md).

Gör dessutom en [Adobe Analytics-inventering](/help/admin/tools/analytics-inventory.md) med verktyget som är tillgängligt för Analytics-administratörer.

## Migrera Adobe Analytics-projekt till Customer Journey Analytics

>[!NOTE]
>
>Innan du migrerar några projekt till Customer Journey Analytics enligt beskrivningen i det här avsnittet bör du lära dig mer om hur du migrerar projekt i [Förbered för att migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics](/help/admin/tools/component-migration/prepare-component-migration.md).
>
>**Alla dimensioner eller mått som du mappar gäller för det här projektet och för alla framtida projekt i hela IMS-organisationen, oavsett vilken användare som utför migreringen. Dessa mappningar kan uppdateras när framtida projekt migreras.**

1. I Adobe Analytics väljer du fliken [!UICONTROL **Admin**] och sedan [!UICONTROL **All admin**].

1. Välj [!UICONTROL **Komponentmigrering**] under [!UICONTROL **Datakonfiguration och samling**].

1. Leta reda på varje projekt som du vill migrera. Du kan filtrera, sortera och söka i projektlistan.

   Som standard visas endast projekt som delas med dig. Om du vill visa alla projekt i organisationen väljer du ikonen **Filter** , expanderar [!UICONTROL **Andra filter**] och väljer [!UICONTROL **Visa alla**] . (Mer information om filtrering, sortering och sökning i projektlistan finns i [Filtrera, sortera och söka i listan med projekt](#filter-sort-and-search-the-list-of-projects).)

1. (Villkorligt) Om du vill migrera flera projekt samtidigt markerar du kryssrutan till vänster om varje projekt som du vill migrera och väljer sedan [!UICONTROL **Migrera till Customer Journey Analytics**].

   Tänk på följande när du migrerar flera projekt:

   * Du kan välja upp till 20 projekt att migrera samtidigt.

   * Migreringsstatusen måste vara densamma för alla projekt som du migrerar.

     Om du till exempel väljer ett projekt som ska migreras och har migreringsstatusen **[!UICONTROL Not started]**, kan du inte välja ett annat projekt som har migreringsstatusen **[!UICONTROL Failed]**.

   * Du måste ange samma projektägare för alla projekt som du migrerar.

   * Dimensioner och mätvärden måste mappas till samma datavy för alla projekt som du migrerar.

   Dialogrutan [!UICONTROL **Migrera project_name till Customer Journey Analytics**] visas.

   <!-- add screenshot -->

1. (Villkorligt) Om du vill migrera ett enskilt projekt för du musen över det projekt som du vill migrera och väljer sedan ikonen **Migrera** ![Migrera projekt](assets/migrate.svg) .

   Dialogrutan [!UICONTROL **Migrera project_name till Customer Journey Analytics**] visas.

   <!-- add screenshot -->

1. I fältet [!UICONTROL **Projektägare**] börjar du skriva namnet på den användare som du vill ange som ägare till de projekt som migreras i Customer Journey Analytics och väljer sedan namnet i listrutan.

   Ägaren som du anger har fullständig hanteringsbehörighet för de migrerade projekten. Ägaren måste vara administratör i Customer Journey Analytics. Du kan ändra ägarskapet för projekten i ett senare steg.

1. Välj en rapportsvit i [!UICONTROL **Kartschemat för rapportsviter**].

1. I listrutan [!UICONTROL **Datavy**] väljer du den datavy i Customer Journey Analytics där du vill att projekten och komponenterna ska migreras.

   När du migrerar flera projekt kombineras alla projekt som du migrerar till datavymappningen.

1. Välj [!UICONTROL **Kartschema**].

1. Expandera avsnitten [!UICONTROL **Dimensioner**] och [!UICONTROL **Metrisk**] i avsnittet [!UICONTROL **Kartschema**].

   Vissa mått och mätvärden i Adobe Analytics mappas automatiskt till en dimension eller ett mätvärde i Customer Journey Analytics. Andra måste mappas manuellt.

   **Mappa dimensioner och mått automatiskt**

   >[!NOTE]
   >
   >   Om du använde WebSDK för att importera data till Adobe Experience Platform kan mått och mått inte mappas automatiskt. Mer information finns i [Förutsättningar](/help/admin/tools/component-migration/prepare-component-migration.md#prerequisites) i [Förbered migrering av komponenter och projekt från Adobe Analytics till Customer Journey Analytics](/help/admin/tools/component-migration/prepare-component-migration.md).

   Vissa mått och mätvärden i Adobe Analytics mappas automatiskt till en dimension eller ett mätvärde i Customer Journey Analytics. Du kan inte fatta några mappningsbeslut för de här dimensionerna och måtten.

   Måttet **Besök** i Adobe Analytics mappas till exempel automatiskt med måttet **Sessioner** i Customer Journey Analytics.

   Du kan välja vilken dimension eller vilket mätvärde som helst för att visa deras associerade ID:n.

   <!-- update screenshot after I can see the Status column -->

   ![Projektmigreringsschema](assets/project-migration-schema.png)

   **Mappa dimensioner och mått manuellt**

   Vissa mått och mätvärden i Adobe Analytics kan inte automatiskt mappas till en dimension eller ett mätvärde i Customer Journey Analytics.

   När en dimension eller ett mätvärde inte kan mappas automatiskt visas en orange räknare bredvid avsnittshuvudet [!UICONTROL **Dimensions**] eller [!UICONTROL **Metrics**] som anger antalet dimensioner eller mätvärden som behöver mappas manuellt. I tabellen visas en varningsikon ![varningsikon](assets/schema-warning.png) bredvid varje dimension eller mätvärde som behöver mappas manuellt.

   Dessutom står det [!UICONTROL **Inte mappat**] i kolumnen [!UICONTROL **Status**].

   <!-- update screenshot after I can see the Status column -->

   ![Manuell karta för migreringsschema](assets/schema-manual-map.png)

1. Om du vill mappa dimensioner och mått manuellt väljer du en dimension eller ett mätvärde som innehåller en varningsikon ![varningsikon](assets/schema-warning.png). I fältet [!UICONTROL **Mappat Customer Journey Analytics-mätvärde**] (eller i fältet [!UICONTROL **Mappat Customer Journey Analytics-mått**] om du mappar en dimension) väljer du den dimension eller det mätvärde i Customer Journey Analytics som du vill mappa till den dimension eller det mätvärde du valde.

   ![kartdimensioner och mått](assets/schema-manual-map-drop-down.png)

   När en dimension eller ett mått har mappats försvinner varningsikonen och kolumnen [!UICONTROL **Status**] ändras till [!UICONTROL **Mappad**] med en grön punkt. (Statusen [!UICONTROL **Mappad**] med en grå punkt anger att dimensionen eller måttet mappades under en tidigare migrering. Det går inte att uppdatera tidigare mappningar.)

   Upprepa den här processen för varje dimension eller mätvärde som innehåller varningsikonen.

   När alla dimensioner och mätvärden i Adobe Analytics rapportsserie har mappats till en dimension eller ett mätvärde i Customer Journey Analytics rapportsvit, visas en grön bockmarkering ![bockmarkering](assets/report-suite-check.png) bredvid rapportsvitens namn i [!UICONTROL **Kartschemat för rapportsviter**] .

1. (Villkorligt) Om de projekt som du migrerar innehåller mer än en rapportsvit väljer du en annan rapportsvit i [!UICONTROL **Kartschemat för rapportsviter**] och upprepar sedan steg 6 till steg 10. <!-- double-check that the step numbers are still correct -->

1. Välj [!UICONTROL **Migrera**].

   >[!WARNING]
   >
   >Ett varningsmeddelande visas när du har valt [!UICONTROL **Migrera**]. Innan du fortsätter bör du vara medveten om att alla dimensioner och mätvärden som du mappar gäller för det här projektet och för alla framtida projekt i hela IMS-organisationen, oavsett vilken användare som utför migreringen. Dessa mappningar kan uppdateras när du migrerar framtida projekt.

   När en migrering har slutförts ger sidan [!UICONTROL **Migreringsstatus**] en sammanfattning av vad som migrerades.

   Om migreringen misslyckas finns mer information i avsnittet [Försök igen med en misslyckad migrering](#retry-a-failed-migration) nedan.

1. (Valfritt) När projekten har migrerats kan du överföra ägarskapet för projekten till vilken användare som helst i Customer Journey Analytics. Mer information finns i [Överför resurser](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/tools/asset-transfer/transfer-assets) i Customer Journey Analytics Guide.

## Försök att utföra migreringen igen

Om en migrering misslyckas kan du försöka migrera igen.

Innan du försöker utföra en misslyckad migrering igen måste du ta bort alla [element som inte stöds](/help/admin/tools/component-migration/prepare-component-migration.md#understand-unsupported-elements-that-cause-errors) från projektet.

>[!NOTE]
>
>Om migreringen fortsätter att misslyckas efter ett nytt försök kontaktar du kundtjänst med projekt-ID:t. Du hittar projekt-ID:t på statussidan för migrering. <!-- when does this page display? How can they get there -->

Så här gör du om en misslyckad migrering:

1. I Adobe Analytics väljer du fliken [!UICONTROL **Admin**] och sedan [!UICONTROL **All admin**].

1. Välj [!UICONTROL **Komponentmigrering**] under [!UICONTROL **Datakonfiguration och samling**].

1. Välj [!UICONTROL **Misslyckades**] i kolumnen [!UICONTROL **Migreringsstatus**] bredvid projektet som du vill försöka igen.

   ![Kolumnen för migreringsstatus misslyckades](assets/migration-failed.png)

   Sidan [!UICONTROL **Migreringsstatus**] visas.

   Den här sidan visas också omedelbart efter att migreringsstegen som beskrivs i avsnittet [Migrera Adobe Analytics-projekt till Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics) ovan har slutförts.

1. Välj [!UICONTROL **Försök migrera igen**].

## Filtrera, sortera och söka i projektlistan

Du kan filtrera, sortera och söka i projektlistan på sidan Komponentmigrering.

### Filtrera listan med projekt

Du kan filtrera efter följande kriterier:

| Filter | Beskrivning |
|---------|----------|
| [!UICONTROL **Status**] | Flyttningens status: <ul><li>[!UICONTROL **Inte igång**]</li><li>[!UICONTROL **Startades**]</li><li>[!UICONTROL **Slutförd**]</li><li>[!UICONTROL **Misslyckades**]</li></ul>. |
| [!UICONTROL **Taggar**] | Markera eventuella taggar i listan med taggar. Endast projekt där de markerade taggarna används visas. |
| [!UICONTROL **Rapportsviten**] | Välj en rapportsvit i listan med rapportsviter. Endast projekt som använder de valda rapportsviterna visas. |
| [!UICONTROL **Ägare**] | Välj en ägare i listan över ägare. Endast projekt som ägs av de användare du väljer visas. |
| [!UICONTROL **Andra filter**] | Följande ytterligare filter är tillgängliga: <ul><li>[!UICONTROL **Min**]: Visar endast projekt där du har angetts som ägare.</li><li>[!UICONTROL **Delad med mig**]: Visar endast projekt som har delats med dig.</li><li>[!UICONTROL **Favoriter**]: Visar endast projekt som har markerats som favoriter. (Du kan markera ett projekt som en favorit på [projektstartsidan](/help/analyze/landing.md).)</li><li>[!UICONTROL **Månadsvis**]</li><li>[!UICONTROL **År**]</li></ul> |

{style="table-layout:auto"}

### Sortera listan med projekt

Du kan sortera projektlistan efter valfri kolumn.

Så här sorterar du listan med projekt:

1. Markera kolumnrubriken för den kolumn som du vill sortera efter.

1. (Valfritt) Markera samma kolumnrubrik igen om du vill kasta om sorteringsordningen.

### Söka efter ett projekt

Du kan söka i listan med projekt på sidan Komponentmigrering för att hitta det projekt som du vill migrera.

1. I sökfältet högst upp på sidan Komponentmigrering börjar du skriva namnet på projektet som du vill migrera.

1. Välj projektet när det visas i listrutan.

<!-- is there going to be a way to customize the columns that are displayed? -->
