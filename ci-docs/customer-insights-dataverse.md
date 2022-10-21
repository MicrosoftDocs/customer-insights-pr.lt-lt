---
title: Dirbkite su „Customer Insights“ duomenimis „Microsoft Dataverse” platformoje
description: Sužinokite, kaip sujungti "Customer Insights" ir Microsoft Dataverse suprasti išvesties objektus, eksportuojamus į ""Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9433c411a2c7eb0db137c6392578993d47be82a2
ms.sourcegitcommit: 8559ca47a22d1d7cd9be13531c2eaf0c1083942b
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671261"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Dirbkite su „Customer Insights“ duomenimis „Microsoft Dataverse” platformoje

„Customer Insights” suteikia parinktį padaryti išvesties objektus prieinamus [„Microsoft Dataverse”](/powerapps/maker/data-platform/data-platform-intro). Ši integracija leidžia lengvai dalytis duomenimis ir kurti pasirinktinius duomenis naudojant žemo kodo / be kodo metodą. Išvesties [objektai](#output-entities) galimi kaip lentelės Dataverse aplinkoje. Duomenis galite naudoti bet kuriai kitai programai, pagrįstai Dataverse lentelėmis. Šios lentelės įgalina tokius scenarijus kaip automatizuotos darbo eigos naudojant Power Automate arba programų kūrimas naudojant ""Power Apps.

Prisijungę prie savo Dataverse aplinkos taip pat galite [praryti duomenis iš vietinis duomenų šaltinių naudodami Power Platform duomenų srautus ir šliuzus](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Būtinosios sąlygos

- "Customer Insights" ir Dataverse aplinkos turi būti nuomojamos tame pačiame regione.
- Visuotinio administratoriaus vaidmuo, nustatytas aplinkoje.Dataverse Patikrinkite, ar ši [Dataverse aplinka susieta](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) su tam tikromis saugos grupėmis, ir įsitikinkite, kad esate įtraukti į tas saugos grupes.
- Jokia kita "Customer Insights" aplinka dar nėra susieta su aplinka, Dataverse kurią norite prijungti. Sužinokite, [kaip pašalinti esamą ryšį su Dataverse aplinka](#remove-an-existing-connection-to-a-dataverse-environment).
- Aplinka, Microsoft Dataverse susieta su vienu saugyklos abonementu, jei sukonfigūruosite aplinką naudoti [savo Azure Data Lake Storage](own-data-lake-storage.md)"".

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse teisė į saugojimo pajėgumus

"Customer Insights" prenumerata suteikia jums papildomų pajėgumų esamai [Dataverse organizacijos saugyklos talpai](/power-platform/admin/capacity-storage). Papildoma talpa priklauso nuo profilių, kuriuos naudoja jūsų prenumerata, skaičiaus.

**Pavyzdys:**

Darant prielaidą, kad gausite 15 GB duomenų bazės saugyklą ir 20 GB failų saugyklą 100 000 klientų profilių. Jei jūsų prenumeratoje yra 300 000 klientų profilių, bendra saugyklos talpa yra 45 GB (3 x 15 GB) duomenų bazės saugykla ir 60 GB failų saugykla (3 x 20 GB). Panašiai, jei turite B-to-B prenumeratą su 30K paskyromis, bendra saugyklos talpa yra 45 GB (3 x 15 GB) duomenų bazės saugykla ir 60 GB failų saugykla (3 x 20 GB).

Žurnalo pajėgumas nėra papildomas ir fiksuotas jūsų organizacijoje.

Daugiau informacijos apie išsamias pajėgumo teises ieškokite ["Dynamics 365" licencijavimo vadove](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Aplinkos prijungimas Dataverse prie "Customer Insights"

Šis **Microsoft Dataverse** veiksmas leidžia susieti "Customer Insights" su savo Dataverse aplinka kuriant ["Customer Insights" aplinką](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Duomenų bendrinimas su Microsoft Dataverse automatiniu įgalinimu naujose aplinkose.":::

1. Pateikite savo aplinkos URL Dataverse arba palikite tuščią, kad jis būtų sukurtas jums.

   > [!NOTE]
   > Sukūrę ryšį tarp "Customer Insights" ir Dataverse"", nekeiskite aplinkos organizacijos pavadinimo Dataverse. URL naudojamas Dataverse organizacijos pavadinimas, o pakeistas pavadinimas nutraukia ryšį su "Customer Insights".

   [Power Platform Administratoriai gali valdyti, kas gali sukurti naują Dataverse aplinką](/power-platform/admin/control-environment-creation). Jei bandote nustatyti naują "Customer Insights" aplinką, bet negalite, gali būti, kad administratorius išjungė aplinkų Dataverse kūrimą visiems, išskyrus administratorius.

1. Jei naudojate savo "Data Lake Storage" paskyrą:
   1. Pasirinkite **Įgalinti duomenų bendrinimą** naudojant Dataverse.
   1. Įveskite **leidimų identifikatorių**. Norėdami gauti leidimo identifikatorių, [įgalinkite duomenų bendrinimą su Dataverse savo Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Duomenų bendrinimo įgalinimas naudojant Dataverse savuosius Azure Data Lake Storage (peržiūra)

Savo [Azure Data Lake Storage paskyroje](own-data-lake-storage.md) patikrinkite, ar "Customer Insights" aplinką nustatantis vartotojas turi bent saugyklos "Blob Data Reader **" teises** saugyklos `customerinsights` paskyros sudėtiniame rodinyje.

> [!NOTE]
> Duomenų bendrinimas taikomas tik tuo atveju, jei naudojate savo Azure Data Lake Storage paskyrą. Šis parametras nepasiekiamas, jei "Customer Insights" aplinkoje naudojama numatytoji Dataverse saugykla.

### <a name="limitations"></a>Apribojimai

- Tik individualus susiejimas Dataverse tarp organizacijos ir Azure Data Lake Storage paskyros. Dataverse Kai organizacija yra prijungta prie saugyklos paskyros, ji negali prisijungti prie kitos saugyklos paskyros. Šis apribojimas neleidžia Dataverse užpildyti kelių saugyklos paskyrų.
- Duomenų bendrinimas neveiks, jei norint pasiekti jūsų Azure Data Lake Storage paskyrą reikalinga "Azure Private Link" sąranka, nes ji yra už užkardos. Dataverse šiuo metu nepalaiko ryšio su privačiais galiniais punktais per privatų saitą.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Savarankiškai nustatykite saugos grupes Azure Data Lake Storage

1. Savo "Azure" prenumeratoje sukurkite dvi saugos grupes - vieną "Reader"**saugos grupę ir vieną** **bendraautorių** saugos grupę ir nustatykite Microsoft Dataverse paslaugą kaip abiejų saugos grupių savininką.

1. Tvarkykite prieigos kontrolės sąrašą (ACL) `customerinsights` savo saugyklos paskyros konteineryje naudodami šias saugos grupes.
   1. Įtraukite paslaugą ir visas Microsoft Dataverse"-based" verslo programas, Dataverse pvz., "Dynamics 365 Marketing", į **"Reader"** saugos grupę su **tik** skaitymo teisėmis.
   1. Įtraukite *tik* "Customer Insights" programą į **bendraautorių** saugos grupę, kad suteiktumėte skaitymo **ir rašymo** teises rašyti profilius ir įžvalgas.

### <a name="set-up-powershell"></a>"PowerShell" nustatymas

Nustatykite, kad "PowerShell" vykdytų "PowerShell" scenarijus.

1. Įdiekite naujausią " [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2)" versiją.
   1. Savo kompiuteryje pasirinkite klaviatūroje pasirinkite "Windows" klavišą ir ieškokite **Windows PowerShell** bei pasirinkite **Paleisti kaip administratorių**.
   1. „PowerShell“ atsivėrusiame lange įveskite `Install-Module AzureAD`.

1. Importuokite tris modulius.
   1. "PowerShell" lange įveskite `Install-Module -Name Az.Accounts` ir atlikite veiksmus.
   1. Pakartokite ir `Install-Module -Name Az.Resources``Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Vykdykite "PowerShell" scenarijus ir gaukite leidimo identifikatorių

1. Atsisiųskite du "PowerShell" scenarijus, kuriuos turite paleisti, iš mūsų inžinieriaus ["GitHub" atpirkimo](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: reikia nuomotojo administratoriaus teisių.
   - `ByolSetup.ps1`: reikalingi saugyklos didelių dvejetainių objektų duomenų savininko leidimai saugyklos paskyros / sudėtinio rodinio lygiu. Šis scenarijus sukurs jums leidimą. Sėkmingai paleidus scenarijų, jūsų vaidmenų priskyrimą galima pašalinti rankiniu būdu.

1. Vykdykite `CreateSecurityGroups.ps1` naudodami "Windows PowerShell" pateikdami "Azure" prenumeratos ID, kuriame yra jūsų Azure Data Lake Storage"". Atidarykite "PowerShell" scenarijų redaktoriuje, kad peržiūrėtumėte papildomą informaciją ir įdiegtą logiką.

   Šis scenarijus sukuria dvi saugos grupes jūsų "Azure" prenumeratoje: vieną "Reader" grupei, o kitą "Contributor" grupei. Microsoft Dataverse paslauga yra abiejų šių saugos grupių savininkė.

1. Išsaugokite abi šio scenarijaus sugeneruotas saugos grupės ID reikšmes, kad galėtumėte jas naudoti scenarijuje `ByolSetup.ps1`.

   > [!NOTE]
   > Saugos grupės kūrimas jūsų nuomotojuje gali būti išjungtas. Tokiu atveju reikės rankinės sąrankos, o jūsų Azure AD administratorius turės įgalinti [saugos grupės kūrimą](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Vykdykite `ByolSetup.ps1` sistemoje "Windows PowerShell" pateikdami "Azure" prenumeratos ID, kuriame yra jūsų Azure Data Lake Storage, saugyklos abonemento pavadinimas, išteklių grupės pavadinimas ir "Reader" bei bendraautorio saugos grupės ID reikšmės. Atidarykite "PowerShell" scenarijų redaktoriuje, kad peržiūrėtumėte papildomą informaciją ir įdiegtą logiką.

   Šis scenarijus prideda reikiamą vaidmenimis pagrįstą prieigos valdymą paslaugai ir bet kokioms Microsoft Dataverse Dataverse-pagrįstoms verslo programoms. Ji taip pat atnaujina prieigos valdymo sąrašą (ACL) `customerinsights` saugos grupių, sukurtų naudojant scenarijų, `CreateSecurityGroups.ps1` konteineryje. Bendraautorių grupei suteikiamas *rwx* leidimas, o skaitytojų grupei *– tik r-x* leidimas.

1. Nukopijuokite išvesties eilutę, kuri atrodo taip: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Įveskite nukopijuotą išvesties eilutę į **aplinkos konfigūravimo veiksmo** lauką Teisių identifikatorius Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigūravimo parinktys, leidžiančios įgalinti duomenų bendrinimą iš savo Azure Data Lake Storage su Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Esamo ryšio su aplinka šalinimas Dataverse

Jungiantis prie aplinkos, klaidos pranešimas Dataverse Ši CDS organizacija jau prijungta prie **kito "Customer Insights" egzemplioriaus**, reiškia, Dataverse kad aplinka jau naudojama "Customer Insights" aplinkoje. Galite pašalinti esamą ryšį kaip visuotinis Dataverse aplinkos administratorius. Pakeitimų užpildymas gali užtrukti kelias valandas.

1. Eikite į [Power Apps](https://make.powerapps.com).
1. Pasirinkite aplinką iš aplinkos parinkiklio.
1. Eikite į **Sprendimai**.
1. Pašalinkite arba panaikinkite sprendimą, pavadintą **Dynamics 365 Customer Insights Kliento kortelės papildinys (peržiūra)**.

OR

1. Atidarykite savo Dataverse aplinką.
1. Eikite į **Išplėstinių nustatymų** > **sprendimai**.
1. Pašalinkite **"CustomerInsightsCustomerCard"** sprendimą.

Jei ryšio pašalinti nepavyksta dėl priklausomybių, turite pašalinti ir priklausomybes. Daugiau informacijos ieškokite [Priklausomybių](/power-platform/alm/removing-dependencies) šalinimas.

## <a name="output-entities"></a>Išvesties objektai

Kai kurie išvesties objektai iš "Customer Insights" galimi kaip lentelės.Dataverse Toliau aprašomos numatomos šių lentelių schemos.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [„AlternateKey”](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [„CustomerMeasure”](#customermeasure)
- [Papildymas](#enrichment)
- [Prognozė](#prediction)
- [Segmento narystė](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Šioje lentelėje pateikiamas vieningasis kliento profilis iš „Customer Insights”. Vieningo kliento profilio schema priklauso nuo objektų ir atributų, naudojamų duomenų suvienijimo procese. Kliento profilio schemoje paprastai yra atributų antrinis rinkinys iš [Kliento profilio „Common Data Model” aprašo](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Pagal scenarijų B–B kliento profilyje yra suvienodintos sąskaitos, o schemoje paprastai yra atributų poaibis iš [sąskaitos](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account) bendrojo duomenų modelio aprašo.

### <a name="contactprofile"></a>ContactProfile

ContactProfile yra vieninga informacija apie kontaktą. Kontaktai yra [asmenys, susieti su paskyra](data-unification-contacts.md) pagal scenarijų nuo B iki B.

| Column                       | Tipas                | Aprašą     |
| ---------------------------- | ------------------- | --------------- |
|  Gimimo_data            | Data ir laikas       |  Kontaktinio asmens gimimo data               |
|  Miestas                 | Tekstinė žinutė |  Kontaktinio adreso miestas               |
|  Kontaktinis ID            | Tekstinė žinutė |  Kontaktinio profilio ID               |
|  ContactProfileId     | Unikalusis identifikatorius   |  GUID kontaktui               |
|  ŠalisOrregionas      | Tekstinė žinutė |  Kontaktinio adreso šalis / regionas               |
|  CustomerId           | Tekstinė žinutė |  Paskyros, su kuria susietas kontaktas, ID               |
|  EntityName           | Tekstinė žinutė |  Subjektas, iš kurio gaunami duomenys                |
|  FirstName            | Tekstinė žinutė |  Kontakto vardas               |
|  Lytys               | Tekstinė žinutė |  Kontakto lytis               |
|  Id                   | Tekstinė žinutė |  Deterministinis GUID, pagrįstas`Identifier`               |
|  Identifikatorius           | Tekstinė žinutė |  Vidinis kontaktinio profilio ID: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Tekstinė žinutė |  Kontakto pareigos               |
|  LastName             | Tekstinė žinutė |  Kontakto pavardė               |
|  PostalCode           | Tekstinė žinutė |  Kontaktinio adreso pašto kodas               |
|  PrimaryEmail         | Tekstinė žinutė |  Kontakto el. pašto adresas               |
|  PrimaryPhone         | Tekstinė žinutė |  Kontaktinio asmens telefono numeris               |
|  Valstija arba provincija      | Tekstinė žinutė |  Kontaktinio adreso valstija arba provincija               |
|  Gatvės adresas        | Tekstinė žinutė |  Kontaktinio adreso gatvė               |

### <a name="alternatekey"></a>„AlternateKey”

Alternatyvaus rakto lentelėje yra suvienodinimo procese dalyvavusių objektų raktų rinkinys.

|Column  |Tipas  |Aprašą  |
|---------|---------|---------|
|„DataSourceName”    |Tekstinė žinutė         | Duomenų šaltinio pavadinimas. Pavyzdžiui: `datasource5`.        |
|EntityName        | Tekstinė žinutė        | Objekto pavadinimas programoje "Customer Insights". Pavyzdžiui: `contact1`.        |
|„AlternateValue”    |Tekstinė žinutė         |Alternatyvusis ID, susietas su kliento ID. Pavyzdys: `cntid_1078`         |
|„KeyRing”           | Tekstinė žinutė        | JSON reikšmė  </br> Pavyzdys: [{„dataSourceName”:„ datasource5 ”,</br>„entityName”:„ contact1”,</br>„preferredKey”:„ cntid_1078”,</br>„keys”:[„ cntid_1078”]}]       |
|CustomerId         | Tekstinė žinutė        | Vieningojo kliento profilio ID.         |
|„AlternateKeyId”     | Unikalusis identifikatorius        |  Alternatyvus raktas deterministinis GUID, pagrįstas`Identifier`      |
|Identifikatorius |   Tekstinė žinutė      |   `DataSourceName|EntityName|AlternateValue`  </br> Pavyzdys: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Šioje lentelėje pateikiamos vartotojų veiklos, galimos „Customer Insights”.

| Column            | Tipas        | Aprašą                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Tekstinė žinutė      | Kliento profilio ID                                                                      |
| „ActivityId”        | Tekstinė žinutė      | Vidinis kliento veiklos ID (pirminis raktas)                                       |
| „SourceEntityName”  | Tekstinė žinutė      | Šaltinio objekto pavadinimas                                                                |
| „SourceActivityId”  | Tekstinė žinutė      | Pirminis raktas iš šaltinio objekto                                                       |
| „ActivityType”      | Tekstinė žinutė      | Pasirinktinės veiklos semantinis veiklos tipas arba pavadinimas                                        |
| „ActivityTimeStamp” | Data ir laikas    | Veiklos laiko žyma                                                                      |
| Antraštė             | Tekstinė žinutė      | Veiklos antraštė arba pavadinimas                                                               |
| Aprašą       | Tekstinė žinutė      | Veiklos aprašas                                                                     |
| URL               | Tekstinė žinutė      | Nuoroda į išorinį URL, būdingą veiklai                                         |
| „SemanticData”      | Tekstinė žinutė | Apima pagrindinių reikšmių porų sąrašą, skirtą semantinio susiejimo laukams, būdingiems veiklos tipui |
| „RangeIndex”        | Tekstinė žinutė      | „Unix” laiko žyma, naudojama veiklos laiko planavimo juostai ir efektyvioms diapazono užklausoms rikiuoti |
| UnifiedActivityId   | Unikalusis identifikatorius | Vidinis kliento veiklos ID („ActivityId”) |

### <a name="customermeasure"></a>„CustomerMeasure”

Šioje lentelėje pateikiami kliento atributais pagrįstų matavimų išvesties duomenys.

| Column             | Tipas             | Aprašą                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Tekstinė žinutė           | Kliento profilio ID        |
| Matavimai           | Tekstinė žinutė      | Pateikiamas matavimų pavadinimų ir reikšmių pagrindinių reikšmių porų sąrašas nurodytam klientui |
| Identifikatorius | Tekstinė žinutė           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Unikalusis identifikatorius     | Kliento profilio ID |

### <a name="enrichment"></a>Papildymas

Šioje lentelėje pateikiami papildymo proceso rezultatai.

| Column               | Tipas             |  Aprašą                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Tekstinė žinutė           | Kliento profilio ID                                 |
| „EnrichmentProvider”   | Tekstinė žinutė           | Papildymo tiekėjo pavadinimas                                  |
| „EnrichmentType”       | Tekstinė žinutė           | Papildymo tipas                                      |
| Reikšmės               | Tekstinė žinutė      | Papildymo proceso metu sukurtų atributų sąrašas |
| SodrinimasId | Unikalusis identifikatorius            | Deterministinis GUID, sukurtas iš`Identifier` |
| Identifikatorius   | Tekstinė žinutė           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prognozė

Šioje lentelėje pateikiami modelio prognozių rezultatai.

| Column               | Tipas        | Aprašą                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Tekstinė žinutė      | Kliento profilio ID                                  |
| „ModelProvider”        | Tekstinė žinutė      | Modelio tiekėjo pavadinimas                                      |
| Modelis                | Tekstinė žinutė      | Modelio pavadinimas                                                |
| Reikšmės               | Tekstinė žinutė | Modelio sukurtų atributų sąrašas |
| PredictionId | Unikalusis identifikatorius       | Deterministinis GUID, sukurtas iš`Identifier` |
| Identifikatorius   | Tekstinė žinutė      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmento narystė

Šioje lentelėje pateikiama klientų profilių segmento narystės informacija.

| Column        | Tipas | Aprašą                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Tekstinė žinutė       | Kliento Profilio ID        |
| SegmentasProvider      | Tekstinė žinutė       | Programa, kuri skelbia segmentus.      |
| SegmentMembershipType | Tekstinė žinutė       | Šio segmento narystės įrašo kliento tipas. Palaiko kelis tipus, pvz., klientas, kontaktas arba klientas. Numatytoji reikšmė: klientas  |
| Segmentai       | Tekstinė žinutė  | Unikalių segmentų, kurių narys yra kliento profilis, sąrašas      |
| Identifikatorius  | Tekstinė žinutė   | Unikalus segmento narystės įrašo identifikatorius. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Unikalusis identifikatorius      | Deterministinis GUID, sukurtas iš`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
