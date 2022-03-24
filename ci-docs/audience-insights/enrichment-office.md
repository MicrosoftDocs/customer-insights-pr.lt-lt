---
title: Praturtinkite klientų profilius duomenimis iš Microsoft Office 365
description: Naudokite nuosavybės duomenis, kad Microsoft Office praturtintumėte savo klientų profilius įtraukimo duomenimis.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 47239bd7f0c89742cf9c673bb2ebe4c41d853233
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376840"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Klientų profilių praturtinimas įtraukimo duomenimis (peržiūra)

Naudokite duomenis iš Microsoft Office 365, kad praturtintumėte savo klientų abonementų profilius įžvalgomis apie įtraukimus per Office 365 programas. Įtraukimo duomenis sudaro el. pašto ir susitikimo veikla, kuri kaupiama paskyros lygiu. Pavyzdžiui, el. laiškų iš verslo paskyros skaičius arba susitikimų su paskyra skaičius. Duomenų apie atskirus vartotojus nepateikiama. 

Šis praturtinimas yra prieinamas šiuose regionuose: Jungtinėje Karalystėje, Europoje, Šiaurės Amerikoje.

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint konfigūruoti sodrinimą, turi būti įvykdytos šios būtinosios sąlygos:

- Turite aktyvią Office 365 debesies licenciją.
- [Suvienodinote klientų profilius](customer-profiles.md) pagal [verslo sąskaitas](work-with-business-accounts.md).
- Jūsų "Customer Insights" aplinka turi būti [Microsoft Dataverse susieta su organizacija](create-environment.md#step-3-connect-to-microsoft-dataverse).
- [Turite administratoriaus](permissions.md#admin) teises.
- Turite arba galite gauti nuomotojo Office 365 administratoriaus sutikimą naudoti Office 365 duomenis" Dynamics 365 " programų organizacijos **įžvalgoms teikti**.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Publikos įžvalgose, eikite į **Duomenys** > **Praturtinimas**.

1. Eikite į skirtuką **Atrasti** ir plytelėje Abonemento **įtraukimas** pasirinkite **Praturtinti mano duomenis**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Abonemento įtraukimo plytelė.":::
   
1. Atlikdami peržiūros **veiksmą pasirinkite** **Pirmyn** ir įveskite savo organizacijos, kurios "Office" duomenys bus kaupiami, el. pašto adresus. Atitinkamam ryšiui apdorojami tik duomenys iš išvardytų el. pašto adresų. Geriausia praktika yra naudoti el. pašto grupes, pavyzdžiui, *JAV pardavimų komandą*, kuri yra lengvai valdoma Office 365. El. pašto adresų skaičius grupėse išsprendžiamas ir rodomas. Bendras el. pašto adresų skaičius turi būti ne mažesnis kaip 2 ir negali viršyti 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Abonemento įtraukimo el. pašto adresai.":::

1. Peržiūrėkite sutikimo patvirtinimą **, pažymėkite žymės langelį Sutinku** ir pasirinkite **Pirmyn**.

1. Pasirinkite kliento duomenų rinkinį ir pasirinkite **Pirmyn**.

1. Susiekite kontakto el. pašto adreso lauką ir pasirinkite **Pirmyn**.

1. Peržiūrėkite sodrinimo konfigūraciją, suteikite sodrinimui pavadinimą ir pasirinkite **Įrašyti sodrinimą**, kad įrašytumėte sodrinimą.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 nuomotojo administratoriaus sutikimas

Norint suaktyvinti Office 365 sodrinimą, reikalingas nuomotojo administratoriaus sutikimas. Įrašius sodrinimą nuomotojo Office 365 administratoriams siunčiamas el. laiškas, kuriame prašoma peržiūrėti ir sutikti leisti "Dynamics 365" Office 365 programoms naudoti jūsų įmonių duomenis organizacijos **įžvalgoms teikti**. Nuomotojo Office 365 administratorius taip pat gali duoti sutikimą tiesiogiai savo Office 365 administravimo konsolėje pasirinkdamas **Organizacijos** įžvalgas.

## <a name="running-the-enrichment-for-the-first-time"></a>Praturtėjimas pirmą kartą

Kai praturtėjimas pradedamas pirmą kartą, nuomininko Office 365 administratoriui davus sutikimą, duomenys atsisiunčiami nuo Office 365 pradžios. Šis procesas užtrunka šiek tiek laiko. Planuojama, kad pirmasis sodrinimo etapas bus atidėtas po šešių valandų. Galite matyti, kiek dienų duomenys apima paskyros įtraukimo apžvalgos puslapyje po sodrinimo pabaigos. Turėdami didelį duomenų kiekį, po kelių dienų vėl paleiskite sodrinimą. Tai užtikrina, kad duomenys būtų išsamūs visam laikotarpiui, kuris yra vieneri metai.

Norėdami pradėti procesą, puslapyje Abonemento įtraukimo konfigūracija pasirinkite **Vykdyti**. Be to, galite leisti sistemai automatiškai vykdyti sodrinimą kaip suplanuoto [atnaujinimo](system.md#schedule-tab) dalį. Pagal numatytuosius nustatymus sodrinimas vyksta kartą per savaitę.

Atsižvelgiant į jūsų "Office" duomenų dydį, sodrinimo vykdymas gali užtrukti kelias valandas.

Kai vykdote papildymą, "Microsoft" apdoros duomenis atitikties ribose Office 365, kad sukurtų apibendrintas įžvalgas, kurios vėliau bus įtrauktos į jūsų "Customer Insights" aplinką. Jokie duomenys atskiru lygiu (pvz., bet kokio el. laiško ar kalendoriaus kvietimo turinys) "Customer Insights" vartotojams netampa prieinami. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Papildymo rezultatai

Paleidę sodrinimo procesą, eikite į **Mano praturtėjimas**, kad peržiūrėtumėte sodrinimo rezultatus. Rasite bendrą praturtintų klientų skaičių ir sodrinimo rezultatų apžvalgą. Tai apima apdorotų el. laiškų ir susitikimų skaičių, dienų, kurioms duomenys buvo apibendrinti, skaičių ir dar daugiau.

Taip pat rasite diagramą su praturtintų klientų skaičiumi laikui bėgant ir sodrinimo duomenų peržiūrą.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Rezultatų peržiūra atlikus papildymo procesą.":::

Visi duomenys kaupiami iki sąskaitos lygio. Sistema apskaičiuoja įtraukimo balą, kuris svyruoja nuo 0 iki 100, kiekvienai sąskaitai. Įtraukimo balas suteikia sudėtinį paskyros įsitraukimo į el. laiškus ir susitikimus, palyginti su kitomis paskyromis, matą. Šiame sąraše yra apibendrinti duomenys, kuriuos teikia paskyros įtraukimo sodrinimas:



| Duomenys                                                                              | Stulpelio pavadinimas                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Įtraukimo rezultatas                                                                  |  EngagementScore                         |
| El. laiškų į paskyrą skaičius                                                       |  NoOfEmails_ToAccount                    |
| El. laiškų iš paskyros skaičius                                                     |  NoOfEmails_FromAccount                  | 
| Pagal paskyrą inicijuotų susitikimų skaičius                                           |  NoOfMeetings_FromAccount                | 
| Jūsų organizacijos inicijuotų susitikimų skaičius                                 |  NoOfMeetings_ToAccount                  | 
| Jūsų organizacijos žmonių skaičius susitikimuose su paskyra                  |  NoOfContactsInvolved_Meetings           | 
| Jūsų organizacijos žmonių skaičius el. pašto pokalbiuose su abonementu       |  NoOfContactsInvolved_Emails             | 
| Žmonių iš paskyros skaičius susitikimuose su jūsų organizacija                  |  NoOfAccountContactsInvolved_Meetings    | 
| Žmonių iš abonemento skaičius el. pašto pokalbiuose su jūsų organizacija       |  NoOfAccountContactsInvolved_Emails      | 
| Įtraukimo pradžios data (pirmasis el. laiškas arba susitikimas duomenyse)                        |  EngagementStartDate                     | 
| Dienos nuo paskutinio el. laiško                                                             |  DaysSinceLastEmail                      | 
| Dienos nuo paskutinio susitikimo                                                           |  DaysSinceLastMeeting                    | 
| Vidutinė susitikimų trukmė                                                      |  AverageDuration_Of_Meetings             | 
| Vidutinė el. laiškų atsakymų iš paskyros trukmė                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Agregavimo pradžios data                                                            |  AgregacijaStartDate                    | 
| Agregacijos lygis (metai, mėnuo ar savaitė)                                          |  Agregacijoslygmenys                        | 


Peržiūrėkite praturtintus duomenis peržiūros skyriuje pasirinkdami **Matyti daugiau**. Jis atidaro "Office"*objektą*. Objektą, išvardytą išteklių grupėje Duomenų **sąlygos,** **·** > **taip pat galite rasti**. Taip pat rasite *Office_UserEntity*, kuriame yra "Active Directory" ID, skirti el. pašto adresams, pasirinktiems sodrinimo konfigūravimo metu 

## <a name="see-enrichment-data-on-the-customer-card"></a>Žr. papildymo duomenis kliento kortelėje

Paskyros įtraukimą taip pat galima peržiūrėti atskirose klientų kortelėse. Eikite į **Klientai** ir pasirinkite kliento profilį. Kliento kortelėje rasite paskyros įtraukimo balą, bendrą el. laiškų skaičių ir bendrą susitikimų, sukauptų per pastaruosius metus, skaičių. Taip pat rasite diagramas, kuriose rodomas el. paštas ir susitikimų retrospektyva.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kliento kortelė su papildytais duomenimis.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Segmentų ir priemonių kūrimas pagal praturtintus duomenis

Praturtinti duomenys gali būti naudojami segmentams ir priemonėms kurti, kaip nurodyta toliau. Pavyzdžiui, segmentas, kuriame yra visi klientai, kurių vertė viršija 60 dienų nuo paskutinio el. laiško *ir* *dienų nuo paskutinio susitikimo*. Tame segmente yra pasenusių paskyrų, kurias galite bandyti suaktyvinti iš naujo. 

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
