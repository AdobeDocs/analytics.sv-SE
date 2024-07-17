---
description: Information om specialtecken som används i dataflödet.
keywords: Datafeed;jobb;specialtecken;hit_data;multivärdesvariabler;events_list;products_list;mvvars
subtopic: data feeds
title: Specialtecken i dataflöden
feature: Data Feeds
exl-id: b816ebc5-0b23-4420-aa8c-b88953d031e6
source-git-commit: 6e59ee3cb3eb59b025053603cd1357c5a2709d00
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 1%

---

# Specialtecken i dataflöden

Adobe använder escape-logik för att se till att värden som skickas till datainsamlingsservrar inte är skadade eller negativt datafeedfiler. Följande tecken har reserverats av Adobe för följande syften i `hit_data.tsv`.

## Specialtecken i valfri kolumn

| Tecken | Beskrivning |
|--- |--- |
| `\t` | Representerar en flik. Markerar slutet på en kolumn eller ett datafält. |
| `\n` | Representerar en ny rad. Markerar slutet av en rad eller träff. |
| `\` | Backslash. Undersöker tecken när de skickas som en del av datainsamlingen. |

När dessa reserverade värden föregås av ett omvänt snedstreck skickades de som en del av datainsamlingen.

| Tecken | Beskrivning |
|--- |--- |
| `\\t` | Värdet `\t` skickades under datainsamlingen, som escape-konverterades av Adobe. |
| `\\n` | Värdet `\n` skickades under datainsamlingen, som escape-konverterades av Adobe. |
| `\\` | Värdet `\` skickades under datainsamlingen, som escape-konverterades av Adobe. |

En besökare på din webbplats använder till exempel intern sökning och sökningar för `"search\nstring"`. Du fyller i eVar1 med `"search\nstring"` och skickar det värdet till Adobe. Adobe tar emot den här träffen och flyter från den nya raden som finns i strängen. Det faktiska värdet i rådata är `"search\\nstring"`.

## Specialtecken i variabler med flera värden (events_list, products_list, mvvars)

Följande tecken har en speciell betydelse i kolumner som kan innehålla flera värden.

| Tecken | Beskrivning |
|--- |--- |
| `,` | Komma. Representerar slutet av ett enskilt värde. Separerar produktsträngar, händelse-ID eller andra värden. |
| `;` | Halvkolon. Representerar slutet på ett enskilt värde i `product_list`. Separerar fält i en enskild produktsträng. |
| `=` | Likhetstecken. Tilldelar ett värde till en händelse i `product_list`. |
| `^` | Cirkumflex. Undersöker tecken när de skickas som en del av datainsamlingen. |

När dessa reserverade värden föregås av en cirkumflex skickades de som en del av datainsamlingen.

| Tecken | Beskrivning |
|--- |--- |
| `^,` | Värdet `,` skickades under datainsamlingen, som escape-konverterades av Adobe. |
| `^;` | Värdet `;` skickades under datainsamlingen, som escape-konverterades av Adobe. |
| `^=` | Värdet `=` skickades under datainsamlingen, som escape-konverterades av Adobe. |
| `^^` | Värdet `^` skickades under datainsamlingen, som escape-konverterades av Adobe. |
