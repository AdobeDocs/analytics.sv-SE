---
description: Beskriver hur du migrerar komponenter och projekt från Adobe Analytics till Customer Journey Analytics.
title: Migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics
feature: Admin Tools
exl-id: 49c7e47a-464b-4465-9b30-d77f886ca6dc
source-git-commit: 9e3c82214256a37df311f31c886a52f1ec8398b5
workflow-type: tm+mt
source-wordcount: '1453'
ht-degree: 0%

---

# Migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics

Adobe Analytics-administratörer kan migrera Adobe Analytics-projekt och tillhörande komponenter till Customer Journey Analytics.

Migreringsprocessen omfattar:

* Återskapande av Adobe Analytics-projekt i Customer Journey Analytics.

* Mappa mått och mätvärden från Adobe Analytics rapporteringsprogram till mått och mätvärden i datavyer i Customer Journey Analytics.

  Vissa dimensioner och mätvärden mappas automatiskt, andra måste du manuellt mappa som en del av migreringsprocessen. Segment migreras också, men de behöver inte mappas som en del av migreringsprocessen.

  Alla migrerade komponenter visas i migreringssammanfattningen när migreringen är klar.

## Förbereda för migrering

Innan du migrerar några projekt till Customer Journey Analytics bör du lära dig mer om hur du migrerar projekt i [Förbered för att migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).

## Migrera Adobe Analytics-projekt till Customer Journey Analytics

>[!IMPORTANT]
>
>Innan du migrerar några projekt till Customer Journey Analytics enligt beskrivningen i det här avsnittet bör du lära dig mer om hur du migrerar projekt i [Förbered för att migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).
>
>**Alla dimensioner eller mätvärden som du mappar är permanenta, både för det här projektet och för alla framtida projekt som migreras i hela IMS-organisationen, oavsett vilken användare som utför migreringen. Dessa mappningar kan inte ändras eller ångras förutom genom att kontakta kundtjänst.**

1. I Adobe Analytics väljer du fliken [!UICONTROL **Admin**] och sedan [!UICONTROL **All admin**].

1. Välj [!UICONTROL **Komponentmigrering**] under [!UICONTROL **Datakonfiguration och samling**].

1. Leta reda på det projekt som du vill migrera. Du kan filtrera, sortera och söka i projektlistan.

   Som standard visas endast projekt som delas med dig. Om du vill visa alla projekt i organisationen väljer du ikonen **Filter** , expanderar [!UICONTROL **Andra filter**] och väljer [!UICONTROL **Visa alla**] . (Mer information om filtrering, sortering och sökning i projektlistan finns i [Filtrera, sortera och söka i listan med projekt](#filter-sort-and-search-the-list-of-projects).)

1. För musen över projektet som du vill migrera och välj sedan ikonen **Migrera** ![Migrera projekt](assets/migrate.svg) .

   eller

   Markera det projekt som du vill migrera och välj sedan [!UICONTROL **Migrera till Customer Journey Analytics**].

   Du kan bara välja ett projekt åt gången för migrering.

   Dialogrutan [!UICONTROL **Migrera project_name till Customer Journey Analytics**] visas.

   <!-- add screenshot -->

1. I fältet [!UICONTROL **Projektägare**] börjar du skriva namnet på den användare som du vill ange som projektägare i Customer Journey Analytics och markerar sedan namnet i listrutan.

   Ägaren som du anger har fullständig behörighet till projektet. Ägaren måste vara administratör i Customer Journey Analytics. Du kan ändra ägarskapet för projektet i ett senare steg.

1. Välj en rapportsvit i [!UICONTROL **Kartschemat för rapportsviter**].

1. I listrutan [!UICONTROL **Datavy**] väljer du datavyn i Customer Journey Analytics där du vill att projektet och komponenterna ska migreras.

1. Välj [!UICONTROL **Kartschema**].

1. Expandera avsnitten [!UICONTROL **Dimensioner**] och [!UICONTROL **Metrisk**] i avsnittet [!UICONTROL **Kartschema**].

   Vissa mått och mätvärden i Adobe Analytics mappas automatiskt till en dimension eller ett mätvärde i Customer Journey Analytics. Andra måste mappas manuellt.

   **Mappa dimensioner och mått automatiskt**

   >[!NOTE]
   >
   >   Om du använde WebSDK för att importera data till Adobe Experience Platform kan mått och mått inte mappas automatiskt. Mer information finns i [Förutsättningar](/help/admin/admin/component-migration/prepare-component-migration.md#prerequisites) i [Förbereda för att migrera komponenter och projekt från Adobe Analytics till Customer Journey Analytics](/help/admin/admin/component-migration/prepare-component-migration.md).

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

1. Om du vill mappa dimensioner och mått manuellt markerar du en dimension eller ett mått som innehåller en varningsikon ![varningsikon](assets/schema-warning.png). I fältet [!UICONTROL **Mappat Customer Journey Analytics-mått**] (eller fältet [!UICONTROL **Mappat Customer Journey Analytics-mått**] om du mappar en dimension) markerar du den dimension eller det mått i Customer Journey Analytics som du vill mappa till den dimension eller det mätvärde du har valt.

   ![kartdimensioner och mått](assets/schema-manual-map-drop-down.png)

   När en dimension eller ett mått har mappats försvinner varningsikonen och kolumnen [!UICONTROL **Status**] ändras till [!UICONTROL **Mappad**] med en grön punkt. (Statusen [!UICONTROL **Mappad**] med en grå punkt anger att dimensionen eller måttet mappades under en tidigare migrering. Det går inte att uppdatera tidigare mappningar.)

   Upprepa den här processen för varje dimension eller mätvärde som innehåller varningsikonen.

   När alla dimensioner och mätvärden i Adobe Analytics rapportserie har mappats till en dimension eller ett mätvärde i rapportsviten Customer Journey Analytics, visas en grön bockmarkering ![bockmarkering](assets/report-suite-check.png) bredvid rapportsvitens namn i [!UICONTROL **schemat för rapportsviter**] .

1. (Villkorligt) Om projektet som du migrerar innehåller mer än en rapportsvit väljer du en annan rapportsvit i [!UICONTROL **Kartschemat för rapportsviter**] och upprepar sedan steg 6 till steg 10. <!-- double-check that the step numbers are still correct -->

1. Välj [!UICONTROL **Migrera**].

   >[!WARNING]
   >
   >   Ett varningsmeddelande visas när du har valt [!UICONTROL **Migrera**]. Innan du fortsätter bör du vara medveten om att alla dimensioner och mätvärden som du mappar är permanenta, både för det här projektet och för alla framtida projekt som migreras i hela organisationen. Om du fortsätter går det inte att ändra de mappningar du gör.

   När en migrering har slutförts ger sidan [!UICONTROL **Migreringsstatus**] en sammanfattning av vad som migrerades.

   Om migreringen misslyckas finns mer information i avsnittet [Försök igen med en misslyckad migrering](#retry-a-failed-migration) nedan.

1. (Valfritt) När ett projekt har migrerats kan du överföra ägarskapet för projektet till valfri användare i Customer Journey Analytics. Mer information finns i [Överför resurser](https://experienceleague.adobe.com/en/docs/analytics-platform/using/tools/asset-transfer/transfer-assets) i handboken för Customer Journey Analytics.

## Försök att utföra migreringen igen

Om en migrering misslyckas kan du försöka migrera igen.

Innan du försöker utföra en misslyckad migrering igen måste du ta bort alla [element som inte stöds](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html#understand-unsupported-elements-that-cause-errors) från projektet.

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
