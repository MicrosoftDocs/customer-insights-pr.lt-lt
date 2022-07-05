---
title: Duomenų šaltinių apžvalga
description: Sužinokite, kaip importuoti arba nuryti duomenis iš įvairių šaltinių.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051463"
---
# <a name="data-sources-overview"></a>Duomenų šaltinių apžvalga

Dynamics 365 Customer Insights teikia ryšius, kad būtų galima gauti duomenis iš plataus šaltinių rinkinio. Prisijungimas prie duomenų šaltinio dažnai vadinamas *duomenų įtraukimo procesu*. Prariję duomenis, galite [suvienodinti](data-unification.md), generuoti įžvalgas ir suaktyvinti duomenis, kad sukurtumėte suasmenintas funkcijas.

## <a name="add-data-sources"></a>Duomenų šaltinių įtraukimas

Duomenų šaltinius galite pridėti arba importuoti į "Customer Insights". Toliau pateiktose nuorodose pateikiamos duomenų šaltinių pridėjimo instrukcijos.

**Pritvirtinkite duomenų šaltinis**

Jei turite duomenų, paruoštų vienoje iš "Microsoft Azure" duomenų paslaugų, "Customer Insights" gali lengvai prisijungti prie duomenų šaltinis ir nereikia iš naujo nuryti duomenų. Pažymėkite vieną iš šių parinkčių:
- [Azure Data Lake Storage(csv arba parketo failai aplanke "Common Data Model")](connect-common-data-model.md)
- [Azure Synapse Analytics(Ežerų duomenų bazės)](connect-synapse.md)
- [Microsoft Dataverse duomenų ežeras](connect-dataverse-managed-lake.md)

**Importuokite ir transformuokite**

Jei naudojate vietinius duomenų šaltinius, "Microsoft" arba trečiųjų šalių duomenis, importuokite ir transformuokite duomenis naudodami Power Query jungtis.
- [Power Query Jungtys](connect-power-query.md)

## <a name="review-data-sources"></a>Duomenų šaltinių peržiūra

Jei jūsų aplinka buvo sukonfigūruota naudoti "Customer Insights" saugyklą ir naudojate vietinius duomenų šaltinius, naudojate Power Platform duomenų srautus. Naudodami Power Platform duomenų srautus galite peržiūrėti bendrinamus duomenų šaltinius ir kitų valdomus duomenų šaltinius. Puslapyje **Duomenų šaltiniai** duomenų šaltiniai pateikiami trijuose skyriuose:
- **Bendrinama**: duomenų šaltiniai, kuriuos gali valdyti visi "Customer Insights" administratoriai. Power Platform duomenų srautai, jūsų saugyklos paskyra ir pridėjimas prie Dataverse valdomo duomenų ežero yra bendrinamų duomenų šaltinių pavyzdžiai.
- **Valdou aš**: Power Platform duomenų srautus sukūrėte ir valdote tik jūs. Kiti "Customer Insights" administratoriai gali peržiūrėti tik šias duomenų srautus, bet jų neredaguoti, atnaujinti ar ištrinti.
- **Valdo kiti**: Power Platform duomenų srautai, kuriuos sukūrė kiti administratoriai. Galite tik juos peržiūrėti. Jame pateikiamas duomenų srauto savininkas, į kurį reikia kreiptis dėl bet kokios pagalbos.
> [!NOTE]
> Visus objektus gali peržiūrėti ir naudoti kiti vartotojai. Nors duomenų šaltiniai priklauso juos sukūrusiam vartotojui, gautus objektus, gautus dėl duomenų įtraukimo, gali naudoti kiekvienas "Customer Insights" vartotojas.

Jei jūsų aplinka nenaudoja Power Platform duomenų srautų, **puslapyje Duomenų šaltiniai** yra tik visų duomenų šaltinių sąrašas. Nerodomi skyriai.

Eikite į **Duomenų** > **duomenų šaltiniai**, kad peržiūrėtumėte kiekvieno praryto duomenų šaltinis pavadinimą, jo būseną ir paskutinį kartą, kai duomenys buvo atnaujinti tame šaltinyje. Galite rūšiuoti duomenų šaltinių sąrašą pagal kiekvieną stulpelį.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Įtrauktas duomenų šaltinis.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Duomenų įkėlimas gali užtrukti. Sėkmingai atnaujinus, galima peržiūrėti apdorotus duomenis puslapyje **Objektai**. Norėdami gauti daugiau informacijos, žr. [Objektai](entities.md).

## <a name="refresh-data-sources"></a>Duomenų šaltinių atnaujinimas

Duomenų šaltiniai gali būti paleisti iš naujo automatiniu grafiku arba rankiniu būdu pagal poreikį. [Vietoje esantys duomenų šaltiniai](connect-power-query.md#add-data-from-on-premises-data-sources) atnaujinami pagal savo tvarkaraščius, kurie nustatomi duomenų įsisavinimo metu. Pridedamų duomenų šaltinių atveju duomenų nurijimas sunaudoja naujausius duomenis, gautus iš to duomenų šaltinis.

Eikite į **administratoriaus** > **sistemos** > [**tvarkaraštį**](system.md#schedule-tab), kad sukonfigūruotumėte sistemos suplanuotus nurijusių duomenų šaltinių atnaujinimus.

Norėdami paleisti iš naujo duomenų šaltinį pagal poreikį, atlikite šiuos veiksmus:

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite vertikalią daugtaškį (&vellip;) šalia duomenų šaltinis norite atnaujinti, ir išskleidžiamajame sąraše pasirinkite **Atnaujinti**. Šis duomenų šaltinis dabar yra įjungtas rankiniam paleidimui iš naujo. Atnaujinus duomenų šaltinį bus atnaujinta ir objekto schema, ir duomenys, skirti visiems duomenų šaltinyje nurodytiems objektams.

1. Pasirinkite **Stabdyti paleidimą iš naujo** jei norite atšaukti esantį paleidimą iš naujo ir duomenų šaltinis grįš į paskutinę paleidimo iš naujo būseną.

## <a name="delete-a-data-source"></a>Naikinti duomenų šaltinį

Duomenų šaltinis galima panaikinti tik tuo atveju, jei duomenys nenaudojami jokiam apdorojimui, pvz., suvienijimui, įžvalgoms, aktyvinimui ar eksportui.

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pasirinkite vertikalią daugtaškį (&vellip;) šalia duomenų šaltinis norite pašalinti, ir išskleidžiamajame meniu pasirinkite **Ištrinti**.

3. Patvirtinkite šį naikinimą.


[!INCLUDE [footer-include](includes/footer-banner.md)]
