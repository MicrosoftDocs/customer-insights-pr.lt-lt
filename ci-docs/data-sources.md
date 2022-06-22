---
title: Naudokite duomenų šaltinius duomenų suvartojimui
description: Sužinokite, kaip importuoti duomenis iš įvairių šaltinių.
ms.date: 05/31/2022
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
ms.openlocfilehash: e22977107565a0b28b74f41576a1c7ccc74f6dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011759"
---
# <a name="data-sources-overview"></a>Duomenų šaltinių apžvalga

Dynamics 365 Customer Insights teikia ryšius, kad gautų duomenis iš plataus šaltinių rinkinio. Prisijungimas prie duomenų šaltinio dažnai vadinamas *duomenų įtraukimo procesu*. Prariję duomenis, galite [suvienyti](data-unification.md), generuoti įžvalgas ir suaktyvinti duomenis, kad sukurtumėte suasmenintą patirtį.

## <a name="add-data-sources"></a>Duomenų šaltinių įtraukimas

Galite pridėti arba importuoti duomenų šaltinius į "Customer Insights". Toliau pateiktose nuorodose pateikiamos duomenų šaltinių pridėjimo instrukcijos.

**Pridėti duomenų šaltinis**

Jei turite duomenų, parengtų vienoje iš "Microsoft Azure" duomenų tarnybų, "Customer Insights" gali lengvai prisijungti prie duomenų šaltinis, iš naujo nenaudodama duomenų. Pažymėkite vieną iš šių parinkčių:
- [Azure Data Lake Storage(csv arba parketo failai aplanke "Common Data Model")](connect-common-data-model.md)
- [Azure Synapse Analytics(Ežerų duomenų bazės)](connect-synapse.md)
- [Microsoft Dataverse duomenų ežeras](connect-dataverse-managed-lake.md)

**Importuoti ir transformuoti**

Jei naudojate vietinius duomenų šaltinius, "Microsoft" arba trečiųjų šalių duomenis, importuokite ir transformuokite duomenis naudodami Power Query jungtis.
- [Power Query Jungtys](connect-power-query.md)

## <a name="review-data-sources"></a>Peržiūrėti duomenų šaltinius

Jei jūsų aplinka buvo sukonfigūruota naudoti "Customer Insights" saugyklą ir naudojate vietinius duomenų šaltinius, naudojate Power Platform duomenų srautus. Naudodami Power Platform duomenų srautus galite peržiūrėti bendrinamus duomenų šaltinius ir kitų valdomus duomenų šaltinius. Puslapyje **Duomenų šaltiniai** duomenų šaltiniai išvardijami trijuose skyriuose:
- **Bendrinama**: duomenų šaltiniai, kuriuos gali valdyti visi "Customer Insights" administratoriai. Power Platform duomenų srautai, jūsų pačių saugyklos abonementas ir pridėjimas Dataverse prie valdomo duomenų ežero yra bendrinamų duomenų šaltinių pavyzdžiai.
- **Valdo aš**: Power Platform duomenų srautai, kuriuos sukūrėte ir valdote tik jūs. Kiti "Customer Insights" administratoriai gali peržiūrėti tik šias duomenų sekas, bet jų neredaguoti, neatnaujinti ar panaikinti.
- **Valdo kiti**: Power Platform duomenų srautai, kuriuos sukūrė kiti administratoriai. Juos galite tik peržiūrėti. Jame išvardijamas duomenų srauto savininkas, su kuriuo reikia susisiekti dėl bet kokios pagalbos.
> [!NOTE]
> Visus objektus gali peržiūrėti ir naudoti kiti vartotojai. Nors duomenų šaltiniai priklauso juos sukūrusiam vartotojui, gautus objektus iš duomenų nurijimo gali naudoti kiekvienas "Customer Insights" vartotojas.

Jei jūsų aplinkoje duomenų srautai nenaudojami Power Platform, **puslapyje Duomenų šaltiniai** yra tik visų duomenų šaltinių sąrašas. Sekcijų nerodoma.

Eikite į **Duomenų** > **duomenų šaltinius**, kad peržiūrėtumėte kiekvieno praryto duomenų šaltinis pavadinimą, jo būseną ir paskutinį kartą, kai duomenys buvo atnaujinti tame šaltinyje. Galite rūšiuoti duomenų šaltinių sąrašą pagal kiekvieną stulpelį.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Įtrauktas duomenų šaltinis.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Duomenų įkėlimas gali užtrukti. Sėkmingai atnaujinus, galima peržiūrėti apdorotus duomenis puslapyje **Objektai**. Norėdami gauti daugiau informacijos, žr. [Objektai](entities.md).

## <a name="refresh-data-sources"></a>Duomenų šaltinių atnaujinimas

Duomenų šaltiniai gali būti paleisti iš naujo automatiniu grafiku arba rankiniu būdu pagal poreikį. [Vietiniai duomenų šaltiniai](connect-power-query.md#add-data-from-on-premises-data-sources) atnaujinami pagal savo tvarkaraščius, kurie nustatomi prarijus duomenis. Pridėtų duomenų šaltinių atveju duomenų nurijimas sunaudoja naujausius iš to duomenų šaltinis turimus duomenis.

Eikite į **Administravimo** > **sistemos** > [**tvarkaraštis**](system.md#schedule-tab), kad sukonfigūruotumėte sistemoje suplanuotus prarytų duomenų šaltinių atnaujinimus.

Norėdami paleisti iš naujo duomenų šaltinį pagal poreikį, atlikite šiuos veiksmus:

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite vertikalią daugtaškį (&vellip;) šalia duomenų šaltinis norite atnaujinti, ir išplečiamajame sąraše pasirinkite **Atnaujinti**. Šis duomenų šaltinis dabar yra įjungtas rankiniam paleidimui iš naujo. Atnaujinus duomenų šaltinį bus atnaujinta ir objekto schema, ir duomenys, skirti visiems duomenų šaltinyje nurodytiems objektams.

1. Pasirinkite **Stabdyti paleidimą iš naujo** jei norite atšaukti esantį paleidimą iš naujo ir duomenų šaltinis grįš į paskutinę paleidimo iš naujo būseną.

## <a name="delete-a-data-source"></a>Naikinti duomenų šaltinį

Duomenų šaltinis gali būti panaikintas tik tuo atveju, jei duomenys nenaudojami jokiame apdorojime, pvz., suvienijimo, įžvalgų, aktyvinimų ar eksportavimo.

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pasirinkite vertikalią daugtaškį (&vellip;) šalia duomenų šaltinis norite pašalinti, ir išplečiamajame meniu pasirinkite **Naikinti**.

3. Patvirtinkite šį naikinimą.


[!INCLUDE [footer-include](includes/footer-banner.md)]
