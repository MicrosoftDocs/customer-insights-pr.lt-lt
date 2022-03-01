---
title: Peržiūrėti kliento profilius
description: Gaukite bendrą jūsų suvienodintų kliento duomenų rodinį.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 433e6ceda0ec7827bd672cff40f895d7719561df
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896337"
---
# <a name="customer-profiles"></a>Klientų profiliai

**Klientų** puslapis rodo suderintą jūsų klientų rodinį pagrįstą profilio duomenimis gautais iš [visų duomenų šaltinių](data-sources.md). Klientų profiliai yra pasiekiami, tik [sukūrus sujungtą kliento objektą](data-unification.md). Įsitikinkite, kad užbaigėte duomenų sujungimo procesą, kad gautumėte geresnius klientų rodinius. Puslapyje taip pat galite ieškoti klientų.

Klientai gali būti asmenys arba organizacijos (peržiūra). Kiekvienas kliento arba organizacijos profilis atvaizduojamas plytele. Pasirinkite plytelę, kad sužinotumėte papildomos informacijos apie konkretų klientą arba organizaciją. Norėdami pamatyti papildomus įrašus, naudokite puslapio apačioje esančius skaidymo į puslapius valdiklius.

> [!div class="mx-imgBorder"] 
> ![B2C klientų profiliai](media/profiles-customers.png "B2C klientų profiliai")

Organizacijos (peržiūra)
> [!div class="mx-imgBorder"] 
> ![B2B klientų profiliai](media/profile-customers-b2b.png "B2B klientų profiliai")

> [!NOTE]
> Jei naršymo juostoje pasirinkus **Klientai** plytelės nerodomos, reikia, kad administratorius **ieškos ir filtro rodyklėje** [apibrėžtų bent vieną ieškomą atributą ](search-filter-index.md).

## <a name="search-for-customers"></a>Klientų paieška

Klientų galite ieškoti, į paieškos laukelį įvesdami vardą ar kokį nors kitą atributą. Paieška veikia tik kliento profilio objekte, sukurtame duomenų sujungimo proceso metu.

Turėdami administratoriaus teises, galite konfigūruoti paieškai pasiekiamus atributus, naudodami puslapį **Ieškos ir filtro rodyklė**. Daugiau informacijos rasite [Ieškos ir filtro rodyklės valdymas](search-filter-index.md).

## <a name="filter-customers"></a>Klientų filtravimas

Klientus galite filtruoti pagal kliento profilio objekto laukus. Panašiai kaip ir atliekant iešką, jūsų administratoriui pirmiausia reikės apibrėžti laukus kaip galimus filtruoti, naudojant puslapį **Ieškos ir filtro rodyklė**.

1. Pasirinkite **Filtruoti**  **Klientų** puslapyje.

2. Pažymėkite laukelius šalia atributų, pagal kuriuos norite filtruoti klientus.

   > [!div class="mx-imgBorder"] 
   > ![Klientų profiliai](media/profiles-customers3.png "Klientų profiliai")

3. Pašalinkite savo filtrus pasirinkę **Pašalinti filtrus** **Klientų** puslapyje.

##  <a name="customer-details-page"></a>Kliento informacijos puslapis

Pasirinkite bet kurias kliento plytas tam, kad atvertumėte **Kliento informacijos puslapį**. Šis rodinys apima suvienodintą informaciją pasirinktam klientui.

Kliento išsami informacija apima:

-   **Kliento profilio plyta:** Ši plyta rodo skirtingas vertes lyginant su suvienodintu kliento profilio objektu. Ši išsami informacija gali apimti el. pašto adresą, vardą, miestą ir t.t. 

-   **Galimi interesai, galimi prekės ženklai:** Rodo, ar jūs sukonfigūravote pirmosios šalies praturtinimą. Jis rodo galimus interesus ir panašumus su kliento turimais prekių ženklais su profiliu. Daugiau informacijos žr. [Klientų profilių papildymas prekių ženklų ir pomėgių panašumais](enrichment-microsoft.md).

-   **Priemonės:** Rodo, ar jūs sukonfigūravote vieną ar keletą priemonių konkrečiam tipui: kliento savybių priemonėms. Jos apima apskaičiuotą KPI pagal jūsų klientus individualiu kliento lygmeniu. Dėl daugiau informacijos, žr. [Nustatyti ir valdyti priemones](measures.md).

-   **Aktyvumo laiko juosta:** Rodo, ar konfigūravote veiklas. Laiko juostos rodinys turi chronologiškai surikiuotas šio kliento veiklas, pradedant su naujausia veikla. Norėdami gauti daugiau informacijos, žr. [Klientų veiklos](activities.md).

Pasirinkite **Atgal į klientus** norėdami grįžti į kliento paieškos puslapį.

## <a name="next-steps"></a>Tolesni veiksmai

[Daugiau duomenų šaltinių įtraukimas](data-sources.md) arba [Klientų segmentų kūrimas](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]