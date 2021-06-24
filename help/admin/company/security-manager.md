---
description: Låter dig styra åtkomsten till rapportdata. Du kan välja starka lösenord, lösenord, IP-inloggningsbegränsningar och e-postdomänbegränsningar.
title: Säkerhetshanteraren
feature: Administratörsverktyg
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
exl-id: 6dcf0354-4b4a-4bd5-ba6c-ae42c7b9e4df
source-git-commit: c420a9468dc39922bd02047160bb07623503eee4
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 1%

---

# Säkerhetshanteraren

Med Säkerhetshanteraren kan du styra åtkomsten till rapportdata. Du kan välja starka lösenord, lösenord, IP-inloggningsbegränsningar och e-postdomänbegränsningar.

## Inställningar

**[!UICONTROL Analytics]** >  **[!UICONTROL Admin]** >  **[!UICONTROL All admin]** >  **[!UICONTROL Company settings]** >  **[!UICONTROL Security]**

| Inställning | Beskrivning |
| --- | --- |
| Kräv starka lösenord | Tvingar användarna att skapa säkrare lösenord som följer följande regler: <ul><li>Måste innehålla minst åtta tecken.</li><li>Måste ha minst ett symbol-/nummertecken mellan det första och det sista tecknet.</li><li>Måste ha minst ett alfatecken.</li><li>Kan inte hittas i en ordlista eller innehålla ord från en ordlista (engelska).</li><li>Får inte innehålla tre (3) på varandra följande tecken från inloggningsanvändarnamnet.</li><li>Måste skilja sig från de tidigare 10 lösenorden.</li></ul>**Obs**: Den här funktionen används för nya lösenord som fortsätter. Det kontrollerar inte befintliga lösenord eller tvingar användare att ändra befintliga lösenord. Därför bör du överväga att aktivera förfallodatum för lösenord för att tvinga användare att ändra sina lösenord och följa reglerna för starka lösenord. |
| Lösenordets förfallodatum | Tvingar användare att regelbundet ändra sitt lösenord för användarkontot. Du kan ange med vilket intervall du vill att lösenord ska förfalla och tvinga lösenord att förfalla omedelbart. |
| Tvinga begränsningar för IP-inloggning | (Den här funktionen kan inte användas tillsammans med inloggning i Experience Cloud. Observera att den här funktionen inte längre är tillgänglig från och med oktober 2020. [Mer...](/help/admin/company/login-restrictions-eol.md)) <br> Begränsar rapportåtkomst till specifika IP-adresser eller IP-adressintervall. Du kan lägga till upp till 100 poster i listan IP-adressfilter, och varje post kan vara en specifik adress eller ett adressintervall. Tvinga begränsningar för IP-inloggning tillämpas inte förrän det finns minst en post i listan IP-adressfilter. Godkänd IP-adress: Om du vill ange ett IP-adressintervall avgränsar du intervallet med hakparenteser (till exempel `192.168.10.[20-240]`). Du kan också använda jokertecken för att ange valfritt antal mellan 0 och 255 (till exempel `192.168.[10-14].*8`) Misslyckade inloggningar loggas och kan visas från [användnings- och åtkomstloggen](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html#section_6FBAF92D9EA244809C45A78A2F0A7232). |
| Tvinga begränsningar för e-postdomän | Filtrerar e-postadresser och domäner där Analytics skickar bokmärken, hämtningsbara rapporter och varningar. E-postfilterlistan stöder upp till 100 poster, och varje post kan vara en e-postadress eller en hel e-postdomän. Om en schemalagd rapport har ett ogodkänt e-postmål skickar Analytics ett e-postmeddelande om problemet och en länk för att avschemalägga rapporten. **[!UICONTROL Enforce Email Domain Restrictions]** används inte förrän det finns minst en post i listan över godkända e-postdomänfilter. **[!UICONTROL Accepted Email Address and Domains]**: Om du vill ange ett IP-adressintervall avgränsar du intervallet med hakparenteser (till exempel  `192.168.10.[20-240]`). Du kan också använda jokertecken för att ange ett tal mellan 0 och 255 (till exempel `192.168.[10-14].*`) |
| Meddelande om lösenordsåterställning | Meddelar de angivna administratörerna när en användare försöker återställa ett lösenord för ett användarkonto. **[!UICONTROL Available Admins]**: Visar alla administratörer. Du kan Ctrl-klicka och Skift-klicka för att välja flera administratörer. **[!UICONTROL Email Members]**: Visar den definierade e-postgruppen. |
