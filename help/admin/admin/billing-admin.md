---
description: På sidan Fakturering kan du få tillgång till faktureringsinformation, inklusive trafikinformation för varje rapportsvit. Endast en auktoriserad administratör har åtkomst till den här sidan.
title: Fakturering
feature: Admin Tools
uuid: ad6ee1c4-d317-4320-a36e-ee966c8f145e
exl-id: cea802e4-99c4-491e-99c2-8476870001f7
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 1%

---

# Fakturering

På sidan Fakturering kan du få tillgång till faktureringsinformation, inklusive trafikinformation för varje rapportsvit. Endast en auktoriserad administratör har åtkomst till den här sidan.

>[!NOTE]
>
>Kontakta din kontoansvarige om åtkomst till faktureringsfliken är inaktiverad för ditt företag.

Med trafiköversiktsdata från faktureringssidan kan du korrelera sidvisningsdata i rapporter med fakturerbara serversamtal på fakturan. På sidan [!UICONTROL Billing] kan du göra följande:

* Granska din faktura.
* Dela upp kostnader per rapportserie för interna redovisningsfördelningar.
* Visa distributionen av primära och sekundära serversamtal.

Sidan [!UICONTROL Billing] organiserar information per månad.

Om du vill visa månatliga trafiköversiktsdata letar du reda på månaden där du vill visa trafikdata och klickar sedan på **[!UICONTROL View]**.

Den resulterande [!UICONTROL Monthly Invoice]-rapporten innehåller följande information:

| Kolumn | Beskrivning |
|--- |--- |
| Report Suite | Rapportsviten som ingår i datainsamlingsaktiviteten. |
| Plats | Datacentret som lagrar rapportsvitens data: San Jose (Kalifornien), Dallas (Texas), Pacific Northwest (US), London (UK) eller Singapore. I de flesta fall finns alla företagsrapportsviter i samma datacenter. |
| Primära serveranrop | Begäranden som tas emot direkt från besökarwebbläsare eller API:t för datainfogning. Innehåller primära träffar (sidvyer), primära anpassade händelser, primära nedladdningshändelser och primära avslutningshändelser. |
| Sekundära serveranrop | Kopior av primära serveranrop som har skapats av flera Suite-taggar eller kopierats/flyttats av en VISTA-regel.  Om ett sekundärt serveranrop har flyttats (inte kopierats) till en annan rapportserie via en VISTA-regel, identifierar faktureringssidan överföringen med ett negativt tal. I detta fall dras de ackumulerade sekundära anropen från de primära serversamtalen. |
| Totalt antal serveranrop | Det sammanlagda antalet primära och sekundära servrar kräver den här rapportsviten på den angivna platsen. |
| Sidvisningar | Totalt antal sidvisningar för varje rapportsserie. Du kan bekräfta värdena i sidvyn i   Site Metrics > Page Views. |
| Nedladdningar | Ladda ned summor för varje rapportserie. Du kan bekräfta hämtningsvärdena i Webbplatsinnehåll > Länkar > Filhämtningar. |
| Anpassade länkar | Anpassade länksummor för varje rapportserie. Du kan bekräfta de anpassade länkvärdena i Webbplatsinnehåll > Länkar > Anpassade länkar. |
| Länkar för sista besökssida | Avsluta länksummor för varje rapportserie. Du kan bekräfta värdena för länken för att avsluta i Webbplatsinnehåll > Länkar > Avsluta länkar. |

>[!NOTE]
>
>Om du vill få en arbetskopia av [!UICONTROL Monthly Invoice]-rapporten kopierar du den till Urklipp och klistrar in den i ett kalkylbladsprogram som Microsoft Excel*.

## Rapportdatum kontra bearbetningsdatum {#section_51A48C2F223F4904BE1407C13333C457}

I det rapporterande användargränssnittet är de data som presenteras alltid kopplade till **rapporteringsdatumet**, som är den tidsstämpel som är kopplad till händelsen.

Å andra sidan används alltid **Bearbetningsdatumet** eller när data bearbetades i systemet. På grund av grundläggande latens, dataimport eller skillnader i händelsetidszon (allt behandlas i Pacific Time) matchar rapportdatum och bearbetningsdatum vanligtvis inte fullständigt.
