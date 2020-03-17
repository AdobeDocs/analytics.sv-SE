---
description: Lägg till eller aktivera marknadsföringskanaler i Marketing Channel Manager. För rapportsviter som inte har några marknadsföringskanaler kan du med en automatisk inställning skapa flera kanaler åt dig, tillsammans med deras regler. Du kan redigera fördefinierade kanaler efter dina behov eller skapa egna (upp till totalt 25).
subtopic: Marketing channels
title: Hantera marknadsföringskanaler
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: c10a12781a8fe52b7b897cd337dc686aa0bbb240

---


# Hantera marknadsföringskanaler

Lägg till eller aktivera marknadsföringskanaler i Marketing Channel Manager. För rapportsviter som inte har några marknadsföringskanaler kan du med en automatisk inställning skapa flera kanaler åt dig, tillsammans med deras regler. Du kan redigera fördefinierade kanaler efter dina behov eller skapa egna (upp till totalt 25).

Här följer riktlinjer för hur du skapar kanaler:

* Planera i förväg genom att skapa en lista över alla era kanaler, så att alla era besökarträffar kategoriseras i rätt kanal.
* Inkludera alltid kanaler för kategorierna med [interna](/help/components/c-marketing-channels/c-faq.md) träffar och [direktträffar](/help/components/c-marketing-channels/c-faq.md) .

Att lägga till kanaler på [!UICONTROL Marketing Channels] sidan görs oberoende av hur regler skapas på sidan Bearbetningsregler för [marknadsföringskanaler](/help/components/c-marketing-channels/c-rules.md) . Du kopplar regler till kanaler när du skapar regeln.

## Lägg till marknadsföringskanaler {#add-mktg-channels}

Lägg till marknadsföringskanaler i Marketing Channel Manager.

> [!NOTE] Du kan inte ta bort en kanal. Om du inte vill använda en kanal kan du inaktivera den eller byta namn på den och bevara den för senare bruk.

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Välj en rapportsvit på [!UICONTROL Report Suite Manager] sidan.

   Om du väljer flera rapportsviter väljer du en mall som kopierar inställningar från mallen till de valda rapportsviterna.

   Se [Använda inställningar för mallrapportsviter på flera rapportsviter](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   Om det inte finns några definierade kanaler för rapportsviten visas sidan [Automatisk inställning](/help/components/c-marketing-channels/c-getting-started-mchannel.md) .

1. På [!UICONTROL Marketing Channel Manager] sidan klickar du på **[!UICONTROL Add Channel]**.

   Det här alternativet är inte tillgängligt när 25 kanaler har definierats.

1. Klicka på **[!UICONTROL Save.]**
1. Om du vill konfigurera regler för kanalen klickar du på **[!UICONTROL Marketing Channel Processing Rules]**.

   Se [Skapa regler](/help/components/c-marketing-channels/c-rules.md)för bearbetning av marknadsföringskanaler.

## Marketing Channel Manager - gränssnittsdefinitioner {#mktg-channel-mgr}

Fältdefinitioner för [!UICONTROL Marketing Channel Manager] sidan.

| Fält | Definition |
|--- |--- |
| Aktiverad | Aktiverar eller inaktiverar den här marknadsföringskanalen. |
| Kanalnamn | Marknadsföringskanalens egna namn. |
| Åsidosätt sista tryckkanalen | Gör att du kan välja om du vill åsidosätta en befintlig, beständig sista-beröringskanal med den valda kanalen. Om du markerar den här kryssrutan åsidosätts en befintlig sista-beröringskanal av alla kanaler (inklusive Direkt och Intern). Resultatet är att konverteringen tilldelas en kanal som kanske inte förtjänar någon kredit. Det här alternativet kan till exempel säkerställa att direktkanalen inte får krediter för konvertering om användaren tidigare har förvärvats via den naturliga sökkanalen. |
| Kanaluppdelning | Gör att du kan dela upp en kanal med det här värdet. Du kan lägga till möjliga kanaluppdelningar (delkanaler) när du skapar [marknadsföringskanalklassificeringar](/help/components/c-marketing-channels/classifictions-mchannel.md). |
| Typ | Anger hur användaren kom till din plats. Du kan välja Online eller Offline. Använd onlinekanaler för besökare som kommer via en sökmotor eller e-postkampanj. Offlinekanaler gäller besökare som har hittat er webbplats via tidningskuponger eller tidningsannonser. Offlinekanaler inkluderar vanligtvis data som importerats via rapportering av datakällor. Se [Datakällor](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html). Se [Lägg till offlinedata](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |
| Färg | Färgen som är associerad med den här marknadsföringskanalen. Den här färgen representerar kanalen i Marketing Channel-rapporten. |

## Definiera kanaler

Skapa kanalerna och de underliggande reglerna som bearbetar data innan kanaler och kanaldata kan visas i rapporten. Ni kan också skapa kostnads- och budgetbelopp för associerade kanaler och ange hur länge ni vill att besökarinteraktionsperioden ska vara. Du utför rapportkonfigurationsåtgärder i Admin Tools.

Tänk dig en kanal som en behållare för besök. Reglerna tilldelar besöken till rätt behållare.

![](assets/buckets_2.png)

Adobe tillhandahåller flera fördefinierade kanaler under en [automatisk konfiguration](/help/components/c-marketing-channels/c-getting-started-mchannel.md) som du kan redigera efter behov.

>[!NOTE]
>
>Adobe rekommenderar att du skapar rapporten i en rapportsserie som du kan använda som mall för testning. Du kan använda mallen för att tillämpa kanal- och regeluppsättningar globalt på en eller flera produktionsrapportsviter.
>
>Se [Använda inställningar för mallrapportssviten på flera rapportsviter](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

### Förutsättningar {#prereqs}

Kontakta kundtjänst om det behövs för att få hjälp med följande:

* Aktivera alternativet **[!UICONTROL Conversion Level]** (e-handel) för rapportsviten i administrationskonsolen (Allmänna kontoinställningar).

   Mer information finns i [Allmänna kontoinställningar](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/general-acct-settings-admin.html) i hjälpen för Analytics.

* Ställ in åtkomst till dimensionerna för marknadsföringskanalen.

   Se Behörigheter för [marknadsföringskanaler](/help/components/c-marketing-channels/c-channel-report-access.md).

* Se till att din kontohanterare har aktiverat **[!UICONTROL Channel Reports]** för din rapportsvit.

### Viktiga bearbetningsanteckningar {#important-proc-rules}

* Systemet bearbetar reglerna i den ordning som du anger, och när en regel uppfylls avbryts bearbetningen av de återstående reglerna.
* Regler kan komma åt variabler som har angetts av VISTA, men de kan inte komma åt data som har tagits bort av VISTA.
* Kanaler lagrar bara konverteringsvärden. Trafikmätvärden är inte tillgängliga.
* Två marknadsföringskanaler får aldrig någon kredit för samma event (som köp eller klick). På så sätt skiljer sig marknadsföringskanalerna från eVars (där två eVars kan få krediter för samma händelse).
* Rapporten kan bearbeta upp till 25 kanaler i taget.

