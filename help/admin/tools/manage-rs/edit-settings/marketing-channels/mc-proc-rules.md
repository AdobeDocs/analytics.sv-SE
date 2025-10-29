---
title: Bearbetningsregler för marknadsföringskanaler
description: Använd regler för att avgöra vilken marknadsföringskanal en träff tillhör.
feature: Marketing Channels
exl-id: 825f70a5-cce3-4b1c-bb42-828388348216
role: Admin
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 0%

---

# Bearbetningsregler för marknadsföringskanaler

_Den här sidan refererar till bearbetningsregler som tilldelar en marknadsföringskanal till en träff. Se [Bearbetningsregler](../general/processing-rules/pr-overview.md) för en funktion som gör att du kan justera hur data samlas in._

Med bearbetningsregler för marknadsföringskanaler kan du skapa logik som bestämmer värdet för dimensionerna [Marknadskanal](/help/components/dimensions/marketing-channel.md) och [Marknadskanal &#x200B;](/help/components/dimensions/marketing-detail.md) . Använd [Marketing Channel Manager](c-channels.md) för att avgöra vilka marknadsföringskanaler du använder och använd sedan bearbetningsregler för att avgöra hur varje kanal är inställd.

![Marknadsföringskanalbucklar](assets/buckets_2.png)

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**

När den [automatiska konfigurationen](/help/components/c-marketing-channels/c-getting-started-mchannel.md) körs skapas en regel för varje kanal som genereras under konfigurationen.

![Standardregler](assets/marketing_channel_rules.png)

Ni kan använda flera regler för att definiera en enda marknadsföringskanal. Det kan vara bra att använda flera regler för en kanal om du vill ställa in kanaldetaljen på olika sätt beroende på regelvillkoren. Du kan också använda flera villkor för att definiera en regel.

## Regeldefinitioner

Varje regel innehåller ett villkor och ett uppdrag:

* **[!UICONTROL If any/all of the following are true]**: Om du lägger till flera villkor i en enskild regel kan du bestämma om alla villkor måste uppfyllas eller om något av villkoren ska uppfyllas för att ange kanalen och det associerade värdet.
* **Regelvillkor**: Ange ett eller flera regelvillkor som måste uppfyllas. Vanligtvis anger du en dimension som en träff måste matcha för att kvalificera dig för marknadsföringskanalen.
* **[!UICONTROL Then do the following]**: När regelvillkoren matchar anger du [Marknadskanal](/help/components/dimensions/marketing-channel.md) ([!UICONTROL Identify the channel as]) och [Information om marknadsföringskanal](/help/components/dimensions/marketing-detail.md) ([!UICONTROL Set the channel's value]).

## Regelvillkor

Följande alternativ är tillgängliga när du ställer in regelvillkor.

>[!NOTE]
>
>Alla textfält utvärderas som **skiftlägeskänsliga**. Om du till exempel använder ett regelvillkor där frågesträngsparametern `cmp` är lika med `abc123` kan både frågesträngsparametern och -värdet använda vilken kombination som helst av versaler och gemener.

**Adobe-identifierade villkor** innehåller inga alternativ eller fält för att ange text.

| Adobe-identifierat villkor | Beskrivning |
|---|---|
| **[!UICONTROL Matches Paid Search Detection Rules]** | Träffen kom från en erkänd sökmotor och matchade [regler för betald sökningsidentifiering](../general/paid-search-detection/paid-search-detection.md). |
| **[!UICONTROL Matches Natural Search Detection Rules]** | Träffen härstammar från en erkänd sökmotor och matchar inte reglerna för betald sökningsidentifiering. |
| **[!UICONTROL Referrer Matches Internal URL Filters]** | Träffen innehöll en [referens](/help/components/dimensions/referrer.md) som matchade [interna URL-filter](../general/internal-url-filter-admin.md). |
| **[!UICONTROL Referrer Does Not Match Internal URL Filters]** | Träffen innehöll en referens som inte matchade interna URL-filter. |
| **[!UICONTROL Is First Hit of Visit]** | Träffen var den första på ett besök. |
| **[!UICONTROL Referrer Is Social Network]** | [Refererartypen](/help/components/dimensions/referrer-type.md) är Sociala nätverk. |
| **[!UICONTROL Referrer Is Not Social Network]** | Referenstypen är inte &quot;Sociala nätverk&quot;. |
| **[!UICONTROL Referrer Is Conversational AI]** | Referenstypen är &quot;Conversational AI&quot;. |
| **[!UICONTROL Referrer Is Not Conversational AI]** | Referenstypen är inte&quot;Konversations-AI&quot;. |

**Träffattribut** gör att du kan ange en dimension, en matchande operator och ett värde som du vill söka efter.

| Villkor för träff-attribut | Beskrivning |
|---|---|
| **[!UICONTROL Page]** | Dimensionen [Sida](/help/components/dimensions/page.md). |
| **[!UICONTROL Page Domain]** | Domänen för URL:en. Exempel: `products.example.com`. |
| **[!UICONTROL Page Domain And Path]** | Domänen och sökvägen för URL:en. Exempel: `products.example.com/mens/pants/overview.html`. |
| **[!UICONTROL Page Root Domain]** | URL:ens rotdomän. Exempel: `example.co.uk`. |
| **[!UICONTROL Page URL]** | Den fullständiga sidans URL. |
| **[!UICONTROL Query String Parameter]** | En enskild frågesträngsparameter i sidans URL. Använd en frågesträngsparameter per regelvillkor. Om du vill ta med flera frågesträngsparametrar i en regel använder du flera regelvillkor. |
| **[!UICONTROL Referrer]** | Dimensionen [Referent](/help/components/dimensions/referrer.md). |
| **[!UICONTROL Referring Domain]** | Dimensionen [Referensdomän](/help/components/dimensions/referring-domain.md). |
| **[!UICONTROL Referring Domain And Path]** | En sammanfogning av refererande domän och referentens URL-sökväg. Till exempel `www.example.com/products/id/12345` eller `ad.example.com/foo`. |
| **[!UICONTROL Referring Parameter]** | En frågesträngsparameter i referenten. |
| **[!UICONTROL Referring Root Domain]** | Den refererande rotdomänen. |
| **[!UICONTROL Search Engine]** | Dimensionen [Sökmotor](/help/components/dimensions/search-engine.md). |
| **[!UICONTROL Search Keyword(s)]** | Dimensionen [Söknyckelord](/help/components/dimensions/search-keyword.md). |
| **[!UICONTROL Search Engine + Search Keyword(s)]** | En sammanfogning av sökmotor och söknyckelord. |
| **[!UICONTROL AMO ID]** | Den primära spårningskod som används av Adobe Advertising- och Advertising Analytics-integreringar. När en av dessa integreringar är aktiverad kan spårningskod-prefixet användas för att identifiera Advertising-specifika kanaler. Värden som börjar med &quot;AL&quot; är för Sök och Socialt. Värden som börjar med &quot;AC&quot; är för visning. När AMO-ID används i marknadsföringskanaler kan mått för klickning/kostnad/intryck tillskrivas rätt kanal. |
| **[!UICONTROL AMO EF ID]** | Den sekundära spårningskod som används av Adobe Advertising. Fungerar som nyckel för att skicka data tillbaka till Advertising. Den kan användas för att identifiera ett musklick och visa en bild i två olika marknadsföringskanaler. Det gör du genom att ange marknadsföringskanallogiken för&quot;AMO EF ID&quot; avslutas med `:d` för att visa klickningar eller så avslutas&quot;AMO EF ID&quot; med `:i` för att visa hela bilden. Om du inte vill dela upp visningen i två kanaler använder du AMO ID-dimensionen i stället. |

**Med konverteringsvariabler** kan du ange en anpassad eVar, en matchande operator och ett värde som du vill söka efter.

| Variabelvillkor för konvertering | Beskrivning |
|---|---|
| **eVar 1-250** | Den associerade [eVar](/help/components/dimensions/evar.md)-dimensionen. |
