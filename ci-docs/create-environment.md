---
title: Kaip sukurti naują aplinką
description: Veiksmai, skirti kurti aplinkas su Dynamics 365 Customer Insights.
ms.date: 05/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 6dfaa09cd80498e9a4e4dea6a07ce6e9d29105e2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011621"
---
# <a name="how-to-create-a-new-environment"></a>Kaip sukurti naują aplinką

Įsigijęs [prenumeratos licenciją, visuotinis Dynamics 365 Customer Insights](paid-license.md) nuomotojo Microsoft 365 administratorius gauna el. laišką, kuris kviečia juos kurti aplinką. Eikite į [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start), kad pradėtumėte. Tokiu atveju galite pereiti tiesiai į 1 veiksmą [: pateikite pagrindinę informaciją](#step-1-provide-basic-information).

Sukūrus pirmąją aplinką, visuotinis nuomotojo administratorius Microsoft 365 gali [įtraukti vartotojus į savo organizaciją kaip administratorius](permissions.md). Judėdami į priekį, šie administratoriai gali valdyti vartotojus ir aplinkas. Jei jūsų organizacija perka daugiau nei vieną "Customer Insights" licenciją, susisiekite su mūsų palaikymo komanda [,](https://go.microsoft.com/fwlink/?linkid=2079641) kad padidintumėte galimų aplinkų skaičių. Norėdami gauti daugiau informacijos apie pajėgumą ir priedų talpą, peržiūrėkite ["Dynamics 365" licencijavimo vadovą](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Jei norite išbandyti paslaugą, žr. [Bandomosios versijos aplinkos nustatyti](trial-signup.md).

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint kurti arba tvarkyti aplinkas, reikia [administratoriaus](permissions.md) teisių programoje "Customer Insights".

## <a name="start-the-environment-creation-process"></a>Pradėti aplinkos kūrimo procesą

1. Atidarykite aplinkos parinkiklį ir pasirinkite **+ Naujas**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Rinkitės aplinkos parinkiklį..":::

1. Vadovaukitės toliau pateiktuose skyriuose aprašyta vadovo patirtimi, kad pateiktumėte visą reikalingą informaciją naujai aplinkai. Jei aplinką sukonfigūravote anksčiau, taip pat [galite nukopijuoti konfigūraciją](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>1 veiksmas: pateikite pagrindinę informaciją

Pagrindinės **informacijos žingsnyje** pasirinkite, ar norite kurti aplinką nuo pradžių, ar [kopijuokite duomenis iš kitos aplinkos](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Naujos Customer Insights aplinkos sukūrimo dialogo langas.":::

Nurodykite toliau pateiktą informaciją.

- **Pavadinimas**: Šios aplinkos pavadinimas. Šis laukas jau užpildytas, jei kopijuojate esamą aplinką, tačiau jį galite keisti.
- **Pasirinkite savo verslą**: pasirinkite pagrindinę naujos aplinkos auditoriją. Galite dirbti su individualiais atsiliepimais (B 2 C) arba [verslo klientais](work-with-business-accounts.md) (B2B). Jei jūsų organizacija daugiausia užsiima verslu su asmenimis, pvz., Mažmenininku ar kavine, pasirinkite atskirus vartotojus. Jei jūsų pagrindinė auditorija yra kitos įmonės, pvz., Automobilių gamintojas ar popieriaus įmonė, pasirinkite verslo sąskaitas.
- **Tipas**: pasirinkite, ar norite sukurti gamybos, ar smėlio dėžės aplinką. Smėlio dėžės aplinkos neleidžia suplanuoto duomenų atnaujinimo ir yra skirtos išankstiniam diegimui ir testavimui. Smėlio dėžės aplinkos naudoja tą pačią pagrindinę auditoriją kaip ir dabar pažymėta gamybos aplinka.
- **Sritis**: sritis, kurioje įdiegta ir teikiama ši paslauga. Norint [naudoti savo Azure Data Lake Storage abonementą](own-data-lake-storage.md) arba [prisijungti prie esamos Microsoft Dataverse organizacijos](customer-insights-dataverse.md), "Customer Insights" aplinka turi būti tame pačiame regione.

## <a name="step-2-configure-data-storage"></a>2 žingsnis: konfigūruokite duomenų saugyklą

Veiksmų duomenų **saugojimo** veiksme pasirinkite, kur saugoti "Customer Insights" duomenis.

Yra dvi parinktys, iš kurių galite rinktis:

- **"Customer Insights" saugykla**: duomenų saugyklą valdo "Customer Insights" komanda. Tai numatytoji parinktis ir, jei nėra konkrečių reikalavimų duomenims saugoti savo saugyklos paskyroje, rekomenduojame naudoti šią parinktį.
- **Azure Data Lake Storage**: Nurodykite savo Azure Data Lake Storage paskyrą duomenims saugoti, kad galėtumėte visiškai kontroliuoti, kur saugomi duomenys. Daugiau informacijos ieškokite [Use your own Azure Data Lake Storage account](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Pasirinkite tinkamiausią duomenų saugojimo parinktį.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>3 žingsnis: Prisijungti prie „Microsoft Dataverse“

Šis **Microsoft Dataverse** veiksmas leidžia „Customer Insights“ susieti su „Dataverse“ aplinka. Bendrinkite duomenis su Dataverse jais, kad galėtumėte juos naudoti su verslo programomis, pagrįstomis Dataverse, pvz., "Dynamics 365 Marketing" arba modeliu pagrįstomis programomis.Power Apps


Palikite šį lauką tuščią, jei neturite savo Dataverse aplinkos, ir mes ją sukursime jums.

Daugiau informacijos ieškokite [Work with Customer Insights data in Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="duomenų bendrinimas su Microsoft Dataverse automatiniu įgalinimu naujoms grynosioms aplinkoms.":::

### <a name="step-4-finalize-the-settings"></a>4 veiksmas: užbaikite nustatymus

Atlikdami veiksmą **Peržiūra**, peržiūrėkite visus nurodytus parametrus. Baigę viską, pasirinkite **Kurti** ir nustatykite aplinką.

Vėliau galite pakeisti kai kuriuos parametrus. Daugiau informacijos žr. [Aplinkų valdymas](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Darbas su nauja aplinka

Peržiūrėkite šiuos straipsnius, kad būtų galima pradėti konfigūruoti „Customer Insights“:

- [Įtraukite daugiau vartotojų ir priskirkite teises](permissions.md).
- [Įtraukite savo duomenų šaltinius](data-sources.md) ir paleiskite juos per [duomenų suvienodinimo procesą](data-unification.md), kad gautumėte [suvienodintus klientų profilius](customer-profiles.md).
- [Papildykite vieninguosius klientų profilius](enrichment-hub.md) arba [paleiskite numatomus modelius](predictions-overview.md).
- [Kurkite segmentus](segments.md), kad sugrupuotumėte klientus ir [priemones](measures.md) KPI peržiūrai.
- [Nustatykite ryšius](connections.md) ir [eksportavimus](export-destinations.md), kad kitose taikomosiose programose būtų apdorojami antriniai duomenų rinkiniai.

## <a name="copy-the-environment-configuration"></a>Aplinkos konfigūracijos kopijavimas

Kaip administratorius galite pasirinkti kopijuoti konfigūraciją iš esamos aplinkos, kai kuriate naują.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Aplinkos parametrų parinkčių ekrano kopija.":::

Matysite visų jūsų organizacijoje pasiekiamų aplinkų sąrašą, iš kurių galima kopijuoti duomenis.

Kopijuojami šie konfigūracijos parametrai:

- Duomenų šaltiniai, importuoti per Power Query
- Duomenų suvienijimo konfigūracija
- Segmentai
- Matavimai
- Ryšiai
- Veiklos
- Ieškos ir filtro rodyklė
- Eksportavimai
- Atnaujinti grafiką
- Papildymai
- Prognozė modeliai
- Vaidmenų priskyrimai

## <a name="set-up-a-copied-environment"></a>Nukopijuotos aplinkos nustatymas

Kai kopijuojate aplinkos konfigūraciją, turite atlikti keletą papildomų veiksmų, kad patvirtintumėte kredencialus:

- Klientų profiliai. Pirma, autentifikuoti ir nuryti savo duomenų šaltinius ir paleiskite duomenų suvienijimą, kad atkurtumėte klientų profilius.
- Duomenų šaltinio kredencialai. Turite pateikti kiekvieno duomenų šaltinis, kad neautentifikuotumėte ir atnaujintumėte duomenų šaltinius rankiniu būdu, kredencialus.
- Duomenų šaltiniai iš aplanko Bendrųjų duomenų modelis ir Dataverse. Šiuos duomenų šaltinius turite sukurti rankiniu būdu tuo pačiu pavadinimu, kaip ir šaltinio aplinkoje.
- Ryšio paslaptys, naudojamos eksportui ir sodrinimui. Jūs turite iš naujo atkurti ryšius ir tada iš naujo suaktyvinti sodrinimą ir eksportą.

Sukūrę nukopijuotą aplinką, pamatysite patvirtinimo pranešimą. Pasirinkite **Eiti į duomenų šaltinius**, kad peržiūrėtumėte duomenų šaltinių sąrašą.

Visi duomenų šaltiniai rodys būseną **Reikia kredencialų**. Redaguokite duomenų šaltinius ir įveskite kredencialus, kad juos atnaujintumėte.

:::image type="content" source="media/data-sources-copied.png" alt-text="Duomenų šaltinių, kurie buvo nukopijuoti ir kuriems reikalingas autentifikavimas, sąrašas.":::

Atnaujinę duomenų šaltinius, eikite į **Duomenys** > **Suvienodinti**. Čia rasite parametrus iš šaltinio aplinkos. Jei reikia, redaguokite juos arba pasirinkite **Vykdyti**, kad pradėtumėte duomenų sujungimo procesą ir sukurtumėte bendrąjį kliento objektą.

Kai duomenų sujungimas baigtas, eikite į **Priemonės** ir **Segmentai**, kad jie būtų atnaujinti.

Prieš iš naujo suaktyvindami eksportą ir praturtinimus, eikite į **Administratoriaus** > **ryšiai**, kad iš naujo atkurtumėte ryšius naujoje aplinkoje.

[!INCLUDE [footer-include](includes/footer-banner.md)]
