---
title: Vad är variabeln currencyCode och hur använder jag den?
description: För e-handelswebbplatser anger den valuta som sidan handlar i.
exl-id: 3332c366-c472-4778-96c8-ef0aa756cca8
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 0%

---

# currencyCode

För webbplatser som använder e-handel är intäkter och valuta en viktig del av Analytics. Många webbplatser, särskilt de som spänner över flera länder, använder olika valutor. Använd variabeln `currencyCode` för att se till att intäktsattributen är rätt valuta.

Om `currencyCode` inte är definierad behandlas monetära värden som definieras för variabeln [`products`](../page-vars/products.md) och valutakändelser som om de är samma som rapportsvitens valuta. Se [Allmänna kontoinställningar](/help/admin/admin/general-acct-settings-admin.md) i användarhandboken för Admin för att se rapportsvitens valuta.

Om `currencyCode` är definierad och matchar rapportsvitens valuta används ingen valutakonvertering.

Om `currencyCode` har definierats och skiljer sig från rapportsvitens valuta, använder Adobe en valutakonvertering som baseras på den aktuella dagens växelkurs. Adobe samarbetar med [XE](https://xe.com) för att konvertera valuta varje dag. Alla värden som lagras på datainsamlingsservrar lagras slutligen i rapportsvitens valuta.

>[!IMPORTANT]
>
>Om `currencyCode` innehåller ett ogiltigt värde ignoreras hela träffen, vilket orsakar dataförlust. Kontrollera att variabeln är korrekt definierad om du använder den i implementeringen.

Den här variabeln finns inte mellan träffar. Kontrollera att variabeln är definierad på varje sida som innehåller intäkt- eller valutakurser.

## Valutakod som använder taggar i Adobe Experience Platform

Valutakod är ett fält under dragspelet [!UICONTROL General] när du konfigurerar Adobe Analytics-tillägget.

1. Logga in på [användargränssnittet för datainsamling](https://experience.adobe.com/data-collection) med inloggningsuppgifterna för ditt Adobe-ID.
1. Klicka på önskad egenskap.
1. Gå till fliken [!UICONTROL Extensions] och klicka sedan på knappen [!UICONTROL Configure] under Adobe Analytics.
1. Expandera dragspelet [!UICONTROL General], som visar fältet [!UICONTROL Currency Code].

Du kan antingen använda en förinställd valutakod eller en anpassad valutakod. Kontrollera att koden är giltig om du använder en anpassad valutakod.

## Valutakod i Adobe Experience Platform Mobile SDK

Valutakoden skickas till Adobe Experience Platform Mobile SDK:er via kontextdatavariabler i tillägget Adobe Analytics.

1. Ange valutakoden i en kontextdatavariabel under antingen `trackState` eller `trackAction`.
1. Skapa en bearbetningsregel i Adobe Analytics Admin Console för rapportsviten. Ställ in regeln så att variabeln Valutakod skrivs över.
1. Skicka valutakoden till variabeln `products` i ditt anrop till `trackState` eller `trackAction`.

Du kan antingen använda en förinställd valutakod eller en anpassad valutakod. Kontrollera att koden är giltig om du använder en anpassad valutakod.

## s.currencyCode i AppMeasurement och anpassad kodredigerare

Variabeln `s.currencyCode` är en sträng som innehåller en 3-bokstavskod som representerar valutan på sidan.

```js
s.currencyCode = "USD";
```

Följande valutakoder är giltiga:

| Valutakod | Valutabeskrivning |
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
| `BYR` | Vitryssland Rubles |
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
| `GBP` | United Kingdom Pounds |
| `GEL` | Georgia Lari |
| `GGP` | Guernsey Pounds |
| `GHC` | Ghana Cedis |
| `GIP` | Gibraltar Pounds |
| `GMD` | Gambia Dalasi |
| `GNF` | Guineanska franc |
| `GTQ` | Guatemala Quetzales |
| `GYD` | Guyana-dollar |
| `HKD` | Hongkongdollar |
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
| `SIT` | Slovenska tolarer |
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
| `ZAR` | Sydafrika, Rand |
| `ZMK` | Zambia Kwacha |
| `ZWD` | Zimbabwes dollar |
