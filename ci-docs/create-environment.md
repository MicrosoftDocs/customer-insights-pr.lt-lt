---
title: Kurti naują aplinką
description: Veiksmai, kaip sukurti aplinkas Dynamics 365 Customer Insights.
ms.date: 08/15/2022
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
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304254"
---
# <a name="create-a-new-environment"></a>Kurti naują aplinką

Įsigijęs [prenumeratos licenciją Dynamics 365 Customer Insights](paid-license.md), visuotinis nuomotojo Microsoft 365 administratorius gauna el. laišką, kuriame jis kviečiamas kurti aplinką. Eikite į [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start), kad pradėtumėte. Pagal šį scenarijų pradėkite nuo [1 veiksmo: pateikite pagrindinę informaciją](#step-1-provide-basic-information).

Sukūrus pirmąją aplinką, nuomotojo Microsoft 365 visuotinis administratorius gali [įtraukti vartotojus iš savo organizacijos kaip administratorius](permissions.md). Tada šie administratoriai gali valdyti vartotojus ir aplinkas. Jei jūsų organizacija įsigyja daugiau nei vieną "Customer Insights" licenciją, susisiekite su mūsų palaikymo komanda [,](https://go.microsoft.com/fwlink/?linkid=2079641) kad padidintumėte galimų aplinkų skaičių. Norėdami gauti daugiau informacijos apie pajėgumą ir priedo pajėgumą, peržiūrėkite ["Dynamics 365" licencijavimo vadovą](https://go.microsoft.com/fwlink/?LinkId=866544). Kai turėsite galimybę kurti papildomas aplinkas, eikite į [Pradėti aplinkos kūrimo procesą](#start-the-environment-creation-process).

> [!TIP]
> Jei norite išbandyti paslaugą, žr. [Bandomosios versijos aplinkos nustatyti](trial-signup.md).

## <a name="prerequisites"></a>Būtinosios sąlygos

[Administratoriaus teisės](permissions.md) programoje "Customer Insights"

## <a name="start-the-environment-creation-process"></a>Pradėkite aplinkos kūrimo procesą

1. Atidarykite aplinkos parinkiklį ir pasirinkite **+ Naujas**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Rinkitės aplinkos parinkiklį..":::

1. Vadovaukitės tolesniuose skyriuose aprašyta patirtimi, kad pateiktumėte visą naujai aplinkai reikalingą informaciją.

## <a name="step-1-provide-basic-information"></a>1 veiksmas: pateikite pagrindinę informaciją

1. Pasirinkite, ar norite kurti aplinką nuo pradžių, ar kopijuoti duomenis iš kitos aplinkos. [Norint kopijuoti duomenis iš kitos aplinkos](#copy-the-environment-configuration), reikia atlikti papildomus veiksmus.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Naujos Customer Insights aplinkos sukūrimo dialogo langas.":::

1. Nurodykite toliau pateiktą informaciją.

   - **Pavadinimas**: Šios aplinkos pavadinimas. Šis laukas jau užpildytas, jei kopijuojate esamą aplinką, tačiau jį galite keisti.
   - **Pasirinkite savo įmonę**: pagrindinė naujos aplinkos auditorija: individualūs vartotojai (nuo B iki C) arba [verslo paskyros](work-with-business-accounts.md) (nuo B iki B). Jei jūsų organizacija daugiausia užsiima verslu su asmenimis, pvz., mažmenininku ar kavine, rinkitės individualius vartotojus. Jei jūsų pagrindinė auditorija yra kitos įmonės, pvz., Automobilių gamintojas ar popieriaus įmonė, pasirinkite verslo sąskaitas.
   - **Tipas**: Aplinkos tipas: gamyba arba smėlio dėžė. Smėlio dėžės aplinkos neleidžia suplanuoto duomenų atnaujinimo ir yra skirtos išankstiniam diegimui ir testavimui. Smėlio dėžės aplinkos naudoja tą pačią pagrindinę auditoriją kaip ir dabar pažymėta gamybos aplinka.
   - **Regionas**: regionas, kuriame tarnyba įdiegta ir priglobta. Norint [naudoti savo Azure Data Lake Storage paskyrą](own-data-lake-storage.md) arba [prisijungti prie esamos Microsoft Dataverse organizacijos](customer-insights-dataverse.md), "Customer Insights" aplinka turi būti tame pačiame regione.

1. Pasirinkite **Toliau**.

## <a name="step-2-configure-data-storage"></a>2 žingsnis: konfigūruokite duomenų saugyklą

1. Pasirinkite, kur saugoti "Customer Insights" duomenis:

   - **"Customer Insights" saugykla**: duomenų saugykla valdoma automatiškai. Tai numatytoji parinktis ir, jei nėra konkrečių reikalavimų saugoti duomenis savo saugyklos paskyroje, rekomenduojame naudoti šią parinktį.
   - **Azure Data Lake Storage**: Jūsų paskyra Azure Data Lake Storage duomenims saugoti, kad galėtumėte visiškai valdyti, kur saugomi duomenys. Atlikite veiksmus, nurodytus [Dalyje Naudojimas savo Azure Data Lake Storage paskyrai](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Pasirinkite pageidaujamą duomenų saugojimo parinktį.":::

1. Pasirinkite **Toliau**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>3 žingsnis: Prisijungti prie „Microsoft Dataverse“

Jei turite Dataverse aplinką, prijunkite "Customer Insights". Bendrinkite duomenis su Dataverse jais, kad galėtumėte juos naudoti su verslo programomis, pagrįstomis Dataverse, pvz., "Dynamics 365 Marketing" arba modeliu pagrįstomis Power Apps programomis.

1. Atlikite veiksmus, nurodytus [Darbe su "Customer Insights" duomenimis Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="duomenų bendrinimas su Microsoft Dataverse automatiškai įgalinta naujų internetinių aplinkų funkcija.":::

1. Pasirinkite **Toliau**.

## <a name="step-4-finalize-the-settings"></a>4 veiksmas: užbaikite nustatymus

Peržiūrėkite nurodytus nustatymus. Baigę viską, pasirinkite **Kurti** ir nustatykite aplinką.

Norėdami pakeisti kai kuriuos parametrus vėliau, žiūrėkite [Tvarkyti aplinkas](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Darbas su nauja aplinka

Peržiūrėkite šiuos straipsnius, kad būtų galima pradėti konfigūruoti „Customer Insights“:

- [Įtraukite daugiau vartotojų ir priskirkite teises](permissions.md).
- [Įtraukite savo duomenų šaltinius](data-sources.md) ir paleiskite juos per [duomenų suvienodinimo procesą](data-unification.md), kad gautumėte [suvienodintus klientų profilius](customer-profiles.md).
- [Papildykite vieninguosius klientų profilius](enrichment-hub.md) arba [paleiskite numatomus modelius](predictions-overview.md).
- [Kurkite segmentus](segments.md), kad sugrupuotumėte klientus ir [priemones](measures.md) KPI peržiūrai.
- [Nustatykite ryšius](connections.md) ir [eksportavimus](export-destinations.md), kad kitose taikomosiose programose būtų apdorojami antriniai duomenų rinkiniai.

## <a name="copy-the-environment-configuration"></a>Aplinkos konfigūracijos kopijavimas

Jei kaip administratorius pasirinkote kopijuoti konfigūraciją iš esamos aplinkos, pasirinkite iš visų organizacijos galimų aplinkų sąrašo.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Aplinkos parametrų parinkčių ekrano kopija.":::

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

### <a name="set-up-a-copied-environment"></a>Nukopijuotos aplinkos nustatymas

Kai kopijuojate aplinkos konfigūraciją, sukuriama nukopijuota aplinka rodomas patvirtinimo pranešimas. Atlikite šiuos veiksmus, kad patvirtintumėte kredencialus.

1. Pasirinkite **Eiti į duomenų šaltinius**, kad peržiūrėtumėte duomenų šaltinių sąrašą. Visuose duomenų šaltiniuose rodoma **būsena Būtina kredencialai**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Duomenų šaltinių, kurie buvo nukopijuoti ir kuriems reikalingas autentifikavimas, sąrašas.":::

1. Redaguokite duomenų šaltinius ir įveskite kredencialus, kad juos atnaujintumėte. Duomenų šaltiniai iš aplanko "Common Data Model" ir Dataverse turi būti sukurti rankiniu būdu tuo pačiu pavadinimu kaip ir šaltinio aplinkoje.

1. Atnaujinę duomenų šaltinius, eikite į **Duomenys** > **Suvienodinti**. Čia rasite parametrus iš šaltinio aplinkos. Jei reikia, redaguokite juos arba pasirinkite **Suvienodinti** > **klientų profilius ir priklausomybes**, kad pradėtumėte duomenų suvienijimo procesą ir sukurtumėte vieningą kliento objektą.

   > [!TIP]
   > Jei naudojate paskyras ir kontaktus, pasirinkite **Suvienodinti paskyras** > **Suvienodinti profilius ir priklausomybes**.

1. Kai duomenų suvienijimas bus baigtas, eikite į **Priemonės** ir **segmentai**, kad juos atnaujintumėte.

1. Eikite į **Administratoriaus** > **ryšiai**, kad iš naujo nustatytumėte ryšius naujoje aplinkoje.

1. Eikite į **Duomenų** > **papildymas** ir **duomenų** > **eksportavimas**, kad juos suaktyvintumėte iš naujo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
