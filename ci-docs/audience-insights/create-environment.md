---
title: Kurti aplinkas „Customer Insights“
description: Veiksmai, norint kurti aplinkas su licencijuota „Dynamics 365 Customer Insights“.
ms.date: 03/28/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: a538237322615f69f0a5cb43d394275bf79af00b
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491923"
---
# <a name="create-an-environment-in-audience-insights"></a>Kurti aplinką publikos auditorijos įžvalgose

Šiame straipsnyje paaiškinta, kaip sukurti naują aplinką jūsų organizacijai įsigijus „Dynamics 365 Customer Insights” prenumeratą. 

Organizacijos gali sukurti *dvi* aplinkas kiekvienai „Customer Insights“ licencijai. Jei jūsų organizacija įsigyja daugiau nei vieną licenciją, [kreipkitės į palaikymo komandą](https://go.microsoft.com/fwlink/?linkid=2079641) ir padidinkite galimų aplinkos sąlygų skaičių. Norėdami gauti daugiau informacijos apie pajėgumą ir papildinio pajėgumą, atsisiųskite [„Dynamics 365” licencijavimo vadovą](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Jei norite išbandyti paslaugą, žr. [Bandomosios versijos aplinkos nustatyti](../trial-signup.md).

## <a name="create-a-new-environment"></a>Kurti naują aplinką

Įsigijęs "Customer Insights" prenumeratos licenciją, visuotinis nuomotojo Microsoft 365 administratorius gauna el. laišką, kviečiantį kurti aplinką. Eikite į [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start), kad pradėtumėte. 

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
> - Azure Data Lake Storage abonementai, kurie yra Gen2 ir kuriuose *įgalinta hierarchinė vardų sritis*. "Azure Data Lake Gen1" saugyklos abonementai nepalaikomi.

Galite „Azure Data Lake Storage“ pasirinkti iš išteklių pagrįstą parinktį ir prenumerata pagrįstą autentifikavimo parinktį. Dėl išsamesnės informacijos, žr. [Prisijungti prie „Azure Data Lake Storage“ paskyros su „Azure“ pagrindinėmis paslaugomis](connect-service-principal.md). Konteinerio **pavadinimas** bus ir jo keisti nebus `customerinsights` galima.

Kai sistema apdoroja, pvz., užbaigė duomenų sugadinimą, sistema sukuria atitinkamus aplankus jūsų nurodytame saugyklos abonemente. Duomenų failai ir *model.json* failai yra kuriami ir įtraukiami į aplankus pagal proceso pavadinimą.

Jei sukuriate kelias „Customer Insights“ aplinkas ir pasirenkate įrašyti išvesties objektus iš šių aplinkos į saugyklos klientą, „Customer Insights“ sukuria atskirus kiekvienos aplinkos aplankus `ci_environmentID` konteineryje.

### <a name="step-3-connect-to-microsoft-dataverse"></a>3 žingsnis: Prisijungti prie „Microsoft Dataverse“
   
Šis **Microsoft Dataverse** veiksmas leidžia „Customer Insights“ susieti su „Dataverse“ aplinka.

Pateikite savo Microsoft Dataverse aplinką duomenims (profiliams ir įžvalgoms) bendrinti su verslo programomis, pagrįstomis Dataverse, pvz., "Dynamics 365 Marketing" arba modeliu pagrįstomis programomis programoje Power Apps. Palikite šį lauką tuščią, jei neturite savo Dataverse aplinkos, ir mes ją suteiksime jums.

Prisijungimas prie savo Dataverse aplinkos taip pat leidžia nuryti [duomenis iš vietinis duomenų šaltinių, naudojant Power Platform duomenų srautus ir šliuzus](data-sources.md#add-data-from-on-premises-data-sources). Taip pat galite naudoti [prognozė modelius](predictions-overview.md?tabs=b2c#out-of-box-models) neprisijungdami prie Dataverse aplinkos.

> [!IMPORTANT]
> 1. Klientų įžvalgos ir Dataverse turi būti tame pačiame regione, kad būtų galima dalytis duomenimis.
> 1. Aplinkoje turite atlikti pasaulinio administratoriaus Dataverse vaidmenį. Patikrinkite, ar ši [Dataverse aplinka susieta su](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) tam tikromis saugos grupėmis, ir įsitikinkite, kad esate įtraukti į tas saugos grupes.
> 1. Jokia esama "Customer Insights" aplinka dar nėra susieta su šia Dataverse aplinka. Sužinokite, [kaip pašalinti esamą ryšį su Dataverse aplinka](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="duomenų bendrinimas su Microsoft Dataverse automatiniu įgalintu neto naujiems egzemplioriams.":::

Daugiau informacijos apie duomenų bendrinimo įgalinimą Microsoft Dataverse su savo Azure Data Lake Storage duomenimis ieškokite [Connect to Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Jūsų „Customer Insights“ aplinkos konfigūracija nepalaiko šių duomenų bendrinimo scenarijų:
- Įjungę duomenų bendrinimą su „Dataverse“, negalėsite kurti prognozuojamų [arba trūkstamų objekto reikšmių](predictions.md).

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
