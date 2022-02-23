---
title: Praturtinkite klientų profilius duomenimis iš Microsoft Office 365
description: Naudokite nuosavybės Microsoft Office duomenis, kad praturtintumėte savo klientų profilius įtraukimo duomenimis.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a30e09b5ed491c8d36019b5f0d35e0a2f7a0199c
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/03/2021
ms.locfileid: "7889780"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Klientų profilių praturtinti įtraukimo duomenimis (peržiūra)

Naudokite duomenis, Microsoft Office 365 kad praturtintumėte savo klientų paskyros profilius įžvalgomis apie įtraukimus per Office 365 programas. Įtraukimo duomenis sudaro el. pašto ir susitikimo veikla, kuri kaupiama paskyros lygiu. Pavyzdžiui, el. laiškų iš verslo paskyros skaičius arba susitikimų su paskyra skaičius. Duomenų apie atskirus vartotojus nėra. 

Šis praturtinimas yra šiuose regionuose: Jungtinėje Karalystėje, Europoje, Šiaurės Amerikoje.

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint konfigūruoti sodrinimo sąlygas, reikia įvykdyti šias būtinas sąlygas:

- Turite aktyvią Office 365 debesies licenciją.
- [Suvienodinote klientų profilius](customer-profiles.md) pagal [verslo sąskaitas](work-with-business-accounts.md).
- Jūsų "Customer Insights" aplinkoje turi būti [Microsoft Dataverse pridėta organizacija](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Turite [administratoriaus](permissions.md#administrator) teises.
- Turite arba galite gauti Office 365 nuomotojo administratoriaus sutikimą naudoti duomenis organizacijos Office 365 įžvalgoms **teikti** "Dynamics 365" programose.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Publikos įžvalgose, eikite į **Duomenys** > **Praturtinimas**.

1. Eikite į **skirtuką Atrasti** ir **pasirinkite Praturtinti savo duomenis** **plytelėje Abonemento** įtraukimas.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Paskyros įtraukimo plytelė.":::
   
1. Veiksmą Peržiūra pasirinkite **Pirmyn** ir įveskite **el**. pašto adresus iš savo organizacijos, kurios "Office" duomenys bus kaupiami. Tik duomenys iš išvardytų el. pašto adresų apdorojami atitinkamam bendravimui. Geriausia praktika yra naudoti el. pašto grupes, pvz., *JAV pardavimų* komandą, kurios lengvai valdomos Office 365. El. pašto adresų skaičius grupėse išsprendžiamas ir rodomas. Bendras el. pašto adresų skaičius turi būti ne mažesnis kaip 2 ir negali viršyti 2500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Paskyros įtraukimo el. pašto adresai.":::

1. Peržiūrėkite sutikimo pareiškimą, pažymėkite **žymės langelį Sutinku** ir pasirinkite **Pirmyn**.

1. Pasirinkite kliento duomenų rinkinį ir pasirinkite **Pirmyn**.

1. Susiekite kontakto el. pašto adreso lauką ir pasirinkite **Pirmyn**.

1. Peržiūrėkite sodrinimo konfigūraciją, suteikite sodrinimo pavadinimą ir pasirinkite **Įrašyti sodrinimo,** kad išsaugotumėte sodrinimo.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 nuomotojo administratoriaus sutikimas

Office 365 Norint suaktyvinti sodrinimo teigiamą, reikalingas nuomotojo administratoriaus sutikimas. Office 365 Įrašius sodrinimo duomenis nuomotojo administratoriams siunčiamas el. laiškas, kuriame prašoma peržiūrėti ir sutikti leisti "Dynamics 365" programoms naudoti jūsų įmonės Office 365 duomenis organizacijos **įžvalgoms** teikti. Office 365 Nuomotojo administratorius taip pat gali sutikti tiesiogiai savo Office 365 administravimo konsolėje pasirinkdamas **Organizacijos įžvalgos**.

## <a name="running-the-enrichment-for-the-first-time"></a>Praturtėjimas – pirmą kartą

Kai praturtėjimas pradedamas pirmą kartą, Office 365 nuomininko administratoriui davus sutikimą, prasideda duomenų Office 365 atsisiuntimas. Šis procesas užima šiek tiek laiko. Planuojama, kad pirmasis sodrinimo bėgimas įvyks vėluojant šešioms valandoms. Pasibaigus sodrinimo užbaigimui, galite matyti dienų, kurias duomenys apima paskyros įtraukimo apžvalgos puslapyje, skaičių. Turėdami didelį duomenų tūrį, po kelių dienų vėl paleiskite sodrinimo duomenis. Tai užtikrina, kad duomenys būtų baigti visam laiko langui, kuris yra vieneri metai.

Norėdami pradėti procesą, **puslapyje** Abonementas įtraukimo konfigūracija pasirinkite Vykdyti. Be to, galite leisti sistemai automatiškai paleisti sodrinimo sistemą kaip [suplanuoto atnaujinimo dalį](system.md#schedule-tab). Pagal numatytuosius nustatymus sodrinimas vyksta kartą per savaitę.

Atsižvelgiant į "Office" duomenų dydį, gali prireikti kelių valandų, kol bus baigtas sodrinimo bandymas.

Kai paleisite sodrinimo procesą, "Microsoft" apdoros Office 365 duomenis atitikties ribose, kad sukurtų apibendrintas įžvalgas, kurios vėliau bus įtrauktos į "Customer Insights" aplinką. "Customer Insights" vartotojams jokie duomenys individualiu lygmeniu (pvz., bet kurio el. laiško ar kalendoriaus kvietimo tekstas) nepasiekiami. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Papildymo rezultatai

Paleidę sodrinimo procesą, eikite į **Mano sodrinimo** rezultatai, kad peržiūrėtumėte sodrinimo rezultatus. Čia rasite bendrą praturtintų klientų skaičių ir sodrinimo rezultatų apžvalgą. Tai apima apdorotų el. laiškų ir susitikimų skaičių, dienų, per kurias duomenys buvo apibendrinti, skaičių ir dar daugiau.

Taip pat rasite diagramą su praturtintų klientų skaičiumi laikui bėgant ir sodrinimo duomenų peržiūrą.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Rezultatų peržiūra atlikus papildymo procesą.":::

Visi duomenys sujungiami iki sąskaitos lygio. Sistema apskaičiuoja kiekvienos sąskaitos sužadėtuvių balą, kuris svyruoja nuo 0 iki 100. Įsitraukimo balas pateikia sudėtinį paskyros įsitraukimo el. laiškuose ir susitikimuose, palyginti su kitomis paskyromis, matą. Šiame sąraše yra apibendrinti duomenys, kuriuos pateikia paskyros įtraukimo papildymas:



| Duomenys                                                                              | Stulpelio pavadinimas                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Įtraukimo rezultatas                                                                  |  EngagementScore                         |
| El. laiškų, į kurį reikia atsižvelgti, skaičius                                                       |  NoOfEmails_ToAccount                    |
| El. laiškų iš paskyros skaičius                                                     |  NoOfEmails_FromAccount                  | 
| Pagal sąskaitą inicijuotų susitikimų skaičius                                           |  NoOfMeetings_FromAccount                | 
| Jūsų organizacijos inicijuotų susitikimų skaičius                                 |  NoOfMeetings_ToAccount                  | 
| Žmonių iš jūsų organizacijos skaičius susitikimuose su abonementu                  |  NoOfContactsInvolved_Meetings           | 
| Jūsų organizacijos žmonių skaičius el. laiškuose su abonementu       |  NoOfContactsInvolved_Emails             | 
| Žmonių iš paskyros skaičius susitikimuose su jūsų organizacija                  |  NoOfAccountContactsInvolved_Meetings    | 
| Žmonių iš paskyros skaičius el. laiškų pokalbiuose su jūsų organizacija       |  NoOfAccountContactsInvolved_Emails      | 
| Įtraukimo pradžios data (pirmasis el. laiškas arba susitikimas duomenyse)                        |  EngagementStartDate                     | 
| Dienos nuo paskutinio el. pašto                                                             |  DaysSinceLastEmail                      | 
| Dienos nuo paskutinio susitikimo                                                           |  DaysSinceLastMeeting                    | 
| Vidutinė susitikimų trukmė                                                      |  AverageDuration_Of_Meetings             | 
| Vidutinė el. laiškų atsakymų iš paskyros trukmė                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Agregavimo pradžios data                                                            |  AgregacijaStartDate                    | 
| Agregacijos lygis (metai, mėnuo ar savaitė)                                          |  AgregacijaLygelis                        | 


Peržiūrėkite praturtintus duomenis **pasirinkdami Peržiūrėti daugiau** peržiūros skyriuje. Jis atidaro *"Office"* objektą. Taip pat galite rasti objektą, nurodytą **duomenų objektų grupėje Sodrinimas** **·** > **·**. Taip pat rasite *Office_UserEntity,* kuriame yra "Active Directory" ID, skirti el. pašto adresams, pasirinktiems sodrinimo konfigūracijos metu 

## <a name="see-enrichment-data-on-the-customer-card"></a>Žr. papildymo duomenis kliento kortelėje

Paskyros įtraukimą taip pat galima peržiūrėti atskirose klientų kortelėse. Eikite į **Klientai** ir pasirinkite kliento profilį. Kliento kortelėje rasite paskyros įsitraukimo balą, bendrą el. laiškų skaičių ir bendrą susitikimų skaičių, sukauptą per praėjusius metus. Taip pat rasite diagramas, kuriose rodoma el. pašto ir susitikimų retrospektyva.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kliento kortelė su papildytais duomenimis.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Kurti segmentus ir priemones pagal praturtintus duomenis

Praturtinti duomenys gali būti naudojami segmentams ir priemonėms kurti, kaip išsamiai aprašyta toliau. Pavyzdžiui, segmentas, kuriame yra visi klientai, kurių vertė yra daugiau nei 60 *dienų nuo paskutinio el. pašto ir* dienų nuo paskutinio *susitikimo*. Šiame segmente yra pasenusių paskyrų, kurias galite bandyti suaktyvinti iš naujo. 

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
