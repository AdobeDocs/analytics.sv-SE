---
description: Instruktioner om hur du kör Ad Hoc-analys med Java 11.
title: Kör ad hoc-analys med Java 11
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Kör ad hoc-analys med Java 11

Du måste följa ytterligare steg när du kör ad hoc-analys med Java 11 jämfört med att köra den med Java 8.

## Förutsättningar

Samarbeta med IT-avdelningen för att säkerställa att följande finns:

* Java 11 måste vara installerat med *JAVA_HOME* -miljövariabeln inställd
* JavaFX måste vara installerat, och miljövariabeln *PATH_TO_FX_SDK* pekar på JavaFX SDK-katalogen. Exempel: *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* på en Mac eller *PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* på en PC.

## Installera ad hoc-analys för Java 11

1. Gå till **[!UICONTROL Analytics > Tools > Ad Hoc Analysis]**.
1. Klicka på **[!UICONTROL Ad Hoc Analysis (Java 11)]**. Detta hämtar en zip-fil.
1. Zippa upp den hämtade filen.
1. **Markera .bat- (PC) eller .sh-filen**(Mac). Välj lämplig datacenterfil genom att titta på numret efter sc i Adobe Analytics-webbadressen. (3 = LON, 4 = SIN, 5 = PNW) Om du använder en dator kontrollerar du om du kör ett 32-bitars eller ett 64-bitars Windows-operativsystem genom att gå till &quot;Om din dator&quot;. Välj sedan lämplig .bat-fil.
1. **Kör den valda filen**. För PC: Dubbelklicka på .bat-filen. För Mac: Högerklicka på .sh-filen och välj sedan **[!UICONTROL Open With > Other... > Utilities > (Enable all applications) > select Terminal > Open]**.
1. Logga in på Ad hoc-analys.

> [!NOTE] Autentiseringsmetoderna Federated ID och Enterprise ID är inte kompatibla med Java 11-versionen av Ad Hoc Analysis.

## Funktioner som inte stöds i Ad hoc-analys (Java 11)

Det finns några kända begränsningar i Java 11-versionen som är kompatibel med Ad Hoc Analysis:

* Autentiseringsmetoderna Federated ID och Enterprise ID stöds inte.
* Linux-operativsystem stöds inte.
* Använd inte Mac-programmenyn (inklusive *cmd + Q*) när du använder en Mac. Detta kan göra att Ad hoc-analysen stängs utan förvarning. Använd i stället menyn i Ad Hoc-analys.
* Visualisering av platsanalys stöds inte när Ad Hoc-analys körs i Mac OS.

## Vanliga frågor

**F: Jag får ett felmeddelande om att det inte går att hitta \bin\javaw (exempel nedan) - vad ska jag göra?**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

S: Om du får det här felet kan du tillsammans med IT-teamet ställa in *JAVA_HOME* -systemvariabeln som krävs för att köra Ad Hoc-analys i Java 11.
