---
description: Klassificeringsreglerna söker regelbundet efter oklassificerade termer. Om en regelmatchning hittas lägger reglerna automatiskt till villkoren i dina klassificeringsdatatabeller. Du kan också använda klassificeringsregler för att skriva över befintliga nycklar.
title: Klassificeringsregler
feature: Classifications
exl-id: 8fe5d838-fa89-4933-a0c0-498d4e59576d
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '1920'
ht-degree: 0%

---

# Klassificeringsregler (äldre)

Klassificeringsreglerna söker regelbundet efter oklassificerade termer. Om en regelmatchning hittas lägger reglerna automatiskt till villkoren i dina klassificeringsdatatabeller. Du kan också använda klassificeringsregler för att skriva över befintliga nycklar.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

Med regelverktyget kan du skapa en *klassificeringsregeluppsättning*, som är en lista med *klassificeringsregler*. En regel matchar de kriterier som du anger och utför sedan en åtgärd.

Klassificeringsreglerna är praktiska för:

* **E-post** och **Visningsannonser**: Skapa klassificeringsregler för att gruppera enskilda displayannonskampanjer så att du kan lära dig hur Display-kampanjer fungerar mot e-postkampanjer.

* **Spårningskoder**: Skapa klassificeringsregler för att kategorisera nyckelvärden som härleds från strängar i spårningskoder och matcha dem med specifika kriterier som du definierar.
* **Söktermer**: Använd [reguljära uttryck](/help/components/classifications/crb/classification-quickstart-rules.md) och jokertecken för att förenkla klassificeringen av söktermer. Om en sökterm till exempel innehåller *`baseball`* kan du ange *`Sports League`* som *`MLB`*.

Anta till exempel att en spårningskod för ett e-postkampanjs-ID är:

`em:Summer:20XX:Sale`.

Du kan ställa in tre regler i en regeluppsättning som identifierar delarna i strängen och sedan klassificera värdena:

| Välj regeltyp | Ange matchningsvillkor | Ange klassificering | Till |
|---|---|---|---|
| Börjar med | em: | Kanal | E-post |
| Slutar med | Försäljning | Typ | Försäljning |
| Innehåller | 20XX | År | 20XX |

## Hur regler bearbetas {#how-rules-are-processed}

Viktig information om hur klassificeringsregler behandlas.

<!-- 

about_classification_rules.xml

 -->

* [Viktig information om regler](/help/components/classifications/crb/classification-rule-builder.md)
* [När klassificerar regler inte nycklar?](/help/components/classifications/crb/classification-rule-builder.md)
* [Om regelprioritet](/help/components/classifications/crb/classification-quickstart-rules.md)

>[!NOTE]
>
>[!UICONTROL Rule Builder] stöder inte Numeric 2-klassificeringar.

## Viktig information om regler

* Ange [gruppbehörigheter](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html?lang=sv-SE) för klassificeringar i [!UICONTROL Admin Tools].

* **Reguljära uttryck**: Hjälp finns under [Reguljära uttryck i klassificeringsregler](/help/components/classifications/crb/classification-quickstart-rules.md).

* **Rapportsviter**: Du kan inte välja en klassificering förrän minst en rapportserie har valts. Du kan inte använda rapportsviten förrän du har skapat regeluppsättningen och tilldelat en variabel.

  När du testar regeluppsättningen kan du använda nycklar (variabeln som klassificeras) från rapporten för att se hur de kommer att påverkas av regeluppsättningen. ([nyckeln](/help/components/classifications/importer/c-saint-data-files.md) är den variabel som klassificeras, eller den första kolumnen i klassificeringens överföringstabell.)

* **Regelprioritet**: Om en nyckel matchar flera regler som anger samma klassificering (i kolumnen [!UICONTROL Set Classification]) används den sista regeln som matchar klassificeringen. Se [Om regelprioritet](/help/components/classifications/crb/classification-quickstart-rules.md).

* **Begränsningar av antalet regler**: Det finns ingen angiven gräns för hur många regler du kan skapa. Ett stort antal regler kan dock påverka webbläsarens prestanda.
* **Bearbetning**: Regler bearbetas med täta intervall, beroende på volymen av klassificeringsrelaterad trafik.

  Aktiva regler bearbetas var fjärde timme och behandlar klassificeringsdata som vanligtvis går tillbaka en månad. Reglerna söker automatiskt efter nya värden och överför klassificeringarna med importverktyget.

* **Skriva över befintliga klassificeringar**: Se [När klassificerar regler inte nycklar?](/help/components/classifications/crb/classification-quickstart-rules.md) Om det behövs kan du ta bort eller ta bort befintliga klassificeringar med hjälp av importeraren.

## När klassificerar regler inte nycklar?

När du aktiverar regler kan du skriva över befintliga klassificeringar. I följande situationer klassificerar en klassificeringsregel inte en [key](/help/components/classifications/importer/c-saint-data-files.md)(variabel) om:

* Nyckeln är redan klassificerad och du väljer inte [Skriv över klassificeringar](/help/components/classifications/crb/classification-rule-definitions.md).

  Du kan skriva över klassificeringar när du [lägger till och aktiverar](/help/components/classifications/crb/classification-quickstart-rules.md) en regel och när du aktiverar en dataanslutningsintegration. (För dataanslutningar skapas regler av partner i Dev Center och visas i [!UICONTROL Classification Rule Builder].)

* En klassificerad nyckel har inte visats i data efter en tidsram som angetts när en nyckel skrevs över, även efter att du aktiverat [Skriv över klassificeringar](/help/components/classifications/crb/classification-rule-definitions.md).
* Nyckeln är inte klassificerad och nyckeln skickas aldrig till [!DNL Adobe Analytics] efter att tidsramen börjar för ungefär en månad sedan.

  >[!NOTE]
  >
  >I rapporter gäller klassificeringar för alla angivna tidsramar när det finns en nyckel. Rapportens datumintervall påverkar inte rapporteringen.

![](assets/overwrite_keys.png)

## Reguljära uttryck i klassificeringsregler {#regex-in-classification-rules}

Använd reguljära uttryck för att matcha konsekvent formaterade strängvärden med en klassificering. Du kan till exempel skapa en klassificering av specifika tecken i en spårningskod. Du kan matcha vissa tecken, ord eller teckenmönster.

>[!NOTE]
>
>Det bästa sättet är att använda reguljära uttryck för att spåra koder som använder avgränsare.

## Reguljärt uttryck - Exempel på spårningskod {#section_2EF7951398EB4C2F8E52CEFAB4032669}

>[!NOTE]
>
>Om spårningskoden är URL-kodad kommer den **inte** att klassificeras av regelbyggaren.

I det här exemplet antar du att du vill klassificera följande kampanj-ID:

Exempelnyckel: `em:JuneSale:20XX0601`

De delar av spårningskoden som du vill klassificera är:

* `em` = e-post
* `JuneSale` = kampanjnamn
* `20XX0601` = datum

Reguljärt uttryck: `^(.+)\:(.+)\:(.+)$`

Så här korrelerar det reguljära uttrycket till kampanj-ID:

![](assets/regex.png)

Matcha grupper: Visar hur det reguljära uttrycket motsvarar kampanj-ID-tecknen, så att du kan klassificera en position i kampanj-ID:t.

![](assets/regex_tracking_code.png)

I det här exemplet anges regeln att kampanjdatumet `20XX0601` finns i den tredje gruppen `(.+)`, som identifieras av `$3`.

**[!UICONTROL Rule Builder]**

Konfigurera regeln på följande sätt i [!UICONTROL Rule Builder]:

| Välj regeltyp | Ange matchningsvillkor | Ange klassificering | Till |
|---|---|---|---|
| Reguljärt uttryck | &Hatt;()+)\:(.+)\:(.+)$ | Kampanjdatum | $3 |

**Syntax**

| Reguljärt uttryck | Sträng eller Matcha resultat | Motsvarande Matcha grupper |
|--- |--- |--- |
| `^(.+)\:(.+)\:(.+)$` | `em:JuneSale:20XX0601` | `$0`: `em:JuneSale:20XX0601` `$1`: em `$2`: JuniSale `$3`: 20XX0601 |
| Skapar syntaxen | `^` = startar raden () = grupperar tecken och låter dig extrahera matchande tecken inom parentes.  `(.+)` = hämtar ett ( . ) och ( + ) eller fler \ = början av en sträng.  `$` = anger att föregående tecken (eller teckengrupp) är det sista tecknet på raden. |

I [Reguljära uttryck - referenstabell](/help/components/classifications/crb/classification-quickstart-rules.md) finns information om vad tecknen i ett reguljärt uttryck betyder.

## Reguljärt uttryck - klassificera ett visst tecken {#section_5D300C03FA484BADACBFCA983E738ACF}

Ett sätt att använda ett reguljärt uttryck är att klassificera ett visst tecken i en teckensträng. Anta till exempel att följande spårningskod innehåller två viktiga tecken:

Exempelnyckel: `4s3234`

* `4` = varumärkesnamn
* `s` = identifierar en sökmotor, som Google

![](assets/regex_char_position.png)

**[!UICONTROL Rule Builder]**

Konfigurera regeln på följande sätt i [!UICONTROL Rule Builder]:

| Välj regeltyp | Ange matchningsvillkor | Ange klassificering | Till |
|--- |--- |--- |--- |
| Reguljärt uttryck | `^.(s).*$` | Varumärke och motor | `$0` (Hämtar de två första tecknen för varumärkesnamn och sökmotor.) |
| Reguljärt uttryck | `^.(s).*$` | Sökmotor | `$1` (Hämtar det andra tecknet för Google.) |

## Reguljära uttryck - matchande spårningskoder med varierande längd {#section_E86F5BF5C2F44ABC8FFCE3EA67EE3BB2}

I det här exemplet visas hur du identifierar specifika tecken mellan kolonavgränsare när du har spårningskoder med olika längder. Adobe rekommenderar att du använder ett reguljärt uttryck för varje spårningskod.

Exempeltangenter:

* `a:b`
* `a:b:c`
* `a:b:c:d`

**Syntax**

![](assets/regex_b.png)

![](assets/regex_varying_length.png)

**[!UICONTROL Rule Builder]**

Konfigurera regeln på följande sätt i [!UICONTROL Rule Builder]:

| Välj regeltyp | Ange matchningsvillkor | Ange klassificering | Till |
|--- |--- |--- |--- |
| Reguljärt uttryck för matchningssträng `a:b` | `^([^\:]+)\:([^\:]+)$` | a | `$1` |
| Reguljärt uttryck för matchningssträng `a:b` | `^([^\:]+)\:([^\:]+)$` | b | `$2` |
| Reguljärt uttryck för matchningssträng `a:b:c` | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | a | `$1` |
| Reguljärt uttryck för matchningssträng `a:b:c` | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | b | `$2` |
| Reguljärt uttryck för matchningssträng `a:b:c` | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | c | `$3` |
| Reguljärt uttryck för matchningssträng `a:b:c:d` | `^([^\:]+)\:([^\:]+)\:([^\:]+)\:([^\:])$` | d | `$4` |

## Reguljära uttryck - Exempel på&quot;Innehåller inte&quot; {#section_FCA88A612A4E4B099458E3EF7B60B59C}

I det här exemplet finns ett reguljärt uttryck som matchar strängar som inte innehåller specifika tecken, i det här fallet `13`.

Reguljärt uttryck:

`^(?!.*13.*).*$`

Teststrängar:

```
a:b:
a:b:1313
c:d:xoxo
c:d:yoyo
```

Matcha resultat:

```
a:b:
c:d:xoxo
c:d:yoyo
```

I det här resultatet visar `a:b:1313` ingen matchning.

## Reguljära uttryck - referenstabell {#section_0211DCB1760042099CCD3ED7A665D716}

| Uttryck | Beskrivning |
|---|---|
| `(?ms)` | Matchar hela det reguljära uttrycket mot flerradiga indata, vilket tillåter . jokertecken som matchar alla radmatningstecken |
| (`?i`) | Gör hela det reguljära uttryckets skiftläge okänsligt |
| [`abc`] | Ett enda tecken: a, b eller c |
| [`^abc`] | Ett enda tecken förutom: a, b eller c |
| [`a-z`] | Ett enskilt tecken i intervallet a-z |
| [`a-zA-Z`] | Ett enskilt tecken i intervallet a-z eller A-Z |
| `^` | Radbörjan (matchar början av raden) |
| `$` | Matcha radens slut (eller före radmatningen i slutet) |
| `\A` | Strängstart |
| `\z` | Strängslut |
| `.` | Matcha alla tecken (utom en ny rad) |
| `\s` | Valfritt blankstegstecken |
| `\S` | Alla tecken som inte är blanksteg |
| `\d` | Alla siffror |
| `\D` | Alla icke-siffror |
| `\w` | Valfritt ordtecken (bokstav, siffra, understreck) |
| `\W` | Valfritt icke-ordtecken |
| `\b` | Valfri ordgräns |
| `(...)` | Fånga allt inneslutet |
| `(a\b)` | a eller b |
| `a?` | Noll eller en av |
| `a*` | Noll eller mer av en |
| `a+` | en eller flera av |
| `a{3}` | Exakt 3 av en |
| `a{3,}` | 3 eller fler av en |
| `a{3,6}` | Mellan 3 och 6 i en |

En bra resurs för att testa giltigheten för reguljära uttryck är [https://rubular.com/](https://rubular.com/).

## Om regelprioritet

Om en nyckel matchas mot flera regler och anger samma klassificeringskolumn som visas i kolumnen [!UICONTROL Set Classification], används den sista regeln. Därför kanske du vill rangordna den viktigaste sista i regeluppsättningen.

<!-- 

rule_priority.xml

 -->

Om du skapar flera regler som inte har samma klassificering spelar bearbetningsordningen ingen roll.

Här följer ett exempel på en sökordsregel som klassificerar sökningstyper för en idrottare:

| Regelnummer | Regeltyp | Matcha | Ange klassificering | Till |
|---|---|---|---|---|
| 1 | Innehåller | Cowboy | Söktyp | Team |
| 2 | Innehåller | Fantasy | Söktyp | Fantasy |
| 3 | Innehåller | Romo | Söktyp | Player |

Om en användare söker efter *`Cowboys fantasy Tony Romo`* klassificeras termen *`Player`* eftersom den matchar den senast givna klassificeringen som visas i kolumnen Ange klassificering.

Anta på samma sätt att du ställer in två regler i en uppsättning för följande söktermer:

| Regelnummer | Regeltyp | Matcha | Ange klassificering | Till |
|---|---|---|---|---|
| 1 | Innehåller | Cowboy | Ort | Dallas |
| 2 | Innehåller | Broncos | Ort | Denver |

En användare söker efter *`Cowboys vs. Broncos`*. Om regelbyggaren hittar en konflikt i regelmatchning, gäller klassificeringen för den andra regeln (Denver) den här sökningen.

## Lägga till en klassificeringsregel i en regeluppsättning {#add-classification-to-rule-set}

<!-- 

t_classification_rule.xml

 -->

Lägg till regler genom att matcha ett villkor med en klassificering och ange åtgärden.

>[!NOTE]
>
>I den här proceduren måste du tillämpa reglerna på en eller flera rapportsviter. Rekommenderat antal regler per regeluppsättning är mellan 500 och 1000, även om det inte finns några begränsningar. Om du har fler än 100 regler kan du förenkla regeluppsättningen genom att använda [underklassificeringar](/help/components/classifications/importer/subclassifications.md).

Så här lägger du till eller redigerar en klassificeringsregel:

1. [Skapa en klassificeringsregeluppsättning](/help/components/classifications/crb/classification-rule-set.md) .
1. Klicka på **[!UICONTROL Add Rule]** på sidan Regeluppsättning.

   ![](assets/add_rule.png)

1. Bredvid **[!UICONTROL Report Suites]** klickar du på **[!UICONTROL Add Suites]** för att ange en eller flera rapportsviter att tilldela till den här regeluppsättningen.

   Sidan **[!UICONTROL Select Report Suites]** visas.

   >[!NOTE]
   >
   >Rapportsviter visas på den här sidan *endast* när följande villkor uppfylls:
   >
   >* Rapportsviterna har minst en klassificering definierad för den variabeln i [!UICONTROL Admin Tools].
   >
   >   (Se *Variabel* i [Klassificeringsregeluppsättningar](/help/components/classifications/crb/classification-rule-set.md) för en förklaring av den här förutsättningen.)
   >
   >* Du har valt rapportsviten på sidan **[!UICONTROL Available Report Suites]**, som visas när du klickar på [Lägg till regeluppsättning](/help/components/classifications/crb/classification-rule-set.md) för att skapa regeluppsättningen.

1. Ange om befintliga värden ska skrivas över:

   | **Regler skriver över befintliga värden** | (Standardinställning) Skriv alltid över befintliga klassificeringsnycklar, inklusive klassificeringar som överförts via importören (SAINT). |
   |---|---|
   | **Regler skriver bara över borttagna värden** | Fyll bara i tomma celler (ta bort). Befintliga klassificeringar ändras inte. |

1. [Definiera regeln eller reglerna](/help/components/classifications/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529).

   ![Stegresultat](assets/classification_rules_page.png)

   Exempel på hur du skapar regler finns i [Klassificeringsregelbyggaren](/help/components/classifications/crb/classification-rule-builder.md) och [Reguljära uttryck i klassificeringsregler](/help/components/classifications/crb/classification-quickstart-rules.md).

   >[!NOTE]
   >
   >Om en nyckel matchar flera regler som anger samma klassificering (i kolumnen Ange klassificering) används den sista regeln som matchar klassificeringen. Mer information om sorteringsregler finns i **Om regelprioritet** ovan.

1. [Testa regeluppsättningen](/help/components/classifications/crb/classification-quickstart-rules.md).
1. Klicka på **[!UICONTROL Active]** efter testningen för att validera och aktivera regeln.

   När du aktiverar en regel skapas filen automatiskt och den överförs åt dig.

   Fältdefinitioner: Se [Klassificeringsregelbyggaren](/help/components/classifications/crb/classification-rule-definitions.md) för fullständiga definitioner av gränssnittsalternativ på den här sidan.

## Testa en klassificeringsregeluppsättning

<!-- 

t_classifications_test_rule.xml

 -->

Du kan testa en klassificeringsregel eller regeluppsättning. När du kör ett test kontrolleras alla regler i en uppsättning.

Så här testar du en klassificeringsregeluppsättning:

1. [Skapa en klassificeringsregeluppsättning](/help/components/classifications/crb/classification-rule-set.md) .
1. Klicka på regeluppsättningens namn på [!UICONTROL Classification Rule Builder].
1. Kontrollera att regeluppsättningen är associerad med en rapportserie.
1. Klicka på **[!UICONTROL Test Rule Set]** i regelredigeraren.

   ![Stegresultat](assets/classification_test_rule_set.png)

1. Skriv eller klistra in testnycklar i fältet [!UICONTROL Sample Keys].

   Exempelnycklar:

   * Spårningskoder
   * Sök efter nyckelord eller fraser

   Mer information om hur du testar reguljära uttryck finns i [Reguljära uttryck i klassificeringsregler](/help/components/classifications/crb/classification-quickstart-rules.md).
1. Klicka på **[!UICONTROL Run Test]**.

   Regler som matchar visas i tabellen [!UICONTROL Results].
1. (Valfritt) Klicka på **[!UICONTROL Activate]** om du vill aktivera regeln och skriva över befintliga klassificeringar.

   Mer information om hur du använder regler för att skriva över befintliga klassificeringar finns.

## Validera och aktivera klassificeringsregler

<!-- 

t_validate_rules.xml

 -->

Så här validerar och aktiverar du klassificeringsregler:

1. [Skapa en klassificeringsregeluppsättning](/help/components/classifications/crb/classification-rule-set.md) och [lägg sedan till klassificeringsregler](/help/components/classifications/crb/classification-quickstart-rules.md) i uppsättningen.
1. Klicka på **[!UICONTROL Activate]** i regelredigeraren.

   ![](assets/overwrite_keys.png)

1. (Valfritt) Om du vill skriva över klassificeringar aktiverar du **[!UICONTROL Overwrite classifications for]** &lt;*selection*>.

   Med det här alternativet kan du skriva över befintliga klassificeringar för berörda nycklar.

   En definition av det här alternativet finns på [Regelsidan](/help/components/classifications/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529).
