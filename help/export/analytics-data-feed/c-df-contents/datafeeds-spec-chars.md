---
description: Information om specialtecken som används i dataflödet.
keywords: Datafeed;jobb;specialtecken;hit_data;multivärdesvariabler;events_list;products_list;mvvars
subtopic: data feeds
title: Specialtecken i dataflöden
feature: Rapporter och analyser - Grunderna och analyser
uuid: 5efe019b-39e6-4226-a936-88202a02f5e6
exl-id: b816ebc5-0b23-4420-aa8c-b88953d031e6
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 1%

---

# Specialtecken i dataflöden

Adobe använder escape-logik för att se till att värden som skickas till datainsamlingsservrar inte är skadade eller negativt datafeedfiler. Följande tecken är reserverade för följande syften i `hit_data.tsv` av Adobe.

## Specialtecken i valfri kolumn

| Tecken | Beskrivning |
|--- |--- |
| `\t` | Representerar en flik. Markerar slutet på en kolumn eller ett datafält. |
| `\n` | Representerar en ny rad. Markerar slutet av en rad eller träff. |
| `\` | Backslash. Undersöker tecken när de skickas som en del av datainsamlingen. |

När dessa reserverade värden föregås av ett omvänt snedstreck skickades de som en del av datainsamlingen.

| Tecken | Beskrivning |
|--- |--- |
| `\\t` | Värdet `\t` skickades under datainsamlingen, escape-konverterat av Adobe. |
| `\\n` | Värdet `\n` skickades under datainsamlingen, escape-konverterat av Adobe. |
| `\\` | Värdet `\` skickades under datainsamlingen, escape-konverterat av Adobe. |

En besökare på webbplatsen använder till exempel intern sökning och söker efter &quot;search\nstring&quot;. Du fyller i eVar1 med &quot;search\nstring&quot; och skickar värdet till Adobe. Adobe tar emot den här träffen och slipper den nya raden som finns i strängen. Det faktiska värdet som placeras i raw-data är &quot;search\\nstring&quot;.

## Specialtecken i variabler med flera värden (events_list, products_list, mvvars)

Följande tecken har en speciell betydelse i kolumner som kan innehålla flera värden.

| Tecken | Beskrivning |
|--- |--- |
| `,` | Komma. Representerar slutet av ett enskilt värde. Separerar produktsträngar, händelse-ID:n eller andra värden. |
| `;` | Halvkolon. Representerar slutet av ett enskilt värde i `product_list`. Separerar fält i en enskild produktsträng. |
| `=` | Likhetstecken. Tilldelar ett värde till en händelse i `product_list`. |
| `^` | Cirkumflex. Undersöker tecken när de skickas som en del av datainsamlingen. |

När dessa reserverade värden föregås av en cirkumflex skickades de som en del av datainsamlingen.

| Tecken | Beskrivning |
|--- |--- |
| `^,` | Värdet `,` skickades under datainsamlingen, escape-konverterat av Adobe. |
| `^;` | Värdet `;` skickades under datainsamlingen, escape-konverterat av Adobe. |
| `^=` | Värdet `=` skickades under datainsamlingen, escape-konverterat av Adobe. |
| `^^` | Värdet `^` skickades under datainsamlingen, escape-konverterat av Adobe. |
