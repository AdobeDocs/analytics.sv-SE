---
description: Här följer instruktioner om hur du kan hitta dina konto-ID:n för Google och Bing.
title: Hitta ditt konto-ID
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# Hitta ditt konto-ID

Här beskrivs hur du kan hjälpa dig att hitta dina konto-ID:n för Google och Bing.

## Google AdWords {#section_2A62AD448BD949889DB77C2AF3E04C33}

>[!IMPORTANT]
>
>Google AdWords använder två typer av konton: a) MCC-konto (My Client Center) och b) standardkonto. För denna integrering med Adobe Analytics **du måste använda en standardkontoinloggning, inte en MCC-kontoinloggning**. Orsaken är att ett MCC-konto fungerar som ett&quot;paraply&quot;-konto som kan komma åt flera AdWords-konton med en enda inloggning, medan standardkontoinloggningen bara kan komma åt ett AdWords-konto per inloggning. Google stöder länkning av ett e-postmeddelande för hantering av fem konton, men Advertising Analytics stöder inte den här funktionen ännu. Ett e-postmeddelande kan bara länkas med ett Adwords-konto.

Klicka på kontoikonen längst upp till höger för att visa AdWords-kontonumret (Kund-ID).

![](assets/google_account.png)

## Bing {#section_F1B9C7E997444746936599732CD62665}

>[!NOTE]
>
>Om ditt Bing-konto använder importfunktionen i Google måste du uppdatera rätt spårningssträng. Spårningssträngen uppdateras inte automatiskt från Google-versionen till rätt Bing-spårningssträng och kan resultera i ospecificerade data. Mer information om funktionen finns [här](https://help.ads.microsoft.com/apex/index/3/en/50851/).

Konto-ID och Kund-ID krävs båda. De visas på fliken Konton.

>[!NOTE]
>
>Kontonumret är inte detsamma som konto-ID:t.

![](assets/bing_id.png)
