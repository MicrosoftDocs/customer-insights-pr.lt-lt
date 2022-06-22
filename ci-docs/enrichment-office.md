---
title: Praturtinkite klientų profilius duomenimis iš Microsoft Office 365
description: Naudokite nuosavybinius duomenis, Microsoft Office kad praturtintumėte savo klientų profilius įtraukimo duomenimis.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954143"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Klientų profilių praturtinimas įtraukimo duomenimis (peržiūra)

Naudokite duomenis, iš Microsoft Office 365 kurių praturtintumėte savo klientų paskyros profilius įžvalgomis apie įtraukimus programose Office 365. Įtraukimo duomenis sudaro el. pašto ir susitikimų veikla, kuri kaupiama paskyros lygiu. Pavyzdžiui, el. laiškų iš įmonės paskyros skaičius arba susitikimų su paskyra skaičius. Duomenų apie atskirus vartotojus nėra.

## <a name="supported-countries-or-regions"></a>Palaikomos šalys arba regionai

Šiuo metu remiame šiuos regionus: Jk, Europą, Šiaurės Ameriką.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi debesies Office 365 licencija.
- [Vieningi klientų profiliai](customer-profiles.md), pagrįsti [verslo sąskaitomis](work-with-business-accounts.md).
- Organizacija [Microsoft Dataverse, pridėta](create-environment.md#step-3-connect-to-microsoft-dataverse) jūsų "Customer Insights" aplinkoje.
- [Administratoriaus](permissions.md#admin) teisės.
- Nuomotojo Office 365 administratoriaus sutikimas naudoti Office 365 duomenis organizacijos įžvalgoms **teikti**"Dynamics 365" taikomosiose programose.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Plytelėje **Paskyros įtraukimas** pasirinkite **Praturtinti mano duomenis**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Paskyros įtraukimo plytelė.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Įveskite savo organizacijos, kurios "Office" duomenys bus kaupiami, el. pašto adresus. Atitinkamiems ryšiams apdorojami tik duomenys iš išvardytų el. pašto adresų. Geriausia praktika yra naudoti el. pašto grupes, pvz., *JAV pardavimų komandą*, kurią galite valdyti naudodami Office 365. El. pašto adresų skaičius grupėse yra išspręstas ir parodytas. Bendras el. pašto adresų skaičius turi būti ne mažesnis kaip 2 ir negali viršyti 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Paskyros įtraukimo el. pašto adresai.":::

1. Peržiūrėkite ir pateikite savo sutikimą dėl [Office 365 nuomininko administratoriaus sutikimo](#office-365-tenant-administrator-consent) pasirinkdami **Sutinku**.

1. Pasirinkite **Toliau**.

1. Pasirinkite kontaktų **duomenų rinkinį** ir pasirinkite profilį, kurį norite praturtinti. Pasirinkite **Toliau**.

1. Susiekite kontakto el. pašto adreso lauką ir pasirinkite **Pirmyn**.

1. **Pateikite sodrinimo ir išvesties objekto** **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Uždaryti**, kad grįžtumėte į **puslapį Praturtinimai**.

### <a name="office-365-tenant-administrator-consent"></a>Office 365 nuomotojo administratoriaus sutikimas

Norint suaktyvinti praturtėjimą, Office 365 reikalingas nuomininko administratoriaus sutikimas. Išsaugojus praturtinimą nuomotojo Office 365 administratoriams siunčiamas el. laiškas, kuriame prašoma peržiūrėti ir sutikti leisti "Dynamics 365" Office 365 programoms naudoti jūsų įmonės duomenis **teikiant organizacijos įžvalgas**. Nuomotojo administratorius Office 365 taip pat gali duoti sutikimą tiesiogiai savo Office 365 administravimo konsolėje, pasirinkdamas **Organizacijos** įžvalgos.

## <a name="running-the-enrichment-for-the-first-time"></a>Pirmą kartą paleidus sodrinimą

Kai praturtinimas pradedamas pirmą kartą, nuomininko Office 365 administratoriui davus sutikimą, prasideda duomenų atsisiuntimas Office 365. Šis procesas užima šiek tiek laiko. Planuojama, kad pirmasis sodrinimo etapas įvyks vėluojant šešias valandas. Pasibaigus praturtinimui, paskyros įtraukimo apžvalgos puslapyje galite matyti, kiek dienų duomenys apima. Turėdami didelį duomenų kiekį, po kelių dienų vėl paleiskite sodrinimą. Tai užtikrina, kad duomenys būtų išsamūs per visą laiko langą, kuris yra vieneri metai.

Atsižvelgiant į "Office" duomenų dydį, gali praeiti kelios valandos, kol bus užbaigtas sodrinimo vykdymas.

Kai paleidžiate sodrinimą, "Microsoft" apdoros atitikties ribose esančius Office 365 duomenis, kad sukurtų apibendrintas įžvalgas, kurios vėliau įtraukiamos į jūsų "Customer Insights" aplinką. Jokie duomenys individualiu lygiu (pvz., bet kokio el. pašto ar kalendoriaus kvietimo turinys) tampa pasiekiami "Customer Insights" vartotojams.

Norėdami pradėti sodrinimo procesą, pasirinkite **Vykdyti**.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Papildymo rezultatai

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Tai yra " *Office"* objektas. Office_UserEntity *yra* "Active Directory" ID el. pašto adresams, kurie buvo pasirinkti konfigūruojant sodrinimą.

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Rezultatų peržiūra atlikus papildymo procesą.":::

Visi duomenys sujungiami iki sąskaitos lygio. Sistema apskaičiuoja kiekvienos paskyros įtraukimo balą, kuris svyruoja nuo 0 iki 100. Įtraukimo balas suteikia sudėtinį paskyros įtraukimo į el. laiškus ir susitikimus, palyginti su kitomis paskyromis, matą. Toliau pateiktame sąraše pateikiami suvestiniai duomenys, kuriuos pateikia paskyros įtraukimo praturtinimas:

| Duomenys                                                                              | Stulpelio pavadinimas                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Įtraukimo rezultatas                                                                  |  EngagementScore                         |
| Paskyroje esančių el. laiškų skaičius                                                       |  NoOfEmails_ToAccount                    |
| El. laiškų iš paskyros skaičius                                                     |  NoOfEmails_FromAccount                  |
| Inicijuotų susitikimų skaičius pagal abonementą                                           |  NoOfMeetings_FromAccount                |
| Jūsų organizacijos inicijuotų susitikimų skaičius                                 |  NoOfMeetings_ToAccount                  |
| Jūsų organizacijos žmonių skaičius susitikimuose su paskyra                  |  NoOfContactsInvolved_Meetings           |
| Jūsų organizacijos žmonių skaičius el. pašto pokalbiuose su paskyra       |  NoOfContactsInvolved_Emails             |
| Žmonių iš paskyros skaičius susitikimuose su jūsų organizacija                  |  NoOfAccountContactsInvolved_Meetings    |
| Žmonių iš paskyros skaičius el. pašto pokalbiuose su jūsų organizacija       |  NoOfAccountContactsInvolved_Emails      |
| Įtraukimo pradžios data (pirmasis el. laiškas arba susitikimas duomenyse)                        |  EngagementStartDate                     |
| Dienos nuo paskutinio el. laiško                                                             |  DaysSinceLastEmail                      |
| Dienos po paskutinio susitikimo                                                           |  DaysSinceLastMeeting                    |
| Vidutinė susitikimų trukmė                                                      |  AverageDuration_Of_Meetings             |
| Vidutinė atsakymų el. paštu iš paskyros trukmė                                    |  AverageDuration_Of_AccountEmailReplies  |
| Agregavimo pradžios data                                                            |  AgregavimasStartDate                    |
| Agregavimo lygis (metai, mėnuo arba savaitė)                                          |  AgregavimasLevel                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>Žr. papildymo duomenis kliento kortelėje

Paskyros įtraukimą taip pat galima peržiūrėti atskirose klientų kortelėse. Eikite į **Klientai** ir pasirinkite kliento profilį. Kliento kortelėje rasite paskyros įtraukimo balą, bendrą el. laiškų skaičių ir bendrą susitikimų skaičių per pastaruosius metus. Taip pat rasite diagramas, kuriose rodoma el. pašto ir susitikimų istorija.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kliento kortelė su papildytais duomenimis.":::

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Pavyzdžiui, segmentas, kuriame yra visi klientai, kurių vertė viršija 60 *dienų nuo paskutinio el. laiško* ir *dienų nuo paskutinio susitikimo*. Šiame segmente yra pasenusių paskyrų, kurias galite bandyti iš naujo suaktyvinti.

[!INCLUDE [footer-include](includes/footer-banner.md)]
