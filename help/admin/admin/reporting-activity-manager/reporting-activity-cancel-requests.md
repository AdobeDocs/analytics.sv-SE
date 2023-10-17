---
description: Lär dig mer om hur du använder Rapporteringsaktivitetshanteraren för att diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå.
title: Avbryt rapportbegäranden i Rapporteringsaktivitetshanteraren
feature: Admin Tools
source-git-commit: 4c4c38329b203b16d24ffc95f2a4580e7ca0ba0a
workflow-type: tm+mt
source-wordcount: '1333'
ht-degree: 0%

---

# Avbryt rapportbegäranden i Rapporteringsaktivitetshanteraren

{{release-limited-testing}}

The [!UICONTROL Reporting Activity Manager] gör det möjligt för administratörer att snabbt diagnostisera och avbryta rapporteringsbegäranden för att åtgärda problem med rapporteringskapaciteten under perioder med hög rapporteringsnivå.

Tänk på följande när du avbryter rapportbegäranden:

* Du kan avbryta specifika begäranden, avbryta alla begäranden från en viss användare eller avbryta alla begäranden som rör ett visst projekt.

* När du avbryter begäranden kan du även välja att begränsa efterföljande begäranden för en viss tidsperiod.

* Du kan inte avbryta en begäran om [!UICONTROL **Användare**] kolumnen i en begäran visas som [!UICONTROL **Okänd**]. När detta inträffar innebär det att användaren befinner sig i ett inloggningsföretag där du inte har administratörsbehörighet.

Mer information om Reporting Activity Manager, inklusive viktiga fördelar och behörighetskrav, finns i [Översikt över Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## Avbryt specifika begäranden

Du kan avbryta enskilda begäranden som förbrukar en stor del av rapporteringskapaciteten.

1. I Adobe Analytics går du till **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Välj den rapportsvit där du vill avbryta rapporteringsbegäranden. <!--double-check this step-->

   Mer information om tillgängliga data på den här sidan finns i [Visa rapporteringsaktivitet i Rapporteringsaktivitetshanteraren](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Välj [!UICONTROL **Begäranden**] och sedan välja en eller flera förfrågningar.

   <!-- add screenshot -->

1. Välj [!UICONTROL **Avbryt begäranden**].

   The [!UICONTROL **Avbryt _x_ rapportförfrågningar**] visas.

1. I meddelandefältet för annullering visas meddelandet som visas för användarna när deras begäranden avbryts. Ett standardmeddelande har angetts. Du kan uppdatera standardmeddelandet om du vill ha mer information.

1. (Valfritt) Begränsa framtida begäranden för en viss tidsperiod:

   1. Aktivera alternativet att [!UICONTROL **Begränsa efterföljande begäranden**]

      ![Begränsa efterföljande begäranden](assets/restrict-subsequent-requests.png)

   1. Välj bland följande alternativ:

      | Alternativ |  -funktion |
      |---------|----------|
      | [!UICONTROL **Användare &amp; projekt**] | Användare som är associerade med de valda förfrågningarna kommer tillfälligt att begränsas från att köra rapportförfrågningar för associerade projekt. |
      | [!UICONTROL **Användare**] | Användare som är associerade med de valda förfrågningarna hindras tillfälligt från att göra några rapportförfrågningar. |
      | [!UICONTROL **Projekt**] | Projekt som är associerade med de valda förfrågningarna begränsas tillfälligt från alla rapporteringsförfrågningar. |
      | [!UICONTROL **Begränsat för**] | Välj hur länge begäranden ska begränsas. Du kan välja 1 minut (standard), 5 minuter, 10 minuter, 15 minuter eller 30 minuter. <!-- double-check this --><p>Du kan inte ta bort en begränsning tidigt efter att den har angetts.</p> |

      {style="table-layout:auto"}

1. Välj [!UICONTROL **Fortsätt med annullering**].

   Ett meddelande visas i Analysis Workspace som informerar användare om att begäran har avbrutits. Mer information om hur detta visas i Analysis Workspace finns i [Upplevelse när användare öppnar en avbruten rapport](#experience-when-users-access-a-cancelled-report).

## Avbryt begäranden från användare

Du kan avbryta alla begäranden som är kopplade till en eller flera användare.

1. I Adobe Analytics går du till **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Välj den rapportsvit där du vill avbryta rapporteringsbegäranden. <!--double-check this step-->

   Mer information om tillgängliga data på den här sidan finns i [Visa rapporteringsaktivitet i Rapporteringsaktivitetshanteraren](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Välj [!UICONTROL **Användare**] och sedan en eller flera användare.

   <!-- add screenshot -->

1. Välj [!UICONTROL **Avbryt begäranden**].

   The [!UICONTROL **Avbryt _x_ rapportförfrågningar från x-användare**] visas.

1. I meddelandefältet för annullering visas meddelandet som visas för användarna när deras begäranden avbryts. Ett standardmeddelande har angetts. Du kan uppdatera standardmeddelandet om du vill ha mer information.

1. (Valfritt) Begränsa framtida begäranden för en viss tidsperiod:

   1. Aktivera alternativet att [!UICONTROL **Begränsa efterföljande begäranden**].

      ![Begränsa efterföljande begäranden per användare](assets/restrict-subsequent-requests-user.png)

   1. Välj bland följande alternativ:

      | Alternativ |  -funktion |
      |---------|----------|
      | [!UICONTROL **Användare &amp; projekt**] | De valda användarna kommer tillfälligt att hindras från att göra några rapportförfrågningar för de associerade projekten. |
      | [!UICONTROL **Användare**] | De valda användarna kommer tillfälligt att hindras från att göra några rapportförfrågningar. |
      | [!UICONTROL **Projekt**] | Projekt som är associerade med de valda användarna kommer att begränsas från alla rapportförfrågningar som görs av alla användare. |
      | [!UICONTROL **Begränsat för**] | Välj hur länge begäranden ska begränsas. Du kan välja 1 minut (standard), 5 minuter, 10 minuter, 15 minuter eller 30 minuter. <!--double-check this--> <p>Du kan inte ta bort en begränsning tidigt efter att den har angetts.</p> |

      {style="table-layout:auto"}

1. Välj [!UICONTROL **Fortsätt med annullering**].

   Ett meddelande visas i Analysis Workspace som informerar användare om att begäran har avbrutits. Mer information om hur detta visas i Analysis Workspace finns i [Upplevelse när användare öppnar en avbruten rapport](#experience-when-users-access-a-cancelled-report).

## Avbryt begäranden per projekt

Du kan avbryta alla begäranden som är kopplade till ett eller flera projekt.

1. I Adobe Analytics går du till **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Välj den rapportsvit där du vill avbryta rapporteringsbegäranden. <!--double-check this step-->

   Mer information om tillgängliga data på den här sidan finns i [Visa rapporteringsaktivitet i Rapporteringsaktivitetshanteraren](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Välj [!UICONTROL **Projekt**] och sedan välja ett eller flera projekt.

   <!-- add screenshot -->

1. Välj [!UICONTROL **Avbryt begäranden**].

   The [!UICONTROL **Avbryt _x_ rapportbegäranden från x-projekt**] visas.

1. I meddelandefältet för annullering visas meddelandet som visas för användarna när deras begäranden avbryts. Ett standardmeddelande har angetts. Du kan uppdatera standardmeddelandet om du vill ha mer information.

1. (Valfritt) Begränsa framtida begäranden för en viss tidsperiod:

   1. Aktivera alternativet att [!UICONTROL **Begränsa efterföljande begäranden**].

      ![Begränsa efterföljande begäranden per projekt](assets/restrict-subsequent-requests-project.png)

   1. Välj bland följande alternativ:

      | Alternativ |  -funktion |
      |---------|----------|
      | [!UICONTROL **Användare &amp; projekt**] | De valda projekten kommer tillfälligt att begränsas från alla rapportförfrågningar som görs av associerade användare. |
      | [!UICONTROL **Användare**] | Användare som är associerade med de valda projekten kommer inte att kunna göra några rapportförfrågningar. |
      | [!UICONTROL **Projekt**] | De valda projekten kommer tillfälligt att begränsas från alla rapportförfrågningar som görs av någon användare. |
      | [!UICONTROL **Begränsat för**] | Välj hur länge begäranden ska begränsas. Du kan välja 1 minut (standard), 5 minuter, 10 minuter, 15 minuter eller 30 minuter. <!--double-check this--> <p>Du kan inte ta bort en begränsning tidigt efter att den har angetts.</p> |

      {style="table-layout:auto"}

1. Välj [!UICONTROL **Fortsätt med annullering**].

   Ett meddelande visas i Analysis Workspace som informerar användare om att begäran har avbrutits. Mer information om hur detta visas i Analysis Workspace finns i [Upplevelse när användare öppnar en avbruten rapport](#experience-when-users-access-a-cancelled-report).

## Avbryt begäranden per program

Du kan avbryta alla begäranden som är kopplade till ett eller flera program. När du avbryter begäranden som är kopplade till ett program kan du välja att begränsa begäranden som är kopplade till det programmet ytterligare under en viss tidsperiod.

Programmen omfattar följande:

* Analysis Workspace UI
* Schemalagda projekt för arbetsyta
* Report Builder
* Användargränssnitt för byggare: segment, beräknade värden, anteckningar, målgrupper osv.
* API-anrop från 1.4 eller 2.0 API
* Intelligenta aviseringar
* Dela med alla länkar
* Alla andra program som frågar efter analysrapportmotorn

Så här avbryter du begäranden per program:

1. I Adobe Analytics går du till **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

1. Välj den anslutning där du vill avbryta rapporteringsbegäranden. <!--double-check this step-->

   Mer information om tillgängliga data på den här sidan finns i [Visa rapporteringsaktivitet i Rapporteringsaktivitetshanteraren](/help/admin/admin/reporting-activity-manager/reporting-activity.md).

1. Välj [!UICONTROL **Program**] och sedan ett eller flera program.

   <!-- add screenshot -->

1. Välj [!UICONTROL **Avbryt begäranden**].

   The [!UICONTROL **Avbryt _x_ rapportbegäranden från x-projekt**] visas.

1. I meddelandefältet för annullering visas meddelandet som visas för användarna när deras begäranden avbryts. Ett standardmeddelande har angetts. Du kan uppdatera standardmeddelandet om du vill ha mer information.

1. (Valfritt) Begränsa framtida begäranden för en viss tidsperiod:

   1. Aktivera alternativet att [!UICONTROL **Begränsa efterföljande begäranden**]

      ![Begränsa efterföljande begäranden efter program](assets/restrict-subsequent-requests-application.png)

   1. Välj bland följande alternativ:

      | Alternativ |  -funktion |
      |---------|----------|
      | [!UICONTROL **Användare &amp; projekt**] | De valda programmen kommer tillfälligt att begränsas från alla rapportförfrågningar som görs av associerade användare och projekt.<p>Det här är det minst restriktiva alternativet.</p> |
      | [!UICONTROL **Användare**] | Användare som är associerade med de valda programmen kommer inte att kunna göra några rapportförfrågningar. |
      | [!UICONTROL **Projekt**] | Projekt som är associerade med de valda programmen kommer att begränsas från alla rapportförfrågningar som görs av alla användare. |
      | [!UICONTROL **Begränsat för**] | Välj hur länge begäranden ska begränsas. Du kan välja 1 minut (standard), 5 minuter, 10 minuter, 15 minuter eller 30 minuter. <!--double-check this--> <p>Du kan inte ta bort en begränsning tidigt efter att den har angetts.</p> |

      {style="table-layout:auto"}

1. Välj [!UICONTROL **Fortsätt med annullering**].

   Ett meddelande visas i programmet (t.ex. Analysis Workspace) som informerar användarna om att begäran har avbrutits. Mer information om hur detta visas i Analysis Workspace finns i [Upplevelse när användare öppnar en avbruten rapport](#experience-when-users-access-a-cancelled-report).

## Upplevelse när användare öppnar en avbruten rapport

I Analysis Workspace visas följande meddelanden när användare försöker få åtkomst till en rapport eller visualisering som påverkas av en annullering:

### Meddelande i projektet

När användare försöker komma åt ett projekt som påverkas av en annullering visas ett meddelande som informerar dem om att rapporten är tillfälligt begränsad:

![Meddelande om avbrutet projekt](assets/workspace-canceled-report.png)

### Meddelande om visualiseringen

När en användare försöker få åtkomst till en visualisering som påverkas av en annullering visas ett meddelande som informerar användaren om att databearbetningen för rapporten är tillfälligt begränsad:

![Meddelande om annullering av visualisering](assets/workspace-cancelled-visualization.png)