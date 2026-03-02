---
title: Konfigurera Report Builder
description: Lär dig med en komplett guide för installation och konfigurering av Adobe Analytics Report Builder for Excel. Stegvisa instruktioner för smidig integration.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 9d0161a9-ee7b-43a9-92ad-4079cf4b9c6c
source-git-commit: 1e893ce94ee3da46bbf22d7a90573681950d1135
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---

# Konfigurera Report Builder

I den här artikeln beskrivs kraven för att använda Report Builder för Adobe Analytics i [!DNL Microsoft] [!DNL Excel]. Och hur du installerar och konfigurerar tillägget.

## Krav

Report Builder för Adobe Analytics stöds av följande operativsystem och webbläsare.

### macOS

- macOS Version 10.x eller senare
- Alla [!DNL Microsoft] [!DNL Excel]-versioner

### Windows

- Windows 10, version 1904 eller senare
- [!DNL Excel] version 2106 eller senare

  Alla användare av Windows-skrivbordet [!DNL Excel] måste installera Microsoft Edge Webview2 för att kunna använda tillägget. Så här installerar du styrenheten:

   1. Gå till <https://aka.ms/webview2installer>.
   1. Välj och hämta Evergreen Standalone Installer.
   1. Följ installationsanvisningarna.

### Webbkontor

- Stöder alla webbläsare och versioner


## Report Builder Excel-tillägg

Du måste installera Report Builder [!DNL Excel]-tillägget för att kunna använda [!DNL Report Builder] för Adobe Analytics. När du har installerat Report Builder [!DNL Excel]-tillägget kan du komma åt Report Builder från en öppen [!DNL Excel]-arbetsbok.

### Hämta och installera Report Builder-tillägget

Så här hämtar och installerar du Report Builder-tillägget

1. Starta [!DNL Excel] och öppna en ny arbetsbok.

1. Välj **[!UICONTROL Insert]** > **[!UICONTROL Get Add-ins]**.

1. I dialogrutan för Office-tillägg väljer du fliken Store.

1. Sök efter Report Builder och klicka på **[!UICONTROL Add]**.

1. Klicka på **[!UICONTROL Continue]** i dialogrutan Licensvillkor och sekretesspolicy.

**Om fliken Store inte visas**

1. I [!DNL Excel] väljer du Arkiv > Konto > Hantera inställningar.

1. Markera rutan bredvid&quot;Aktivera valfria anslutna upplevelser&quot;

1. Starta om [!DNL Excel].

**Om din organisation blockerar åtkomsten till Microsoft Store**

- Kontakta IT-avdelningen eller säkerhetsteamet för att få Report Builder-tillägget godkänt. Välj fliken **[!UICONTROL Admin Managed]** i dialogrutan för Office-tillägg när du har godkänt det.

  ![Fliken Administratörshantering i dialogrutan Office-tillägg.](./assets/image1.png)

- Du kan också hämta [manifestfilen](https://reportbuilder.an.adobe.com/manifest.xml) manuellt och lagra filen i din egen IT-infrastruktur. <br/>Följ [onlinedokumentationen ](https://learn.microsoft.com/en-us/office/dev/add-ins/publish/publish) för Microsoft Office om du vill ha anvisningar om hur du installerar en Excel-manifestfil som inte kan hanteras från Microsoft Store.

När du har installerat Report Builder-tillägget visas Report Builder-ikonen i menyfliksområdet [!DNL Excel] på fliken Hem.

![Report Builder-ikonen i Excel](/help/analyze/report-builder/assets/rb_app_icon.png)

## Logga in på Report Builder

När du har installerat Report Builder for Excel-tillägget för din operativplattform eller webbläsare följer du de här stegen för att logga in på Report Builder.

1. Öppna en Excel-arbetsbok.

1. Klicka på ikonen Report Builder för att starta Report Builder.

1. Klicka på **[!UICONTROL Login]** i verktygsfältet i Adobe Report Builder.

   ![Klicka på inloggningsknappen för Report Builder.](/help/analyze/report-builder/assets/rb_login.png)

1. Ange din kontoinformation för Adobe Experience ID. Kontoinformationen ska överensstämma med dina Adobe Analytics-uppgifter.

   ![Din inloggningsikon och organisation.](/help/analyze/report-builder/assets/image4.png)

När du har loggat in visas din inloggningsikon och organisation högst upp på panelen

## Byt organisation

När du loggar in första gången loggas du in på den standardorganisation som tilldelats din profil.

1. Klicka på namnet på organisationen som visas när du loggar in.

1. Välj en organisation i listan över tillgängliga organisationer. Endast organisationer som du har åtkomst till listas.

   ![Listan över organisationer som du kan komma åt.](/help/analyze/report-builder/assets/image5.png)

## Logga ut

Du kan logga ut från Report Builder från användarprofilen.

1. Spara ändringar i alla öppna arbetsböcker.

1. Klicka på avatarikonen för att visa din användarprofil.

   ![Din användarprofilavatar och knappen Logga ut.](/help/analyze/report-builder/assets/image6.png)

1. Klicka på **Logga ut**.
