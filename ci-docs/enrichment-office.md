---
title: Praturtinkite klientų profilius duomenimis iš Microsoft Office 365
description: Naudokite nuosavybinius duomenis, Microsoft Office kad praturtintumėte savo klientų profilius įtraukimo duomenimis.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 782042ff643bd0cc70ac53e5680bfd0c68944d84
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643458"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Klientų profilių praturtinimas įtraukimo duomenimis (peržiūra)

Naudokite duomenis, iš Microsoft Office 365 kurių praturtintumėte savo klientų paskyros profilius įžvalgomis apie įtraukimus programose Office 365. Įtraukimo duomenis sudaro el. pašto ir susitikimų veikla, kuri kaupiama paskyros lygiu. Pavyzdžiui, el. laiškų iš įmonės paskyros skaičius arba susitikimų su paskyra skaičius. Duomenų apie atskirus vartotojus nėra. 

Šis sodrinimas galimas šiuose regionuose: Jungtinėje Karalystėje, Europoje, Šiaurės Amerikoje.

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint konfigūruoti sodrinimą, turi būti įvykdytos šios būtinosios sąlygos:

- Turite aktyvią Office 365 debesies licenciją.
- Turite [vieningus klientų profilius pagal](customer-profiles.md) verslo [sąskaitas](work-with-business-accounts.md).
- Jūsų "Customer Insights" aplinkoje turi būti [Microsoft Dataverse pridėta](create-environment.md#step-3-connect-to-microsoft-dataverse) organizacija.
- [Turite administratoriaus](permissions.md#admin) teises.
- Turite arba galite gauti nuomotojo administratoriaus sutikimą Office 365 naudoti Office 365 duomenis organizacijos įžvalgoms **teikti**"Dynamics 365" taikomosiose programose.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Eikite į **Duomenys** > **Papildymas**.

1. Eikite į skirtuką **Atrasti** ir plytelėje **Paskyros įtraukimas** pasirinkite **Praturtinti mano duomenis**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Paskyros įtraukimo plytelė.":::
   
1. Žingsnyje Peržiūra pasirinkite **Pirmyn** **ir įveskite** savo organizacijos, kurios "Office" duomenys bus kaupiami, el. pašto adresus. Atitinkamiems ryšiams apdorojami tik duomenys iš išvardytų el. pašto adresų. Geriausia praktika yra naudoti el. pašto grupes, pavyzdžiui, *JAV pardavimų komandą* Office 365, kurios lengvai valdomos. El. pašto adresų skaičius grupėse yra išspręstas ir parodytas. Bendras el. pašto adresų skaičius turi būti ne mažesnis kaip 2 ir negali viršyti 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Paskyros įtraukimo el. pašto adresai.":::

1. Peržiūrėkite sutikimo pareiškimą **, pažymėkite žymės langelį Sutinku** ir pasirinkite **Pirmyn**.

1. Pasirinkite kliento duomenų rinkinį ir pasirinkite **Pirmyn**.

1. Susiekite kontakto el. pašto adreso lauką ir pasirinkite **Pirmyn**.

1. Peržiūrėkite sodrinimo konfigūraciją, suteikite sodrinimui pavadinimą ir pasirinkite **Išsaugoti sodrinimą**, kad išsaugotumėte sodrinimą.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 nuomotojo administratoriaus sutikimas

Norint suaktyvinti praturtėjimą, Office 365 reikalingas nuomininko administratoriaus sutikimas. Išsaugojus praturtinimą nuomotojo Office 365 administratoriams siunčiamas el. laiškas, kuriame prašoma peržiūrėti ir sutikti leisti "Dynamics 365" Office 365 programoms naudoti jūsų įmonės duomenis **teikiant organizacijos įžvalgas**. Nuomotojo administratorius Office 365 taip pat gali duoti sutikimą tiesiogiai savo Office 365 administravimo konsolėje, pasirinkdamas **Organizacijos** įžvalgos.

## <a name="running-the-enrichment-for-the-first-time"></a>Pirmą kartą paleidus sodrinimą

Kai praturtinimas pradedamas pirmą kartą, nuomininko Office 365 administratoriui davus sutikimą, prasideda duomenų atsisiuntimas Office 365. Šis procesas užima šiek tiek laiko. Planuojama, kad pirmasis sodrinimo etapas įvyks vėluojant šešias valandas. Pasibaigus praturtinimui, paskyros įtraukimo apžvalgos puslapyje galite matyti, kiek dienų duomenys apima. Turėdami didelį duomenų kiekį, po kelių dienų vėl paleiskite sodrinimą. Tai užtikrina, kad duomenys būtų išsamūs visam laiko laikotarpiui, kuris yra vieneri metai.

Norėdami pradėti procesą, puslapyje Abonemento įtraukimo konfigūracija pasirinkite **Vykdyti**. Be to, galite leisti sistemai automatiškai paleisti sodrinimą kaip suplanuoto [atnaujinimo](system.md#schedule-tab) dalį. Pagal numatytuosius nustatymus sodrinimas vyksta kartą per savaitę.

Atsižvelgiant į "Office" duomenų dydį, gali praeiti kelios valandos, kol bus užbaigtas sodrinimo vykdymas.

Kai paleidžiate sodrinimą, "Microsoft" apdoros atitikties ribose esančius Office 365 duomenis, kad sukurtų apibendrintas įžvalgas, kurios vėliau įtraukiamos į jūsų "Customer Insights" aplinką. Jokie duomenys individualiu lygiu (pvz., bet kokio el. pašto ar kalendoriaus kvietimo turinys) tampa pasiekiami "Customer Insights" vartotojams. 

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Papildymo rezultatai

Atlikę sodrinimo procesą, eikite į **"My enrichments"**, kad peržiūrėtumėte sodrinimo rezultatus. Rasite bendrą praturtintų klientų skaičių ir sodrinimo rezultatų apžvalgą. Tai apima apdorotų el. laiškų ir susitikimų skaičių, dienų, per kurias duomenys buvo sujungti, skaičių ir dar daugiau.

Taip pat rasite diagramą su praturtintų klientų skaičiumi laikui bėgant ir sodrinimo duomenų peržiūrą.  

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


Peržiūrėkite papildytus duomenis peržiūros skiltyje pasirinkdami **Daugiau žiūrėti**. Jis atidaro " *Office"* objektą. Taip pat galite rasti objektą, nurodytą **"DataEntities** **" sodrinimo** > **grupėje**. Taip pat rasite *Office_UserEntity*, kuriame yra "Active Directory" ID el. pašto adresams, pasirinktiems sodrinimo konfigūravimo metu 

## <a name="see-enrichment-data-on-the-customer-card"></a>Žr. papildymo duomenis kliento kortelėje

Paskyros įtraukimą taip pat galima peržiūrėti atskirose klientų kortelėse. Eikite į **Klientai** ir pasirinkite kliento profilį. Kliento kortelėje rasite paskyros įtraukimo balą, bendrą el. laiškų skaičių ir bendrą susitikimų skaičių per pastaruosius metus. Taip pat rasite diagramas, kuriose rodoma el. pašto ir susitikimų istorija.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kliento kortelė su papildytais duomenimis.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Segmentų ir matų kūrimas remiantis praturtintais duomenimis

Praturtinti duomenys gali būti naudojami segmentams ir priemonėms kurti, kaip nurodyta toliau. Pavyzdžiui, segmentas, kuriame yra visi klientai, kurių vertė viršija 60 *dienų nuo paskutinio el. laiško* ir *dienų nuo paskutinio susitikimo*. Šiame segmente yra pasenusių paskyrų, kurias galite bandyti iš naujo suaktyvinti. 

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
