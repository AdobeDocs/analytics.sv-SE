---
description: Lägg till eller aktivera marknadsföringskanaler i Marketing Channel Manager. För rapportsviter som inte har några marknadsföringskanaler kan du med en automatisk inställning skapa flera kanaler åt dig, tillsammans med deras regler. Du kan redigera fördefinierade kanaler efter dina behov eller skapa egna (upp till totalt 25).
subtopic: Marketing channels
title: Hantera marknadsföringskanaler
feature: Marketing Channels
exl-id: a768a4c2-f922-4d96-a9fb-78a1dfac04d8
source-git-commit: bf0a4d4436da5f6a5ce09fbf7a1f03ef8bcc7094
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 1%

---

# Hantera marknadsföringskanaler

>[!NOTE]
>
> Allmän information om marknadsföringskanaler finns på [Kom igång med marknadsföringskanaler](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
>
> För att maximera effekten av marknadsföringskanalerna för Attribution IQ och Customer Journey Analytics har vi publicerat några [reviderad bästa praxis](/help/components/c-marketing-channels/mchannel-best-practices.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

Lägg till eller aktivera marknadsföringskanaler i Marketing Channel Manager. För rapportsviter som inte har några marknadsföringskanaler kan du med en automatisk inställning skapa flera kanaler åt dig, tillsammans med deras regler. Du kan redigera fördefinierade kanaler efter dina behov eller skapa egna (upp till totalt 25).

Lägga till kanaler i [!UICONTROL Marketing Channels] sidan görs oberoende av hur regler skapas på [Bearbetningsregler för marknadsföringskanal](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md) sida. Du kopplar regler till kanaler när du skapar regeln.

Här följer riktlinjer för hur du skapar kanaler:

* Planera i förväg genom att skapa en lista över alla era kanaler, så att alla era besökarträffar kategoriseras i rätt kanal.
* Inkludera kanaler för kategorierna av [Intern](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md) träffar.
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
1. På [!UICONTROL Report Suite Manager] väljer du en rapportsvit.

   Om du väljer flera rapportsviter väljer du en mall som kopierar inställningar från mallen till de valda rapportsviterna.

   Se [Använd mallrapportsvitsinställningar på flera rapportsviter](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   Om din rapportsvit inte har definierade kanaler [Automatisk inställning](/help/components/c-marketing-channels/c-getting-started-mchannel.md) visas.

1. På [!UICONTROL Marketing Channel Manager] sida, klicka **[!UICONTROL Add Channel]**.

   Det här alternativet är inte tillgängligt när 25 kanaler har definierats.

1. Klicka på **[!UICONTROL Save.]**
1. Om du vill konfigurera regler för kanalen klickar du på **[!UICONTROL Marketing Channel Processing Rules]**.

   Se [Skapa regler för bearbetning av marknadsföringskanal](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md).

## Använda kanalinställningar {#mktg-channel-mgr}

Det finns olika inställningar som kan användas för varje kanal på [!UICONTROL Marketing Channel Manager] sida.

| Fält | Definition |
|--- |--- |
| Aktiverad | Aktiverar eller inaktiverar den här marknadsföringskanalen. |
| Kanalnamn | Marknadsföringskanalens egna namn. |
| Åsidosätt sista tryckkanalen | Gör att du kan välja om du vill åsidosätta en befintlig, beständig sista-beröringskanal med den valda kanalen. Om du markerar den här kryssrutan åsidosätts en befintlig sista-beröringskanal av alla kanaler (inklusive Direkt och Intern). Resultatet är att konverteringen tilldelas en kanal som kanske inte förtjänar någon kredit. Det här alternativet kan till exempel säkerställa att direktkanalen inte får krediter för konvertering om användaren tidigare har förvärvats via den naturliga sökkanalen. |
| Kanaluppdelning | Gör att du kan dela upp en kanal med det här värdet. Du kan lägga till möjliga kanaluppdelningar (delkanaler) när du skapar [klassificeringar av marknadsföringskanaler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md). |
| Typ | Anger hur användaren kom till din plats. Du kan välja Online eller Offline. Använd onlinekanaler för besökare som kommer via en sökmotor eller e-postkampanj. Offlinekanaler gäller besökare som har hittat er webbplats via tidningskuponger eller tidningsannonser. Offlinekanaler inkluderar vanligtvis data som importerats via rapportering av datakällor. Se [Datakällor](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html). Se [Lägg till offlinedata](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |
| Färg | Endast rapporter och analyser: Färgen som är associerad med den här marknadsföringskanalen. Den här färgen representerar kanalen i Marketing Channel-rapporten. |

### Åsidosätta bästa praxis

Det är bäst att avmarkera alternativet för att åsidosätta sista-beröringen för direktkanaler och interna kanaler så att de inte kan ta åt sig kredit från andra beständiga sista beröringskanaler (eller varandra).

![](assets/int-channel2.png)

## Definiera kanalregler

Skapa kanalerna och de underliggande reglerna som bearbetar data innan kanaler och kanaldata kan visas i rapporten. Du kan också ange hur länge du vill ha [besökaranställningsperiod](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md) för att hålla.

Adobe tillhandahåller flera fördefinierade kanaler under en [automatisk inställning](/help/components/c-marketing-channels/c-getting-started-mchannel.md) som du kan redigera efter dina behov. Dessutom kan du ändra den här konfigurationen och definiera egna regler i [Bearbetningsregler för marknadsföringskanaler](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md).

>[!NOTE]
>
>Adobe rekommenderar att du skapar rapporten i en rapportsserie som du kan använda som mall för testningsändamål. Du kan använda mallen för att tillämpa kanal- och regeluppsättningar globalt på en eller flera produktionsrapportsviter.
>
>Se [Använd mallrapportsvitsinställningar på flera rapportsviter](/help/components/c-marketing-channels/c-getting-started-mchannel.md).