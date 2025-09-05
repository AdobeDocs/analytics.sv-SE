---
description: Gör att du kan styra åtkomsten till rapportdata. Du kan välja starka lösenord, lösenord, IP-inloggningsbegränsningar och e-postdomänbegränsningar.
title: Säkerhetshanteraren
feature: Company Settings
exl-id: 6dcf0354-4b4a-4bd5-ba6c-ae42c7b9e4df
role: Admin
source-git-commit: e09234ca27fbf923e026aa1f2ed0ebfed636bf7c
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Säkerhetshanteraren

Med Säkerhetshanteraren kan du styra åtkomsten till rapportdata. Du kan välja starka lösenord, lösenord, IP-inloggningsbegränsningar och e-postdomänbegränsningar.

## Inställningar

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Company settings]** > **[!UICONTROL Security]**

| Inställning | Beskrivning |
| --- | --- |
| Kräv starka lösenord | Tvingar användarna att skapa säkrare lösenord som följer följande regler: <ul><li>Måste innehålla minst åtta tecken.</li><li>Måste ha minst ett symbol-/nummertecken mellan det första och det sista tecknet.</li><li>Måste ha minst ett alfatecken.</li><li>Kan inte hittas i en ordlista eller innehålla ord från en ordlista (engelska).</li><li>Får inte innehålla tre (3) på varandra följande tecken från inloggningsanvändarnamnet.</li><li>Måste skilja sig från de tidigare 10 lösenorden.</li></ul>**Obs!**: Den här funktionen används för nya lösenord som fortsätter. Det kontrollerar inte befintliga lösenord eller tvingar användare att ändra befintliga lösenord. Därför bör du överväga att aktivera förfallodatum för lösenord för att tvinga användare att ändra sina lösenord och följa de starka lösenordsreglerna. |
| Lösenordets förfallodatum | Tvingar användare att regelbundet ändra sitt lösenord för användarkontot. Du kan ange med vilket intervall du vill att lösenord ska förfalla och tvinga lösenord att förfalla omedelbart. |
| Tvinga begränsningar för e-postdomän | Filtrerar e-postadresser och domäner där Analytics skickar bokmärken, hämtningsbara rapporter och varningar. E-postfilterlistan stöder upp till 100 poster, och varje post kan vara en e-postadress eller en hel e-postdomän. Om en schemalagd rapport har ett ogodkänt e-postmål skickar Analytics ett e-postmeddelande om problemet och en länk för att avschemalägga rapporten. **[!UICONTROL Enforce Email Domain Restrictions]** används inte förrän det finns minst en post i listan över godkända e-postdomänfilter. **[!UICONTROL Accepted Email Address and Domains]**: Om du vill ange ett IP-adressintervall måste du omsluta intervallet inom hakparenteser (till exempel `192.168.10.[20-240]`). Du kan också använda jokertecken för att ange ett tal mellan 0 och 255 (till exempel `192.168.[10-14].*`) |
| Meddelande om lösenordsåterställning | Meddelar de angivna administratörerna när en användare försöker återställa ett lösenord för ett användarkonto. **[!UICONTROL Available Admins]**: Visar alla administratörer. Du kan Ctrl-klicka och Skift-klicka för att välja flera administratörer. **[!UICONTROL Email Members]**: Visar den definierade e-postgruppen. |
