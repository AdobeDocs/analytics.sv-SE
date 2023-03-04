---
description: På sidan Fakturering kan du få tillgång till faktureringsinformation, inklusive trafikinformation för varje rapportsvit. Endast en auktoriserad administratör har åtkomst till den här sidan.
title: Fakturering
feature: Admin Tools
exl-id: cea802e4-99c4-491e-99c2-8476870001f7
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 1%

---

# Fakturering

På sidan Fakturering kan du få tillgång till faktureringsinformation, inklusive trafikinformation för varje rapportsvit. Endast en auktoriserad administratör har åtkomst till den här sidan.

>[!NOTE]
>
>Om åtkomst till faktureringsfliken är inaktiverad för ditt företag kontaktar du ditt Adobe-kontoteam.

Med trafiköversiktsdata från faktureringssidan kan du korrelera sidvisningsdata i rapporter med fakturerbara serversamtal på fakturan. The [!UICONTROL Billing] kan du göra följande på sidan:

* Granska din faktura.
* Dela upp kostnader per rapportserie för interna redovisningsfördelningar.
* Visa distributionen av primära och sekundära serversamtal.

The [!UICONTROL Billing] sidan organiserar information per månad.

Om du vill visa månatliga trafiköversiktsdata letar du reda på månaden där du vill visa trafikdata och klickar sedan på **[!UICONTROL View]**.

Resultatet [!UICONTROL Monthly Invoice] rapporten innehåller följande information:

| Kolumn | Beskrivning |
|--- |--- |
| Report Suite | Rapportsviten som ingår i datainsamlingsaktiviteten. |
| Plats | Datacentret som lagrar rapportsvitens data: San Jose (Kalifornien), Dallas (Texas), Pacific Northwest (US), London (UK) eller Singapore. I de flesta fall finns alla företagsrapportsviter i samma datacenter. |
| Primära serveranrop | Begäranden som tas emot direkt från besökarwebbläsare eller API:t för datainfogning. Innehåller primära träffar (sidvyer), primära anpassade händelser, primära nedladdningshändelser och primära avslutningshändelser. |
| Sekundära serveranrop | Kopior av primära serveranrop som har skapats av flera Suite-taggar eller kopierats/flyttats av en VISTA-regel.  Om ett sekundärt serveranrop har flyttats (inte kopierats) till en annan rapportserie via en VISTA-regel, identifierar faktureringssidan överföringen med ett negativt tal. I detta fall dras de ackumulerade sekundära anropen från de primära serversamtalen. |
| Totalt antal serveranrop | Det sammanlagda antalet primära och sekundära servrar kräver den här rapportsviten på den angivna platsen. |
| Sidvisningar | Totalt antal sidvisningar för varje rapportsserie. Du kan bekräfta sidvisningsvärden i Webbplatsmått > Sidvyer. |
| Nedladdningar | Ladda ned summor för varje rapportserie. Du kan bekräfta hämtningsvärdena i Webbplatsinnehåll > Länkar > Filhämtningar. |
| Anpassade länkar | Anpassade länksummor för varje rapportserie. Du kan bekräfta de anpassade länkvärdena i Webbplatsinnehåll > Länkar > Anpassade länkar. |
| Länkar för sista besökssida | Avsluta länksummor för varje rapportserie. Du kan bekräfta värdena för länken för att avsluta i Webbplatsinnehåll > Länkar > Avsluta länkar. |

>[!NOTE]
>
>För att få en arbetskopia av [!UICONTROL Monthly Invoice] , kopiera den till Urklipp och sedan klistra in den i ett kalkylprogram som Microsoft Excel&#42;.

## Rapportdatum kontra bearbetningsdatum {#section_51A48C2F223F4904BE1407C13333C457}

I det rapporterande användargränssnittet är de data som presenteras alltid kopplade till **Rapportdatum**, vilket är den tidsstämpel som är kopplad till händelsen.

Användning/fakturering å andra sidan använder alltid **Bearbetningsdatum** eller när data faktiskt bearbetades i systemet. På grund av grundläggande latens, dataimport eller skillnader i händelsetidszon (allt behandlas i Pacific Time) matchar rapportdatum och bearbetningsdatum vanligtvis inte fullständigt.
