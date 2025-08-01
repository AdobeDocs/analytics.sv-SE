---
description: Tillgängliga mått och mätvärden som du kan läsa och skriva med bearbetningsregler.
subtopic: Processing rules
title: Tillgängliga mått och mätvärden för bearbetningsregler
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
source-git-commit: d62d4699418278bc9f0c7d69846ef12b5f2345d1
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 1%

---

# Tillgängliga mått och mätvärden för bearbetningsregler

Tillgängliga mått och mätvärden som du kan läsa och skriva med bearbetningsregler.

## Anpassade värden och kontextdata

| Värde | Läsa/skriva status | Beskrivning |
| --- | --- | --- |
| **Eget värde** | Skrivskyddad | Anpassad text eller anpassade värden som skrivs direkt i en bearbetningsregel. |
| **Sammansatt värde** | Skrivskyddad | Värden som skapas genom att två värden kombineras. Du kan t.ex. kombinera kanal- och sidnamn för att skapa en underkategori. |

## Träff-attribut

| Attribut | Läsa/skriva status | Beskrivning |
| --- | --- | --- |
| **Sidans URL** | Läs och skriv | Dimensionen för [sid-URL](/help/components/dimensions/page-url.md). Länkspårning träffar den här dimensionen innan bearbetningsreglerna nås. Om du infogar ett sidans URL-värde igen med bearbetningsregler betraktas träffen som en [sidvy](/help/components/metrics/page-views.md) i stället för en [sidhändelse](/help/components/metrics/page-events.md). Adobe rekommenderar att du kontrollerar om det finns ett värde i siddimensionen innan du ändrar den. |
| **Sidnamn** | Läs och skriv | Dimensionen [Sida](/help/components/dimensions/page.md). Länkspårning träffar den här dimensionen innan bearbetningsreglerna nås. Om du infogar ett sidvärde igen med bearbetningsregler betraktas träffen som en [sidvy](/help/components/metrics/page-views.md) i stället för en [sidhändelse](/help/components/metrics/page-events.md). Adobe rekommenderar att du kontrollerar om det finns ett värde i siddimensionen innan du ändrar den. |
| **Rapportera paket-ID** | Skrivskyddad | Rapportsviten som bearbetningsregeln körs på. Den här rapportsviten kan skilja sig från den rapportserie som ursprungligen skickades via AppMeasurement, till exempel när VISTA-regler används. |
| **AppMeasurement-kodversion** | Skrivskyddad | AppMeasurement biblioteksversion som användes för att generera bildbegäran. |
| **IP-adress** | Skrivskyddad | Besökarens IP-adress. |
| **Användaragent** | Skrivskyddad | Besökarens användaragent. |
| **Referent** | Skrivskyddad | Dimensionen [Referent](/help/components/dimensions/referrer.md). |
| **Frågesträngsparameter** | Skrivskyddad | Värdet för en angiven frågesträngsparameter i den aktuella URL:en. |
| **Refererar frågesträngsparameter** | Skrivskyddad | Värdet för en angiven frågesträngsparameter i den refererande URL:en, eller en tom sträng om ingen finns. |
| **Referensdomän** | Skrivskyddad | Den refererande URL:ens siddomän, inklusive underdomäner. |
| **Refererar till rotdomän** | Skrivskyddad | Den refererande URL:ens siddomän, exklusive underdomäner. |
| **Sidfrågesträng** | Skrivskyddad | Alla frågesträngsparametrar och deras värden i den aktuella URL:en. |
| **Referensfrågesträng** | Skrivskyddad | Alla frågesträngsparametrar och deras värden i den refererande URL:en. |
| **Sidsökväg** | Skrivskyddad | Sidsökvägen för den aktuella URL:en. Sidsökvägen innehåller inte protokoll, domän eller frågesträngsparametrar. |
| **Siddomän** | Skrivskyddad | Siddomänen för den aktuella URL-adressen, inklusive underdomäner. Siddomänen innehåller inte parametrar för sidsökväg eller frågesträng. |
| **Sidrotdomän** | Skrivskyddad | Siddomänen för den aktuella URL-adressen, exklusive underdomäner. |
| **Kundperspektiv** | Läs och skriv | En flagga som avgör om träffen är en mobilt bakgrundspåverkan. |

## Konverteringsvariabler

| Variabel | Läsa/skriva status | Beskrivning |
| --- | --- | --- |
| **eVar 1-250** | Läs och skriv | [eVar](/help/components/dimensions/evar.md)-dimensioner. |
| **Campaign** | Läs och skriv | Dimensionen [Spårningskod](/help/components/dimensions/tracking-code.md). |
| **Inköps-ID** | Läs och skriv | Implementeringsvariabeln [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). |
| **Läge** | Läs och skriv | (Borttagen) Implementeringsvariabeln [`state`](/help/implement/vars/page-vars/state.md). |
| **Postnummer** | Läs och skriv | Dimensionen [Postnummer](/help/components/dimensions/zip-code.md). |
| **Valutakod** | Läs och skriv | Implementeringsvariabeln [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). VIKTIGT! Om du anger ett ogiltigt värde för den här variabeln ignoreras träffen. |
| **Transaktions-ID** | Läs och skriv | Implementeringsvariabeln [`transactionID`](/help/import/data-sources/transactionid.md). |

>[!NOTE]
>Adobe stöder inte inställning av implementeringsvariabeln [`products`](/help/implement/vars/page-vars/products.md) med bearbetningsregler.

## Trafikvariabler

| Variabel | Läsa/skriva status | Beskrivning |
| --- | --- | --- |
| **Prop 1-75** | Läs och skriv | [Prop](/help/components/dimensions/prop.md)-dimensioner. |
| **Hierarki 1-5** | Läs och skriv | (Pensionerat) [Hierarki](/help/components/dimensions/hierarchy.md)-dimensioner. |
| **Server** | Läs och skriv | Dimensionen [Server](/help/components/dimensions/server.md). |
| **Kanal** | Läs och skriv | Dimensionen för [webbplatsavsnittet](/help/components/dimensions/site-section.md). |

## Kontextvariabler

Alla [kontextdatavariabler](/help/implement/vars/page-vars/contextdata.md) som den här rapportsviten har visat de senaste 30 dagarna. Se [Användningsexempel för bearbetningsregler](pr-use-cases.md) för exempel.

>[!IMPORTANT]
>
>Om bearbetningsregler inte mappar en viss kontextdatavariabel till en annan variabel (till exempel ett utkast eller eVar), kommer värdet i kontextdatavariabeln att tas bort permanent.

## Slutförda händelser

Bearbetningsregler kan ange händelser men kan inte läsa dem som villkor. Ställ in listrutan för regelåtgärd på **[!UICONTROL Set event]** för att se tillgängliga mått för ökning.

| Variabel | Läsa/skriva status | Beskrivning |
| --- | --- | --- |
| **Beställningar** | Endast skrivning | Måttet [Beställningar](/help/components/metrics/orders.md). |
| **KARTOR** | Endast skrivning | Måttet [Carts](/help/components/metrics/carts.md). |
| **Vyer för kundvagn** | Endast skrivning | [Cart-vyerna](/help/components/metrics/cart-views.md) visar måttet. |
| **Utcheckningar** | Endast skrivning | Måttet [Utcheckningar](/help/components/metrics/checkouts.md). |
| **Kundtillägg** | Endast skrivning | Måttet [Cart har lagts till](/help/components/metrics/cart-additions.md). |
| **Ta bort kundvagn** | Endast skrivning | [Cart tar bort ](/help/components/metrics/cart-removals.md)-måttet. |
| **Event 1-1000** | Endast skrivning | [Anpassade händelser](/help/components/metrics/custom-events.md). |
| **Produktvyer** | Endast skrivning | Mätvärdet för [produktvisningar](/help/components/metrics/product-views.md). |
