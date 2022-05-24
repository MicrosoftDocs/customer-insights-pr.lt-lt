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
ms.openlocfilehash: 599cbaf4e19c3a7331e92bfc54c701fefe6c69b3
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741051"
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

Įgalinus duomenų bendrinimą pažymėjus Microsoft Dataverse žymės langelį duomenų bendrinimas, vieną kartą bus atnaujintas visas jūsų duomenų šaltinių ir visų kitų procesų atnaujinimas.

> [!IMPORTANT]
> 1. "Customer Insights" ir Dataverse turi būti tame pačiame regione, kad būtų galima bendrinti duomenis.
> 1. Turite atlikti visuotinį administratoriaus vaidmenį Dataverse aplinkoje. Patikrinkite, ar ši [Dataverse aplinka susieta su](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) tam tikromis saugos grupėmis, ir įsitikinkite, kad esate įtraukti į tas saugos grupes.
> 1. Jokia esama "Customer Insights" aplinka dar nesusieta su šia Dataverse aplinka. Sužinokite, kaip pašalinti [esamą ryšį su Dataverse aplinka](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Konfigūravimo parinktys duomenų bendrinimui su Microsoft Dataverse įjungti.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Įgalinti duomenų bendrinimą su Dataverse savo Azure Data Lake Storage (Peržiūra)

Jei jūsų aplinka sukonfigūruota naudoti savo Azure Data Lake Storage "Customer Insights" duomenims saugoti, įgalindami duomenų bendrinimą su Microsoft Dataverse tam tikra papildoma konfigūracija.

1. "Azure" prenumeratoje sukurkite dvi saugos grupes – vieną **"Reader"** saugos grupę ir vieną **bendraautorių** saugos grupę ir nustatykite paslaugą Microsoft Dataverse kaip abiejų saugos grupių savininkę.
2. Tvarkykite "Access Control List" (ACL) savo saugyklos abonemento konteineryje CustomerInsights per šias saugos grupes. Įtraukite paslaugą Microsoft Dataverse ir visas Dataverse verslo programas, pvz., "Dynamics 365 Marketing", į **"Reader"** saugos grupę su **tik** skaitymo teisėmis. Įtraukite *tik* "Customers Insights" taikomąją programą į bendraautorių **saugos** grupę, kad suteiktumėte ir **skaitymo, ir rašymo** teises rašyti profilius ir įžvalgas.
   
#### <a name="prerequisites"></a>Būtinosios sąlygos

Norėdami vykdyti "PowerShell" scenarijus, turite importuoti šiuos tris modulius. 

1. Įdiekite naujausią "PowerShell for Graph [Azure Active Directory" versiją](/powershell/azure/active-directory/install-adv2).
   1. Savo kompiuteryje pasirinkite klaviatūroje pasirinkite "Windows" klavišą ir ieškokite **Windows PowerShell** bei pasirinkite **Paleisti kaip administratorių**.
   1. „PowerShell“ atsivėrusiame lange įveskite `Install-Module AzureAD`.
2. Importuokite tris modulius.
    1. "PowerShell" lange įveskite `Install-Module -Name Az.Accounts` ir atlikite veiksmus. 
    1. `Install-Module -Name Az.Resources` Pakartokite ir `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Konfigūravimo veiksmai

1. Atsisiųskite du "PowerShell" scenarijus, kuriuos reikia paleisti iš mūsų inžinieriaus "GitHub" [repo](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Norint paleisti šį "PowerShell" scenarijų, reikia *nuomotojo administratoriaus* teisių. 
       - Šis "PowerShell" scenarijus sukuria dvi saugos grupes "Azure" prenumeratoje. Vienas skirtas "Reader" grupei, o kitas – bendraautorių grupei ir teiks Microsoft Dataverse paslaugas kaip abiejų šių saugos grupių savininkas.
       - Vykdykite šį "PowerShell" scenarijų naudodami "Windows PowerShell" pateikdami "Azure" prenumeratos ID, kuriame yra jūsų Azure Data Lake Storage. Atidarykite "PowerShell" scenarijų redaktoriuje, kad peržiūrėtumėte papildomą informaciją ir įdiegtą logiką.
       - Įrašykite abi saugos grupės ID reikšmes, sugeneruotas šio scenarijaus, nes jas naudosime scenarijuje `ByolSetup.ps1`.
       
        > [!NOTE]
        > Saugos grupės kūrimas gali būti išjungtas nuomotoje. Tokiu atveju reikės neautomatinės sąrankos, o jūsų Azure AD administratorius turėtų įgalinti [saugos grupės kūrimą](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Norint paleisti šį scenarijų, reikia *saugyklos BLOB duomenų savininko* teisių saugyklos abonemento / konteinerio lygiu, arba šis scenarijus sukurs jums. Sėkmingai paleidus scenarijų, jūsų vaidmens priskyrimą galima pašalinti rankiniu būdu.
        - Šis "PowerShell" scenarijus prideda reikiamą "tole" pagrįstą prieigos kontrolę (RBAC) paslaugai Microsoft Dataverse ir visoms Dataverse verslo programoms. Ji taip pat atnaujina su scenarijumi sukurtų saugos grupių prieigos kontrolės sąrašą (ACL) kliento duomenų saugyklų `CreateSecurityGroups.ps1` konteineryje CustomerInsights. Bendraautorių grupė turės *rwx* leidimą, o skaitytojų grupė turės *tik r-x* teises.
        - Vykdykite šį "PowerShell" scenarijų sistemoje "Windows PowerShell" pateikdami "Azure" prenumeratos ID, kuriame yra jūsų Azure Data Lake Storage, saugyklos abonemento pavadinimas, išteklių grupės pavadinimas ir skaitytojo bei bendraautoriaus saugos grupės ID reikšmės. Atidarykite "PowerShell" scenarijų redaktoriuje, kad peržiūrėtumėte papildomą informaciją ir įdiegtą logiką.
        - Sėkmingai paleidę scenarijų nukopijuokite išvesties eilutę. Išvesties eilutė atrodo taip: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Įveskite išeigos eilutę, nukopijuotą iš viršaus, **į** aplinkos konfigūravimo veiksmo, skirto Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigūracijos parinktys, skirtos įgalinti duomenų bendrinimą iš savo Azure Data Lake Storage su Microsoft Dataverse.":::

Jūsų „Customer Insights“ aplinkos konfigūracija nepalaiko šių duomenų bendrinimo scenarijų:
- Įjungę duomenų bendrinimą su „Dataverse“, negalėsite kurti prognozuojamų [arba trūkstamų objekto reikšmių](predictions.md).
- Jei įgalinsite duomenų bendrinimą su Dataverse, negalėsite peržiūrėti jokių pasirinktinių "PowerBI Embedded" ataskaitų "Customer Insights" aplinkoje.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Esamo ryšio su Dataverse aplinka šalinimas

Jungiantis prie Dataverse aplinkos, klaidos pranešimas **Ši KOMPAKTINIŲ diskų organizacija jau pridėta prie kito "Customer Insights" egzemplioriaus** reiškia, kad Dataverse aplinka jau naudojama "Customer Insights" aplinkoje. Galite pašalinti esamą ryšį kaip visuotinį aplinkos administratorių Dataverse. Tai gali užtrukti kelias valandas, kad būtų galima užpildyti pakeitimus.

1. Eikite į [Power Apps](https://make.powerapps.com).
1. Pasirinkite aplinką iš aplinkos parinkiklio.
1. Eikite į **sprendimus**
1. Pašalinkite arba panaikinkite sprendimą, pavadintą **Dynamics 365 Customer Insights Kliento kortelės priedu (peržiūra)**.

OR 

1. Atidarykite savo Dataverse aplinką.
1. Eikite į **Išplėstiniai nustatymų** > **sprendimai**.
1. **Pašalinkite CustomerInsightsCustomerCard** sprendimą.

## <a name="copy-the-environment-configuration"></a>Aplinkos konfigūracijos kopijavimas

Kaip administratorius galite pasirinkti kopijuoti konfigūraciją iš esamos aplinkos, kai kuriate naują. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Aplinkos parametrų parinkčių ekrano kopija.":::

Matysite visų jūsų organizacijoje pasiekiamų aplinkų sąrašą, iš kurių galima kopijuoti duomenis.

Kopijuojami šie konfigūracijos parametrai:

- Įtrauktas / importuotas duomenų šaltinis
- Duomenų suvienijimo konfigūracija
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

Kopijuojant aplinkos konfigūraciją, šie duomenys *nekopijuojami*:

- Klientų profiliai.
- Duomenų šaltinio kredencialai. Turėsite pateikti kiekvieno duomenų šaltinio kredencialus ir rankiniu būdu atnaujinti duomenų šaltinius.
- Duomenų šaltiniai iš bendrojo duomenų modelio aplanko ir „Dataverse“ valdomo „data lake“. Šiuos duomenų šaltinius turėsite kurti rankiniu būdu tuo pačiu pavadinimu kaip ir šaltinio aplinka.
- Ryšio paslaptys, naudojamos eksportui ir sodrinimui. Jūs turite iš naujo atkurti ryšius ir tada iš naujo suaktyvinti sodrinimą ir eksportą. 

Kai kopijuojate aplinką, pamatysite patvirtinimo pranešimą, kad sukurta nauja aplinka. Pasirinkite **Eiti į duomenų šaltinius**, kad peržiūrėtumėte duomenų šaltinių sąrašą.

Visi duomenų šaltiniai rodys būseną **Reikia kredencialų**. Redaguokite duomenų šaltinius ir įveskite kredencialus, kad juos atnaujintumėte.

:::image type="content" source="media/data-sources-copied.png" alt-text="Duomenų šaltinių, kurie buvo nukopijuoti ir kuriems reikalingas autentifikavimas, sąrašas.":::

Atnaujinę duomenų šaltinius, eikite į **Duomenys** > **Suvienodinti**. Čia rasite parametrus iš šaltinio aplinkos. Jei reikia, redaguokite juos arba pasirinkite **Vykdyti**, kad pradėtumėte duomenų sujungimo procesą ir sukurtumėte bendrąjį kliento objektą.

Kai duomenų sujungimas baigtas, eikite į **Priemonės** ir **Segmentai**, kad jie būtų atnaujinti.

Prieš iš naujo suaktyvindami eksportą ir praturtinimus, eikite į **Administratoriaus** > **ryšiai**, kad iš naujo atkurtumėte ryšius naujoje aplinkoje.

## <a name="change-the-owner-of-an-environment"></a>Aplinkos savininko keitimas

Nors keli vartotojai gali turėti administratoriaus teises programoje "Customer Insights", tik vienas vartotojas yra aplinkos savininkas. Pagal numatytuosius nustatymus iš pradžių aplinką sukuria administratorius. Kaip aplinkos administratorius, galite priskirti nuosavybę kitam vartotojui, turinčiam administratoriaus teises.

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite **Redagavimo** piktogramą.

1. **Lauke Redaguoti aplinką** eikite į veiksmą **Pagrindinė informacija**.

1. Lauke **Keisti aplinkos** savininką pasirinkite naują aplinkos savininką.  

1. Pasirinkite **Peržiūra ir baigti**, tada **Naujinti**, kad pritaikytumėte keitimus. 

## <a name="claim-ownership-of-an-environment"></a>Reikalauti nuosavybės teisės į aplinką

Jei aplinkos savininkas palieka organizaciją arba jo vartotojo abonementas panaikinamas, aplinka neturės savininko. Vartotojas, turintis administratoriaus teises, gali reikalauti nuosavybės teisės ir tapti naujuoju savininku. Jie gali ir toliau valdyti aplinką arba [pakeisti nuosavybę į kitą administratorių](#change-the-owner-of-an-environment). 

Norėdami reikalauti nuosavybės teisės, pasirinkite **mygtuką Paimti nuosavybę**, kuris rodomas kiekvieno "Customer Insights" puslapio viršuje, kai pradinis savininkas paliko organizaciją.

## <a name="reset-an-existing-environment"></a>Paleiskite iš naujo esamą aplinką

Kaip aplinkos savininkas, galite iš naujo nustatyti aplinką į tuščią būseną, jei norite panaikinti visas konfigūracijas ir pašalinti prarytus duomenis.

1.  Programos antraštėje pasirinkite **Aplinkos** parinkėją. 

2.  Pažymėkite aplinką, kurią norite nustatyti iš naujo, ir pažymėkite daugtaškį (**...**). 

3. Pasirinkite parinktį **Nustatyti iš naujo**. 

4.  Šio panaikinimo patvirtinimui, įveskite aplinkos pavadinimą ir pasirinkite **Paleisti iš naujo**.

## <a name="delete-an-existing-environment"></a>Esamos aplinkos naikinimas

Kaip aplinkos savininkas galite ištrinti administruojamą aplinką.

1.  Programos antraštėje pasirinkite **Aplinkos** parinkėją.

2.  Pažymėkite aplinką, kurią norite nustatyti iš naujo, ir pažymėkite daugtaškį (**...**). 

3. Pasirinkite parinktį **Naikinti**. 

4.  Norėdami patvirtinti panaikinimą, įveskite aplinkos pavadinimą ir pasirinkite **Naikinti**.

> [!NOTE]
> Aplinkos naikinimas nepašalina susiejimo su Dataverse aplinka. Sužinokite, kaip pašalinti [esamą ryšį su Dataverse aplinka](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE [footer-include](includes/footer-banner.md)]
