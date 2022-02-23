---
title: Duomenų subjekto teisių (DSR) prašymai pagal BDAR | „Microsoft Docs”
description: Atsakykite į duomenų subjekto užklausas dėl Dynamics 365 Customer Insights auditorijos įžvalgų galimybės.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732690"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Duomenų subjekto teisių (DSR) prašymai pagal BDAR

Europos Sąjungos Bendrasis duomenų apsaugos reglamentas (BDAR) įsigaliojo 2018 m. gegužės 25 d. Jis suteikia asmenims svarbių teisių dėl jų duomenų. BDAR paskirtis yra apsaugoti ir užtikrinti asmenų privatumo teises. Daugiau informacijos apie „Microsoft" su sauga ir jos sąrangos tėkme galite sužinoti svetainėje [Microsoft Trust Center“](https://www.microsoft.com/trust-center).

Esame įsipareigoję padėti klientams atitikti jų BDAR reikalavimus. Ji apima teisę naikinti ir eksportuoti duomenis, į kuriuos įtraukta asmeninė informacija, pvz., vartotojo ID, telefono numeriai ir el. pašto adresai. Administratoriai gali įgyvendinti vartotojų užklausas, kad būtų panaikinti arba eksportuoti asmeniniai duomenys.

## <a name="audience-insights"></a>Auditorijos įžvalgos

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Atsakydamas į BDAR duomenų subjektas ištrinti užklausas Dynamics 365 Customer Insights auditorijos įžvalgų galimybes

Teisė naikinti asmens duomenis iš įmonės klientų duomenų bazės buvo įtvirtinta kaip pagrindinė ir saugoma įstatymų Bendrajame duomenų apsaugos reglamente (BDAR). Asmens duomenų naikinimas apima visų asmens duomenų ir sistemos sugeneruotų žurnalų, išskyrus tikrinimo žurnalų informacijos, naikinimą.

#### <a name="manage-data-subject-delete-requests"></a>Duomenų subjektų prašymų naikinti duomenis valdymas

Publikos įžvalgos siūlo tolesnes produkto patirtis siekiant panaikinti asmens duomenis konkretiems klientams ar vartotojams:

- **Prašymų naikinti klientų duomenis valdymas**: klientų duomenys įtraukiami į „Customer Insights” iš pradinių duomenų šaltinių, nepriklausančių „Customer Insights”. Visi prašymai naikinti duomenis pagal BDAR turi būti tenkinami naikinant duomenis pradiniame šaltinyje.
- **Tvarkyti užklausų naikinimą „Customer Insights“ naudotojo duomenims**: Duomenys vartotojams yra sukuriami „Customer Insights“. Visi prašymai naikinti duomenis pagal BDAR turi būti tenkinami naikinant duomenis programoje „Customer Insights”.

##### <a name="manage-requests-to-delete-customer-data"></a>Klientų duomenų naikinimo prašymų tvarkymas

„Customer Insights“ administratorius gali atlikti šiuos veiksmus ir pašalinti kliento duomenis, kurie buvo panaikinti duomenų šaltinyje:

1. Prisijunkite prie Dynamics 365 Customer Insights.
2. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**
3. Kiekvienam duomenų šaltiniui sąraše, kuriame yra panaikintų kliento duomenų:
   1. Pasirinkite (...), tada pasirinkite **Atnaujinti**.
   2. Patikrinkite duomenų šaltinio būseną dalyje **Būsena**. Varnelė reiškia, kad atnaujinti pavyko. Įspėjamasis trikampis reiškia, kad įvyko klaida. Jei rodomas įspėjamasis trikampis, kreipkitės į D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Prašymų naikinti klientų duomenis pagal BDAR tvarkymas.](audience-insights/media/gdpr-data-sources.png "Prašymų naikinti klientų duomenis pagal BDAR tvarkymas")

##### <a name="manage-delete-requests-for-user-data"></a>Tvarkyti užklausų naikinimą vartotojo duomenims

Norėdamas naikinti „Customer Insights” vartotojų duomenis, „Customer Insights” administratorius gali atlikti šiuos veiksmus:

1. Prisijunkite prie Dynamics 365 Customer Insights.
2. Publikos įžvalgose, eikite į **Administratorius** > **Leidimai**.
3. Pažymėkite vartotojo, kurį norite naikinti, žymės langelį.
4. Pasirinkite **Šalinti**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Atsakymas į BDAR duomenų subjekto eksportavimo užklausas

Esame įsipareigoję jums kaip partneriui padėti taikant Bendrąjį duomenų apsaugos reglamentą (BDAR), todėl sukūrėme dokumentaciją, padėsiančią jums pasirengti. Šis dokumentas aprašo žingsnius, kuriuos galite atlikti šiandien siekiant palaikyti BDAR atitiktį naudojant publikos įžvalgas.

#### <a name="manage-export-and-view-requests"></a>Eksporto tvarkymas ir prašymų peržiūra

Teisė į duomenų perkeliamumą leidžia duomenų subjektui prašyti jų asmens duomenų kopijos elektroniniu formatu („struktūrizuotas, dažnai naudojamas, mašininio skaitomumo ir sąveikus formatas“), kurį galima perduoti kitam duomenų valdytojui.

##### <a name="export-customer-data-tenant-admin"></a>Perkelti kliento duomenis (nuomotojo administratorius)

Nuomotojas administratorius gali vadovautis šiais veiksmais duomenims perkelti:

1. Siųsti el. laišką D365CI@microsoft.com prašyme nurodant kliento el. pašto adresą. „Customer Insights“ komanda nusiųs el. laišką į registruoto nuomotojo administravimo el. laiško adresą prašydama patvirtinti eksportavimo duomenis.
2. Patvirtins kliento, dėl kurio buvo pateiktas prašymas, duomenų eksportavimo patvirtinimą.
3. Gaus eksportuotus duomenis, naudodamasis nuomotojo administratoriaus el. pašto adresu.

##### <a name="export-user-data-tenant-admin"></a>Eksportuoti vartotojo duomenis (nuomotojo administravimas)

1. Siųsti el. laišką D365CI@microsoft.com prašyme nurodant vartotojo el. pašto adresą. „Customer Insights“ komanda nusiųs el. laišką į registruoto nuomotojo administravimo el. laiško adresą prašydama patvirtinti eksportavimo duomenis.
2. Patvirtins vartotojo, dėl kurio buvo pateiktas prašymas, duomenų eksportavimo patvirtinimą.
3. Gaus eksportuotus duomenis, naudodamasis nuomotojo administratoriaus el. pašto adresu.

## <a name="consent-management-preview"></a>Sutikimo valdymas (peržiūra)

Sutikimo valdymo funkcija tiesiogiai nerenka vartotojo duomenų. Ji importuoja ir apdoroja tik sutikimo duomenis, kuriuos naudotojai pateikia kitose programose.

Norėdami pašalinti sutikimo duomenis apie konkrečius naudotojus, pašalinkite juos į duomenų šaltinius, nurytus pagal sutikimo valdymo funkciją. Atnaujinus duomenų šaltinis, pašalinti duomenys taip pat bus panaikinti sutikimo centre. Programos, naudojančios sutikimo objektą, taip pat panaikins duomenis, kurie buvo pašalinti šaltinyje po [atnaujinimo](audience-insights/system.md#refresh-processes). Rekomenduojame greitai atnaujinti duomenų šaltinius, atsakius į duomenų subjekto užklausą pašalinti vartotojo duomenis iš visų kitų procesų ir programų.


## <a name="engagement-insights-preview"></a>Įtraukimo įžvalgos (peržiūros versija)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Įvykio duomenų, kuriuose yra galutinio vartotojo identifikavimo informacija, naikinimas ir eksportavimas

Toliau skyriuose aprašyta, kaip panaikinti ir eksportuoti įvykių duomenis, kuriuose gali būti asmeninių duomenų.

Norėdami naikinti ar eksportuoti duomenis:

1. Pažymėkite įvykio ypatybes, kuriose yra duomenų su asmenine informacija.
2. Panaikinkite arba eksportuokite duomenis, susietus su tam tikrų reikšmių (pvz., nurodytu vartotojo ID).

#### <a name="tag-and-update-event-properties"></a>Įvykio ypatybės žymių ir naujinimų naujinimas

Įvykio ypatybių lygyje asmeniniai duomenys yra vienas požymis. Pirmiausia pažymėkite ypatybes, kurios laikomos naikinti arba eksportuoti.

Jei norite pažymėti įvykio ypatybę su asmenine informacija, atlikite toliau nurodytus veiksmus.

1. Atidarykite darbo sritį, kurioje yra įvykis.

1. Eikite į **Duomenys** > **Įvykiai** norėdami pamatyti pasirinktos darbo srities įvykių sąrašą.
  
1. Pasirinkite norimą pažymėti įvykį.

1. Pasirinkite **Redaguoti ypatybes**, kad atidarytumėte srities išsveržkite visas pasirinkto įvykio ypatybes.
     
1. Rinkitės **...** ir tada rinkitės **Redaguoti** norėdami pasiekti **Naujintos ypatybės** langą.

   ![Redaguoti įvykį.](engagement-insights/media/edit-event.png "Redaguoti įvykį")

1. Ypatybių **naujinimo lange** pasirinkite **...** viršutiniame dešiniajame kampe, tada pasirinkite lauką **Apima EUI** laukelį. Rinkitės **Naujinti** norėdami įrašyti savo keitimus.

   ![Įrašykite pakeitimus.](engagement-insights/media/update-property.png "Įrašykite keitimus")

   > [!NOTE]
   > Kiekvieną kartą, kai pasikeičia įvykio schema arba kuriate naują įvykį, rekomenduojama įvertinti susietas įvykio ypatybes ir, jei reikia, pažymėti arba pašalinti jų žymę kaip su asmeniniais duomenimis.

#### <a name="delete-or-export-tagged-event-data"></a>Įvykio duomenų naikinimas arba eksportavimas

Jei visos įvykio ypatybės buvo tinkamai pažymėtos, kaip aprašyta ankstesniame žingsnyje, aplinkos administratorius gali pateikti naikinimo užklausą, o ne naikinamo įvykio duomenis.

Norėdami tvarkyti EUI naikinimą ar eksportavimo užklausas

1. Eikite į **Aministratorius** > **Aplinka** > **Nustatymai**.

1. Skyriuje **Tvarkyti galutinio vartotojo identifikavimo informaciją (EUII)** rinkitės **Tvarkyti EUII**.

##### <a name="deletion"></a>Naikinimas

Norėdami naikinti, galite įvesti kableliais atskirtų vartotojo ID sąrašą skyriuje **Naikinti galutinio vartotojo asmenį galinčią identifikuoti informaciją (EUII)** . Tada šie ID bus lyginami su visomis visų dabartinės aplinkos projektų "string event" ypatybėse naudojant tikslų eilutės gretinimą. 

Jei ypatybės reikšmė atitinka vieną iš pateiktą ID, susietasis įvykis bus visam laikui panaikintas. Dėl šio veiksmo atšaukimo, pažymėję Naikinti, turite patvirtinti **naikinimą**.

##### <a name="export"></a>Eksportavimas

Eksportavimo procesas yra identiškas naikinimo procesui, kai reikia apibrėžti įvykio ypatybių reikšmes skyriuje **Eksportuoti galutinio vartotojo asmenį galinčią identifikuoti informaciją (EUII)** . Be to, norėdami nurodyti eksportavimo paskirties vietą, **turėsite pateikti** „Azure blob storage" URL. „Azure Blob" URL turi [būti bendrai naudojamos prieigos parašas (SAS)](/azure/storage/common/storage-sas-overview).

Pažymėjus **Eksportuoti** visi dabartinės komandos įvykiai, kuriuose yra sutampančių formatavimo ypatybės, bus eksportuojami CSV formatu į eksportavimo paskirties vietą.

### <a name="good-practices"></a>Gerosios praktikos

* Stenkitės nesiunčiami įvykiai, kuriuose yra asmeninių duomenų.
* Jei reikia siųsti įvykius, kuriuose yra EUII duomenų, apribokite įvykių ir įvykių ypatybėse, kuriose yra EUII duomenys, skaičių. Geriausia, apriboti save iki vieno tokio įvykio.
* Įsitikinkite, kad kiek įmanoma mažiau žmonių turėtų prieigą prie išsiųstų asmeninių duomenų.
* Užtikrinkite, kad įvykiams, kuriuose yra asmeninių duomenų, būtų nustatyta viena ypatybė, išsiųsdami unikalų identifikatorių, kurį galima lengvai susieti su konkrečiu vartotojui (pvz., vartotojo ID). Taip lengviau perskirstyti duomenis ir eksportuoti arba panaikinti teisingus duomenis.
* Pažymėkite tik vieną įvykio ypatybę, kurioje yra asmeninių duomenų. Geriausia, kai turi tik unikalų identifikatorių.
* Nežymkite žymių, kuriose yra iose reikšmių (pvz., visos užklausos tekstas). Nustatant, kuriuos įvykius naikinti arba eksportuoti, įtraukimo įžvalgų funkcija naudoja tikslų eilutės gretinimą.

[!INCLUDE[footer-include](includes/footer-banner.md)]