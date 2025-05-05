---
description: Lägg till eller aktivera marknadsföringskanaler i Marketing Channel Manager. För rapportsviter som inte har några marknadsföringskanaler kan du med en automatisk inställning skapa flera kanaler åt dig, tillsammans med deras regler. Du kan redigera fördefinierade kanaler efter dina behov eller skapa egna (upp till totalt 25).
subtopic: Marketing channels
title: Hantera marknadsföringskanaler
feature: Marketing Channels
exl-id: a768a4c2-f922-4d96-a9fb-78a1dfac04d8
role: Admin
source-git-commit: def7d071de1765acf524a638a8f8d13ae69e1a1f
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 0%

---

# Hantera marknadsföringskanaler

>[!NOTE]
>
> Allmän information om marknadsföringskanaler finns i [Kom igång med marknadsföringskanaler](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
>
> För att maximera effekten av marknadsföringskanaler för attribuering och Customer Journey Analytics har vi publicerat [reviderade best practices](/help/components/c-marketing-channels/mchannel-best-practices.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

Lägg till eller aktivera marknadsföringskanaler i Marketing Channel Manager. För rapportsviter som inte har några marknadsföringskanaler kan du med en automatisk inställning skapa flera kanaler åt dig, tillsammans med deras regler. Du kan redigera fördefinierade kanaler efter dina behov eller skapa egna (upp till totalt 25).

Att lägga till kanaler på sidan [!UICONTROL Marketing Channels] görs oberoende av hur regler skapas på sidan [Bearbetningsregler för marknadsföringskanaler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md). Du kopplar regler till kanaler när du skapar regeln.

Här följer riktlinjer för hur du skapar kanaler:

* Planera i förväg genom att skapa en lista över alla era kanaler, så att alla era besökarträffar kategoriseras i rätt kanal.
* Inkludera kanaler för kategorierna av [interna](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md) träffar.
* Inkludera en&quot;övriga kampanjer&quot;-kanal som kan användas som en catch-all-kanal och placeras efter betalda kanaler och före organiska kanaler.


## Förutsättningar {#prereqs}

* Ställ in åtkomst till dimensionerna för marknadsföringskanalen.

  Se [Behörigheter för marknadsföringskanaler](/help/components/c-marketing-channels/c-channel-report-access.md).

## Lägg till marknadsföringskanaler {#add-mktg-channels}

Lägg till marknadsföringskanaler i Marketing Channel Manager.

>[!NOTE]
>
>Du kan inte ta bort en kanal. Om du inte vill använda en kanal kan du inaktivera den eller byta namn på den och bevara den för senare bruk.

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Välj en rapportsvit på sidan [!UICONTROL Report Suite Manager].

   Om du väljer flera rapportsviter väljer du en mall som kopierar inställningar från mallen till de valda rapportsviterna.

   Se [Använda inställningar för mallrapportsviter på flera rapportsviter](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   Om inga kanaler har definierats för rapportsviten visas sidan [Automatisk inställning](/help/components/c-marketing-channels/c-getting-started-mchannel.md) .

1. Klicka på **[!UICONTROL Add Channel]** på sidan [!UICONTROL Marketing Channel Manager].

   Det här alternativet är inte tillgängligt när 25 kanaler har definierats.

1. Klicka på **[!UICONTROL Save.]**
1. Klicka på **[!UICONTROL Marketing Channel Processing Rules]** om du vill konfigurera regler för kanalen.

   Se [Skapa bearbetningsregler för marknadsföringskanaler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md).

## Använda kanalinställningar {#mktg-channel-mgr}

Det finns olika inställningar som kan användas för varje kanal på sidan [!UICONTROL Marketing Channel Manager].

| Fält | Definition |
|--- |--- |
| Aktiverad | Aktiverar eller inaktiverar den här marknadsföringskanalen. |
| Kanalnamn | Marknadsföringskanalens egna namn. |
| Åsidosätt sista tryckkanalen | Gör att du kan välja om du vill åsidosätta en befintlig, beständig sista-beröringskanal med den valda kanalen. Om du markerar den här kryssrutan åsidosätts en befintlig sista-beröringskanal av alla kanaler (inklusive Direkt och Intern). Resultatet är att konverteringen tilldelas en kanal som kanske inte förtjänar någon kredit. Det här alternativet kan till exempel säkerställa att direktkanalen inte får krediter för konvertering om användaren tidigare har förvärvats via den naturliga sökkanalen. |
| Kanaluppdelning | Gör att du kan dela upp en kanal med det här värdet. Du kan lägga till möjliga kanaluppdelningar (delkanaler) när du skapar [klassificeringar av marknadsföringskanaler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md). |
| Typ | Anger hur användaren kom till din plats. Du kan välja Online eller Offline. Använd onlinekanaler för besökare som kommer via en sökmotor eller e-postkampanj. Offlinekanaler gäller besökare som har hittat er webbplats via tidningskuponger eller tidningsannonser. Offlinekanaler inkluderar vanligtvis data som importerats via rapportering av datakällor. Se [Datakällor](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=sv-SE). Se [Lägg till offlinedata](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |

### Åsidosätta bästa praxis

Det är bäst att avmarkera alternativet för att åsidosätta sista-beröringen för direktkanaler och interna kanaler, så att de inte kan ta åt sig kredit från andra beständiga sista beröringskanaler (eller varandra).

![](assets/int-channel2.png)

## Definiera kanalregler

Skapa kanalerna och de underliggande reglerna som bearbetar data innan kanaler och kanaldata kan visas i rapporten. Du kan också ange hur länge du vill att [besökarperioden](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md) ska vara.

Adobe tillhandahåller flera fördefinierade kanaler under en [automatisk konfiguration](/help/components/c-marketing-channels/c-getting-started-mchannel.md) som du kan redigera efter dina behov. Du kan dessutom ändra den här konfigurationen och definiera anpassade regler i [Bearbetningsregler för marknadsföringskanaler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md).

>[!NOTE]
>
>Adobe rekommenderar att du skapar rapporten i en rapportsserie som du kan använda som mall för testningsändamål. Du kan använda mallen för att tillämpa kanal- och regeluppsättningar globalt på en eller flera produktionsrapportsviter.
>
>Se [Tillämpa inställningar för mallrapportsviten på flera rapportsviter](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
