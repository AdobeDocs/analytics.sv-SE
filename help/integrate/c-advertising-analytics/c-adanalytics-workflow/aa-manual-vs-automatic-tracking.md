---
description: Spårningstypen avgör hur Adobe Analytics-implementeringen spårar dina sökmotordata. Den här spårningstypen är ett nödvändigt steg för att utöka Adobe Analytics data korrekt med sökmotordata.
title: Spårningstyp
feature: Advertising Analytics
exl-id: 3e2ed26f-dfb2-43ea-8eb6-e332cd10fb29
source-git-commit: 6bedfb9b1333a442bf17cf71dad1e0883b97fd45
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# Spårningstyp

Spårningstypen avgör hur Adobe Analytics-implementeringen spårar dina sökmotordata. Den här spårningstypen är ett nödvändigt steg för att utöka Adobe Analytics data korrekt med sökmotordata.

<!--

Here is a video overview of how to implement the Advertising Analytics tracking template:

>[!VIDEO](https://video.tv.adobe.com/v/23120/?quality=12)

-->

Två spårningslägen stöds: [!UICONTROL Auto] och [!UICONTROL Manual].

## [!UICONTROL Auto]-spårning {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

Med [!UICONTROL Auto]-spårning kan Advertising Cloud-motorn bestämma hur sökmotordata ska hanteras. Automatisk spårning är enklare, men kanske inte ger den bästa integrerade datauppsättningen.

Därför måste du markera kryssrutan Bekräftelse när du väljer **[!UICONTROL Auto]** innan du kan spara kontoinställningen.

Observera att du ansvarar för följande åtgärder när du konfigurerar ett sökmotorkonto med typen **[!UICONTROL Auto]**:

* Parametern `s_kwcid` och värdet läggs till i kontospårningsmallarna eller URL:erna för landningssidan i det konto som läggs till. Parametern och värdet infogas i slutet av URL:en. Ytterligare åtgärder kan krävas från din sida om webbservern kräver ett visst `key=value`-par i slutet av URL:en. Eller en uppdatering som stöder nya `key=value`-par i URL:en. Det är ditt ansvar att se till att de URL-parametrar som läggs till behålls korrekt på den slutliga landningssidan.
* Dessutom kan nyckelord infogas i landnings-URL:en som en del av värdet `s_kwcid`. Om de innehåller specialtecken eller symboler måste du bekräfta att webbservern har stöd för dessa tecken. Ett vanligt specialtecken är till exempel `+`, som används i nyckelorden&quot;Bred Match Modified&quot;.

>[!IMPORTANT]
>
>Läs mer om huruvida du bör lägga till parametern `s_kwcid` i din [skyddsprofil för innehåll](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp).

## Manuell spårning {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

Med manuell spårning kan du ange hur data i sökmotorn ska hanteras i dataintegreringsprocessen i Advertising Analytics.

### Lägg till manuell spårning till Google-konto {#section_41C1EB1AEB034544A5BC291F53C05C67}

Strängen som behöver läggas till i ditt Google-konto visas nedan. Du måste lägga till strängen i alla spårningsmallar som används i hela kontot.

>[!IMPORTANT]
>
>Värdet *`<Advertising Analytics ID>`* (i **bold** nedan) är generiskt och **måste ersättas med din specifika konto-ID-sträng**. Du kan hämta din specifika konto-ID-sträng från kontoskärmen under avsnittet [!UICONTROL Tracking].

**Spårningssträng för kampanjer:**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![Google](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/google-account.png)

Exempel på spårningskoder i olika spårningsmallformat:

**`{lpurl}`**

```
{lpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**`{lpurl}`med ytterligare URL-parameter**

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**Tredje part (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**Tredje part (DoubleClick)`{lpurl}`**

För att säkerställa att strängen kvarstår genom omdirigeringen till den slutliga URL-adressen för landningssidan måste du koda strängen tillräckligt:

* om URL:en går igenom en omdirigering, och
* använder inte ett unescape-värde.


```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Lägg till manuell spårning på Microsoft Advertising-konto {#section_094F8ACA493C4D65B1F54A695558EBF2}

Strängen som behöver läggas till i ditt Microsoft Advertising-konto visas nedan. Du måste lägga till strängen i alla de slutliga URL-suffixen som används i hela ditt konto.

>[!IMPORTANT]
>
>Värdet _`<Advertising Analytics ID>`_(i **bold**&#x200B;nedan) är generiskt och **måste ersättas med din specifika konto-ID-sträng**. Du kan hämta din specifika konto-ID-sträng från kontoskärmen under avsnittet Spårning.

**Spårningssträng för kampanjer:**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![Lägg till parametrar för spårningskod](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/bing-account.png)

Exempel på spårningskoder i olika slutliga URL-suffixformat:

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**`{lpurl}`med ytterligare URL-parameter**

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**Tredje part (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**Tredje part (DoubleClick)`{lpurl}`**

För att säkerställa att strängen kvarstår genom omdirigeringen till den slutliga URL-adressen för landningssidan måste du koda strängen tillräckligt:

* om URL:en går igenom en omdirigering, och
* använder inte ett unescape-värde.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
