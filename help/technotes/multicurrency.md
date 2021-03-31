---
description: Beskriver hur du definierar målvalutakoder för stöd för flera valutor som ska fungera.
title: Stöd för flera valutor
uuid: null
translation-type: tm+mt
source-git-commit: 4359f451692b86087efe27d4b3ec49ca85b7addc
workflow-type: tm+mt
source-wordcount: '1383'
ht-degree: 0%

---


# Stöd för flera valutor

I det här dokumentet beskrivs hur du definierar målvalutakoder för stöd i flera valutor.

Målvalutakoder definieras på tre nivåer:

## Sidnivå

Du kan ange en JavaScript-variabel för målvalutan på sidnivå. Webbplatsägaren ställer in den här variabeln med lämplig ISO 4217-valutakod med tre bokstäver (som anges nedan i det här dokumentet). Om variabeln [currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/vars/config-vars/currencycode.html) inte är inställd på den här nivån är standardvalutan densamma som den som anges i rapportsviten. Om variabeln på sidnivå står i konflikt med variabeln som anges i rapportsviten, prioriteras variabeln i rapportsviten.


## Rapportsvitens nivå

**basvalutan** anges när [rapportsviter](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html) skapas. Det här är standardinställningen för valuta och har företräde framför valutakoder som har angetts på sidnivå. Om en rapportsvit har order som godkänner amerikanska dollar, euro och brittiska pund och rapportsviten har standardvalutakoden inställd på US Dollars, översätts alla transaktioner till US Dollars av den rapporterande databasen.

Marknadsföringsrapporter använder valutakursen vid den tidpunkt då bildbegäran görs för att översätta sidnivåvalutavärden till standardvalutavärdena för rapportsviten. Rapporteringssviter använder&quot;US Dollars&quot; som standardvaluta.


## Rapportnivå

Användare kan ange den standardrapporterade valutan för användarinloggningssession. Du kommer åt detta via länken **Visningsalternativ** i valfri konverteringsrapport. Marknadsföringsrapporter använder växelkursen vid den tidpunkt då rapporten körs för att omvandla valutavärden för rapportsviten till rapportspecificerade valutavärden.

## Valutakoder som stöds (ISO 4217)

Analyserna har för närvarande stöd för följande valutaformat för konverteringstransaktioner:


&quot;AFA&quot; Afghanistan, Afghanistan (AFA)

Afghanistan (AFN)

ALL&#39; Albanien Leke (ALL)

&quot;DZD&quot; Algeriet Dinars (DZD)

&quot;AOA&quot; Angola Kwanza (AOA)

&#39;ARS&#39; Argentina Pesos (ARS)

&quot;AMD&quot; Armenien Drams (AMD)

&quot;AWG&quot; Aruba Guilders (AWG)

AUD Australiensiska dollar (AUD)

&quot;AZM&quot; Azerbajdzjan Manats (AZM)

AZN&#39; Azerbajdzjan New Manats (AZN)

&quot;BSD&quot; Bahamas Dollars (BSD)

&quot;BHD&quot; Bahrain Dinars (BHD)

&quot;BDT&quot; Bangladesh Taka (BDT)

&quot;BBD&quot; Barbados Dollars (BBD)

BYR - Vitryssland Rubles (BYR)

BZD Belize Dollars (BZD)

BMD Bermuda Dollars (BMD)

Bhutan Ngultrum (BTN)

BOB&#39; Bolivia Bolivianos (BOB)

&quot;BAM&quot; Bosnien och Hercegovina Converitable Marka (BAM)

&quot;BWP&quot; Botswana Pulas (BWP)

BRL&#39; Brasilien Reais (BRL)

&quot;BND&quot; Brunei Dollars (BND)

&quot;BGN&quot; Bulgarien Leva (BGN)

&quot;BIF&quot; Burundi Francs (BIF)

KHR&#39; Kambodja Riels (KHR)

&quot;CAD&quot; Canada Dollars (CAD)

CVE&#39; Kap Verde Escudos (CVE)

KYD Caymanöarna Dollars (KYD)

CLP’ Chile Pesos (CLP)

CNY&#39; China Yuan Renminbi (CNY)

&#39;COP&#39; Colombia Pesos (COP)

&#39;XOF&#39; Kommunauté Financière Africaine Francs BCEAO (XOF)

&#39;XAF&#39; Kommunauté Financière Africaine Francs BEAC (XAF)

&quot;KMF&quot; Comoros Francs (KMF)

&quot;XPF&quot; Comptoirs Français du Pacific Francs (XPF)

CDF&#39; Congo/Kinshasa Francs (CDF)

&quot;CRC&quot; Costa Rica Colones (CRC)

&quot;HRK&quot; Kroatien Kuna (HRK)

CUC:s Kuba Converitable Pesos (CUC)

Kuba Pesos (CUP)

&quot;CYP&quot; Cypern-pund (CYP)

&quot;CZK&quot; Tjeckien Koruny (CZK)

&quot;DKK&quot; Danmark Kroner (DKK)

&quot;DJF&quot; Djibouti Francs (DJF)

&quot;DOP&quot; Dominikanska republiken Pesos (DOP)

&#39;XCD&#39; East Karibien Dollars (XCD)

&quot;EGP&quot; Egypten Pounds (EGP)

SVC El Salvador Colones (SVC)

ERN&#39; Eritrea Nakfa (ERN)

XBT-FEL (XBT)

&quot;EEK&quot; Estland Krooni (EEK)

ETB Etiopien Birr (ETB)

EUR (EUR)

FKP (Falklandsöarna Pounds) (FKP)

Fiji-dollar (FJD)

&quot;GMD&quot; Gambia Dalasi (GMD)

&quot;GEL&quot; Georgia Lari (GEL)

&quot;GHC&quot; Ghana Cedis (GHC)

&quot;GHS&quot; Ghana Cedis (GHS)

&#39;GIP&#39; Gibraltar Pounds (GIP)

&#39;XAU&#39; Gold Ounces (XAU)

&quot;GTQ&quot; Guatemala Quetzales (GTQ)

&#39;GGP&#39; Guernsey Pounds (GGP)

&quot;GNF&quot; Guineas francs (GNF)

&quot;GYD&quot; Guyana-dollar (GYD)

&quot;HTG&quot; Haitis Gourdes (HTG)

&quot;HNL&quot; Honduras Lempiras (HNL)

&quot;HKD&quot; Hongkongdollar (HKD)

HUF: Ungern Forint (HUF)

Island Kronur (ISK)

INR&#39; India Rupees (INR)

&#39;IDR.&#39; Indonesia Rupiahs (IDR.)

&#39;XDR&#39; Internationella valutafondens särskilda riträttigheter (XDR)

IRR Iran Rials (IRR)

IQD-dinarer i Irak (IQD)

&#39;IMP&#39; Isle of Man Pounds (IMP)

&#39;ILS&#39; Israel New Shekels (ILS)

JMD Jamaica Dollars (JMD)

JPY Japan Yen (JPY)

&quot;JEP&quot; Jersey Pounds (JEP)

&quot;JOD&quot; Jordan Dinars (JOD)

KZT&#39; Kazakstan Tenge (KZT)

&quot;KES&quot; Kenya Shillings (KES)

&#39;KWD&#39; Kuwait Dinars (KWD)

KGS&#39; Kirgizistan Soms (KGS)

LAK-kistor (LAK)

&quot;LVL&quot; Lettland Lati (LVL)

&quot;LBP&quot; Libanon Pounds (LBP)

&quot;LSL&quot; Lesotho Maloti (LSL)

&#39;LRD&#39; Liberia Dollars (LRD)

’LYD’ Libyen Dinars (LYD)

&quot;LTL&quot; Litauen Litai (LTL)

&#39;MOP&#39; Macau Patacas (MOP)

&quot;MKD&quot; Makedonien Denars (MKD)

&quot;MGA&quot; Madagaskar Ariary (MGA)

&quot;MWK&quot; Malawi Kwachas (MWK)

&quot;MYR&quot; Malaysia Ringgits (MYR)

MVR&#39; Maldives Rufiyaa (MVR)

&quot;MTL&quot; Malta Liri (MTL)

&quot;MRO&quot; Mauretanien Ouguiyas (MRO)

MUR&#39; Mauritius Rupees (MUR)

&#39;MXN&#39; Mexico Pesos (MXN)

MDL Moldavien Lei (MDL)

&quot;MNT&quot; Mongoliet Tugriks (MNT)

&quot;MAD&quot; Marocko Dirhams (MAD)

&quot;MZN&quot; Mozambique Meticais (MZN)

&quot;MZM&quot; Mozambique Meticais (MZM)

&quot;MMK&quot; Myanmar Kyats (MMK)

&#39;NAD&#39; Namibia Dollars (NAD)

&quot;NPR&quot; Nepal Rupees (NPR)

ANG Nederländska Antillerna Guilders (ANG)

Nya Zeeland-dollar (NZD)

Nicaragua Cordobas (NIO)

NGN i Nigeria Nairas (NGN)

&quot;KPW&quot; Nordkorea Won (KPW)

Norge kronor (NOK)

Oman Rials (OMR)

&quot;PKR&quot; Pakistan Rupees (PKR)

&quot;XPD&quot; Palladium Ounces (XPD)

&#39;PAB&#39; Panama-balboor (PAB)

&quot;PGK&quot; Papua Nya Guinea (PGK)

&quot;PYG&quot; Paraguay Warri (PYG)

&quot;PEN&quot; Peru Nuevos Soles (PEN)

PHP i Filippinerna Pesos (PHP)

&#39;XPT&#39; Platinum Ounces (XPT)

&quot;PLN&quot; Polens Zlotych (PLN)

QAR Qatar Riyals (QAR)

ROL Rumänien Lei (ROL)

RON Rumänien New Lei (RON)

&quot;RUB&quot; Ryssland Rubles (RUB)

&quot;RUR&quot; Ryssland Rubles (RUR)

&quot;RWF&quot; Rwanda Francs (RWF)

&quot;SHP&quot; Saint Helena Pounds (SHP)

&quot;WST&quot; Samoa Tala (WST)

&quot;STD&quot; São Tomé och Príncipe Dobras (STD)

Saudiarabien Riyals (SAR)

&quot;SPL&quot; Seborga Luigini (SPL)

&quot;RSD&quot; serbiska dinarer (RSD)

’värdepapperscentral’ Serbien Dinars (värdepapperscentral)

’SCR’ Seychelles Rupees (SCR)

&quot;SLL&quot; Sierra Leone Leones (SLL)

&quot;XAG&quot; Silver Ounces (XAG)

&quot;SGD&quot; Singapore Dollars (SGD)

&quot;SKK&quot; Slovakien Koruny (SKK)

&quot;SIT&quot; Slovenien Tolars (SIT)

SBD Solomon Islands Dollars (SBD)

’SOS’ Somalia Shillings (SOS)

&quot;ZAR&quot; South Africa Rand (ZAR)

&quot;KRW&quot; Sydkorea Won (KRW)

&quot;LKR&quot; Rupees (LKR)

&quot;SDD&quot; Sudan Dinars (SDD)

SDG Sudan Pounds (SDG)

&#39;SRD&#39; Suriname Dollars (SRD)

&#39;SRG&#39; Suriname Guilders (SRG)

&quot;SZL&quot; Swaziland Emalangeni (SZL)

Sveriges kronor (SEK)

&quot;CHF&quot; Schweiz-francs (CHF)

SYP-syriska pund (SYP)

&quot;TWD&quot; Taiwan New Dollars (TWD)

TJS Tadzjikistan Somoni (TJS)

TZS Tanzania Shillings (TZS)

THB&#39; Thailand Baht (THB)

&#39;TOP&#39; Tonga Pa&#39;anga (TOP)

Trinidad och Tobago Dollars (TTD)

&quot;TND&quot; Tunisien Dinars (TND)

&quot;TRY&quot; Turkey Lira (TRY)

&quot;TRL&quot; Turkiet Liras (TRL)

&quot;TMM&quot; Turkmenistan Manats (TMM)

&quot;TMT&quot; Turkmenistan New Manats (TMT)

&quot;TVD&quot; Tuvalu Dollars (TVD)

&quot;UGX&quot; Uganda Shillings (UGX)

&quot;UAH&quot; Ukraina Hryvnia (UAH)

&quot;AED&quot; Förenade Arabemiraten Dirhams (AED)

&quot;GBP&quot; Förenade kungariket Pounds (GBP)

&quot;USD&quot; valda amerikanska dollar (USD)

&quot;UYU&quot; Uruguay Pesos (UYU)

&#39;UZS&#39; Uzbekistan Sums (UZS)

VUV Vanuatu Vatu (VUV)

VEB’ Venezuela Bolivares (VEB)

&quot;VEF&quot; Venezuela Bolivares Fuertes (VEF)

VND’ Vietnam Dong (VND)

YER&#39; Jemen-rialer (YER)

ZMK&#39; Zambia Kwacha (ZMK)

ZMW Zambia Kwacha (ZMW)

ZWD Zimbabwes dollar (ZWD)


## AppMeasurement.js-exempel

Variabeln `currencyCode` kan definieras globalt i filen AppMeasurement.js. Genom att definiera variabeln currencyCode i den här filen säkerställs att en enhetlig valutakod används för alla valutatransaktioner. I exemplet nedan anges euro som variabeln `currencyCode` i `CONFIG SECTION` för filen AppMeasurement.js. Alla inköpshändelser tolkas genom att de rapporteras som eurotransaktioner.

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
s.account="devnow"
s.currencyCode="EUR"
s.trackInlineStats=true 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
***
    
```

Mer information om hur du redigerar filen AppMeasurement.js finns i [Infoga kod i filen AppMeasurement.js](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html).

## Ytterligare implementeringsinformation

* Tänk på att även om valutakoder kan ändras mellan sidor måste samma valuta användas för alla konverteringsradartiklar som definieras på en viss sidförfrågan (du kan t.ex. inte ha Euro, British Pounds och US Dollars definierade på samma sidvy). Om du inte vill göra någon valutakonvertering bör du lämna värdet currencyCode tomt. Detta gör att skickade värden skickas direkt till rapporter utan konvertering.

* Om du anger en ogiltig currencyCode (ett värde som inte finns i listan över valutakoder som stöds) utesluts hela träffen och data samlas inte in för transaktionen. Innan du ställer in `currencyCode` i produktion ska du använda en testrapportssvit för att kontrollera att data samlas in och att valutakonverteringen är korrekt.

* Valutor som inte använder en punkt (.) eftersom avgränsaren måste ändras så att den använder punkten i stället för den vanliga avgränsaren. Svensk krona, som använder kommatecken (,), måste ändras till att använda en punkt i stället för kommatecken. I Analytics används kommatecken för att avgränsa värden, och data skickas inte korrekt. Perioden skickar värdet korrekt till rapporter.
