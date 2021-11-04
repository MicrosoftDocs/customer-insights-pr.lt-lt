---
title: Kurti aplinkas „Customer Insights“
description: Veiksmai, norint kurti aplinkas su licencijuota „Dynamics 365 Customer Insights“.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 914af46d2d82f3556d149f2836680c902f826d50
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673401"
---
# <a name="create-an-environment-in-audience-insights"></a>Kurti aplinką publikos auditorijos įžvalgose

Šiame straipsnyje paaiškinta, kaip sukurti naują aplinką jūsų organizacijai įsigijus „Dynamics 365 Customer Insights” prenumeratą. 

Organizacijos gali sukurti *dvi* aplinkas kiekvienai „Customer Insights“ licencijai. Jei jūsų organizacija įsigyja daugiau nei vieną licenciją, [kreipkitės į palaikymo komandą](https://go.microsoft.com/fwlink/?linkid=2079641) ir padidinkite galimų aplinkos sąlygų skaičių. Norėdami gauti daugiau informacijos apie pajėgumą ir papildinio pajėgumą, atsisiųskite [„Dynamics 365” licencijavimo vadovą](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Jei norite išbandyti paslaugą, žr. [Bandomosios versijos aplinkos nustatyti](../trial-signup.md).

## <a name="create-a-new-environment"></a>Kurti naują aplinką

Įsigijus „Customer Insights” prenumeratos licenciją, „Microsoft 365” nuomotojo visuotinis administratorius gauna elektroninį laišką, kuris paragina juos sukurti aplinką. Eikite į [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start), kad pradėtumėte. 

Interaktyviuoju būdu galima atlikti visus veiksmus, kurių reikia norint surinkti visą reikiamą informaciją apie naują aplinką. Norint kurti [arba valdyti aplinkas](permissions.md), reikia administratoriaus teisių auditorijos įžvalgų srityje.

1. Auditorijos įžvalgose atidarykite aplinkos parinktuvą ir pažymėkite **+ Naujas**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Rinkitės aplinkos parinkiklį.":::

1. Vykdykite interaktyviąją patirtį, iš apibūdintą tolesniuose skyriuose.

### <a name="step-1-provide-environment-information"></a>1 žingsnis: pateikite informaciją apie aplinką

Pagrindinės **informacijos žingsnyje** pasirinkite, ar norite kurti aplinką nuo pradžių, ar [kopijuokite duomenis iš kitos aplinkos](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Naujos Customer Insights aplinkos sukūrimo dialogo langas.":::

Nurodykite toliau pateiktą informaciją.
   - **Pavadinimas**: Šios aplinkos pavadinimas. Šis laukas jau užpildytas, jei kopijuojate esamą aplinką, tačiau jį galite keisti.
   - **Pasirinkite savo verslą**: pasirinkite pagrindinę naujos aplinkos auditoriją. Galite dirbti su individualiais atsiliepimais (B 2 C) arba [verslo klientais](work-with-business-accounts.md) (B2B).
   - **Tipas**: pasirinkite, ar norite sukurti gamybos, ar smėlio dėžės aplinką. Smėlio dėžės aplinkos neleidžia suplanuoto duomenų atnaujinimo ir yra skirtos išankstiniam diegimui ir testavimui. Smėlio dėžės aplinkos naudoja tą pačią pagrindinę auditoriją kaip ir dabar pažymėta gamybos aplinka.
   - **Sritis**: sritis, kurioje įdiegta ir teikiama ši paslauga.

### <a name="step-2-configure-data-storage"></a>2 žingsnis: konfigūruokite duomenų saugyklą

Atlikdami **duomenų saugyklos** veiksmą pasirinkite, kur norite saugoti duomenis iš auditorijos įžvalgų.

Galėsite pasirinkti dvi galimybes: **„Customer Insights" saugyklą** „Azure Data Lake", kurią valdo klientų įžvalgų komanda ir **Azure Data Lake Storage** (komanda ir „Azure Data Lake Storage“). Pagal numatytuosius parametrus, pasirenkama „Customer Insights“ saugykla.

:::image type="content" source="media/data-storage-environment.png" alt-text="Pasirinkite, „Azure Data Lake Storage“, kurioje norite saugoti auditorijos įžvalgų duomenis.":::

Įrašydami duomenis į, sutinkate, kad duomenys bus perduoti ir saugomi tinkamoje geografinėje to „Azure Data Lake Storage“ „Azure" saugyklos paskyros vietoje. Ši vieta gali skirtis nuo to, kurioje vietoje saugomi duomenys „Dynamics 365 Customer Insights“. Sužinokite daugiau [„Microsoft“ patikimumo centre](https://www.microsoft.com/trust-center).

> [!NOTE]
> „Customer Insights“ dabar palaiko šiuos dalykus:
> - Iš duomenų srautų, „Power BI“ saugomų valdomojoje „Microsoft Dataverse“ „Data Lake“ saugomų objektų.  
> - „Azure Data Lake Storage" paskyrų abonementai iš to paties „Azure" regiono, kurį pasirinkote kurdami aplinką.
> - „Azure Data Lake Storage“ abonementai, kurių *hierarchinė vardų sritis* įjungta.

Galite „Azure Data Lake Storage“ pasirinkti iš išteklių pagrįstą parinktį ir prenumerata pagrįstą autentifikavimo parinktį. Dėl išsamesnės informacijos, žr. [Prisijungti prie „Azure Data Lake Storage“ paskyros su „Azure“ pagrindinėmis paslaugomis](connect-service-principal.md). Konteinerio **pavadinimas** bus ir jo keisti nebus `customerinsights` galima.

Kai sistema apdoroja, pvz., užbaigė duomenų sugadinimą, sistema sukuria atitinkamus aplankus jūsų nurodytame saugyklos abonemente. Duomenų failai ir *model.json* failai yra kuriami ir įtraukiami į aplankus pagal proceso pavadinimą.

Jei sukuriate kelias „Customer Insights“ aplinkas ir pasirenkate įrašyti išvesties objektus iš šių aplinkos į saugyklos klientą, „Customer Insights“ sukuria atskirus kiekvienos aplinkos aplankus `ci_environmentID` konteineryje.

### <a name="step-3-connect-to-microsoft-dataverse"></a>3 žingsnis: Prisijungti prie „Microsoft Dataverse“
   
Šis **Microsoft Dataverse** veiksmas leidžia „Customer Insights“ susieti su „Dataverse“ aplinka.

Jei norite [naudoti iš anksto anksto prognozė modelius](predictions-overview.md#out-of-box-models) konfigūruokite duomenų bendrinimą su „Dataverse“. Arba galite įjungti duomenų nurijimas iš vietinis šaltinių, pateikdami jūsų „Microsoft Dataverse“ organizacijos administruojami aplinkos URL. Pasirinkite **Įjungti duomenų bendrinimą**, jei „Customer Insights“ išvesties duomenis norite bendrinti su „Dataverse“ valdomu „Data Lake“.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Konfigūravimo parinktys duomenų bendrinimui su Microsoft Dataverse įjungti.":::

> [!NOTE]
> Jūsų „Customer Insights“ aplinkos konfigūracija nepalaiko šių duomenų bendrinimo scenarijų:
> - Jei visus duomenis įrašysite savo, negalėsite įjungti bendro duomenų bendrinimo su valdomojo „Azure Data Lake Storage“ duomenų „Dataverse“ sutvarkytas „Data Lake“.
> - Įjungę duomenų bendrinimą su „Dataverse“, negalėsite kurti prognozuojamų [arba trūkstamų objekto reikšmių](predictions.md).

### <a name="step-4-finalize-the-settings"></a>4 veiksmas: užbaikite nustatymus

Peržiūros **žingsnyje** pereikite prie visų nurodytų parametrų. Baigę viską, pasirinkite **Kurti** ir nustatykite aplinką. 

Taip pat daugumą parametrų galite keisti vėliau. Daugiau informacijos žr. [Aplinkų valdymas](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Darbas su nauja aplinka

Peržiūrėkite šiuos straipsnius, kad būtų galima pradėti konfigūruoti „Customer Insights“: 

- [Įtraukite daugiau vartotojų ir priskirkite teises](permissions.md).
- [Įtraukite savo duomenų šaltinius](data-sources.md) ir paleiskite juos per [duomenų suvienodinimo procesą](data-unification.md), kad gautumėte [suvienodintus klientų profilius](customer-profiles.md).
- [Papildykite vieninguosius klientų profilius](enrichment-hub.md) arba [paleiskite numatomus modelius](predictions-overview.md).
- [Kurkite segmentus](segments.md), kad sugrupuotumėte klientus ir [priemones](measures.md) KPI peržiūrai.
- [Nustatykite ryšius](connections.md) ir [eksportavimus](export-destinations.md), kad kitose taikomosiose programose būtų apdorojami antriniai duomenų rinkiniai.
