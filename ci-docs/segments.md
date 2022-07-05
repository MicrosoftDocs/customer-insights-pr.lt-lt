---
title: Segmentų apžvalga
description: Segmentų apžvalga ir jų kūrimo bei valdymo informacija.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 8b2c2f9b84bf8b7f37d1468b871946ecb3e6aa98
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050957"
---
# <a name="segments-overview"></a>Segmentų apžvalga

Segmentai leidžia jums grupuoti jūsų klientus pagal demografiją, perlaidas ar elgesio savybes. Norėdami pasiekti verslo tikslus, galite naudoti segmentus, kad tikslingai vykdytumėte reklamines kampanijas, pardavimo veiklas ir klientų aptarnavimo veiksmus.

Klientų profiliai, atitinkantys segmento apibrėžties filtrus, yra vadinami segmento *nariais*. Kai kurie [paslaugų apribojimai](/dynamics365/customer-insights/service-limits) yra taikomi.

## <a name="create-a-new-segment"></a>Sukurkite naują segmentą

Naują segmentą galima sukurti keliais būdais: 

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

- Sudėtingas segmentas su segmentų kūrimo įrankiu: [Kurkite savo](segment-builder.md#create-a-new-segment) 
- Paprasti segmentai su vienu operatoriumi: [Spartusis segmentas](segment-builder.md#quick-segments) 
- Dirbtiniu intelektu pagrįstas būdas rasti panašius klientus: [Panašūs klientai](find-similar-customer-segments.md) 
- Dirbtiniu intelektu pagrįsti pasiūlymai, paremti priemonėmis arba atributais: [Siūlomi segmentai priemonių patobulinimui](suggested-segments.md) 
- Pasiūlymai, pagrįsti veiklomis: [Siūlomi segmentai, pagrįsti kliento veikla](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

- Sudėtingas segmentas su segmentų kūrimo įrankiu: [Kurkite savo](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Esamų segmentų tvarkymas

Eikite į **puslapį Segmentai**, kad peržiūrėtumėte visus išsaugotus segmentus ir juos tvarkytumėte.

Kiekvieną segmentą atitinka eilutė, kurioje pateikta papildoma informacija apie segmentą.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Pažymėtas segmentas su parinkčių išplečiamajame sąraše ir galimose parinktyse." lightbox="media/segments-selected-segment.png":::

Pasirinkus segmentą, galimi šie veiksmai:

- **Peržiūrėti** segmento išsamią informaciją, įskaitant narių skaičių, tendencijas ir segmento narių peržiūrą.
- **Atsisiųsti** narių sąrašą kaip .CSV failą.
- **Redaguoti** segmentą ir pakeisti jo ypatybes.
- **Kurti dublikatą** segmentui. Galite iš karto pasirinkti redaguoti jo ypatybes arba išsaugoti dublikatą.
- **Atnaujinti** segmentą, kad būtų įtraukti naujausi duomenys.
- **Aktyvinti** arba **Išjungti** segmentą. Neaktyvių segmentų aprašas yra, bet į jį dar neįtraukta klientų. Aktyvus segmentas ieško klientų, atitinkančių segmento apibrėžimą. Jei [suplanuotas atnaujinimas](system.md#schedule-tab) yra sukonfigūruotas, neaktyvių segmentų **Būsena** nurodoma kaip **Praleista** – tai reiškia, kad net nebuvo bandyta atnaujinti. Suaktyvinus neaktyvų segmentą, jis bus atnaujintas ir įtrauktas į suplanuotus atnaujinimus.
  Taip pat galite naudoti funkciją **Planuoti vėliau**, esančią iškleidžiamajame meniu **Aktyvinti / išjungti**, kad nurodytumėte būsimą datą ir laiką, kada reikia aktyvinti ir išjungti tam tikrą segmentą.
- **[Raskite panašių klientų](find-similar-customer-segments.md)** iš segmento.
- **Pervardyti** segmentą.
- **Žymė**, skirta [segmento žymoms](work-with-tags-columns.md#manage-tags) tvarkyti.
- **Atsisiųsti** narių sąrašą kaip .CSV failą.
- **Valdykite eksportavimus**, kad pamatytumėte susijusius segmentus ir juos valdytumėte. [Sužinokite daugiau apie eksportavimus.](export-destinations.md)
- **Naikinti** segmentą.
- **Stulpeliai**, skirti [tinkinti rodomus stulpelius](work-with-tags-columns.md#customize-columns).
- **Filtruokite**, kad filtruotumėte [žymes](work-with-tags-columns.md#filter-on-tags).
- **Ieškokite pavadinimo**, kad galėtumėte ieškoti pagal segmento pavadinimą.

## <a name="refresh-segments"></a>Segmentų atnaujinimas

Visus segmentus galite atnaujinti vienu metu pažymėdami **Atnaujinti viską** puslapyje **Segmentai** arba galite atnaujinti vieną ar kelis segmentus, kai juos pažymite ir parinktyse pasirenkate **Atnaujinti**. Taip pat galite sukonfigūruoti pasikartojantį atnaujinimą dalyje **Administravimas** > **Sistemas** > **Planuoti**. Sukonfigūravus pasikartojantį atnaujinimą, taikomos šios taisyklės:

- Visi segmentai su dinaminio arba **išplėtimo** tipu **bus** automatiškai atnaujinti nustatytu dažniu. Kai atnaujinimas bus baigtas, **būsena** nurodo, ar buvo kokių nors problemų atnaujinant segmentą. Paskutinis **atnaujintas** rodo paskutinio sėkmingo atnaujinimo laiko žymą. Jei įvyksta klaida, pasirinkite klaidą, kad pamatytumėte išsamią informaciją apie tai, kas įvyko.
- Segmentai, kurių tipas **Statinis** *, nebus* atnaujinami automatiškai. Paskutiniame **atnaujintame ekrane** rodoma paskutinio karto, kai statiniai segmentai buvo paleisti arba atnaujinti rankiniu būdu, laiko žyma.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Eksportuokite segmentus

Galite eksportuoti segmentą iš segmentų arba [eksportavimo puslapio](export-destinations.md). 

1. Eikite į puslapį **Segmentai**.

1. Pasirinkite segmento, kurį norite eksportuoti, vertikalią daugtaškį (&vellip;).

1. Veiksmų **išplečiamajame srąraše** pasirinkite Valdyti eksportą.

1. Atidaromas **Segmento eksportavimai (peržiūra)** puslapis. Galite matyti visus sukonfigūruotus eksportus, sugrupuotus pagal tai, ar juose yra dabartinis segmentas, ar ne.

   1. Jei pažymėtą segmentą norite įtraukti į eksportavimą, **redaguokite** atitinkamą eksportavimą, kad pažymėtumėte atitinkamą segmentą, tada įrašykite. Atskirų klientų aplinkose galite pasirinkti eksportą sąraše ir pasirinkti **Įtraukti segmentą**, kad pasiektumėte tą patį rezultatą.

   1. Jei norite sukurti naują eksportavimą su pažymėtu segmentu, pasirinkite **Įtraukti eksportavimą**. Daugiau informacijos apie eksportavimo kūrimą rasite [Naujo eksportavimo nustatymas](export-destinations.md#set-up-a-new-export).

1. Pasirinkite **Atgal**, kad grįžtumėte į pagrindinį segmentų puslapį.

## <a name="track-usage-of-a-segment"></a>Segmento naudojimo takelis

Jei programose naudojate segmentus, pagrįstus ta pačia Microsoft Dataverse organizacija, kuri yra susieta su "Customer Insights", galite sekti segmento naudojimą. " [Customer Insights" segmentuose, naudojamuose "Dynamics 365 Marketing"](/dynamics365/marketing/real-time-marketing-ci-profile) klientų veiklos cikluose, sistema informuoja jus apie to segmento naudojimą.

Redaguojant segmentą, kuris naudojamas "Customer Insights" aplinkoje arba "Marketing" klientų veiklos ciklas, segmento [kūrimo priemonės](segment-builder.md) reklamjuostė informuoja apie priklausomybes. Išsamią priklausomybės informaciją galite patikrinti tiesiai iš reklamjuostės arba segmento **kūrimo priemonėje pasirinkę Naudojimas**.

Segmento **naudojimo** srityje rodoma išsami informacija apie šio segmento naudojimą programomis, pagrįstomis Dataverse programomis. Jei segmentai naudojami klientų veiklos cikluose, rasite saitą, kad galėtumėte patikrinti veiklos ciklą programoje "Marketing", kur naudojamas šis segmentas. Jei turite leidimus pasiekti programą "Marketing", daugiau informacijos galite pasiekti ten.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Šoninė sritis su išsamia informacija apie segmento naudojimą segmento kūrimo priemonėje.":::

Sistema informuoja jus apie stebimo segmento naudojimą, kai bandote jį ištrinti. Jei segmentas, kurį ketinate panaikinti, bus naudojamas klientų veiklos ciklas programoje "Marketing", ši kelionė bus sustabdyta visiems segmento vartotojams. Jei kelionė yra rinkodaros kampanijos dalis, ištrynimas turės įtakos pačiai kampanijai. Tačiau vis tiek galite ištrinti segmentą, nepaisant įspėjimų.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialogo langas, skirtas patvirtinti segmento naikinimą, kai segmentas naudojamas Dataverse programoje.":::

### <a name="supported-apps"></a>Palaikomos programos

Naudojimas šiuo metu stebimas šiose Dataverse programose:

- [Klientų veiklos ciklai programoje "Dynamics 365 Marketing"](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="view-processing-history-and-segment-members"></a>Apdorojimo retrospektyvos ir segmento narių peržiūra

Konsoliduotus duomenis apie segmentą galite peržiūrėti peržiūrėdami išsamią informaciją.

Puslapyje **Segmentai** pažymėkite segmentą, kurį norite peržiūrėti.

Viršutinėje puslapio dalyje yra tendencijos diagrama, vaizduojanti narių skaičiaus pokyčius. Nukreipkite žymiklį virš duomenų taškų ir peržiūrėkite narių skaičių tam tikra data.

Galite atnaujinti vizualizacijos laiko tarpą.

> [!div class="mx-imgBorder"]
> ![Segmento laiko diapazonas.](media/segment-time-range.png "Segmento laiko diapazonas")

Apatinėje dalyje yra segmento narių sąrašas.

> [!NOTE]
> Šiame sąraše pateikiami laukai grindžiami jūsų segmento objektų atributais.
>
>Šiame sąraše rodomi sutampantys segmento nariai ir pirmieji 100 jūsų segmento įrašai, kad galėtumėte greitai jį įvertinti ir peržiūrėti apibrėžimus, jei to reikia. Norėdami peržiūrėti visu sutampančius įrašus, turite [eksportuoti segmentą](export-destinations.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
