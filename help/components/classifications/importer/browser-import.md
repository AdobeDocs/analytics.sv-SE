---
description: Du kan importera (överföra) klassificeringsdata via webbläsaren. Den här metoden begränsar din överföring av klassificeringsdata till en enda rapportserie
title: Import av webbläsare
feature: Classifications
exl-id: 5bef1f6d-9b27-464d-8343-472f300a7437
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# Webbläsarimport (äldre)

Du kan importera (överföra) klassificeringsdata via webbläsaren. Den här metoden begränsar din överföring av klassificeringsdata till en enda rapportserie

## Import av webbläsare {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

Du kan importera (överföra) klassificeringsdata via webbläsaren. Den här metoden begränsar din överföring av klassificeringsdata till en enda rapportserie

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**

## Import av klassificeringswebbläsare - fältbeskrivningar {#section_F628C47081DA4026A4D30E3D3454B1DA}

| Element | Beskrivning |
| --- | --- |
| Välj Report Suite | Rapportsviten där du vill importera klassificeringsdata. Importdatafilen måste matcha datauppsättningens format i rapportsviten. |
| Datauppsättning som ska klassificeras | Den datauppsättning som ska ta emot klassificeringarna. Listrutan innehåller alla rapporter i rapportsviterna som är konfigurerade för klassificeringar. |
| Välj den fil som ska importeras | Gör att du kan bläddra till den importdatafil som du vill överföra.  Obs! Storleksgränsen för överföring av filer är 1 MB. |
| Skriv över data i konflikter | Skriver automatiskt över befintliga data som står i konflikt med importerade data.<br>**Viktigt**: Det här alternativet är inte tillgängligt för rapportsviter som har aktiverats för den nya klassificeringsarkitekturen. |
| Hämta klassificeringsfilen automatiskt när importen är klar | Hämtar automatiskt en tabbavgränsad fil som representerar datauppsättningen med de nyligen överförda klassificeringsdata. Adobe genererar automatiskt den här filen åt dig om importen skapar unika ID:n eller om fel uppstår.<br>**Viktigt**: Det här alternativet är inte tillgängligt för rapportsviter som har aktiverats för den nya klassificeringsarkitekturen. |


## Importera klassificeringar via webbläsaren {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

1. Klicka på **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Klicka på **[!UICONTROL Import File]**.
1. Konfigurera fälten **[!UICONTROL Browser Import]**.
1. Klicka på **[!UICONTROL Import File]**.
1. Titta på statusfönstret för att bearbeta meddelanden.
1. (Villkorligt) Om du valde **[!UICONTROL Automatically Download Classification File After Upload is Complete]** anger du var du vill lagra den resulterande filen när bearbetningen är klar. Observera att det här alternativet inte är tillgängligt för rapportsviter som har aktiverats för den nya klassificeringsarkitekturen.

>Om importen lyckas visas omedelbart de ändringar som gjorts i en export. Dataändringar i rapporter tar dock upp till fyra timmar vid användning av en webbläsarimport och upp till 24 timmar vid användning av en FTP-import.
