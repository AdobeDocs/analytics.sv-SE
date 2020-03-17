---
description: Sammanhangsberoende sessioner i virtuella rapportsviter ändrar hur Adobe Analytics beräknar mobilbesök. I den här artikeln beskrivs konsekvenserna av bakgrundstötar och appstarthändelser (som båda anges av SDK för mobiler) för hur mobilbesök definieras.
title: Sammanhangsberoende sessioner
uuid: d354864a-9163-4970-a3a0-f2e9729bdbe3
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Sammanhangsberoende sessioner

Sammanhangsberoende sessioner i virtuella rapportsviter ändrar hur Adobe Analytics beräknar mobilbesök. I den här artikeln beskrivs konsekvenserna av bakgrundstötar och appstarthändelser (som båda anges av SDK för mobiler) för hur mobilbesök definieras.

Ni kan definiera ett besök som ni vill utan att ändra underliggande data, så att det matchar hur besökarna interagerar med era mobilappar.

## URL-parameter för kundperspektiv {#section_8B298006362341E3AC16A148422D1F65}

Med datainsamlingsprocessen i Adobe Analytics kan du ställa in en frågesträngsparameter som anger kundperspektivet (anges som frågesträngsparametern&quot;cp&quot;). I det här fältet anges tillståndet för slutanvändarens digitala program. Detta hjälper dig att veta om en träff genererades när en mobilapp befann sig i bakgrundsläge.

## Bearbetning av bakgrundsträff {#section_D47B3161B7E145B6A32AB06E9AA03FA3}

En bakgrundträff är en typ av träff som skickas till Analytics från Adobe Mobile SDK version 4.13.6 och senare när appen gör en spårningsbegäran i bakgrundsläge. Typiska exempel på detta är:

* Data som skickas under en geofästning
* En push-meddelandeinteraktion

I följande exempel beskrivs logiken som används för att avgöra när ett besök startar och avslutas för en besökare när inställningen&quot;Förhindra bakgrundstötningar från att starta ett nytt besök&quot; är aktiverad eller inte är aktiverad för en virtuell rapportserie.

**Om alternativet Förhindra att bakgrundsträffar startar ett nytt besök inte är aktiverat:**

Om den här funktionen inte är aktiverad för ett virtuellt rapportpaket behandlas bakgrundstötningar som alla andra träff, vilket innebär att de startar nya besök och fungerar på samma sätt som förgrundstötningar. Om till exempel en bakgrundsträff inträffar mindre än 30 minuter (standardsessionstimeout för en rapportsvit) före en uppsättning förgrundsträffar, är bakgrundsträffen en del av sessionen.

![](assets/nogood1.jpg)

Om bakgrundstöten inträffar mer än 30 minuter före några förgrundstötningar skapar bakgrundstötningen ett eget besök, med ett totalt besöksantal på 2.

![](assets/nogood2.jpg)

**Om alternativet Förhindra att bakgrundstötningar startar ett nytt besök är aktiverat:**

Följande exempel visar hur bakgrundstötningar fungerar när den här funktionen är aktiverad.

Exempel 1: En bakgrundsträff inträffar en viss tidsperiod (t) före en serie förgrundsträffar.

![](assets/nogoodexample1.jpg)

I det här exemplet, om *t* är större än den virtuella rapportsvitens konfigurerade tidsgräns för besök, utesluts bakgrundskompensationen från besöket som utgörs av förgrundsträffarna. Om tidsgränsen för besöket i den virtuella rapportsviten var inställd på 15 minuter och *den* var 20 minuter, skulle besöket som utgörs av den här serien träffar (visas med den gröna konturen) utesluta bakgrundssessionen. Det innebär att alla eVars-variabler som har en &quot;besök&quot;-förfallotid på bakgrundsträffen **inte** kvarstår vid följande besök, och en besökssegmentbehållare skulle bara innehålla förgrundsträffarna inuti den gröna konturen.

![](assets/nogoodexample1-2.jpg)

Omvänt gäller att om *t* är mindre än tidsgränsen för det virtuella rapportsvitens konfigurerade besök, inkluderas bakgrundsträffen som en del av besöket som om det var en förgrundsträff (visas med den gröna konturen):

![](assets/nogoodexample1-3.jpg)

Detta innebär att

* Alla eVars-variabler som har &quot;besök&quot; som förfallodatum i bakgrunden fortsätter att visa sina värden på de andra träffarna i det här besöket.
* Alla värden som anges i bakgrundsträffen inkluderas i logikutvärderingen för besöksnivåsegmentets behållare.

I båda fallen blir det totala antalet besök 1.

Exempel 2: Om en bakgrundsträff inträffar efter en serie förgrundsträffar fungerar det ungefär så här:

![](assets/nogoodexample2.jpg)

Om bakgrundsträffen inträffar efter att den virtuella rapportsvitens konfigurerade tidsgräns har uppnåtts, är bakgrundsträffen inte en del av en session (anges i grönt):

![](assets/nogoodexample2-1.jpg)

Om tidsperioden *t* var kortare än den konfigurerade tidsgränsen för den virtuella rapportsviten, inkluderas även bakgrundsträffen i det besök som skapades av de föregående förgrundsträffarna:

![](assets/nogoodexample2-2.jpg)

Detta innebär att

* Alla eVars-variabler med förfallodatum för besök på föregående förgrundsträffar behåller sina värden på bakgrundsträffen i det här besöket.
* Alla värden som anges i bakgrundsträffen inkluderas i logikutvärderingen för besöksnivåsegmentets behållare.

Som tidigare är det totala antalet besök i båda fallen 1.

Exempel 3: I vissa fall kan en bakgrundstöt göra att två separata besök kombineras till ett enda besök. I följande scenario föregås och följs en bakgrundsträff av en serie förgrundsträffar:

![](assets/nogoodexample3.jpg)

Om både *t1* och *t2* i det här exemplet är mindre än tidsgränsen för konfigurerade besök i den virtuella rapportsviten, kombineras alla dessa träffar till ett enda besök, även om *t1* och *t2* tillsammans är större än tidsgränsen för besök:

![](assets/nogoodexample3-1.jpg)

Om *t1* och *t2* är större än den konfigurerade tidsgränsen för den virtuella rapportsviten skulle dessa träffar delas upp i två skilda besök:

![](assets/nogoodexample3-2.jpg)

Om *t1* är mindre än tidsgränsen och *t2* är mindre än tidsgränsen (som i våra tidigare exempel) inkluderas även bakgrundsträffen i det första besöket:

![](assets/nogoodexample3-3.jpg)

Om *t1* är större än tidsgränsen och *t2* är mindre än tidsgränsen, inkluderas bakgrundsträffen i det andra besöket:

![](assets/nogoodexample3-4.jpg)

Exempel 4: I scenarier där en serie bakgrundsträffar inträffar inom tidsgränsen för besöket i den virtuella rapportsviten utgör träffarna ett osynligt&quot;bakgrundsbesök&quot; som inte räknas in i besöksantalet och som inte är tillgängligt med en besökssegmenteringsbehållare.

![](assets/nogoodexample4.jpg)

Även om detta inte betraktas som ett besök kvarstår värdena för de eVars-uppsättningar som har en förfallotid för besök i bakgrunden i det här bakgrundsbesöket.

Exempel 5: För scenarier där flera bakgrundsträffar inträffar i följd efter en serie förgrundsträffar är det möjligt (beroende på timeoutinställningen) att bakgrundstötarna håller ett besök levande längre än tidsgränsen för besöket. Om *t1* och *t2* tillsammans till exempel var större än tidsgränsen för besöket i den virtuella rapportsviten men var och en mindre än tidsgränsen, skulle besöket ändå omfatta båda bakgrundstötarna:

![](assets/nogoodexample5.jpg)

Om en serie bakgrundstötningar inträffar före en serie förgrundshändelser händer samma sak:

![](assets/nogoodexample5-1.jpg)

Bakgrundsstötarna beter sig på det här sättet för att bevara eventuella attribueringseffekter från eVars eller andra variabler som angetts under bakgrundstötningar. Detta gör att konverteringshändelser för förgrundskonvertering kan kopplas till åtgärder som vidtas när en app befinner sig i bakgrundsläge. Det gör också att en besökssegmentbehållare kan innehålla bakgrundstötar som resulterat i en efterföljande förgrundssession, vilket är användbart för att mäta effekten av push-meddelanden.

## Besök metrisk beteende {#section_50B82618A39B454493B33B1450CCBD3E}

Besöken baseras endast på antalet besök som omfattar minst en förgrundsträff. Det innebär att eventuella överblivna bakgrundstötningar eller &quot;bakgrundsbesök&quot; inte räknas in i besöksmätningen.

## Tidsåtgång per besök, mätarbeteende {#section_0A149ABB3E034B97BD0B3A7F3EB67383}

Tidsåtgången beräknas fortfarande på ett liknande sätt som den är utan bakgrundstötningar med hjälp av tiden mellan träffarna. Även om ett besök omfattar bakgrundstötar (eftersom de inträffade så nära förgrundsträffarna), inkluderas dessa träffar i den tid som läggs på per besök som om de vore en förgrundsträff.

## Bearbetningsinställningar för bakgrundsträff {#section_C8B1D38C06FF4ABAAFA78CE9550C0F4B}

Eftersom träffbearbetning i bakgrunden endast är tillgänglig för virtuella rapportsviter som använder Report Time Processing, har Adobe Analytics stöd för två sätt att bearbeta bakgrundsträffar för att bevara antalet besök i basrapportsviten som inte använder Report Time Processing. Om du vill få tillgång till den här inställningen går du till Adobe Analytics Admin Console, till inställningarna för den tillämpliga basrapportsviten, går till menyn&quot;Hantering av mobilappar&quot; och sedan till undermenyn&quot;Rapportering av mobilprogram&quot;.

1. &quot;Äldre bearbetning på&quot;: Det här är standardinställningen för alla rapportsviter. Att lämna äldre bearbetning på processens bakgrundsträffar som vanliga träffar i vår bearbetningsprocess när det gäller rapportsviten som inte är Report Time Attribution base. Det innebär att eventuella bakgrundstötningar som visas i basrapportsvitens stegvisa ökningar blir en normal träff. Om du inte vill att bakgrundsträffar ska visas i din basrapportsserie ändrar du den här inställningen till Av.
1. &quot;Äldre bearbetning av&quot;: När äldre bearbetning för bakgrundstötlar är inaktiverat ignoreras alla bakgrundstötningar som skickas till basrapportsviten av den grundläggande rapportsviten och är bara tillgängliga när en virtuell rapportsvit som skapats med den här basrapportsviten har konfigurerats för att använda Report Time Processing. Det innebär att alla data som har hämtats av bakgrundsträffar som skickas till den här basrapportsviten bara visas i en virtuell rapportserie som har aktiverats för Report Time Processing.

   Den här inställningen är avsedd för kunder som vill dra nytta av den nya bakgrundsbearbetningen utan att behöva ändra antalet besök i sina basrapporter.

I båda fallen faktureras bakgrundstötarna till samma kostnad som andra träffar som skickas till Analytics.

## Starta nya besök vid varje appstart {#section_9DA9A8B9758248A6B311EFBA06AECA80}

Förutom träffbearbetning i bakgrunden kan virtuella rapportsviter tvinga ett nytt besök att starta när mobilens SDK skickar en programstarthändelse. När den här inställningen är aktiverad kommer ett nytt besök att starta varje gång en programstarthändelse skickas från SDK, oavsett om ett öppet besök har nått sin tidsgräns eller inte. Den träff som innehåller applanseringshändelsen inkluderas som den första träffen vid nästa besök, och ökar antalet besök och skapar en tydlig besöksbehållare för segmentering.
