---
description: Med hjälp av etikettrapportsvitdata kan du tilldela identiteter, känslighet och datastyrningsetiketter till varje variabel i en viss rapportserie. Se till att du först bekanta dig med etiketterna och deras definitioner.
title: Etikettrapportsdata
uuid: a694851c-8933-496e-9118-113cc38cba8a
translation-type: tm+mt
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

---


# Etikettrapportsdata

Med hjälp av etikettrapportsvitdata kan du tilldela identiteter, känslighet och datastyrningsetiketter till varje variabel i en viss rapportserie. Se till att du först bekanta dig med etiketterna och deras definitioner.

> [!NOTE] Kom ihåg att etiketter måste granskas varje gång en ny rapportserie skapas eller när en ny variabel aktiveras i en befintlig rapportserie. Du kan också behöva granska etiketten när nya lösningar är aktiverade, eftersom de kan visa nya variabler som kan kräva etiketter. En omimplementering av dina mobilappar eller webbplatser kan ändra det sätt på vilket befintliga variabler används, vilket också kan göra det nödvändigt att uppdatera etiketterna.

## Tilldela eller redigera etiketter för rapportsviten {#section_39F829F35A274EACA532E2F6FF392996}

**Exempel**: Som registeransvarig planerar du att samla in e-postadresser och cookie-ID:n från registrerade för att behandla deras förfrågningar om dataskydd. Dessa cookie-ID:n lagras i en rapportserie i Adobe Analytics. Om du vill skapa en etikett för e-postadresser och cookie-ID:n måste du använda Adobe Cloud-plattformens ramverk för märkning och framtvingad användning av data (DULE) i Analytics.

1. Navigera till **[!UICONTROL Admin]** > **[!UICONTROL Data Governance]** > **[!UICONTROL (select report suite)]** i Analytics ![](assets/privacy_rs_settings.png)

1. Välj vilken grupp av variabler du vill etikettera.

   ![](assets/variables.png)

   * **Standarddimensioner** (färdiga Adobe Analytics-dimensioner)
   * **Standardvärden** (Adobe Analytics-statistik direkt)
   * **Konverteringshändelser** (anpassade lyckade händelser)
   * **Merchandising Conversion Dimensions** (Merchandising eVars)
   * **Konverteringsdimensioner** (icke-marknadsförande eVars)
   * **Anpassade trafikdimensioner** (props)
   * **Lösningsdimensioner och händelser** (dimensioner/händelser relaterade till lösningar som mobilt, video, aktivitetskarta osv. och integreringar med lösningar som Adobe Campaign, Adobe Experience Manager, Advertising Cloud osv.)
   * **Databearbetningsdimensioner** (variabler som inte exponeras direkt i rapporter via Adobe Analytics-gränssnittet, men som är tillgängliga för dig via dataflöden och/eller datalagerbegäranden)

1. (Valfritt) Klicka på informationsikonen (i) bredvid varje variabel för att bättre förstå de vanligaste värdena under de senaste 90 dagarna. (Den här funktionen är inte tillgänglig för databearbetningsdimensioner eftersom de inte är tillgängliga i analysgränssnittet.)

   ![](assets/info.png)

1. Markera en eller flera variabler genom att klicka på deras kryssruta och markera sedan **[!UICONTROL Edit]** ikonen (till höger) för att redigera en eller flera variabler.

   ![](assets/edit.png)

1. Dialogrutan **Identitetsdataetiketter** öppnas automatiskt. Dessa etiketter klassificerar data som kan användas fristående eller tillsammans med andra data för att identifiera eller möjliggöra direktkontakt med en individ. Mer information om dessa alternativ finns i [Identity Data Labels (DULE).](/help/admin/c-data-governance/gdpr-labels.md#identity-data-labels)

   >[!NOTE]
   >
   >DULE-ramverket (Data Usage Labeling &amp; Enforcement) är utformat för att ge ett enhetligt sätt att samla in, kommunicera och använda metadata om data i hela Adobe Experience Cloud. Metadata hjälper personuppgiftsansvariga att ange vilka data som är personuppgifter, vilka data som är känsliga och vilka avtalsbegränsningar som är kopplade till data.

   ![](assets/identity_labels.png)

1. Öppna avsnittet **Känsliga data** för att ange känsliga dataetiketter, som kategoriserar geolokaliseringsdata. Mer information om de här alternativen finns i [Känsliga dataetiketter (DULE).](/help/admin/c-data-governance/gdpr-labels.md#sensitive-data-labels)

   ![](assets/sensitive_data.png)

1. Öppna avsnittet Data Privacy Data för att ange etiketter för **datastyrning** . I det här avsnittet får Adobe instruera om hur varje variabel ska hanteras för att få tillgång till och ta bort data, samt om vilka variabler som ska genomsökas för att hitta ID:n för registrerade personer för dessa förfrågningar. Mer information om de här alternativen finns i [Datastyrningsetiketter (Dataintegritet).](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels)

   ![](assets/privacy_labels.png)

1. Klicka **[!UICONTROL Apply]** när du är klar med alla etiketter.

## Kopiera etiketter till rapportsviter {#section_7C6FDAFF049F4126B84F6261F72668EE}

Om du vill använda samma sekretessinställningar för DULE/Data för fler än en rapportserie kan du göra så här:

1. Markera variabelgruppen (standarddimensioner, konverteringsdimensioner osv.) som innehåller variabeln som du vill kopiera. Observera att du bara kan kopiera etiketterna för en grupp med variabler åt gången.
1. Markera några eller alla variabler i den här gruppen.
1. Klicka **[!UICONTROL Copy Labels to Report Suite(s)]** längst upp till höger i dialogrutan Datastyrning.

   ![](assets/apply_as_template.png)

1. Markera antingen **[!UICONTROL Select All]** för att kopiera etiketter för de valda variablerna till alla rapportsviter eller välj de enskilda rapportsviter som du vill kopiera etiketterna till.

   >[!IMPORTANT]
   >
   >Kom ihåg att alla rapporteringsprogram du väljer måste mappas till din Experience Cloud-organisation.

   När du kopierar etiketterna för en variabel eller variabeluppsättning till en annan rapportserie, flyttas kopian till variabeln på motsvarande plats i målrapportsviten. För standarddimensioner, standardmått, lösningsdimensioner samt händelser och databearbetningsdimensioner kopieras etiketterna till variabeln med **samma namn** i målrapportsviten.

   För Conversion Variables (eVars), Merchandising Conversion Dimensions och Custom Traffic Dimensions (props) kommer dock kopian att skickas till variabeln med **samma nummer** i målrapportsviten. eVar12 kopieras till exempel till eVar12 i alla målrapportsviter. Namnen på dessa variabler ignoreras när kopians mål bestäms. Om motsvarande variabel inte är aktiverad i målrapportsviten misslyckas kopieringen för den variabeln.

   När du kopierar etiketterna för klassificeringar som definierats för en variabel kopieras etiketterna till en klassificering för motsvarande variabel i målrapportsviten (t.ex. eVar7 till eVar7) som har ett namn som är identiskt med den klassificering som kopieras. I annat fall kommer kopian för den klassificeringens etiketter att misslyckas.

   Ett statusmeddelande visas när en uppsättning etiketter har tillämpats. Statusmeddelandet innehåller namnen på de målvariabler eller -klassificeringar och deras rapportsviter för vilka kopieringen misslyckades.

   >[!IMPORTANT]
   >
   >Du bör alltid kontrollera målrapportsviterna för att säkerställa att etiketterna som kopieras över är korrekta. Detta är särskilt viktigt för variabler som har ID- eller DEL-etiketter.

1. Klicka på **[!UICONTROL Apply]**.

