---
description: Här beskrivs hur du kan hjälpa dig att hitta dina konto-ID:n för Google och Bing.
title: Hitta ditt konto-ID
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
source-git-commit: 0453f374e9027d1c539682212e880c4ebc81152f
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# Hitta ditt konto-ID

Här beskrivs hur du kan hjälpa dig att hitta dina konto-ID:n för Google och Bing.

## Google Ads (AdWords) {#section_2A62AD448BD949889DB77C2AF3E04C33}

>[!IMPORTANT]
>
>Google AdWords använder två typer av konton:
>
>- MCC-konto (My Client Center) och
>- Standardkonto.
>
>För den här integreringen med Adobe Analytics måste **du använda en standardkontoinloggning**, inte en MCC-kontoinloggning. Orsaken är att ett MCC-konto fungerar som ett&quot;paraply&quot;-konto som kan komma åt flera AdWords-konton med en enda inloggning, medan standardkontoinloggningen bara kan komma åt ett AdWords-konto per inloggning. Google stöder länkning av ett e-postmeddelande för hantering av fem konton, men Advertising Analytics stöder inte den här funktionen ännu. Ett e-postmeddelande kan bara länkas med ett Adwords-konto.

Klicka på kontoikonen längst upp till höger för att visa AdWords-kontonumret (Kund-ID).

![Google Ads Manager-konto](assets/google-account.png)

## Microsoft Advertising (Bing) {#section_F1B9C7E997444746936599732CD62665}

>[!NOTE]
>
>Om ditt Microsoft Advertising-konto (tidigare kallat Bing) använder importfunktionen i Google måste du uppdatera rätt spårningssträng. Spårningssträngen uppdateras inte automatiskt från Google-versionen till rätt Bing-spårningssträng och kan resultera i ospecificerade data. Mer information om funktionen finns [här](https://help.ads.microsoft.com/apex/index/3/en/50851/).

Både **[!UICONTROL Account ID]** och **[!UICONTROL Account Number]** krävs. De visas på fliken **[!UICONTROL Accounts settings]** i **[!UICONTROL Settings]**.

>[!NOTE]
>
>Kontonumret är inte detsamma som konto-ID:t.

![Microsoft Advertising](assets/bing-id.png)
