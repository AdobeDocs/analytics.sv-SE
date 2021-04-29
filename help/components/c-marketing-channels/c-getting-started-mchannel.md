---
title: Kom igång med marknadsföringskanaler
description: Lär dig mer om arbetsflödet för marknadsföringskanaler, den automatiska konfigurationen och hur du tillämpar mallrapportsvitsinställningar på flera rapportsviter.
translation-type: tm+mt
source-git-commit: 7202a49dda7c3ef4f4b535476d3cf637b9e9f7f6
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 2%

---


# Kom igång med marknadsföringskanaler

>[!NOTE]
>
>För att maximera effekten av marknadsföringskanalerna för Attribution IQ och Customer Journey Analytics har vi publicerat [reviderade best practices](/help/components/c-marketing-channels/mchannel-best-practices.md).

Marknadsföringskanaler används ofta för att ge insikter om hur besökarna kommer in på er webbplats. Ni kan anpassa era regler för kanalbearbetning för marknadsföring baserat på vilka kanaler ni vill spåra och hur ni vill spåra dem.

Marknadsföringskanalerna kretsar kring första och sista beröringsstatistik, som är komponenter i standardkonverteringsstatistik.

## Arbetsflöde för marknadsföringskanaler

![](assets/step1_icon.png) Definiera varje kanal utifrån era affärsbehov.

Att definiera de kanaler du använder är en av de viktigaste komponenterna i marknadsföringskanalerna. Att definiera kanalerna kan kräva samarbete mellan flera personer i organisationen. Här är några frågor att tänka på:

* Använder du en betald sökning?
* Använder ni e-postkampanjer? Använder ni flera e-postkampanjer som ni vill spåra separat?
* Har ni filialer som dirigerar trafik till er webbplats? Finns det filialer som du vill spåra individuellt?
* Finns det externa kampanjer som skulle vara fördelaktiga när det gäller att spåra separat?
* Vill du samla alla sociala nätverksplatser, eller vill du spåra enskilda?
* Finns det andra kanaler som kan påverka konverteringen som du vill spåra?

En lista över rekommenderade kanaler finns i [Vanliga frågor och exempel](/help/components/c-marketing-channels/c-faq.md). Skapa en lista med kanaler som du vill använda, så att det blir enklare att aktivera och definiera dem när du skapar kanaler.

![](assets/step2_icon.png) Lägg till marknadsföringskanaler på  [!UICONTROL Marketing Channel Manager] sidan.

När du har definierat vilka kanaler som ska spåras aktiverar du dem i **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

Se [Kanaler och regler](/help/components/c-marketing-channels/c-channels.md) för viktig information om förutsättningar och begrepp.

Se [Lägg till marknadsföringskanaler](/help/components/c-marketing-channels/c-channels.md) för proceduren.

>[!NOTE]
>
>Om marknadsföringskanaler inte har konfigurerats tidigare visas [den automatiska konfigurationen](/help/components/c-marketing-channels/c-getting-started-mchannel.md). Den här konfigurationen innehåller flera förkonfigurerade kanaler som du kan anpassa. Adobe rekommenderar att du använder dessa regler som en mall. Om du redan har helkanalsdefinitioner kan du hoppa över den automatiska inställningen.

![](assets/step3_icon.png) Konfigurera eller förfina varje kanals regler på  [!UICONTROL Marketing Channel Processing Rules] sidan.

När du har skapat kanaler på sidan [!UICONTROL Marketing Channel Manager] konfigurerar du reglerna så att kanalerna kan hämta och rapportera data.

Se [Bearbetningsregler för marknadsföringskanaler](/help/components/c-marketing-channels/c-rules.md).

Om kanaler skapades i den automatiska konfigurationen definieras reglerna i dessa kanaler. Du kan ändra dem så att de passar dina behov.

## Automatisk inställning för marknadsföringskanaler {#run-auto-setup}

Marketing Channel-rapporten innehåller en konfigurationssida som hjälper dig att komma igång. Det innehåller flera marknadsföringskanaler som du kan använda för att spåra. Du kan hoppa över den här konfigurationen om du känner dig trygg med att skapa kanaler och regler. Adobe rekommenderar dock att du låter guiden skapa kanalerna åt dig. Med den automatiska konfigurationen kan du se hur regler är uppbyggda eller redigera dem för egna syften. Du kan när som helst inaktivera eller ta bort de fördefinierade kanalerna.

Så här kör du den automatiska konfigurationen av marknadsföringskanalerna.

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Välj en rapportsvit på [!UICONTROL Report Suite Manager].
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   ![Stegresultat](assets/wizard.png)

   >[!NOTE]
   >
   >Sidan [!UICONTROL Marketing Channels: Auto Setup] visas automatiskt när du öppnar kanalkonfigurationsprogram i Admin Tools. (Se [Marketing Channel Manager](/help/components/c-marketing-channels/c-channels.md).) Den här sidan visas inte om rapportsviten innehåller en eller flera marknadsföringskanaler. Du kan inte komma åt den här sidan igen om du inte väljer en annan rapportsvit som inte innehåller marknadsföringskanaler.

1. Kontrollera att de kanaler som du vill skapa är markerade.

   När du väljer det här alternativet är **[!UICONTROL Email]**, **[!UICONTROL Display]** och **[!UICONTROL Affiliate]** obligatoriska fält.

1. Klicka på **[!UICONTROL Save]**.

## Använd mallrapportsvitsinställningar på flera rapportsviter

Så här använder du en överordnad rapportsvit som mall för att testa konfigurationen av marknadsföringskanalen. Du kan spara tid genom att använda den här mallen på en eller flera produktionsrapportsviter i en massuppdatering. Du utför den här uppgiften för kanaler och regeluppsättningar separat.

>[!NOTE]
>
>Använd kanaler från en mall innan du använder regeluppsättningar. Kanalerna måste vara desamma i alla rapportsviter när du utför den här proceduren.

1. Kontrollera att Marketing Channel-rapporten är aktiverad för valda rapportsviter. Kontohanteraren utför det här steget.
1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. På sidan **[!UICONTROL Report Suite Manager]** väljer du mallrapportsviten samt en eller flera målrapportsviter.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.
1. Välj en mallrapportsserie på **[!UICONTROL Select Master Report Suites]**-sidan.
1. Klicka på **[!UICONTROL Save All]**.
1. Tillämpa regler från en mall på flera rapportsviter:
   1. Gå tillbaka till sidan [!UICONTROL Report Suite Manager].
   1. Välj mallrapportsviten samt en eller flera målrapportsviter.
   1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.
   1. Klicka på **[!UICONTROL Save]**. Om knappen Spara är inaktiverad i det här steget kan du aktivera den genom att utöka en av reglerna.

