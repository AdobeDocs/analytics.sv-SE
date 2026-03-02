---
title: Konvertera äldre Report Builder-arbetsböcker
description: Lär dig hur du migrerar och konverterar äldre Report Builder-arbetsböcker till nya Report Builder. Följ steg-för-steg-instruktionerna i den här migreringsguiden om hur du sömlöst konverterar dina Adobe Analytics-baserade arbetsböcker.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 9743d7ac2a6c7e63d7a6701e60d05683c5680d36
workflow-type: tm+mt
source-wordcount: '1096'
ht-degree: 0%

---

# Konvertera äldre Report Builder-arbetsböcker

Den gamla Report Builder upphör i juni 2026. Du bör migrera dina arbetsböcker från den gamla Report Builder till den nya Report Builder. Nya Report Builder är ett bekvämt sätt att migrera arbetsböcker snabbt som har skapats med äldre Report Builder.

>[!IMPORTANT]
>
>Duplicera varje arbetsbok och byt namn på en version innan du konverterar den äldre arbetsboken. Det ser till att du alltid har en kopia av den ursprungliga arbetsboken om du behöver den.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Konvertera arbetsböcker](https://experienceleague.adobe.com/sv/docs/analytics-learn/tutorials/exporting/report-builder/upgrade-and-reschedule-workbooks){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Om du vill konvertera äldre arbetsböcker måste du först [konfigurera nya Report Builder](/help/analyze/report-builder/report-builder-setup.md).


## Öppna en äldre arbetsbok

Om du vill öppna en äldre arbetsbok kan du:

* Öppna en schemalagd äldre arbetsbok från fliken **[!UICONTROL Schedule]** i [Report Builder-hubben](report-builder-hub.md). Den här åtgärden rekommenderas för schemalagda äldre arbetsböcker. Du får alternativet att använda schemat som är associerat med den äldre arbetsboken så snart du [schemalägger den konverterade äldre arbetsboken](#schedule-a-converted-legacy-workbook).

   1. Öppna [!DNL Excel] och välj ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** i menyfliksområdet [!DNL Excel].

   1. Välj **[!UICONTROL Login]** och logga in på Report Builder.

   1. Välj **[!UICONTROL Schedule]** i [Report Builder-hubben](report-builder-hub.md).
   1. Välj fliken **[!UICONTROL Legacy]**. På fliken visas en lista över de gamla Report Builder-baserade schemalagda arbetsböcker som du har skapat.

      ![Äldre arbetsböcker](assets/upgrade-legacy-schedule.png)

   1. Välj ![SelectBox](/help/assets/icons/SelectBox.svg) för den schemalagda arbetsbok som du vill konvertera från listan och välj ![Hämta](/help/assets/icons/Download.svg). Arbetsboken hämtas och öppnas i ett nytt fönster i [!DNL Excel]. Du kan nu [konvertera den gamla Report Builder-arbetsboken](#convert-a--workbook).


* Öppna en äldre arbetsbok direkt från den lokala datorn eller nätverket. När du använder den här metoden erbjuds du inte att använda det schema som kan vara kopplat till den äldre arbetsboken. <br/>När den äldre arbetsboken är öppen i [!DNL Excel]:

   1. Välj ![AdobeLogoRedOnWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** i menyfliksfältet [!DNL Excel] .
   1. Välj **[!UICONTROL Login]** och logga in på Report Builder.
   1. [konvertera sedan den äldre arbetsboken](#convert-a-workbook).


## Konvertera en äldre arbetsbok

Så här konverterar du din gamla arbetsbok:

1. När du har öppnat en äldre arbetsbok upptäcker den nya Report Builder om arbetsboken innehåller [äldre Report Builder](/help/analyze/legacy-report-builder/home.md)-begäranden.

   ![Skärmbild av uppgraderingsrapporten för [!DNL Excel] Report Builder som visar migreringsuppgradering](assets/upgrade-workbook.png){zoomable="yes"}

1. Om en eller flera tidigare begäranden hittas klickar du på **[!UICONTROL Upgrade]** i dialogrutan **[!UICONTROL Upgrade workbook]** för att uppgradera arbetsboken.

   >[!NOTE]
   >
   >Du måste uppgradera varje begäran separat. Massuppgradering stöds inte.


1. En **[!UICONTROL Warning]**-dialogruta visas som varnar dig om ändringar i arbetsboken om du uppgraderar. Du uppmanas också att skapa en säkerhetskopia av din gamla arbetsbok innan du fortsätter.

   ![Skärmbild av uppgraderingsrapporten för [!DNL Excel] Report Builder med en migreringsvarning](assets/upgrade-warning.png){zoomable="yes"}

1. Klicka på **[!UICONTROL Proceed]** om du vill fortsätta med uppgraderingen.

   Om uppgraderingen lyckas visas ett meddelande om **[!UICONTROL The workbook upgrade is now completed]**.

   ![Skärmbild av uppgraderingsrapporten för [!DNL Excel] Report Builder som visar att migreringen har slutförts](assets/upgrade-complete.png)

   * Välj **[!UICONTROL Close]** om du vill stänga meddelandet och fortsätta arbeta i arbetsboken med uppdaterade begäranden för nya Report Builder.

   * Välj **[!UICONTROL Download upgrade report]** om du vill hämta och öppna en ny [!DNL Excel]-arbetsbok som visar resultatet av uppgraderingen. Se ett exempel nedan.

     ![Skärmbild av uppgraderingsrapporten för [!DNL Excel] Report Builder som visar migreringsrapporten &#x200B;](assets/upgrade-report.png)

Du kan nu [hantera datablocken](/help/analyze/report-builder/manage-reportbuilder.md) i arbetsboken. Dessa datablock är resultatet av uppgraderingen och ersätter dina tidigare förfrågningar från Report Builder.


## Schemalägg en konverterad äldre arbetsbok

Du kan använda schemainformationen från den äldre arbetsboken som du har hämtat och öppnat från fliken **[!UICONTROL Schedule]** i Report Builder-hubben. Det här alternativet är inte tillgängligt för äldre arbetsböcker med schemainformation som du öppnar från den lokala datorn eller nätverket.

1. Så här schemalägger du en konverterad äldre arbetsbok med ett äldre schema:

   * Välj **[!UICONTROL Send workbook]** från Report Builder-navet, eller
   * Välj **[!UICONTROL Schedule workbook]** på fliken **[!UICONTROL Workbooks]** som finns på fliken **[!UICONTROL Schedules]** i Report Builder.

1. Du kan använda schemainformationen från den äldre arbetsboken som standardinställningar för scheman.

   ![Skärmbild av [!DNL Excel] Report Builder äldre schemainställningsalternativ &#x200B;](assets/upgrade-legacy-schedule-convert.png)

   * Välj **[!UICONTROL Use]** om du vill använda äldre schemadetaljer. Schemainformationen är förifylld i gränssnittet [Skicka arbetsbok](schedule-reportbuilder.md#schedule-a-workbook).
   * Välj **[!UICONTROL Don't use]** om du inte vill använda äldre schemainformation.
   * Välj **[!UICONTROL Cancel]** om du vill avbryta.

   Välj **[!UICONTROL Remove legacy metadata from future use]** om du inte vill använda äldre schemainformation för den här arbetsboken i framtiden.


## Migrera från äldre Report Builder

Vissa funktioner i den äldre Report Builder stöds inte, stöds delvis eller implementeras på ett annat sätt i Report Builder:

* **Realtidsbegäranden**. Realtidsbegäranden stöds inte och tas bort från den konverterade äldre arbetsboken.

* **Rapportering om sökväg/bortfall**. Utfallsbegäranden stöds inte och tas bort från den konverterade äldre arbetsboken.

* **[!DNL FTP]alternativ för schemalagda rapporter**. Alternativet att schemalägga rapporter som ska skickas till en [!DNL FTP]-plats är inte längre tillgängligt.

* **Publicera arbetsbok till alternativet [!DNL Power BI] för schemalagda rapporter**. Alternativet att schemalägga rapporter till [!DNL Power BI] är inte längre tillgängligt.

* **Besökarstatistik**. Följande mått konverteras till *unika besökare* i den konverterade äldre arbetsboken, även om rapportresultatet kanske inte är en exakt matchning: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` och `visitorsyearly`. Den här konverteringen gäller även för `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` och `mobilevisitorsyearly`.

* **Automatisk omautentisering**. När du öppnar en ny [!DNL Excel]-fil måste du autentisera igen explicit. Den här omautentiseringen är en säkerhetsfunktion i funktionen [!DNL Office Add-ins].

* **Kopiera ett kalkylblad med en grupp datablock**. Så här stöder du kopian av ett kalkylblad som innehåller mer än ett datablock:

   1. Välj fliken för kalkylblad i arbetsboken [!DNL Excel] som du vill kopiera.
   1. Välj **[!UICONTROL Move or Copy...]** på snabbmenyn på fliken
   1. I dialogrutan **[!UICONTROL Move or Copy]**:
      1. Välj till vilken plats det kopierade kalkylbladet ska kopieras.
      1. Se till att du aktiverar **[!UICONTROL Create a copy]**.
      1. Välj **[!UICONTROL OK]**.
   1. Från källkalkylbladet:
      1. Markera cellområdet som omfattar alla datablock.
      1. Välj ![Kopiera](/help/assets/icons/Copy.svg) **[!UICONTROL Copy data block]** på [Report Builder-hubben](/help/analyze/report-builder/report-builder-hub.md).
   1. I målkalkylbladet:
      1. Markera cellen där du vill att det kopierade cellområdet ska klistras in.
      1. Välj ![Klistra in](/help/assets/icons/Paste.svg) **[!UICONTROL Paste data block]** på [Report Builder-hubben](/help/analyze/report-builder/report-builder-hub.md).

* **Datumintervall**. Report Builder migrerar inte formateringsalternativen **[!UICONTROL Show start and end period as]** för datumintervall som används på en radetikett för ett datumintervall i den tidigare Report Builder-versionen.

* **Medel**. Report Builder migrerar inte det valda formateringsalternativet **[!UICONTROL Average options]** (**[!UICONTROL Daily Average]** upp till **[!UICONTROL Yearly Average]**) som används på ett mätvärde i den tidigare Report Builder-versionen. Använd ett beräknat mätvärde för att ersätta det valda alternativet.

* **Lägg till/skjuta upp text**. Report Builder migrerar inte **[!UICONTROL Prepend/postpend text]** som används för ett mått i den tidigare Report Builder.

* **Delsummor**. Report Builder migrerar inte formateringsalternativet **[!UICONTROL SubTotal(this request)]** som används på ett mätvärde i den tidigare Report Builder-versionen. När du har använt **[!UICONTROL SubTotal(this request)]** i en äldre arbetsboksbegäran konverteras funktionen till **[!UICONTROL Total]**. Exempel: i ett äldre datablock med de fem översta sidnamnen där du har använt **[!UICONTROL SubTotal(Page Views)]** för att returnera summan av sidvyerna för de fem översta sidnamnen. Efter migreringen returnerar samma datablock med de fem översta sidnamnen summan av sidvyerna för *alla* sidnamn. Använd funktionen för beräknade värden för att ersätta den gamla funktionen **[!UICONTROL SubTotal]**.
