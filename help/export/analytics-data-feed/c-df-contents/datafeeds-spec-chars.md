---
description: Information om specialtecken som används i dataflödet.
keywords: Data Feed;job;special characters;hit_data;multi-valued variables;events_list;products_list;mvvars
subtopic: data feeds
title: Specialtecken i dataflöden
topic: Reports and analytics
uuid: 5efe019b-39e6-4226-a936-88202a02f5e6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Specialtecken i dataflöden

Adobe använder escape-logik för att säkerställa att värden som skickas till datainsamlingsservrar inte är skadade eller negativt datafeedfiler. Följande tecken är reserverade för följande syften i `hit_data.tsv`.

## Specialtecken i valfri kolumn

| Tecken | Beskrivning |
|--- |--- |
| `\t` | Representerar en flik. Markerar slutet på en kolumn eller ett datafält. |
| `\n` | Representerar en ny rad. Markerar slutet av en rad eller träff. |
| `\` | Backslash. Undersöker tecken när de skickas som en del av datainsamlingen. |

När dessa reserverade värden föregås av ett omvänt snedstreck skickades de som en del av datainsamlingen.

| Tecken | Beskrivning |
|--- |--- |
| `\\t` | Värdet&quot;`\t`&quot; skickades under datainsamlingen, som rymdes av Adobe. |
| `\\n` | Värdet&quot;`\n`&quot; skickades under datainsamlingen, som rymdes av Adobe. |
| `\\` | Värdet&quot;`\`&quot; skickades under datainsamlingen, som rymdes av Adobe. |

En besökare på webbplatsen använder till exempel intern sökning och söker efter &quot;search\nstring&quot;. Du fyller i eVar1 med &quot;search\nstring&quot; och skickar värdet till Adobe. Adobe tar emot den här träffen och slipper den nya raden som finns i strängen. Det faktiska värdet som placeras i raw-data är &quot;search\\nstring&quot;.

## Specialtecken i variabler med flera värden (events_list, products_list, mvvars)

Följande tecken har en speciell betydelse i kolumner som kan innehålla flera värden.

| Tecken | Beskrivning |
|--- |--- |
| `,` | Komma. Representerar slutet av ett enskilt värde. Separerar produktsträngar, händelse-ID:n eller andra värden. |
| `;` | Halvkolon. Representerar slutet på ett enskilt värde i `product_list`. Separerar fält i en enskild produktsträng. |
| `=` | Likhetstecken. Tilldelar ett värde till en händelse i `product_list`. |
| `^` | Cirkumflex. Undersöker tecken när de skickas som en del av datainsamlingen. |

När dessa reserverade värden föregås av en cirkumflex skickades de som en del av datainsamlingen.

| Tecken | Beskrivning |
|--- |--- |
| `^,` | Värdet&quot;`,`&quot; skickades under datainsamlingen, som rymdes av Adobe. |
| `^;` | Värdet&quot;`;`&quot; skickades under datainsamlingen, som rymdes av Adobe. |
| `^=` | Värdet&quot;`=`&quot; skickades under datainsamlingen, som rymdes av Adobe. |
| `^^` | Värdet&quot;`^`&quot; skickades under datainsamlingen, som rymdes av Adobe. |
