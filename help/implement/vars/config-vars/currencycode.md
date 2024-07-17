---
title: Vad är variabeln currencyCode och hur använder jag den?
description: För eCommerce-webbplatser anger den valuta som sidan handlar i.
feature: Variables
exl-id: 3332c366-c472-4778-96c8-ef0aa756cca8
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 0%

---

# currencyCode

För webbplatser som använder e-handel är intäkter och valuta en viktig del av Analytics. Många webbplatser, särskilt de som omfattar flera länder, använder olika valutor. Använd variabeln `currencyCode` för att kontrollera att intäktsattributen är rätt valuta.

Vid valutakonvertering används följande logik för varje träff. De här stegen gäller för intäktsvärden som anges av variabeln [`products`](../page-vars/products.md) och för alla händelser som anges som&quot;Valuta&quot; i [Slutfört-händelser](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) under inställningarna för rapportsviten.

* Om `currencyCode` inte har definierats antar Adobe att alla valutavärden är rapportsvitens valuta. Se [Allmänna kontoinställningar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) i Rapportsvitens inställningar för att se rapportsvitens valuta.
* Om `currencyCode` har definierats och matchar rapportsvitens valuta används ingen valutakonvertering.
* Om `currencyCode` har definierats och skiljer sig från rapportsvitens valuta, använder Adobe en valutakonvertering som baseras på den aktuella dagens växelkurs. Adobe samarbetar med [XE](https://xe.com) för att konvertera valuta varje dag. Alla värden som lagras i rapportsviten finns i rapportsvitens valuta.
* Om `currencyCode` är inställt på ett ogiltigt värde ignoreras **hela träffen vilket orsakar dataförlust.** Kontrollera att variabeln är korrekt definierad när den används.

Den här variabeln finns inte kvar över träffar. Kontrollera att den här variabeln är definierad på varje sida som innehåller intäkt- eller valutahändelser som inte matchar rapportsvitens standardvaluta.

>[!NOTE]
>
>Även om valutakoder kan ändras mellan sidor måste alla valutamått för en enda träff använda samma valuta.

En period **måste** användas som valutasparator för alla valutor när variabeln implementeras. Svensk krona, som vanligtvis visar en kommaavgränsare, måste ändras för att använda en punkt i variabeln `products` och alla valutakändelser. Adobe visar rätt valutavaldare vid rapportering.

## Valutakod med Web SDK

Valutakoden mappas till följande variabler:

* [XDM-objekt](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.currencyCode`
* [Dataobjekt](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.currencyCode` eller `data.__adobe.analytics.cc`

## Valutakod som använder Adobe Analytics-tillägget

Valutakod är ett fält under dragspelet [!UICONTROL General] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) med dina inloggningsuppgifter för AdobeID.
1. Klicka på den önskade taggegenskapen.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen **[!UICONTROL Configure]** under Adobe Analytics.
1. Expandera dragspelsfliken [!UICONTROL General] som visar fältet [!UICONTROL Currency Code].

Du kan antingen använda en förinställd valutakod eller en anpassad valutakod. Kontrollera att koden är giltig om du använder en anpassad valutakod.

## Valutakod i Adobe Experience Platform Mobile SDK

Valutakoden skickas till Adobe Experience Platform Mobile SDK:er via kontextdatavariabler i tillägget Adobe Analytics.

1. Ange valutakoden i en kontextdatavariabel under antingen `trackState` eller `trackAction`.
1. Skapa en bearbetningsregel i Adobe Analytics Admin Tools för rapportserien. Ställ in regeln så att variabeln Valutakod skrivs över.
1. Skicka valutakoden till variabeln `products` i ditt anrop till `trackState` eller `trackAction`.

Du kan antingen använda en förinställd valutakod eller en anpassad valutakod. Kontrollera att koden är giltig om du använder en anpassad valutakod.

## s.currencyCode i AppMeasurementet och den anpassade kodredigeraren för Analytics-tillägget

Variabeln `s.currencyCode` är en sträng som innehåller en 3-bokstavskod som representerar valutan på sidan. Värdena är skiftlägeskänsliga.

```js
s.currencyCode = "USD";
```

Följande valutakoder är giltiga:

| Valutakod | Etikett |
| --- | --- |
| `AED` | Förenade Arabemiraten Dirhams |
| `AFA` | Afghanistan, Afghanistan |
| `ALL` | Albanien Leke |
| `AMD` | Armeniska kramar |
| `ANG` | Nederländska Atillerna Guilders |
| `AOA` | Angola Kwanza |
| `ARS` | Argentina Pesos |
| `AUD` | Australiensiska dollar |
| `AWG` | Aruba Guilders |
| `AZM` | Azerbajdzjanska Manat |
| `BAM` | Bosnien och Hercegovina - konvertibel marka |
| `BBD` | Barbados Dollars |
| `BDT` | Bangladesh Taka |
| `BGN` | Bulgarien Leva |
| `BHD` | Bahrain Dinars |
| `BIF` | Burundi Francs |
| `BMD` | Bermuda Dollars |
| `BND` | Brunei dollar |
| `BOB` | Bolivia Bolivianos |
| `BRL` | Brasilien Reader |
| `BSD` | Bahamas-dollar |
| `BTN` | Bhutan Ngultrum |
| `BWP` | Botswana Pulas |
| `BYR` | Vitryssland-rubel |
| `BZD` | Belize Dollars |
| `CAD` | Kanadensiska dollar |
| `CDF` | Congo/Kinshasa Francs |
| `CHF` | Schweiz francs |
| `CLP` | Chile Pesos |
| `CNY` | Yuanska renminbi |
| `COP` | Colombia Pesos |
| `CRC` | Costa Rica Colones |
| `CSD` | Serbiska dinarer |
| `CUP` | Kuba Pesos |
| `CVE` | Kap Verde Escudos |
| `CYP` | Cyperns pund |
| `CZK` | Tjeckien Koruny |
| `DJF` | Djibouti francs |
| `DKK` | Danmark kronor |
| `DOP` | Dominikanska republiken Pesos |
| `DZD` | Algeriets dinarer |
| `EEK` | Estland Krooni |
| `EGP` | Egypten Pounds |
| `ERN` | Eritrea Nakfa |
| `ETB` | Etiopiska Birr |
| `EUR` | Euro |
| `FJD` | Fiji-dollar |
| `FKP` | Falklandsöarna |
| `GBP` | Storbritannien |
| `GEL` | Georgia Lari |
| `GGP` | Guernsey Pounds |
| `GHC` | Ghana Cedis |
| `GIP` | Gibraltar Pounds |
| `GMD` | Gambia Dalasi |
| `GNF` | Guineanska franc |
| `GTQ` | Guatemala Quetzales |
| `GYD` | Guyana-dollar |
| `HKD` | Hongkong-dollar |
| `HNL` | Honduras Lempiras |
| `HRK` | Kroatien Kuna |
| `HTG` | Haitiska Gourdes |
| `HUF` | Ungern Forint |
| `IDR` | Indonesien Rupiahs |
| `ILS` | Israel New Shekels |
| `IMP` | Isle of Man Pounds |
| `INR` | Indiska rupier |
| `IQD` | Irak-dinarer |
| `IRR` | Iran Rials |
| `ISK` | Island Kronur |
| `JEP` | Jersey Pounds |
| `JMD` | Jamaica Dollars |
| `JOD` | Jordanska dinarer |
| `JPY` | Japan Yen |
| `KES` | Kenya Shillings |
| `KGS` | Kirgizistan Soms |
| `KHR` | Kambodjanska riels |
| `KMF` | Komorernas franc |
| `KPW` | Nordkoreanskt Won |
| `KRW` | Sydkoreanska won |
| `KWD` | Kuwait Dinars |
| `KYD` | Caymanöarna, dollar |
| `KZT` | Kazakstan Tenge |
| `LAK` | Laos Kips |
| `LBP` | Libanon Pounds |
| `LKR` | Rupaner i Sri Lanka |
| `LRD` | Liberia Dollars |
| `LSL` | Lesotho Maloti |
| `LTL` | Litauen Litai |
| `LVL` | Lettland Lati |
| `LYD` | Libyska dinarer |
| `MAD` | Marocko Dirhams |
| `MDL` | Moldavien Lei |
| `MGA` | Madagaskar Ariary |
| `MKD` | Makedonien Denars |
| `MMK` | Myanmar Kyats |
| `MNT` | Mongoliet Tugriks |
| `MOP` | Macau Patacas |
| `MRO` | Mauretanien Ouguiyas |
| `MTL` | Malta Liri |
| `MUR` | Mauritius rupier |
| `MVR` | Maldives Rufiyaa |
| `MWK` | Malawi Kwachas |
| `MXN` | Mexico Pesos |
| `MYR` | Malaysia Ringgits |
| `MZM` | Moçambique Meticais |
| `NAD` | Namibia-dollar |
| `NGN` | Nigeria Nairas |
| `NIO` | Nicaragua Gold Cordobas |
| `NOK` | Norska kronor |
| `NPR` | Nepal-rupier |
| `NZD` | Nya Zeeland-dollar |
| `OMR` | Oman Rials |
| `PAB` | Panama Balboas |
| `PEN` | Peru Nuevos Soles |
| `PGK` | Papua Nya Guinea |
| `PHP` | Filippinernas pesos |
| `PKR` | Pakistan Rupes |
| `PLN` | Polen Zlotych |
| `PYG` | Paraguay Warri |
| `QAR` | Qatar Riyals |
| `ROL` | Rumänien Lei |
| `RUR` | Ryssland |
| `RWF` | Rwandfranc |
| `SAR` | Saudiarabiska riyals |
| `SBD` | Salomonöarnas dollar |
| `SCR` | Seychelliska rupier |
| `SDD` | Sudan Dinars |
| `SEK` | Sverige Kronor |
| `SGD` | Singapore-dollar |
| `SHP` | Saint Helena Pounds |
| `SIT` | Slovenien Tolars |
| `SKK` | Slovakien Koruny |
| `SLL` | Sierra Leone Leones |
| `SOS` | Somalia Shillings |
| `SPL` | Seborga Luigini |
| `SRD` | Surinamdollar |
| `SRG` | Suriname Guilders |
| `STD` | Sao Tome och Principe Dobras |
| `SVC` | El Salvador Colones |
| `SYP` | Syrien Pounds |
| `SZL` | Swaziland Emalangeni |
| `THB` | Thailand Baht |
| `TJS` | Tadzjikistan Somoni |
| `TMM` | Turkmenistan Manats |
| `TND` | Tunisien, dinarer |
| `TOP` | Tonga Pa&#39;anga |
| `TRL` | Turkiet Liras |
| `TTD` | Trinidad och Tobago Dollars |
| `TVD` | Tuvalu-dollar |
| `TWD` | Taiwan - nya dollar |
| `TZS` | Tanzania Shillings |
| `UAH` | Ukraina Hryvnia |
| `UGX` | Uganda Shillings |
| `USD` | Amerikanska dollar |
| `UYU` | Uruguay Pesos |
| `UZS` | Uzbekistan-summor |
| `VEB` | Venezuela Bolivares |
| `VND` | Vietnam Dong |
| `VUV` | Vanuatu Vatu |
| `WST` | Samoa Tala |
| `XAF` | Kommunauté Financière Africaine Francs B |
| `XAG` | Silver Ounes |
| `XAU` | Guld |
| `XCD` | Östkaribiska dollar |
| `XDR` | Internationella valutafondens särskilda Draw |
| `XOF` | Kommunauté Financière Africaine Francs B |
| `XPD` | Palladium Ounces |
| `XPF` | Comptoirs Français du Pacific Francs |
| `XPT` | Platinum Ounes |
| `YER` | Jemen-rialer |
| `ZAR` | Sydafrika Rand |
| `ZMK` | Zambia Kwacha |
| `ZWD` | Zimbabwes dollar |
