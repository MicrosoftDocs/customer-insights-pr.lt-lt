---
title: Aplinkų kūrimas ir valdymas
description: Sužinokite, kaip prisijungti prie paslaugų ir kaip valdyti aplinkas.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: ba29bcd173e615e544bd10e69043f310c009eb47
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/29/2022
ms.locfileid: "8492014"
---
# <a name="manage-environments"></a>Aplinkų valdymas

## <a name="switch-environments"></a>Perjungti aplinką

Norėdami keisti aplinkas, viršutiniame dešiniajame puslapio kampe pasirinkite valdiklį **Aplinka**.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Aplinkų perjungimo valdiklio ekrano kopija.":::

Administratoriai gali [kurti](create-environment.md) ir valdyti aplinkas.

## <a name="edit-an-existing-environment"></a>Esamos aplinkos redagavimas

Galite redaguoti kai kurią esamos aplinkos informaciją.

1.  Programos antraštėje pasirinkite **Aplinkos** parinkėją.

2.  Pasirinkite **Redagavimo** piktogramą.

3. Lauke **Redaguoti aplinką** galite atnaujinti aplinkos parametrus.

Daugiau informacijos apie aplinkos parametrus žr. [Naujos aplinkos kūrimas](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Prisijungti prie „Microsoft Dataverse“
   
Šis **Microsoft Dataverse** veiksmas leidžia „Customer Insights“ susieti su „Dataverse“ aplinka. 

Pateikite savo Microsoft Dataverse aplinką duomenims (profiliams ir įžvalgoms) bendrinti su verslo programomis, pagrįstomis Dataverse, pvz., "Dynamics 365 Marketing" arba modeliu pagrįstomis programomis programoje Power Apps.

Jei norite [naudoti iš anksto anksto prognozė modelius](predictions-overview.md#out-of-box-models) konfigūruokite duomenų bendrinimą su „Dataverse“. Arba galite įjungti duomenų nurijimas iš vietinis šaltinių, pateikdami jūsų „Microsoft Dataverse“ organizacijos administruojami aplinkos URL.

Įgalinus dalijimąsi Microsoft Dataverse duomenimis pažymėjus duomenų bendrinimo žymės langelį, bus suaktyvintas vienkartinis visiškas duomenų šaltinių ir visų kitų procesų atnaujinimas.

> [!IMPORTANT]
> 1. Klientų įžvalgos ir Dataverse turi būti tame pačiame regione, kad būtų galima dalytis duomenimis.
> 1. Aplinkoje turite atlikti pasaulinio administratoriaus Dataverse vaidmenį. Patikrinkite, ar ši [Dataverse aplinka susieta su](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) tam tikromis saugos grupėmis, ir įsitikinkite, kad esate įtraukti į tas saugos grupes.
> 1. Jokia esama "Customer Insights" aplinka dar nėra susieta su šia Dataverse aplinka. Sužinokite, [kaip pašalinti esamą ryšį su Dataverse aplinka](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Konfigūravimo parinktys duomenų bendrinimui su Microsoft Dataverse įjungti.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Įgalinti dalijimąsi Dataverse duomenimis iš savo Azure Data Lake Storage (Peržiūra)

Jei jūsų aplinka sukonfigūruota naudoti savo Azure Data Lake Storage "Customer Insights" duomenims saugoti, įgalinkite dalijimąsi duomenimis su Microsoft Dataverse papildoma konfigūracija.

1. Sukurkite dvi saugos grupes savo "Azure" prenumeratoje - vieną **skaitytuvo** saugos grupę ir vieną **bendraautorių** saugos grupę ir nustatykite Microsoft Dataverse paslaugą kaip abiejų saugos grupių savininką.
2. Tvarkykite prieigos teisių sąrašą (ACL) "CustomerInsights" konteineryje savo saugyklos paskyroje per šias saugos grupes. Microsoft Dataverse Įtraukite paslaugą ir visas Dataverse pagrįstas verslo taikomąsias programas, pvz., "Dynamics 365 Marketing", į skaitytuvo **saugos** grupę, kurioje **yra tik** skaitymo teisės. Įtraukite *tik* "Customer Insights" taikomąją programą į **"Contributor"** saugos grupę, kad suteiktumėte **ir skaitymo, ir rašymo** teises rašyti profilius ir įžvalgas.
   
#### <a name="prerequisites"></a>Būtinosios sąlygos

Norėdami vykdyti "PowerShell" scenarijus, turite importuoti šiuos tris modulius. 

1. Įdiekite naujausią "PowerShell for Graph" versiją [Azure Active Directory](/powershell/azure/active-directory/install-adv2).
   1. Savo kompiuteryje pasirinkite klaviatūroje pasirinkite "Windows" klavišą ir ieškokite **Windows PowerShell** bei pasirinkite **Paleisti kaip administratorių**.
   1. „PowerShell“ atsivėrusiame lange įveskite `Install-Module AzureAD`.
2. Importuokite tris modulius.
    1. "PowerShell" lange įveskite `Install-Module -Name Az.Accounts` ir atlikite veiksmus. 
    1. Pakartokite ir `Install-Module -Name Az.Resources``Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Konfigūravimo veiksmai

1. Atsisiųskite du "PowerShell" scenarijus, kuriuos reikia paleisti iš mūsų inžinieriaus "GitHub" [repo](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Norint paleisti šį "PowerShell" scenarijų, reikia *nuomotojo administratoriaus* teisių. 
       - Šis "PowerShell" scenarijus sukuria dvi "Azure" prenumeratos saugos grupes. Vienas skirtas "Reader" grupei, o kitas - "Contributor" grupei ir tarnaus Microsoft Dataverse kaip abiejų šių saugos grupių savininkas.
       - Vykdykite šį "PowerShell" scenarijų sistemoje "Windows PowerShell", pateikdami "Azure" prenumeratos ID, kuriame yra jūsų Azure Data Lake Storage. Atidarykite "PowerShell" scenarijų rengyklėje, kad peržiūrėtumėte papildomą informaciją ir įdiegtą logiką.
       - Įrašykite abi šio scenarijaus sugeneruotas saugos grupės ID reikšmes, nes jas naudosime scenarijuje `ByolSetup.ps1`.
       
        > [!NOTE]
        > Nuomotojo saugos grupės kūrimą galima išjungti. Tokiu atveju reikės rankinio nustatymo ir jūsų Azure AD administratorius turėtų įgalinti [saugos grupės kūrimą](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Norint paleisti šį scenarijų, reikia *saugyklos blob duomenų savininko* teisių saugyklos abonemento / konteinerio lygiu arba šis scenarijus sukurs jums vieną. Sėkmingai paleidus scenarijų, vaidmenų priskyrimą galima pašalinti rankiniu būdu.
        - Šis "PowerShell" scenarijus prideda reikiamą tarnybos ir bet kokių Microsoft Dataverse verslo programų prieigos kontrolę (RBAC).Dataverse Ji taip pat atnaujina prieigos teisių sąrašą (ACL) "CustomerInsights" konteineryje, skirtame saugos grupėms, sukurtoms naudojant scenarijų `CreateSecurityGroups.ps1`. Bendraautorių grupė turės *rwx* leidimą, o skaitytojų grupė turės *tik r-x* teises.
        - Vykdykite šį "PowerShell" scenarijų sistemoje "Windows PowerShell" pateikdami "Azure" prenumeratos ID, kuriame yra jūsų Azure Data Lake Storage, saugyklos abonemento pavadinimas, išteklių grupės pavadinimas ir skaitytuvo bei bendraautorių saugos grupės ID reikšmės. Atidarykite "PowerShell" scenarijų rengyklėje, kad peržiūrėtumėte papildomą informaciją ir įdiegtą logiką.
        - Sėkmingai paleidus scenarijų nukopijuokite išvesties eilutę. Išvesties eilutė atrodo taip: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Įveskite išvesties eilutę, nukopijuotą iš viršaus, į **aplinkos konfigūravimo veiksmo, skirto**.Microsoft Dataverse

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigūravimo parinktys, leidžiančios bendrinti duomenis iš savo Azure Data Lake Storage su Microsoft Dataverse.":::

Jūsų „Customer Insights“ aplinkos konfigūracija nepalaiko šių duomenų bendrinimo scenarijų:
- Įjungę duomenų bendrinimą su „Dataverse“, negalėsite kurti prognozuojamų [arba trūkstamų objekto reikšmių](predictions.md).
- Jei įgalinsite duomenų bendrinimą, Dataverse negalėsite peržiūrėti jokių pasirinktinių "PowerBI Embedded" ataskaitų "Customer Insights" aplinkoje.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Esamo ryšio su Dataverse aplinka šalinimas

Jungiantis prie Dataverse aplinkos, klaidos pranešimas **Ši CDS organizacija jau pridėta prie kito "Customer Insights" egzemplioriaus**, o tai reiškia, kad Dataverse aplinka jau naudojama "Customer Insights" aplinkoje. Esamą ryšį galite pašalinti kaip visuotinį aplinkos administratorių Dataverse. Tai gali užtrukti kelias valandas užpildyti pakeitimus.

1. Eikite į [Power Apps](https://make.powerapps.com).
1. Pasirinkite aplinką iš aplinkos parinkiklio.
1. Eikite į **sprendimus**
1. Pašalinkite arba panaikinkite sprendimą, pavadintą **Dynamics 365 Customer Insights Kliento kortelės papildinys (Peržiūra)**.

OR 

1. Atverkite savo Dataverse aplinką.
1. Eikite į **Išplėstiniai parametraiSolutions** > **·**.
1. Pašalinkite **"CustomerInsightsCustomerCard"** sprendimą.

## <a name="copy-the-environment-configuration"></a>Aplinkos konfigūracijos kopijavimas

Kaip administratorius galite pasirinkti kopijuoti konfigūraciją iš esamos aplinkos, kai kuriate naują. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Aplinkos parametrų parinkčių ekrano kopija.":::

Matysite visų jūsų organizacijoje pasiekiamų aplinkų sąrašą, iš kurių galima kopijuoti duomenis.

Kopijuojami šie konfigūracijos parametrai:

- Įtrauktas / importuotas duomenų šaltinis
- Duomenų sujungimo (susiejimo, atitikimo, suliejimo) konfigūracija
- Segmentai
- Matavimai
- Ryšiai
- Veiklos
- Paieškos ir filtravimo rodyklė
- Eksportavimo paskirties vietos
- Suplanuotas atnaujinimas
- Papildymai
- Modelio valdymas
- Vaidmenų priskyrimai

## <a name="set-up-a-copied-environment"></a>Nukopijuotos aplinkos nustatymas

Kai kopijuojate aplinkos konfigūraciją, šie duomenys *nėra* kopijuojami:

- Klientų profiliai.
- Duomenų šaltinio kredencialai. Turėsite pateikti kiekvieno duomenų šaltinio kredencialus ir rankiniu būdu atnaujinti duomenų šaltinius.
- Duomenų šaltiniai iš bendrojo duomenų modelio aplanko ir „Dataverse“ valdomo „data lake“. Šiuos duomenų šaltinius turėsite kurti rankiniu būdu tuo pačiu pavadinimu kaip ir šaltinio aplinka.
- Ryšio paslaptys, naudojamos eksportui ir praturtėjimui. Jūs turite iš naujo pripažinti ryšius ir tada iš naujo suaktyvinti sodrinimą ir eksportą. 

Kai kopijuojate aplinką, pamatysite patvirtinimo pranešimą, kad sukurta nauja aplinka. Pasirinkite **Eiti į duomenų šaltinius**, kad peržiūrėtumėte duomenų šaltinių sąrašą.

Visi duomenų šaltiniai rodys būseną **Reikia kredencialų**. Redaguokite duomenų šaltinius ir įveskite kredencialus, kad juos atnaujintumėte.

:::image type="content" source="media/data-sources-copied.png" alt-text="Duomenų šaltinių, kurie buvo nukopijuoti ir kuriems reikalingas autentifikavimas, sąrašas.":::

Atnaujinę duomenų šaltinius, eikite į **Duomenys** > **Suvienodinti**. Čia rasite parametrus iš šaltinio aplinkos. Jei reikia, redaguokite juos arba pasirinkite **Vykdyti**, kad pradėtumėte duomenų sujungimo procesą ir sukurtumėte bendrąjį kliento objektą.

Kai duomenų sujungimas baigtas, eikite į **Priemonės** ir **Segmentai**, kad jie būtų atnaujinti.

Prieš iš naujo suaktyvindami eksportą ir sodrinimą, eikite į **"AdminConnections** > **·**", kad iš naujo patvirtintumėte ryšius naujoje aplinkoje.

## <a name="change-the-owner-of-an-environment"></a>Aplinkos savininko keitimas

Nors keli vartotojai gali turėti administratoriaus teises "Customer Insights", tik vienas vartotojas yra aplinkos savininkas. Pagal numatytuosius nustatymus administratorius iš pradžių sukuria aplinką. Kaip aplinkos administratorius, galite priskirti nuosavybę kitam vartotojui, turinčiam administratoriaus teises.

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite **Redagavimo** piktogramą.

1. Lauke Aplinkos redagavimas **eikite** **į veiksmą Pagrindinė informacija**.

1. **Lauke Aplinkos savininko** keitimas pasirinkite naują aplinkos savininką.  

1. Pasirinkite **Peržiūra ir pabaiga**, tada **Naujinti**, kad pritaikytumėte keitimus. 

## <a name="claim-ownership-of-an-environment"></a>Reikalauti nuosavybės teisės į aplinką

Jei aplinkos savininkas palieka organizaciją arba jo vartotojo abonementas panaikinamas, aplinka neturės savininko. Vartotojas, turintis administratoriaus teises, gali reikalauti nuosavybės teisių ir tapti nauju savininku. Jie gali ir toliau valdyti aplinką arba [pakeisti nuosavybę į kitą administratorių](#change-the-owner-of-an-environment). 

Norėdami reikalauti nuosavybės, pasirinkite mygtuką **Paimti nuosavybę**, kuris rodomas kiekvieno "Customer Insights" puslapio viršuje, kai pradinis savininkas paliko organizaciją.

## <a name="reset-an-existing-environment"></a>Paleiskite iš naujo esamą aplinką

Kaip aplinkos savininkas, galite iš naujo nustatyti aplinką į tuščią būseną, jei norite panaikinti visas konfigūracijas ir pašalinti nurytus duomenis.

1.  Programos antraštėje pasirinkite **Aplinkos** parinkėją. 

2.  Pažymėkite aplinką, kurią norite nustatyti iš naujo, ir pažymėkite daugtaškį (**...**). 

3. Pasirinkite parinktį **Nustatyti iš naujo**. 

4.  Šio panaikinimo patvirtinimui, įveskite aplinkos pavadinimą ir pasirinkite **Paleisti iš naujo**.

## <a name="delete-an-existing-environment"></a>Esamos aplinkos naikinimas

Kaip aplinkos savininkas, galite panaikinti savo administruojamą aplinką.

1.  Programos antraštėje pasirinkite **Aplinkos** parinkėją.

2.  Pažymėkite aplinką, kurią norite nustatyti iš naujo, ir pažymėkite daugtaškį (**...**). 

3. Pasirinkite parinktį **Naikinti**. 

4.  Norėdami patvirtinti panaikinimą, įveskite aplinkos pavadinimą ir pasirinkite **Naikinti**.

> [!NOTE]
> Aplinkos naikinimas nepašalina susiejimo su Dataverse aplinka. Sužinokite, [kaip pašalinti esamą ryšį su Dataverse aplinka](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
