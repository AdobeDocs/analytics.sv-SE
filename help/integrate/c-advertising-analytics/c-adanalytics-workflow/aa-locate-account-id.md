---
description: Instruktioner för hur du hittar ditt konto-ID för Google Ads och Microsoft Advertising.
title: Hitta ditt konto-ID
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
source-git-commit: 586459d99674f01a3b18f84f975a3365ddf2fcd9
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Hitta ditt konto-ID {#locate-your-account-ids}

Lär dig hur du hittar ditt konto-ID för Google Ads och Microsoft Advertising.

## Google Ads (AdWords) {#google}

>[!IMPORTANT]
>
>Google Ads har två typer av konton:
>
>- MCC-konto (My Client Center) och
>- Standardkonto.
>
>För den här integreringen med Adobe Analytics måste **du använda en standardkontoinloggning**, inte en MCC-kontoinloggning. Orsaken är att ett MCC-konto fungerar som ett&quot;paraply&quot;-konto som kan komma åt flera Google Ads-konton med en enda inloggning, medan standardkontoinloggningen bara kan komma åt ett konto per inloggning. Google stöder länkning av ett e-postmeddelande för hantering av 5-konton, men Advertising Analytics stöder inte den här funktionen ännu. Ett e-postmeddelande kan bara länkas med ett Google Ads-konto.

Klicka på kontoikonen längst upp till höger för att visa Google Ads-kontonumret (Kund-ID).

![Google Ads Manager-konto](assets/google-account.png)

## Microsoft Advertising (Bing) {#microsoft}

>[!NOTE]
>
>Om ditt Microsoft Advertising-konto (tidigare kallat Bing) använder importfunktionen i Google måste du uppdatera rätt spårningssträng. Spårningssträngen uppdateras inte automatiskt från Google-versionen till rätt spårningssträng för Microsoft Advertising och kan resultera i ospecificerade data. Mer information finns i [Vad som importeras från Google Ads](https://help.ads.microsoft.com/apex/index/3/en/50851/) i hjälpen för Microsoft Advertising.

Både **[!UICONTROL Account ID]** och **[!UICONTROL Manager account ID]** krävs.

- **[!UICONTROL Account ID]** finns under **[!UICONTROL Settings]** > **[!UICONTROL Account settings]** > **[!UICONTROL Account ID]**. Se till att du använder [!UICONTROL Account ID] och INTE [!UICONTROL Account number].
- **[!UICONTROL Manager account ID]** finns under **[!UICONTROL Settings]** > **[!UICONTROL Manager account settings]** > **[!UICONTROL Manager account ID]**. Se till att du använder [!UICONTROL Manager account ID] och INTE [!UICONTROL Manager account number].

![Microsoft Advertising-navigering](assets/bing-id.png)

>[!CONTEXTUALHELP]
>id="adanalytics_ma_account_id"
>title="Konto-ID"
>abstract="Konto-ID:t är ett numeriskt värde som finns i Microsoft Advertising-gränssnittet. Du hittar den genom att gå till Inställningar > Kontoinställningar > Konto-ID."

>[!CONTEXTUALHELP]
>id="adanalytics_ma_manager_account_id"
>title="Hanterarkonto-ID"
>abstract="Konto-ID:t för hanteraren är ett numeriskt värde som finns i Microsoft Advertising-gränssnittet. Du hittar den genom att gå till Inställningar > Kontoinställningar för hanterare > ID för hanterarkonto."
