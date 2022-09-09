---
title: Dirbkite su „Customer Insights“ duomenimis „Microsoft Dataverse” platformoje
description: Sužinokite, kaip prijungti "Customer Insights" ir Microsoft Dataverse suprasti išvesties objektus, kurie eksportuojami į Dataverse.
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
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424319"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Dirbkite su „Customer Insights“ duomenimis „Microsoft Dataverse” platformoje

„Customer Insights” suteikia parinktį padaryti išvesties objektus prieinamus [„Microsoft Dataverse”](/powerapps/maker/data-platform/data-platform-intro). Ši integracija leidžia lengvai dalytis duomenimis ir pasirinktinai kurti naudojant žemo kodo / kodo nebuvimo metodą. Išvesties [objektai](#output-entities) galimi kaip lentelės aplinkoje Dataverse. Duomenis galite naudoti bet kuriai kitai programai, pagrįstoms Dataverse lentelėmis. Šiose lentelėse įgalinami tokie scenarijai kaip automatizuotos darbo eigos arba Power Automate programų kūrimas naudojant Power Apps.

Prisijungę prie savo Dataverse aplinkos taip pat galite nuryti [duomenis iš vietinis duomenų šaltinių naudodami Power Platform duomenų srautus ir šliuzus](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Būtinosios sąlygos

- Klientų įžvalgos ir Dataverse aplinkos turi būti priglobtos tame pačiame regione.
- Visuotinio administratoriaus vaidmuo, Dataverse nustatytas aplinkoje. Patikrinkite, ar ši [Dataverse aplinka susieta su](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) tam tikromis saugos grupėmis, ir įsitikinkite, kad esate įtraukti į tas saugos grupes.
- Jokia kita "Customer Insights" aplinka, jau susieta su aplinka, Dataverse prie kurios norite prisijungti. Sužinokite, [kaip pašalinti esamą ryšį su Dataverse aplinka](#remove-an-existing-connection-to-a-dataverse-environment).
- Aplinka Microsoft Dataverse, prijungta prie vienos saugyklos abonemento, jei konfigūruojate aplinką taip, kad ji [naudotų jūsų Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse saugojimo pajėgumų teisė

"Customer Insights" prenumerata suteikia jums teisę į papildomą pajėgumą, susijusį su jūsų organizacijos esama [Dataverse saugyklos talpa](/power-platform/admin/capacity-storage). Pridėta talpa priklauso nuo jūsų prenumeratos naudojamų profilių skaičiaus.

**Pavyzdys:**

Darant prielaidą, kad gausite 15 GB duomenų bazės saugyklą ir 20 GB failų saugyklą 100 000 klientų profilių. Jei jūsų prenumeratoje yra 300 000 klientų profilių, bendra saugyklos talpa yra 45 GB (3 x 15 GB) duomenų bazės saugykla ir 60 GB failų saugykla (3 x 20 GB). Panašiai, jei turite B-to-B prenumeratą su 30K paskyromis, jūsų bendra saugyklos talpa yra 45 GB (3 x 15 GB) duomenų bazės saugykla ir 60 GB failų saugykla (3 x 20 GB).

Jūsų organizacijoje žurnalo pajėgumas nėra laipsniškas ir fiksuotas.

Daugiau informacijos apie išsamias pajėgumo teises rasite ["Dynamics 365" licencijavimo vadove](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Aplinkos prijungimas Dataverse prie "Customer Insights"

Šis **Microsoft Dataverse** veiksmas leidžia susieti "Customer Insights" su aplinka Dataverse kuriant ["Customer Insights" aplinką](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="duomenų bendrinimas su Microsoft Dataverse automatiškai įgalinta naujų aplinkų informacija.":::

1. Pateikite savo Dataverse aplinkai URL arba palikite tuščią, kad jis būtų sukurtas jums.

   > [!NOTE]
   > Nustatę ryšį tarp "Customer Insights" ir Dataverse, nekeiskite organizacijos aplinkos pavadinimo Dataverse. Organizacijos pavadinimas naudojamas URL, Dataverse o pakeistas pavadinimas nutraukia ryšį su "Customer Insights".

   [Power Platform administratoriai gali valdyti, kas gali kurti naujas Dataverse aplinkas](/power-platform/admin/control-environment-creation). Jei bandote nustatyti naują "Customer Insights" aplinką, bet negalite to padaryti, administratorius galėjo išjungti aplinkų Dataverse kūrimą visiems, išskyrus administratorius.

1. Jei naudojate savo "Data Lake Storage" paskyrą:
   1. Pasirinkite **Įgalinti duomenų bendrinimą** su Dataverse.
   1. Įveskite leidimų **identifikatorių**. Norėdami gauti leidimo identifikatorių, [įgalinkite duomenų bendrinimą su Dataverse savo Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Įgalinkite duomenų bendrinimą su Dataverse savo Azure Data Lake Storage (peržiūra)

[Savo paskyroje Azure Data Lake Storage](own-data-lake-storage.md) patikrinkite, ar vartotojas, nustatantis "Customer Insights" aplinką, turi bent "**Storage Blob Data Reader"** teises `customerinsights` saugykloje esančiame konteineryje.

### <a name="limitations"></a>Apribojimai

- Tik asmeninis susiejimas Dataverse tarp organizacijos ir Azure Data Lake Storage paskyros. Kai organizacija prijungiama Dataverse prie saugyklos abonemento, ji negali prisijungti prie kito saugyklos abonemento. Šis apribojimas neleidžia Dataverse užpildyti kelių saugyklos paskyrų.
- Duomenų bendrinimas neveiks, jei norint pasiekti paskyrą Azure Data Lake Storage reikia "Azure Private Link" sąrankos, nes ji yra už užkardos. Dataverse šiuo metu nepalaiko ryšio su privačiais galiniais taškais per "Private Link".

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Saugos grupių nustatymas savarankiškai Azure Data Lake Storage

1. "Azure" prenumeratoje sukurkite dvi saugos grupes – vieną **skaitytuvo** saugos grupę ir vieną **bendraautorių** saugos grupę ir nustatykite paslaugą Microsoft Dataverse kaip abiejų saugos grupių savininkę.

1. Valdykite prieigos kontrolės sąrašą (ACL), esantį `customerinsights` saugyklos abonemento konteineryje, naudodami šias saugos grupes.
   1. Įtraukite paslaugą Microsoft Dataverse ir visas Dataverse verslo programas, pvz., "Dynamics 365 Marketing", **į skaitytuvo** saugos grupę su **tik** skaitymo teisėmis.
   1. Į bendraautorių *saugos grupę įtraukite* **tik** programą "Customer Insights", kad suteiktumėte **skaitymo ir rašymo** teises rašyti profilius ir įžvalgas.

### <a name="set-up-powershell"></a>"PowerShell" nustatymas

Nustatykite "PowerShell", kad būtų vykdomi "PowerShell" scenarijai.

1. Įdiekite naujausią "PowerShell for Graph"[Azure Active Directory versiją](/powershell/azure/active-directory/install-adv2).
   1. Savo kompiuteryje pasirinkite klaviatūroje pasirinkite "Windows" klavišą ir ieškokite **Windows PowerShell** bei pasirinkite **Paleisti kaip administratorių**.
   1. „PowerShell“ atsivėrusiame lange įveskite `Install-Module AzureAD`.

1. Importuokite tris modulius.
   1. "PowerShell" lange įveskite `Install-Module -Name Az.Accounts` ir atlikite veiksmus.
   1. Pakartokite ir `Install-Module -Name Az.Resources``Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Vykdykite "PowerShell" scenarijus ir gaukite leidimo identifikatorių

1. Atsisiųskite du "PowerShell" scenarijus, kuriuos turite paleisti iš mūsų inžinieriaus ["GitHub" atpirkimo sandorio](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Reikia nuomotojo administratoriaus teisių.
   - `ByolSetup.ps1`: reikia saugyklos "Blob Data Owner" leidimų saugyklos paskyros / konteinerio lygiu. Šis scenarijus sukurs jums leidimą. Sėkmingai paleidus scenarijų, jūsų vaidmens priskyrimą galima pašalinti rankiniu būdu.

1. Vykdykite " `CreateSecurityGroups.ps1` Windows PowerShell" pateikdami "Azure" prenumeratos ID, kuriame yra jūsų Azure Data Lake Storage. Atidarykite "PowerShell" scenarijų redaktoriuje, kad peržiūrėtumėte papildomą informaciją ir įdiegtą logiką.

   Šis scenarijus sukuria dvi saugos grupes jūsų "Azure" prenumeratoje: vieną skaitytojų grupei, kitą – bendraautorių grupei. Microsoft Dataverse paslauga yra abiejų šių saugos grupių savininkė.

1. Įrašykite abi saugos grupės ID reikšmes, sugeneruotas pagal šį scenarijų, kad galėtumėte naudoti scenarijuje `ByolSetup.ps1`.

   > [!NOTE]
   > Saugos grupės kūrimas gali būti išjungtas jūsų nuomotojuje. Tokiu atveju reikės rankinio nustatymo, o jūsų Azure AD administratorius turėtų įjungti [saugos grupės kūrimą](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Vykdykite `ByolSetup.ps1` "Windows PowerShell" pateikdami "Azure" prenumeratos ID, kuriame yra jūsų Azure Data Lake Storage, saugyklos abonemento pavadinimas, išteklių grupės pavadinimas ir skaitytuvo bei bendradarbio saugos grupės ID reikšmės. Atidarykite "PowerShell" scenarijų redaktoriuje, kad peržiūrėtumėte papildomą informaciją ir įdiegtą logiką.

   Šis scenarijus prideda reikiamą vaidmenimis pagrįstą prieigos valdiklį Microsoft Dataverse paslaugai ir visoms Dataverse verslo programoms. Ji taip pat atnaujina konteinerio prieigos kontrolės sąrašą (ACL), `customerinsights` skirtą saugos grupėms, sukurtoms naudojant `CreateSecurityGroups.ps1` scenarijų. Bendraautorių grupei suteikiamas *rwx* leidimas, o skaitytojų grupei suteikiamas *tik r-x* leidimas.

1. Nukopijuokite išvesties eilutę, kuri atrodo taip: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Įveskite nukopijuotą išvesties eilutę į **aplinkos konfigūravimo veiksmo lauką Teisių identifikatorius**, skirtą Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigūravimo parinktys, leidžiančios įgalinti duomenų bendrinimą iš savo Azure Data Lake Storage su Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Esamo ryšio su Dataverse aplinka šalinimas

Jungiantis prie Dataverse aplinkos, klaidos pranešimas **Ši CDS organizacija jau prijungta prie kito "Customer Insights" egzemplioriaus** reiškia, kad Dataverse aplinka jau naudojama "Customer Insights" aplinkoje. Esamą ryšį galite pašalinti kaip visuotinis aplinkos administratorius Dataverse. Pakeitimų užpildymas gali užtrukti kelias valandas.

1. Eikite į [Power Apps](https://make.powerapps.com).
1. Pasirinkite aplinką iš aplinkos parinkiklio.
1. Eikite į **Sprendimai**.
1. Pašalinkite arba panaikinkite sprendimą, pavadintą **Dynamics 365 Customer Insights Kliento kortelės papildinys (peržiūra)**.

OR

1. Atidarykite savo Dataverse aplinką.
1. Eikite į **Išplėstiniai nustatymų** > **sprendimai**.
1. Pašalinkite **"CustomerInsightsCustomerCard"** sprendimą.

Jei ryšio pašalinimas nepavyksta dėl priklausomybių, turite pašalinti ir priklausomybes. Norėdami gauti daugiau informacijos, žiūrėkite [Priklausomybių](/power-platform/alm/removing-dependencies) šalinimas.

## <a name="output-entities"></a>Išvesties objektai

Kai kurie išvesties objektai iš "Customer Insights" pasiekiami kaip lentelės Dataverse. Toliau aprašomos numatomos šių lentelių schemos.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [„AlternateKey”](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [„CustomerMeasure”](#customermeasure)
- [Papildymas](#enrichment)
- [Prognozė](#prediction)
- [Segmento narystė](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Šioje lentelėje pateikiamas vieningasis kliento profilis iš „Customer Insights”. Vieningo kliento profilio schema priklauso nuo objektų ir atributų, naudojamų duomenų suvienijimo procese. Kliento profilio schemoje paprastai yra atributų antrinis rinkinys iš [Kliento profilio „Common Data Model” aprašo](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Pagal scenarijų B–B kliento profilyje yra suvienodinti abonementai, o schemoje paprastai yra atributų pogrupis iš [abonemento](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account) bendrojo duomenų modelio aprašo.

### <a name="contactprofile"></a>ContactProfile

"ContactProfile" yra vieninga informacija apie kontaktą. Kontaktai yra [asmenys, susieti su abonementu](data-unification-contacts.md) pagal scenarijų nuo B iki B.

| Column                       | Tipas                | Aprašą     |
| ---------------------------- | ------------------- | --------------- |
|  Gimimo_data            | Data ir laikas       |  Kontakto gimimo data               |
|  Miestas                 | Tekstinė žinutė |  Kontaktinio adreso miestas               |
|  ContactId            | Tekstinė žinutė |  Kontaktinio profilio ID               |
|  ContactProfileId     | Unikalusis identifikatorius   |  GUID kontaktui               |
|  CountryOrRegion      | Tekstinė žinutė |  Kontaktinio adreso šalis / regionas               |
|  CustomerId           | Tekstinė žinutė |  Paskyros, su kuria kontaktas susietas, ID               |
|  EntityName           | Tekstinė žinutė |  Subjektas, iš kurio gaunami duomenys                |
|  FirstName            | Tekstinė žinutė |  Kontakto vardas               |
|  Lytys               | Tekstinė žinutė |  Kontakto lytis               |
|  Id                   | Tekstinė žinutė |  Deterministinis GUID, pagrįstas`Identifier`               |
|  Identifikatorius           | Tekstinė žinutė |  Kontaktinio profilio vidinis ID: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Tekstinė žinutė |  Kontaktinio asmens pareigų pavadinimas               |
|  LastName             | Tekstinė žinutė |  Kontakto pavardė               |
|  PostalCode           | Tekstinė žinutė |  Kontaktinio adreso pašto kodas               |
|  PrimaryEmail         | Tekstinė žinutė |  Kontakto el. pašto adresas               |
|  Pirminis telefonas         | Tekstinė žinutė |  Kontakto telefono numeris               |
|  Valstija arba provincija      | Tekstinė žinutė |  Kontaktinio adreso valstija arba provincija               |
|  GatvėAddress        | Tekstinė žinutė |  Kontaktinio adreso gatvė               |

### <a name="alternatekey"></a>„AlternateKey”

Alternatyvaus rakto lentelėje yra suvienodinimo procese dalyvavusių objektų raktų rinkinys.

|Column  |Tipas  |Aprašą  |
|---------|---------|---------|
|„DataSourceName”    |Tekstinė žinutė         | Duomenų šaltinio pavadinimas. Pavyzdžiui: `datasource5`.        |
|EntityName        | Tekstinė žinutė        | Objekto pavadinimas programoje "Customer Insights". Pavyzdžiui: `contact1`.        |
|„AlternateValue”    |Tekstinė žinutė         |Alternatyvusis ID, susietas su kliento ID. Pavyzdys: `cntid_1078`         |
|„KeyRing”           | Tekstinė žinutė        | JSON reikšmė  </br> Pavyzdys: [{„dataSourceName”:„ datasource5 ”,</br>„entityName”:„ contact1”,</br>„preferredKey”:„ cntid_1078”,</br>„keys”:[„ cntid_1078”]}]       |
|CustomerId         | Tekstinė žinutė        | Vieningojo kliento profilio ID.         |
|„AlternateKeyId”     | Unikalusis identifikatorius        |  AlternateKey deterministinis GUID, pagrįstas`Identifier`      |
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
| SodrinimasId | Unikalusis identifikatorius            | Deterministinis GUID, sugeneruotas iš`Identifier` |
| Identifikatorius   | Tekstinė žinutė           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prognozė

Šioje lentelėje pateikiami modelio prognozių rezultatai.

| Column               | Tipas        | Aprašą                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Tekstinė žinutė      | Kliento profilio ID                                  |
| „ModelProvider”        | Tekstinė žinutė      | Modelio tiekėjo pavadinimas                                      |
| Modelis                | Tekstinė žinutė      | Modelio pavadinimas                                                |
| Reikšmės               | Tekstinė žinutė | Modelio sukurtų atributų sąrašas |
| PredictionId | Unikalusis identifikatorius       | Deterministinis GUID, sugeneruotas iš`Identifier` |
| Identifikatorius   | Tekstinė žinutė      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmento narystė

Šioje lentelėje pateikiama klientų profilių segmento narystės informacija.

| Column        | Tipas | Aprašą                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Tekstinė žinutė       | Kliento Profilio ID        |
| Segmentprovider      | Tekstinė žinutė       | Programa, skelbianti segmentus.      |
| SegmentasMembershipType | Tekstinė žinutė       | Šio segmento narystės įrašo kliento tipas. Palaiko kelių tipų, pvz., Klientas, Kontaktas arba Paskyra. Numatytasis nustatymas: klientas  |
| Segmentai       | Tekstinė žinutė  | Unikalių segmentų, kurių narys yra kliento profilis, sąrašas      |
| Identifikatorius  | Tekstinė žinutė   | Unikalus segmento narystės įrašo identifikatorius. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| Segmento narysId | Unikalusis identifikatorius      | Deterministinis GUID, sugeneruotas iš`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
