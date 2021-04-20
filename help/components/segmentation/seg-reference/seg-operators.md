---
description: Med segmentbyggaren kan du jämföra och begränsa värden med valda operatorer.
title: Jämförelseoperatorer för segment
feature: Segmentation
uuid: 02ad814c-2c7c-4833-9bb2-4113dcf9475d
exl-id: 1ec1ff05-03a9-4151-8fcb-a72ebbce87dd
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 1%

---

# Jämförelseoperatorer för segment

Med segmentbyggaren kan du jämföra och begränsa värden med hjälp av valda operatorer.

Det finns tre kategorier av operatorer: Standard, Data warehouse och Distinct Count.

Det enda jokertecken som stöds är asterisk: *. Om du behöver söka efter * kan du undvika det med ett omvänt snedstreck.

**Exempel**: Anta att du har ett sidnamn som heter&quot;Min coola produkt&quot;. Segmentregeln &quot;Sidnamnet matchar My*product&quot; kommer att matcha ovanstående sidnamn. Däremot matchar regeln&quot;Sidnamn matchar Min\\*produkt&quot; bara sidnamnet&quot;Min*produkt&quot;.

| Operator | Den valda dimensionen, segmentet eller metriska händelsen... |
|--- |--- |
| **Standard** |  |
| är lika med | Returnerar objekt som matchar exakt för ett numeriskt värde eller strängvärde. Obs!  Om du använder jokertecken använder du operatorn &quot;match&quot;. |
| är inte lika med | Returnerar alla objekt som inte innehåller den exakta matchningen av det angivna värdet.  Obs!  Om du använder jokertecken använder du operatorn &quot;matchar inte&quot;. |
| är lika med något av | Returnerar objekt som matchar exakt för alla värden i indatafältet (upp till 500 objekt). Om du till exempel anger &quot;Sökresultat, hemsida&quot; med den här operatorn matchar &quot;Sökresultat&quot; och &quot;Hemsida&quot; och räknas som två objekt. Indatafältet för den här operatorn är kommaavgränsat. |
| motsvarar inte något av | Identifierar objekt som matchar exakt för alla värden i indatafältet (upp till 500 objekt) och returnerar sedan bara objekt utan dessa värden. Om du t.ex. anger &quot;Sökresultat, hemsida&quot; med den här operatorn identifieras &quot;Sökresultat&quot; och &quot;Hemsida&quot; och utesluts sedan från de returnerade objekten. Det här exemplet räknas som 2 objekt. Indatafältet för den här operatorn är kommaavgränsat. |
| innehåller | Returnerar objekt som jämför med delsträngarna för de angivna värdena. Om regeln för &quot;Sida&quot; till exempel innehåller &quot;Sök&quot;, kommer den att matcha alla sidor som innehåller delsträngen &quot;Sök&quot;, inklusive &quot;Sökresultat&quot;, &quot;Sök&quot; och &quot;Sökning&quot;. |
| innehåller inte | Returnerar inversen av regeln &quot;contains&quot;. I synnerhet kommer alla objekt som matchar det angivna värdet att exkluderas från de angivna värdena. Om regeln för &quot;Sida&quot; till exempel inte innehåller &quot;Sök&quot;, kommer den inte att matcha någon sida som innehåller delsträngen &quot;Sök&quot;, inklusive &quot;Sökresultat&quot;, &quot;Sök&quot; och &quot;Sökning&quot;. Dessa värden kommer att uteslutas från resultaten. |
| innehåller alla | Returnerar objekt jämfört med delsträngarna, inklusive flera värden som sammanfogats. Om du till exempel anger &quot;Sökresultat&quot; med den här operatorn skulle det matcha &quot;Sökresultat&quot; och &quot;Sökresultat&quot;, men inte &quot;Sök&quot; eller &quot;Resultat&quot; separat. Det skulle matcha sökningar och resultat som hittades tillsammans. Indatafältet för den här operatorn är blankstegsavgränsat (100 ord). |
| innehåller inte alla | Identifierar objekt jämfört med delsträngar - inklusive flera värden som förenas - och returnerar sedan bara objekt utan dessa värden. Om du t.ex. anger &quot;Sökresultat&quot; med den här operatorn skulle det identifiera &quot;Sökresultat&quot; och &quot;Sökresultat&quot; (men inte &quot;Sök&quot; eller &quot;Resultat&quot; separat) och sedan utesluta dessa objekt. Indatafältet för den här operatorn är blankstegsavgränsat (100 ord). |
| innehåller någon av | Returnerar objekt jämfört med delsträngarna, inklusive flera värden som är förenade eller oberoende av varandra. Om du till exempel anger &quot;Sökresultat&quot; med den här operatorn matchar det &quot;Sökresultat&quot;, &quot;Sökresultat&quot;, &quot;Sök&quot; och &quot;Resultat&quot;. Det skulle matcha antingen &quot;Sök&quot; ELLER &quot;Resultat&quot; som hittades tillsammans eller oberoende av varandra. Indatafältet för den här operatorn är blankstegsavgränsat (100 ord). |
| innehåller inte något av | Identifierar objekt baserat på delsträngar och returnerar sedan värden som inte innehåller dessa delsträngar. Den kan ha flera sammanfogade värden eller värden som identifieras separat. Om du till exempel anger &quot;Sökresultat&quot; matchar&quot;Sökresultat&quot;, &quot;Sökresultat&quot;, &quot;Sök&quot; och &quot;Resultat&quot; där antingen &quot;Sök&quot; eller &quot;Resultat&quot; hittas tillsammans eller oberoende av varandra. Då exkluderas objekt som innehåller dessa delsträngar. Indatafältet för den här operatorn är blankstegsavgränsat (100 ord). |
| börjar med | Returnerar objekt som börjar med tecknet eller strängarna för det angivna värdet. |
| börjar inte med | Returnerar alla objekt som inte börjar med tecknen eller strängarna för de angivna värdena. Det här är inversen till operatorn &quot;börjar med&quot;. |
| slutar med | Returnerar objekt som slutar med tecknet eller strängarna för det angivna värdet. |
| slutar inte med | Returnerar alla objekt som inte slutar med tecknen eller strängarna för det angivna värdet. Detta är inversen till operatorn &quot;ends with&quot;. |
| matchar | Returnerar objekt som matchar exakt baserat på ett givet numeriskt värde eller strängvärde. Obs!  Använd den här operatorn när du använder jokertecken (globbing). |
| matchar inte | Returnerar alla objekt som inte innehåller den exakta matchningen av det angivna värdet. Obs!  Använd den här operatorn när du använder jokertecken (globbing). |
| exists | Returnerar antalet objekt som finns. Om du till exempel utvärderar dimensionen Sidor som inte hittas med operatorn &quot;finns&quot; returneras antalet felsidor som finns. |
| finns inte | Returnerar alla objekt som inte finns. Om du till exempel utvärderar dimensionen Ej hittade sidor med operatorn &quot; finns inte&quot; returneras antalet sidor där den här felsidan inte fanns. |
| **Data Warehouse** |  |
| är mindre än | Returnerar objekt vars numeriska antal är mindre än det angivna värdet. |
| är mindre än eller lika med | Returnerar objekt vars numeriska värde är mindre än eller lika med det angivna värdet. |
| är större än | Returnerar objekt vars numeriska antal är större än det angivna värdet. |
| är större än eller lika med | Returnerar objekt vars numeriska värde är större än eller lika med det angivna värdet. |
| **Distinkt antal** | Du kan segmentera ett visst antal artiklar i en dimension. Exempel: &quot;Besökare som tittade på mer än fem olika produkter&quot; eller &quot;Besök där mer än fem olika sidor sågs.&quot; |
| är lika med | Returnerar dimensionsobjekt vars unika antal är lika med det angivna värdet. |
| är inte lika med | Returnerar dimensionsobjekt vars unika antal inte är lika med det angivna värdet. |
| är större än | Returnerar dimensionsobjekt vars unika antal är större än det angivna värdet. |
| är mindre än | Returnerar dimensionsobjekt vars unika antal är mindre än det angivna värdet. |
| är större än eller lika med | Returnerar dimensionsobjekt vars unika antal är större än eller lika med det angivna värdet. |
| är mindre än eller lika med | Returnerar dimensionsobjekt vars unika antal är mindre än eller lika med det angivna värdet. |
