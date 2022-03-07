---
title: Klientų profilių papildymas duomenimis iš Microsoft Office 365
description: Naudokite nuosavybės duomenis, Microsoft Office kad praturtintumėte savo klientų profilius įtraukimo duomenimis.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 938a9de83fd8f5ff0c9ae815d626cdfa35228aba
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228484"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Klientų profilių praturtinti įtraukimo duomenimis (peržiūra)

Naudokite duomenis, kad Microsoft Office 365 papildytumėte savo klientų paskyros profilius įžvalgomis apie įtraukimus per Office 365 programas. Įtraukimo duomenis sudaro el. pašto ir susitikimo veikla, kuri kaupiama paskyros lygiu. Pavyzdžiui, el. laiškų iš verslo abonemento skaičius arba susitikimų su abonementu skaičius. Duomenų apie atskirus naudotojus nėra. 

Šis praturtėjimas yra prieinamas šiuose regionuose: Jungtinėje Karalystėje, Europoje, Šiaurės Amerikoje.

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint konfigūruoti sodrinimą, reikia įvykdyti šias būtinas sąlygas:

- Turite aktyvią Office 365 debesies licenciją.
- [Turite suvienodintus klientų profilius](customer-profiles.md) pagal [verslo sąskaitas](work-with-business-accounts.md).
- Jūsų "Customer Insights" aplinkoje turi būti [Microsoft Dataverse pridėta](create-environment.md#step-3-connect-to-microsoft-dataverse) organizacija.
- [Turite administratoriaus](permissions.md#administrator) teises.
- Turite arba galite gauti nuomotojo Office 365 administratoriaus sutikimą naudoti Office 365 duomenis organizacijos **įžvalgoms teikti**"Dynamics 365" programose.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Publikos įžvalgose, eikite į **Duomenys** > **Praturtinimas**.

1. Eikite į skirtuką **Atrasti** ir plytelėje Abonemento **įtraukimas** pasirinkite **Praturtinti mano duomenis**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Paskyros įtraukimo plytelė.":::
   
1. Atlikdami veiksmą Apžvalga **pasirinkite** **Pirmyn** ir įveskite savo organizacijos el. pašto adresus, kurių "Office" duomenys bus kaupiami. Tik duomenys iš išvardytų el. pašto adresų apdorojami atitinkamam bendravimui. Geriausia praktika yra naudoti el. pašto grupes, pvz., *JAV pardavimų komandą* Office 365, kuri yra lengvai valdoma. El. pašto adresų skaičius grupėse yra išspręstas ir rodomas. Bendras el. pašto adresų skaičius turi būti ne mažesnis kaip 2 ir negali viršyti 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Paskyros įtraukimo el. pašto adresai.":::

1. Peržiūrėkite sutikimo pareiškimą, pažymėkite **žymės langelį Sutinku** ir pasirinkite **Pirmyn**.

1. Pasirinkite kliento duomenų rinkinį ir pasirinkite **Pirmyn**.

1. Susiekite kontakto el. pašto adreso lauką ir pasirinkite **Pirmyn**.

1. Peržiūrėkite sodrinimo konfigūraciją, suteikite sodrinimo pavadinimą ir pasirinkite **Įrašyti sodrinimą**, kad išsaugotumėte sodrinimą.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 nuomotojo administratoriaus sutikimas

Office 365 Norint suaktyvinti sodrinimą, reikalingas nuomininko administratoriaus sutikimas. Įrašius praturtėjimą nuomotojo administratoriams siunčiamas Office 365 el. laiškas, kuriame prašoma peržiūrėti ir sutikti leisti "Dynamics 365" Office 365 programoms naudoti jūsų įmonės duomenis, kad būtų galima pateikti **organizacijos** įžvalgas. Nuomotojo administratorius Office 365 taip pat gali tiesiogiai sutikti savo Office 365 administratoriaus konsolėje, pasirinkdamas **Organizacijos** įžvalgos.

## <a name="running-the-enrichment-for-the-first-time"></a>Pirmą kartą veikia praturtėjimas

Kai praturtėjimas pradedamas pirmą kartą, nuomininko Office 365 administratoriui davus sutikimą, duomenys atsisiunčiami iš Office 365 pradžių. Šis procesas užtrunka šiek tiek laiko. Planuojama, kad pirmasis sodrinimo važiavimas įvyks su šešių valandų vėlavimu. Dienų, kurias duomenys apima paskyros įtraukimo apžvalgos puslapyje pasibaigus sodrinimo pabaigai, skaičių. Turėdami didelį duomenų kiekį, po kelių dienų vėl paleiskite sodrinimą. Tai užtikrina, kad duomenys būtų išsamūs visą laiko langą, kuris yra vieneri metai.

Norėdami pradėti procesą, puslapyje Abonemento įtraukimo konfigūracija pasirinkite **Vykdyti**. Be to, galite leisti sistemai automatiškai vykdyti sodrinimą kaip suplanuoto [atnaujinimo](system.md#schedule-tab) dalį. Pagal numatytuosius nustatymus sodrinimas vyksta kartą per savaitę.

Atsižvelgiant į "Office" duomenų dydį, gali užtrukti kelias valandas, kol bus baigtas sodrinimas.

Kai paleisite papildymą, "Microsoft" tvarkys duomenis atitikties ribose Office 365, kad sukurtų apibendrintas įžvalgas, kurios vėliau bus įtrauktos į jūsų "Customer Insights" aplinką. Jokie atskiro lygio duomenys (pvz., bet kokio el. laiško ar kalendoriaus kvietimo tekstas) "Customer Insights" naudotojams tampa prieinami. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Papildymo rezultatai

Atlikę sodrinimo procesą, eikite į **Mano praturtėjimą**, kad peržiūrėtumėte sodrinimo rezultatus. Rasite bendrą praturtintų klientų skaičių ir sodrinimo rezultatų apžvalgą. Tai apima apdorotų el. laiškų ir susitikimų skaičių, dienų, kurių duomenys buvo apibendrinti, skaičių ir dar daugiau.

Taip pat rasite diagramą su praturtintų klientų skaičiumi laikui bėgant ir sodrinimo duomenų peržiūrą.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Rezultatų peržiūra atlikus papildymo procesą.":::

Visi duomenys kaupiami iki sąskaitos lygio. Sistema apskaičiuoja kiekvienos sąskaitos įsitraukimo balą, kuris svyruoja nuo 0 iki 100. Sužadėtuvių balas pateikia sudėtinį paskyros įtraukimo el. laiškuose ir susitikimuose, palyginti su kitomis paskyromis, matą. Šiame sąraše pateikiami apibendrinti duomenys, kuriuos pateikia paskyros įtraukimo sodrinimas:



| Duomenys                                                                              | Stulpelio pavadinimas                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Įtraukimo rezultatas                                                                  |  EngagementScore                         |
| El. laiškų į sąskaitą skaičius                                                       |  NoOfEmails_ToAccount                    |
| El. laiškų iš paskyros skaičius                                                     |  NoOfEmails_FromAccount                  | 
| Susitikimų, inicijuotų pagal paskyrą, skaičius                                           |  NoOfMeetings_FromAccount                | 
| Jūsų organizacijos inicijuotų susitikimų skaičius                                 |  NoOfMeetings_ToAccount                  | 
| Žmonių iš jūsų organizacijos skaičius susitikimuose su abonementu                  |  NoOfContactsInvolved_Meetings           | 
| Jūsų organizacijos žmonių skaičius el. pašto pokalbiuose su abonementu       |  NoOfContactsInvolved_Emails             | 
| Žmonių iš paskyros skaičius susitikimuose su jūsų organizacija                  |  NoOfAccountContactsInvolved_Meetings    | 
| Žmonių iš paskyros skaičius el. pašto pokalbiuose su jūsų organizacija       |  NoOfAccountContactsInvolved_Emails      | 
| Įtraukimo pradžios data (pirmasis el. laiškas arba susitikimas duomenyse)                        |  EngagementStartDate                     | 
| Dienos nuo paskutinio el. laiško                                                             |  DaysSinceLastEmail                      | 
| Dienos nuo paskutinio susitikimo                                                           |  DaysSinceLastMeeting                    | 
| Vidutinė susitikimų trukmė                                                      |  AverageDuration_Of_Meetings             | 
| Vidutinė el. pašto atsakymų iš paskyros trukmė                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Agregavimo pradžios data                                                            |  AgregacijaStartDate                    | 
| Agregacijos lygis (metai, mėnuo ar savaitė)                                          |  AgregacijaLygu                        | 


Peržiūrėkite praturtintus duomenis pasirinkdami **Peržiūrėti daugiau** peržiūros skyriuje. Jis atidaro "Office"*objektą*. Objektą, nurodytą **duomenųentybių grupėje** **Sodrinimas** > **,** taip pat galite rasti. Taip pat rasite *Office_UserEntity*, kuriame yra "Active Directory" asmens, skirtas el. pašto adresams, pasirinktiems sodrinimo konfigūravimo metu, 

## <a name="see-enrichment-data-on-the-customer-card"></a>Žr. papildymo duomenis kliento kortelėje

Paskyros įtraukimą taip pat galima peržiūrėti atskirose klientų kortelėse. Eikite į **Klientai** ir pasirinkite kliento profilį. Kliento kortelėje rasite paskyros įtraukimo balą, bendrą el. laiškų skaičių ir bendrą susitikimų skaičių, sukauptą per pastaruosius metus. Taip pat rasite diagramas, kuriose rodoma el. pašto ir susitikimų istorija.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kliento kortelė su papildytais duomenimis.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Segmentų ir priemonių kūrimas remiantis praturtintais duomenimis

Praturtinti duomenys gali būti naudojami kuriant segmentus ir priemones, kaip išsamiai aprašyta toliau. Pavyzdžiui, segmentas, kuriame yra visi klientai, kurių vertė viršija 60 *dienų nuo paskutinio el. laiško* ir *dienų nuo paskutinio susitikimo*. Tame segmente yra pasenusių paskyrų, kurias galite bandyti suaktyvinti iš naujo. 

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
