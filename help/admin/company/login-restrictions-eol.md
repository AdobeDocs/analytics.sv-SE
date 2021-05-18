---
title: Slutet av livscykeln för [!UICONTROL Enforce IP login restrictions]
description: Lär dig mer om timing och konsekvenser för [!UICONTROL Enforce IP login restrictions]
exl-id: 67d822ee-005b-46cf-80b4-a5aa4412d746
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 0%

---

# Slutet av livscykeln för [!UICONTROL Enforce IP login restrictions]

Med funktionen **[Tvinga begränsningar för IP-inloggning](/help/admin/company/security-manager.md)** i Adobe Analytics kan du lägga till specifika IP-adresser (som anses säkra) i en tillåtelselista, så att du kan logga in och få åtkomst till din Adobe Analytics-miljö. I många fall används den här funktionen för att konfigurera en företags-IP-adress som den enda säkra IP-adressen som användare kan logga in från. För att kunna använda Adobe Analytics måste användarna antingen vara på ett företagskontor eller logga in i nätverket via VPN.

Vi planerar att avsluta den här funktionen i januari 2021.

## Varför upphör den här funktionen?

Den här funktionen bryts under vissa omständigheter av migreringen av inloggningen till Experience Cloud och/eller inloggningen till Experience Cloud. Det är känt att brytas för kunder som använder **[!UICONTROL Customer Attributes]** eller **[!UICONTROL Audience Library]**.

Om du äger flera Experience Cloud-lösningar kan du dessutom kringgå detta krav genom att logga in på Experience Cloud med en av de andra lösningarna, eftersom den här funktionen inte finns eller inte stöds utanför själva analysen. Användare kan också kringgå detta via IP-förfalskning.

Slutligen har Adobe en fungerande och överlägsen alternativ lösning via Single-Sign-On och Federated ID. Med den här funktionen får du bättre kontroll och säkerhet över användarnas inloggning. Mer information finns nedan.

## Hur påverkar borttagningen av den här funktionen dig?

För alla kunder som har **[!UICONTROL Enforce IP login restrictions]** installerat tas den här funktionen bort i januari 2021. Vid den tidpunkten kommer eventuella begränsningar för IP-inloggning som fortfarande gäller inte längre att gälla. Om du fortfarande behöver begränsa inloggningen med IP-adressen bör du granska och implementera den rekommenderade lösningen för enkel inloggning och Federated ID (mer information och resurser nedan).

Dessutom kommer **[!UICONTROL Enforce IP login restrictions]**-inställningen att tas bort från **[!UICONTROL Admin]> [!UICONTROL All admin] > [!UICONTROL Company settings] >[!UICONTROL Security Manager]** i analysgränssnittet (se nedan).

![](assets/sec-manager2.png)

## Vilka andra alternativ har du?

Den här analysfunktionen upphör som sagt. För att ge dig tid att implementera SSO och Federated ID har vi fördröjt EOL-datumet till januari 2021.

Både SSO och Federated ID är överlägsna lösningar jämfört med funktionen för IP-inloggningsbegränsning som vi har på plats idag och ger dig bättre kontroll, säkerhet och funktioner. Mer information om hur du konfigurerar SSO/Federated ID finns i följande hjälpdokumentation. Vi rekommenderar att du läser dem noggrant och samarbetar med din IT-avdelning för att implementera dem:

* [Enkel inloggning och Experience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [Admin Console - Dokumentation för identitetsinställningar](https://helpx.adobe.com/enterprise/using/set-up-identity.html)
* [Admin Console - Självstudiekurs om identitetsinställningar (video)](https://helpx.adobe.com/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&amp;ref=helpx.adobe.com)
* [Konfigurera självstudiekurs om Federated ID (video)](https://helpx.adobe.com/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&amp;ref=helpx.adobe.com)
* [Enkel inloggning - vanliga frågor](https://helpx.adobe.com/enterprise/using/sso-faq.html)
* [Identitetstyper som stöds av Adobe](https://helpx.adobe.com/enterprise/using/identity.html)

Om du vill fortsätta att röja ditt stöd för IP-inloggningsbegränsningar och begära att få det från Experience Cloud kan du rösta för den här funktionen på vår [forumsida](https://forums.adobe.com/ideas/11648).
