---
title: Kom igång med marknadsföringskanaler
description: Lär dig mer om arbetsflödet för marknadsföringskanaler, den automatiska konfigurationen och hur du tillämpar mallrapportsvitsinställningar på flera rapportsviter.
feature: Marketing Channels
exl-id: 35938bf9-89ab-434f-9dc2-7a65251412ef
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 1%

---

# Kom igång med marknadsföringskanaler

>[!NOTE]
>
>För att maximera effekten av marknadsföringskanaler för Attribution och Customer Journey Analytics har vi publicerat [reviderade best practices](/help/components/c-marketing-channels/mchannel-best-practices.md).
>
>Analysadministratörer kan hantera marknadsföringskanaler för sina organisationer enligt beskrivningen i [Hantera marknadsföringskanaler](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

Marknadsföringskanaler används ofta för att ge insikter om hur besökarna kommer in på er webbplats. Ni kan anpassa era regler för kanalbearbetning för marknadsföring baserat på vilka kanaler ni vill spåra och hur ni vill spåra dem.

Marknadsföringskanalerna kretsar kring första och sista beröringsstatistik, som är komponenter i standardkonverteringsstatistik.

## Arbetsflöde för marknadsföringskanaler

![](assets/step1_icon.png) Definiera varje kanal baserat på dina affärsbehov.

Att definiera de kanaler du använder är en av de viktigaste komponenterna i marknadsföringskanalerna. Att definiera kanalerna kan kräva samarbete mellan flera personer i organisationen. Här är några frågor att tänka på:

* Använder du en betald sökning?
* Använder ni e-postkampanjer? Använder ni flera e-postkampanjer som ni vill spåra separat?
* Har ni filialer som dirigerar trafik till er webbplats? Finns det filialer som du vill spåra individuellt?
* Finns det externa kampanjer som skulle vara fördelaktiga när det gäller att spåra separat?
* Vill du samla alla sociala nätverksplatser, eller vill du spåra enskilda?
* Finns det andra kanaler som kan påverka konverteringen som du vill spåra?

En lista med rekommenderade kanaler finns i [Vanliga frågor och exempel](/help/components/c-marketing-channels/c-faq.md). Skapa en lista med kanaler som du vill använda, så att det blir enklare att aktivera och definiera dem när du skapar kanaler.

![](assets/step2_icon.png) Lägg till marknadsföringskanaler på sidan [!UICONTROL Marketing Channel Manager].

När du har definierat vilka kanaler som ska spåras aktiverar du dem i **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

Se [Kanaler och regler](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md) om du vill ha viktig information om förutsättningar och begrepp.

Se [Lägg till marknadsföringskanaler](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md) för proceduren.

>[!NOTE]
>
>Om marknadsföringskanaler inte har konfigurerats tidigare visas den [automatiska konfigurationen](/help/components/c-marketing-channels/c-getting-started-mchannel.md). Den här konfigurationen innehåller flera förkonfigurerade kanaler som du kan anpassa. Adobe rekommenderar att du använder dessa regler som en mall. Om du redan har helkanalsdefinitioner kan du hoppa över den automatiska inställningen.

![](assets/step3_icon.png) Konfigurera eller förfina varje kanals regler på sidan [!UICONTROL Marketing Channel Processing Rules].

När du har skapat kanaler på sidan [!UICONTROL Marketing Channel Manager] konfigurerar du reglerna så att kanalerna kan hämta och rapportera data.

Se [Bearbetningsregler för marknadsföringskanaler](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md).

Om kanaler skapades i den automatiska konfigurationen definieras reglerna i dessa kanaler. Du kan ändra dem efter dina behov.

## Automatisk inställning för marknadsföringskanaler {#run-auto-setup}

Marketing Channel-rapporten innehåller en konfigurationssida som hjälper dig att komma igång. Det innehåller flera marknadsföringskanaler som du kan använda för att spåra. Du kan hoppa över den här konfigurationen om du känner dig trygg med att skapa kanaler och regler. Adobe rekommenderar dock att du låter guiden skapa kanalerna åt dig. Med den automatiska konfigurationen kan du se hur regler är uppbyggda eller redigera dem för egna syften. Du kan när som helst inaktivera eller ta bort de fördefinierade kanalerna.

Så här kör du den automatiska konfigurationen av marknadsföringskanalerna.

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Välj en rapportsvit på [!UICONTROL Report Suite Manager].
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   ![Stegresultat](assets/wizard.png)

   >[!NOTE]
   >
   >Sidan [!UICONTROL Marketing Channels: Auto Setup] visas automatiskt när du öppnar kanalkonfigurationsprogram i Admin Tools. (Se [Marketing Channel Manager](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).) Den här sidan visas inte om rapportsviten innehåller en eller flera marknadsföringskanaler. Du kan inte komma åt den här sidan igen om du inte väljer en annan rapportsvit som inte innehåller marknadsföringskanaler.

1. Kontrollera att de kanaler som du vill skapa är markerade.

   När du väljer det här alternativet är **[!UICONTROL Email]**, **[!UICONTROL Display]** och **[!UICONTROL Affiliate]** obligatoriska fält.

1. Klicka på **[!UICONTROL Save]**.

## Använd mallrapportsvitsinställningar på flera rapportsviter

Så här använder du en huvudrapportsserie som mall för att testa konfigurationen av marknadsföringskanalen. Du kan spara tid genom att använda den här mallen på en eller flera produktionsrapportsviter i en massuppdatering. Du utför den här uppgiften för kanaler och regeluppsättningar separat.

>[!NOTE]
>
>Använd kanaler från en mall innan du använder regeluppsättningar. Kanalerna måste vara desamma i alla rapportsviter när du utför den här proceduren.

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. På sidan **[!UICONTROL Report Suite Manager]** väljer du mallrapportsviten samt en eller flera målrapportsviter.
1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.
1. Välj en mallrapportsserie på sidan **[!UICONTROL Select Master Report Suites]**.
1. Klicka på **[!UICONTROL Save All]**.
1. Tillämpa regler från en mall på flera rapportsviter:
   1. Gå tillbaka till sidan [!UICONTROL Report Suite Manager].
   1. Välj mallrapportsviten samt en eller flera målrapportsviter.
   1. Klicka på **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.
   1. Klicka på **[!UICONTROL Save]**. Om knappen Spara är inaktiverad i det här steget kan du aktivera den genom att utöka en av reglerna.
