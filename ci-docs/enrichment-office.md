---
title: Praturtinkite klientų profilius duomenimis iš Microsoft Office 365 (peržiūra)
description: Naudokite nuosavybės teise priklausančius duomenis Microsoft Office, kad praturtintumėte savo klientų profilius įtraukimo duomenimis.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 75762afb70814c8a81c1574ee7ea1553a2048737
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055684"
---
# <a name="enrich-customer-profiles-with-data-from-microsoft-office-365-preview"></a>Praturtinkite klientų profilius duomenimis iš Microsoft Office 365 (peržiūra)

Naudokite duomenis iš Microsoft Office 365, kad praturtintumėte savo klientų paskyrų profilius įžvalgomis apie įtraukimus per Office 365 programas. Įtraukimo duomenis sudaro el. pašto ir susitikimų veikla, kuri agreguojama paskyros lygiu. Pavyzdžiui, el. laiškų iš verslo paskyros skaičius arba susitikimų su paskyra skaičius. Jokie duomenys apie atskirus naudotojus nepateikiami.

## <a name="supported-countries-or-regions"></a>Palaikomos šalys arba regionai

Šiuo metu remiame šiuos regionus: JK, Europą, Šiaurės Ameriką.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi Office 365 debesies licencija.
- [Vieningi klientų profiliai](customer-profiles.md), pagrįsti [verslo sąskaitomis](work-with-business-accounts.md).
- Organizacija [Microsoft Dataverse, įtraukta į](create-environment.md#step-3-connect-to-microsoft-dataverse) jūsų "Customer Insights" aplinką.
- [Administratoriaus](permissions.md#admin) teisės.
- Nuomotojo Office 365 administratoriaus sutikimas naudoti Office 365 duomenis organizacijos **įžvalgoms teikti**"Dynamics 365" programose.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Pasirinkite **Papildyti mano duomenis** plytelėje **Paskyros įtraukimas**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Paskyros įtraukimo plytelė.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Įveskite organizacijos el. pašto adresus, kurių "Office" duomenys bus kaupiami. Tik duomenys iš išvardytų el. pašto adresų apdorojami atitinkamai komunikacijai. Geriausia praktika yra naudoti el. pašto grupes, pvz., *JAV pardavimo komandą* Office 365, kurią galite valdyti. El. pašto adresų skaičius grupėse išsprendžiamas ir rodomas. Bendras el. pašto adresų skaičius turi būti bent 2 ir negali viršyti 2 500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Paskyros įtraukimo el. pašto adresai.":::

1. Peržiūrėkite ir pateikite savo sutikimą dėl nuomotojo [Office 365 administratoriaus sutikimo](#office-365-tenant-administrator-consent) pasirinkdami **Sutinku**.

1. Pasirinkite **Toliau**.

1. Pasirinkite kontaktų **duomenų rinkinį** ir pasirinkite profilį, kurį norite papildyti. Pasirinkite **Toliau**.

1. Susiekite kontakto el. pašto adreso lauką ir pasirinkite **Pirmyn**.

1. **Pateikite papildymo ir objekto** **Išvestis pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Uždaryti**, kad grįžtumėte į **puslapį Papildymai**.

### <a name="office-365-tenant-administrator-consent"></a>Office 365 nuomotojo administratoriaus sutikimas

Norint suaktyvinti papildymą, reikalingas nuomotojo Office 365 administratoriaus sutikimas. Įrašant papildymą Office 365 nuomotojo administratoriams siunčiamas el. laiškas, kuriame prašoma jų peržiūrėti ir sutikti leisti "Dynamics 365" Office 365 programoms naudoti jūsų įmonių duomenis įžvalgoms **organizacijai teikti**. Nuomotojo Office 365 administratorius taip pat gali duoti sutikimą tiesiogiai savo Office 365 administratoriaus konsolėje, pasirinkdamas **Organizacijos** įžvalgos.

## <a name="running-the-enrichment-for-the-first-time"></a>Sodrinimas pirmą kartą

Kai papildymas pradedamas pirmą kartą, nuomotojo Office 365 administratoriui davus sutikimą, prasideda duomenų atsisiuntimas.Office 365 Šis procesas užtrunka šiek tiek laiko. Planuojama, kad pirmasis sodrinimo bėgimas įvyks su šešių valandų vėlavimu. Galite matyti dienų, kurias apima duomenys, skaičių paskyros įtraukimo apžvalgos puslapyje, kai papildymas bus baigtas. Turėdami didelį duomenų kiekį, po kelių dienų vėl paleiskite papildymą. Tai užtikrina, kad duomenys būtų išsamūs per visą laiko langą, kuris yra vieneri metai.

Atsižvelgiant į jūsų "Office" duomenų dydį, gali praeiti kelios valandos, kol baigsis papildymo vykdymas.

Kai paleidžiate papildymą, "Microsoft" apdoros duomenis neperžengdama Office 365 atitikties ribos, kad sukurtų apibendrintas įžvalgas, kurios vėliau įtraukiamos į jūsų "Customer Insights" aplinką. Jokie duomenys individualiu lygiu (pvz., bet kokio el. laiško ar kalendoriaus kvietimo turinys) netampa prieinami "Customer Insights" vartotojams.

Pasirinkite **Vykdyti**, kad pradėtumėte papildymo procesą.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Papildymo rezultatų peržiūra

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Tai yra *"Office"* objektas. Office_UserEntity *yra* "Active Directory" ID, skirti el. pašto adresams, kurie buvo pasirinkti atliekant papildymo konfigūraciją.

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Rezultatų peržiūra atlikus papildymo procesą.":::

Visi duomenys kaupiami iki paskyros lygio. Sistema apskaičiuoja užduoties balą, kuris svyruoja nuo 0 iki 100, kiekvienai sąskaitai. Įtraukimo balas pateikia sudėtinį paskyros įtraukimo į el. laiškus ir susitikimus matą, palyginti su kitomis paskyromis. Šiame sąraše pateikiami apibendrinti duomenys, kuriuos teikia paskyros įtraukimo papildymas:

| Duomenys                                                                              | Stulpelio pavadinimas                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Įtraukimo rezultatas                                                                  |  "EngagementScore"                         |
| Į paskyrą siunčiamų el. laiškų skaičius                                                       |  NoOfEmails_ToAccount                    |
| El. laiškų iš paskyros skaičius                                                     |  NoOfEmails_FromAccount                  |
| Pagal sąskaitą inicijuotų susitikimų skaičius                                           |  NoOfMeetings_FromAccount                |
| Jūsų organizacijos inicijuotų susitikimų skaičius                                 |  NoOfMeetings_ToAccount                  |
| Žmonių iš jūsų organizacijos skaičius susitikimuose su paskyra                  |  NoOfContactsInvolved_Meetings           |
| Žmonių iš jūsų organizacijos skaičius el. pašto pokalbiuose su paskyra       |  NoOfContactsInvolved_Emails             |
| Žmonių iš paskyros susitikimuose su jūsų organizacija skaičius                  |  NoOfAccountContactsInvolved_Meetings    |
| Žmonių iš paskyros skaičius el. pašto pokalbiuose su jūsų organizacija       |  NoOfAccountContactsInvolved_Emails      |
| Įtraukimo pradžios data (pirmasis el. laiškas arba susitikimas duomenyse)                        |  ĮsitraukimasStartDate                     |
| Dienos nuo paskutinio el. laiško                                                             |  DaysSinceLastemail                      |
| Dienos nuo paskutinio susitikimo                                                           |  DaysSinceLastMeeting                    |
| Vidutinė posėdžių trukmė                                                      |  AverageDuration_Of_Meetings             |
| Vidutinė el. pašto atsakymų iš paskyros trukmė                                    |  AverageDuration_Of_AccountEmailReplies  |
| Agregavimo pradžios data                                                            |  AggregationStartDate                    |
| Sumavimo lygis (metai, mėnuo arba savaitė)                                          |  Agregavimolygislygis                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>Žr. papildymo duomenis kliento kortelėje

Įtraukimą į paskyrą taip pat galima peržiūrėti atskirose klientų kortelėse. Eikite į **Klientai** ir pasirinkite kliento profilį. Kliento kortelėje rasite paskyros įtraukimo balą, bendrą el. laiškų skaičių ir bendrą per pastaruosius metus sukauptų susitikimų skaičių. Taip pat rasite diagramų, kuriose rodomi el. laiškai ir susitikimų istorija.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kliento kortelė su papildytais duomenimis.":::

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Pavyzdžiui, segmentas, kuriame yra visi klientai, kurių vertė viršija 60 *dienų nuo paskutinio el. pašto* ir *dienų nuo paskutinio susitikimo*. Tame segmente yra pasenusių paskyrų, kurias galite pabandyti suaktyvinti iš naujo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
