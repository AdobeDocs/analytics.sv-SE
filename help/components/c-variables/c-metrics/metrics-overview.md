---
description: Visar standardmåtten i Adobe Analytics.
title: Snabbreferens för mått
topic: Metrics
uuid: 34160c96-7cb3-4e2f-9956-9ffa9d9a359e
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Snabbreferens för mått

Visar standardmåtten i Adobe Analytics.

>[!NOTE]
>
>Alla mått (händelser) som inte anges nedan är ett [anpassat mått](/help/components/c-variables/c-metrics/metrics-custom.md) (anpassad händelse).

>[!IMPORTANT]
>
>Analysarbetsytan skiljer inte längre mellan trafik- och konverteringsmått. Därför är mätningstypen endast relevant för verktyg som Rapporter och analyser, Web Services 1.4 och Report Builder.)

| Måttnamn | Beskrivning | Typ |
|--- |--- |---|
| Genomsnittligt siddjup | Visar i genomsnitt hur långt inom ett besök varje värde har utlösts. Detta mått är värdefullt för att avgöra hur långt inom ett besök målgruppen kommer till en viss sida eller ett visst prop-värde. Genomsnittligt siddjup är tillgängligt för alla variabler där målning är aktiverat. | Trafik |
| Genomsnittlig tid spenderad på sidan | Representerar den genomsnittliga tiden som har tillbringats på en sida under ett besök. | Trafik |
| Genomsnittlig tid på platsen | Representerar den genomsnittliga tid som tillbringats på en webbplats under ett besök. | Trafik |
| Studsfrekvens | Visar procentandelen besök som innehåller en enda träff. Studsfrekvensen använder Bounces-måttet och beräknas som: Satser dividerade med poster. | Konvertering |
| studsar | Ett besök som består av ett enda serversamtal. Ett enda sidbesök är till exempel ett studs om en besökare inte interagerar med sidan på ett sätt som skickar data till Adobe, till exempel klickar på en länk eller en videostart. Om fler än en träff tas emot under ett besök räknas inte en studs. | Konvertering |
| Kampanjklickningar | Klickningar representerar det antal gånger som en spårningskod för en viss kampanj skickades till rapporteringen. När en besökare klickar på en filiallänk som har taggats med någon av dessa spårningskoder, dirigeras besökaren till din landningssida och spårningskoden registreras i s.campaign. Dessa data skickas till rapporter och en klickfrekvens registreras. | Konvertering |
| Cart Additions | Antalet gånger som en artikel har lagts till i en kundvagn. Det här värdet kommer från scAdd-händelsen. | Konvertering |
| Öppna kundvagn | Antalet gånger som en kund öppnade en kundvagn genom att lägga till den första artikeln. Inträffar första gången en artikel läggs till i kundvagnen. Det här värdet kommer från scOpen-händelsen. | Konvertering |
| Cart Removals | Antalet gånger som en artikel har tagits bort från en kundvagn. Det här värdet kommer från scRemove-händelsen. | Konvertering |
| Korgar | Antalet gånger som en ny kundvagn öppnades eller initierades. | Konvertering |
| Vyer | Antalet gånger som innehållet i kundvagnen visas av kunden. | Konvertering |
| Utcheckningar | En händelse som inträffar när kunderna kommer till kassan för ett köp. Utcheckningsfasen sker vanligtvis precis innan ett inköp är slutfört och innebär vanligtvis att kunden måste ange personlig information (som frakt- och faktureringsinformation). Du har kontroll över de händelser på din webbplats som räknas som utcheckningar. Det här värdet kommer från scCheckout-händelsen. | Konvertering |
| Klickningar | Klickningar representerar det antal gånger som en spårningskod för en viss kampanj skickades till rapporteringen. När en besökare klickar på en filiallänk som har taggats med någon av dessa spårningskoder, dirigeras besökaren till din landningssida och spårningskoden registreras i s.campaign. Dessa data skickas till rapporter och en klickfrekvens registreras. | Konvertering |
| Kund (New, Return, Loyal) | Kategorier i kundlojalitetsrapporten: Ny kund: Kund med 0 inköp.  Returkund: Kund med 1 köp.  Loyal Customer: Kund med mer än ett inköp. | Trafik |
| Dagliga återbesök | Visar antalet besökare på webbplatsen mer än en gång på en viss dag. En dag definieras som den sista 24-timmarsperioden. | Trafik |
| Poster | Posterna anger hur många gånger ett givet värde hämtas som det första värdet vid ett besök. Tävlingsbidragen får endast förekomma en gång per besök. Men det är inte nödvändigtvis den första träffen om variabeln inte är definierad. | Trafik |
| Avslutar | Antalet gånger ett givet värde hämtas som det sista värdet vid ett besök. Utträden kan bara göras en gång per besök. | Trafik |
| Instanser | Antalet gånger som ett värde har angetts för en variabel. Förekomster räknas för alla träfftyper, men räknas inte när ett värde registreras för en variabel vid en efterföljande träff på grund av persistence. | Konvertering |
| Mobilvyer | Antalet gånger som en sida visas eller en dimension anges när den används via en mobil enhet. Endast ad hoc-analys. Istället för att använda måtten för mobilvyerna rekommenderar vi att du använder segmentet&quot;Besök från mobila enheter&quot;. | Konvertering |
| Nya åtaganden | Nya åtaganden är ett marknadsföringskanalrapporteringsmått som räknar nya besökare som kommer som ett resultat av en kanal. Det här måttet räknar även besökare som inte har varit på webbplatsen de senaste 30 dagarna. Ett nytt engagemang är en eVar-uppsättning i början av varje besök (ursprunglig allokering). Första beröringskanalen kan också vara nya engagemang, beroende på vad besökarna förfaller. | Konvertering |
| Förekomster | Antalet gånger som ett specifikt värde hämtas, plus antalet sidvyer som det angivna värdet bevaras för. Med andra ord är förekomster summan av sidvyer och sidhändelser. Förekomster är bara tillgängliga i ad hoc-analyser. | Inte tillgängligt i Rapporter och analyser, Webbtjänster 1.4 eller Report Builder |
| Beställningar | Antalet beställningar som gjorts på webbplatsen under den valda tidsperioden. Du kan dela upp enskilda tidsperioder med andra mått för att visa artiklar (till exempel produkter eller kampanjer) som bidrog till de flesta beställningarna under den tidsramen. | Konvertering |
| Siddjup | Genomsnittligt antal klick som användare behöver för att komma till en viss sida på webbplatsen. | Trafik |
| Sidhändelser | Sidhändelser består av bildbegärandedata från bildförfrågningar som inte är standard. Källor för bildbegäranden som inte är standard är hämtningslänkar, avslutslänkar och anpassad länkspårning. | Trafik |
| Sidvyer | En sidvy räknas för varje serveranrop som skickas. Det här måttet visar totalt antal instanser av sidvyn. TrackLink-anrop räknas inte som sidvyer och ökar inte måttet för sidvyer. | Konvertering |
| Banvyer | Mätvärdet för sökvägsvyer baseras på sökningsdata, som spåras för alla användare som accepterar beständiga cookies.  Termen Sökvägsvy används för att ange hur många gånger en sida har visats, med hänsyn till begränsningarna för de visade sökvägarna. Det här måttet visar antalet sidvisningar för den angivna sidan som inträffade i den valda sökvägen. Det här måttet är tillgängligt i rapporten Banor. Vyer över banor visar hur många gånger en viss sidsekvens har visats. | Trafik |
| Produktvyer | Instans av produktvyn som anges. Inträffar när produktinformationssidan visas. Det här värdet kommer från prodView-händelsen. | Konvertering |
| Läs in igen | Räknas när samma sidnamn läses in två gånger i rad. Det innebär vanligtvis att sidan har uppdaterats. Observera att besök på samma sida två gånger under samma besök inte räknas som återinläsning såvida inte båda besöken gjordes på en rad. | Trafik |
| Returbesök | Visar antalet besök där besöksnumret är större än 1. Returbesök innehåller besökare som inte är cookies. | Konvertering |
| Intäkter | Intäkter anges för köphändelsen och definieras som det totala beloppet i USD för summan av ordern för varje produkt. Det här värdet kommer från köphändelsen. | Konvertering |
| Sökningar | Sökningar är inte ett standardmått - det är alltid ett anpassat mått.  Det är det rekommenderade standardmåttet för sökmotorer och nyckelord. Det här måttet representerar instanser av en klickfrekvens och visar sidan som är associerad med en viss motor eller ett nyckelord. Sökmetadata kan rapporteras retroaktivt till början av datauppsättningen. | Konvertering |
| Enkel åtkomst | Enkel åtkomst definieras av antalet besök på webbplatsen som innehöll ett unikt sidnamnsvärde. Om en användare kommer till din webbplats och klickar på en spårad länk, utlöser en händelse (till exempel en videovy) eller läser in sidan igen, betraktas besöket fortfarande som ett Single Access-besök. Så länge värdet för pageName-variabeln inte ändras kan ett antal begäranden skickas och besöket betraktas fortfarande som en enskild åtkomst. | Trafik |
| Tillagd tid | Mätvärden som visar hur mycket tid besökarna tillbringar på en sida, en webbplats eller per besök. | Trafik |
| Totalt | Totala värden rapporterar värdet för alla rapportrader för en rapporterad period. Om ett filter är valt kan summan motsvara den filtrerade summan i stället för rapportsvitens totala summa. Om inget filter har valts representerar summan för rapportsviten. | Den totala versionen av ett mätvärde följer typen av basmätvärde. Till exempel, `totalpageviews` skulle vara trafik eftersom `pageviews` är trafik. |
| Unik kund | (Varje timme, Varje dag, Varje vecka, Varje månad, Varje kvartal, Varje år) En unik kund räknas en gång för den tidsramen men kan inte räknas igen, oavsett hur många gånger besökaren återgår till att göra ett köp. En unik besökare räknas en gång för det första besöket under en angiven period och räknas inte igen förrän perioden går ut. När perioden är slut räknas den unika besökaren igen. Unika kunder räknas alltid som unika besökare eftersom de måste besöka webbplatsen för att kunna göra köpet. | Konvertering |
| Unika besökare | Visar det totala antalet unika besökare för rapporteringsperioden (kan konfigureras till dagliga, veckovisa, månadsvisa, kvartalsvisa, årliga). | Konvertering |
| Enheter | Det totala antalet enheter som beställts för den valda tidsperioden. Eftersom du har många inköpta enheter per order är Enheter ett viktigt mått som visar den allmänna lagerrörelsen. | Konvertering |
| Besökare | Antalet unika besökare på webbplatsen för en viss timme, dag, vecka, månad, kvartal eller år. | Konvertering |
| Besök | En sekvens med sidvyer i ett möte. Besöksmåtten används ofta i rapporter som visar antalet användarsessioner under den valda tidsperioden.  Besöken är alltid kopplad till en tidsperiod, så du vet om du ska räkna med ett nytt besök om samma besökare kommer tillbaka till din webbplats. | Konvertering |

