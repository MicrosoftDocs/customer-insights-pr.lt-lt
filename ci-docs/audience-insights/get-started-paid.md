---
title: Mokamos „Customer Insights” licencijos kūrimas ir konfigūravimas
description: Veiksmai norint gauti licencijuotą „Dynamics 365 Customer Insights” prenumeratą ir sukonfigūruoti ją.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f8cf1be97ee8af46145a450009fd278b1821f8fe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650492"
---
# <a name="get-started-with-a-paid-subscription"></a>Pradėkite darbą su mokama prenumerata

Šiame straipsnyje paaiškinta, kaip sukurti naują aplinką jūsų organizacijai įsigijus „Dynamics 365 Customer Insights” prenumeratą. Jei norėtumėte įsigyti „Customer Insights”, mūsų kontaktų parinktys išvardytos [„Dynamics 365 Customer Insights” svetainėje](https://dynamics.microsoft.com/ai/customer-insights/). 

Jei norite išbandyti paslaugą ir funkcijas, skaitykite [Bandomosios versijos aplinkos nustatymas](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Aplinkos kūrimas esamoje organizacijoje

Įsigijus „Customer Insights” prenumeratos licenciją, „Microsoft 365” nuomotojo visuotinis administratorius gauna elektroninį laišką, kuris paragina juos sukurti aplinką. Eikite į [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start), kad pradėtumėte. 

„Customer Insights” nėra licencijuota vienam vartotojui, todėl ji nebus rodoma srityje Licencijos. Jei ieškote licencijos „Microsoft 365” administravimo centre, eikite į **Jūsų produktai**. 

> [!NOTE]
> Organizacijos gali sukurti *dvi* aplinkas kiekvienai „Customer Insights“ licencijai. Jei jūsų organizacija įsigyja daugiau nei vieną licenciją, [kreipkitės į mūsų palaikymo komandą](https://go.microsoft.com/fwlink/?linkid=2079641), kad padidintumėte galimų aplinkų skaičių. Norėdami gauti daugiau informacijos apie pajėgumą ir papildinio pajėgumą, atsisiųskite [„Dynamics 365” licencijavimo vadovą](https://go.microsoft.com/fwlink/?LinkId=866544).

Norėdami sukurti aplinką:

1. Dialogo lange **Aplinkos kūrimas** pažymėkite **Nauja aplinka**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Naujos Customer Insights aplinkos sukūrimo dialogo langas.":::

   Rekomenduojame aplinkos nustatymą pradėti nuo nulio. Tačiau, jei esate bandomosios versijos aplinkos administratorius ar narys, galite [kopijuoti duomenis iš kitos aplinkos](manage-environments.md#copy-the-environment-configuration) pasirinkdami **Kopijuoti iš esamos aplinkos**. Matysite visų jūsų organizacijoje pasiekiamų aplinkų sąrašą, iš kurių galima kopijuoti duomenis.

1. Nurodykite toliau pateiktą informaciją.
   - **Pavadinimas**: Šios aplinkos pavadinimas. Šis laukas jau užpildytas, jei kopijuojate esamą aplinką, tačiau jį galite keisti.
   - **Sritis**: sritis, kurioje įdiegta ir teikiama ši paslauga.
   - **Tipas**: pasirinkite, ar norite sukurti gamybos, ar smėlio dėžės aplinką. Smėlio dėžės aplinkos neleidžia suplanuoto duomenų atnaujinimo ir yra skirtos išankstiniam diegimui ir testavimui.
   
1. Pasirinktinai galite spustelėti **Išplėstiniai parametrai**.

   - **Įrašyti visus duomenis į**: nurodo, kur norite saugoti išvesties duomenis, sugeneruotus iš „Customer Insights“. Galėsite pasirinkti dvi galimybes: **„Customer Insights" saugyklą** („Azure Data Lake", kurią valdo „Customer Insights" komanda) ir **Azure Data Lake Storage** (komanda ir „Azure Data Lake Storage“). Pagal numatytuosius parametrus, pasirenkama „Customer Insights“ saugykla.

     > [!NOTE]
     > Įrašydami duomenis į „Azure Data Lake Storage, sutinkate, kad jūsų duomenys būtų perkelti ir saugomi konkrečiai „Azure“ paskyrai paskirtoje geografinėje vietovėje , kuri gali skirtis nuo vietovės, kurioje saugomi „Dynamics 365 Customer Insights“ duomenys. [Sužinokite daugiau „Microsoft“ patikimumo centre.](https://www.microsoft.com/trust-center)
     >
     > Šiuo metu iš „Power BI” duomenų srautų įtraukti objektai yra saugomi „Microsoft Dataverse“ valdomame „data lake”. 
     > 
     > Palaikome tik to „Azure Data Lake Storage“ paties „Azure" regiono, kurį pasirinkote kurdami aplinką, abonementus. 
     > 
     > Palaikome tik „Azure Data Lake Storage“ abonementus, kurių hierarchinė vardų sritis įjungta.


   - Galite „Azure Data Lake Storage“ pasirinkti iš išteklių pagrįstą parinktį ir prenumerata pagrįstą autentifikavimo parinktį. Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md). **Talpyklės** pavadinimo keisti negalima, jis bus `customerinsights`.
   
   - Jei norite naudoti [visiškai parengtus modelius](predictions-overview.md#out-of-box-models), konfigūruokite duomenų bendrinimą su „Microsoft Dataverse” arba įgalinkite duomenų įtraukimą iš vietinių duomenų šaltinių, pateikite „Microsoft Dataverse” aplinkos URL dalyje **Konfigūruoti duomenų bendrinimą su „Microsoft Dataverse” ir įgalinti papildomas galimybes**. Pasirinkite Įjungti **duomenų bendrinimą** ir bendrinkite Customer Insights išvedimo duomenis su Microsoft Dataverse valdomu Data Lake.

     > [!NOTE]
     > - Duomenų bendrinimas Microsoft Dataverse su valdomasis duomenų telkiniais šiuo metu nepalaikomas, kai įrašote visus duomenis savo Azure Data Lake Storage.
     > - [Trūkstamų objekto verčių prognozė](predictions.md) šiuo metu nepalaikoma, kai įjungiate duomenų bendrinimą su Microsoft Dataverse valdomu „Data Lake“.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Konfigūravimo parinktys duomenų bendrinimui su Microsoft Dataverse įjungti.":::

   Kai sistemos procesai, pavyzdžiui, duomenų įtraukimas užbaigiami, sistema sukuria atitinkamus aplankus jūsų nurodytame saugyklos abonemente. Duomenų failai ir model.json failai yra kuriami ir įtraukiami į aplankus pagal proceso pavadinimą.

   Jei sukuriate keletą „Customer Insights“ aplinkų ir pasirenkate įrašyti išvesties objektus iš tų aplinkų į jūsų talpinimo paskyrą, atskiri katalogai bus sukurti kiekvienai aplinka su ci_<environmentid> talpykloje.

1. Pasirinkite **Kurti**, kad nustatytumėte aplinką. 

## <a name="configure-an-environment"></a>Aplinkos konfigūravimas

Peržiūrėkite šiuos straipsnius, kad galėtumėte pradėti konfigūruoti „Customer Insights”. 

- [Įtraukite daugiau vartotojų ir priskirkite teises](permissions.md).
- [Įtraukite savo duomenų šaltinius](data-sources.md) ir paleiskite juos per [duomenų suvienodinimo procesą](data-unification.md), kad gautumėte [suvienodintus klientų profilius](customer-profiles.md).
- [Papildykite vieninguosius klientų profilius](enrichment-hub.md) arba [paleiskite numatomus modelius](predictions-overview.md).
- Kurkite [segmentus](segments.md), kad sugrupuotumėte klientus ir [priemones](measures.md) KPI peržiūrai.
- Nustatykite [ryšius](connections.md) ir [eksportavimus](export-destinations.md), kad kitose taikomosiose programose būtų apdorojami antriniai duomenų rinkiniai.
