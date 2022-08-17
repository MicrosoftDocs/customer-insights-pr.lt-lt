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
ms.openlocfilehash: 195a7c733f047c24f9f47a151c1cb623fe34d055
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246303"
---
# <a name="segments-overview"></a>Segmentų apžvalga

Segmentai leidžia jums grupuoti jūsų klientus pagal demografiją, perlaidas ar elgesio savybes. Norėdami pasiekti verslo tikslus, galite naudoti segmentus, kad tikslingai vykdytumėte reklamines kampanijas, pardavimo veiklas ir klientų aptarnavimo veiksmus.

Klientų profiliai, atitinkantys segmento aprašo filtrus, *vadinami segmento nariais*. Kai kurie [paslaugų apribojimai](/dynamics365/customer-insights/service-limits) yra taikomi.

## <a name="create-a-segment"></a>Kurti segmentą

Pasirinkite, kaip sukurti segmentą pagal tikslinę auditoriją.

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

- Sudėtingi segmentai su segmentų kūrimo priemone: [sukurkite savo](segment-builder.md)
- Paprasti segmentai su vienu operatoriumi: [Spartusis segmentas](segment-quick.md)
- Dirbtiniu intelektu pagrįstas būdas rasti panašius klientus: [panašūs klientai](find-similar-customer-segments.md)
- Dirbtiniu intelektu pagrįsti pasiūlymai, pagrįsti matais arba atributais: [siūlomi segmentai pagal matus](suggested-segments.md)
- Pasiūlymai, pagrįsti veiklomis: [Siūlomi segmentai, pagrįsti kliento veikla](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

- Paprasti arba sudėtingi segmentai su segmentų kūrimo priemone: [sukurkite savo](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Esamų segmentų tvarkymas

Eikite **į puslapį Segmentai** ir peržiūrėkite sukurtus segmentus, jų būseną ir būseną, narių skaičių ir paskutinį kartą, kai duomenys buvo atnaujinti. Galite rūšiuoti segmentų sąrašą pagal bet kurį stulpelį arba naudoti ieškos lauką, kad rastumėte segmentą, kurį norite tvarkyti.

Pasirinkite segmentą, kad peržiūrėtumėte galimus veiksmus.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Pažymėtas segmentas su parinkčių išplečiamajame sąraše ir galimose parinktyse." lightbox="media/segments-selected-segment.png":::

- [**Peržiūrėkite**](#view-segment-details) išsamią segmento informaciją, įskaitant narių skaičiaus tendencijas ir segmento narių peržiūrą.
- **Atsisiųsti** narių sąrašą kaip .CSV failą.
- **Redaguoti** segmentą ir pakeisti jo ypatybes.
- **Kurti dublikatą** segmentui. Galite iš karto pasirinkti redaguoti jo ypatybes arba išsaugoti dublikatą.
- [**Atnaujinkite**](#refresh-segments) segmentą, kad įtrauktumėte naujausius duomenis.
- **Aktyvinti** arba **Išjungti** segmentą. Neaktyvūs segmentai nebus atnaujinti suplanuoto atnaujinimo [metu](schedule-refresh.md), o **būsena** bus nurodyta kaip **Praleista**, o tai rodo, kad atnaujinti net nebuvo bandyta. Aktyvūs segmentai atnaujinami atsižvelgiant į jų tipą: statinį arba dinaminį.
- **Padarykite statinį** arba **Padarykite dinamišką** segmento tipą. Statiniai segmentai turi būti atnaujinami rankiniu būdu. Dinaminiai segmentai automatiškai atnaujinami atnaujinant sistemą.
- [**Raskite panašių klientų**](find-similar-customer-segments.md) iš segmento.
- **Pervardyti** segmentą.
- **Žymė**, skirta [segmento žymoms](work-with-tags-columns.md#manage-tags) tvarkyti.
- [**Valdykite eksportą**](#export-segments), kad pamatytumėte su eksportu susijusius segmentus, ir juos valdykite. [Sužinokite daugiau apie eksportavimus.](export-destinations.md)
- **Naikinti** segmentą.
- **Stulpeliai**, skirti [tinkinti rodomus stulpelius](work-with-tags-columns.md#customize-columns).
- **Filtruokite**, kad filtruotumėte [žymes](work-with-tags-columns.md#filter-on-tags).
- **Ieškokite pavadinimo**, kad galėtumėte ieškoti pagal segmento pavadinimą.

## <a name="view-segment-details"></a>Peržiūrėkite išsamią segmento informaciją

**Puslapyje Segmentai** pasirinkite segmentą, kad peržiūrėtumėte apdorojimo istoriją ir segmento narius.

Viršutinėje puslapio dalyje yra tendencijos diagrama, vaizduojanti narių skaičiaus pokyčius. Nukreipkite žymiklį virš duomenų taškų ir peržiūrėkite narių skaičių tam tikra data. Pakeiskite vizualizacijos laiko tarpą.

:::image type="content" source="media/segment-time-range.png" alt-text="Segmento laiko diapazonas.":::

Apatinėje dalyje yra segmento narių sąrašas.

> [!NOTE]
> Šiame sąraše pateikiami laukai grindžiami jūsų segmento objektų atributais.
>
>Šiame sąraše rodomi sutampantys segmento nariai ir pirmieji 100 jūsų segmento įrašai, kad galėtumėte greitai jį įvertinti ir peržiūrėti apibrėžimus, jei to reikia. Norėdami peržiūrėti visus sutampančius įrašus, [eksportuokite segmentą](export-destinations.md).

## <a name="refresh-segments"></a>Segmentų atnaujinimas

Segmentus galima atnaujinti automatiniu grafiku arba atnaujinti rankiniu būdu pagal poreikį. Norėdami rankiniu būdu atnaujinti vieną ar daugiau segmentų, pažymėkite juos ir pasirinkite **Atnaujinti**.

Norėdami [suplanuoti automatinį atnaujinimą](schedule-refresh.md), eikite į **Administratoriaus** > **sistemos** > **tvarkaraštis**. Taikomos šios taisyklės:

- Visi segmentai su dinaminio arba **išplėtimo** tipu **bus** automatiškai atnaujinti nustatytu dažniu. Kai atnaujinimas bus baigtas, būsena **nurodo,** ar buvo kokių nors problemų atnaujinant segmentą. Paskutinis **atnaujintas** rodo paskutinio sėkmingo atnaujinimo laiko žymą. Jei įvyksta klaida, pasirinkite klaidą, kad pamatytumėte išsamią informaciją apie tai, kas įvyko.
- Segmentai, kurių tipas **Statinis** *, nebus* atnaujinami automatiškai. Paskutiniame **atnaujintame ekrane** rodoma paskutinio karto, kai statinis segmentas buvo paleistas arba atnaujintas rankiniu būdu, laiko žyma.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Eksportuokite segmentus

Eksportuokite segmentus į kitas programas, kad galėtumėte toliau naudoti duomenis. Eksportuokite segmentą iš segmentų puslapio arba eksportavimo [puslapio](export-destinations.md).

1. Eikite į **puslapį Segmentai** ir pasirinkite segmentą, kurį norite eksportuoti.

1. Pasirinkite **Tvarkyti eksportą**. Atidaromas **Segmento eksportavimai (peržiūra)** puslapis. Peržiūrėkite visus sukonfigūruotus eksportavimus, sugrupuotus pagal tai, ar juose yra dabartinis segmentas, ar ne.

   1. Jei pažymėtą segmentą norite įtraukti į eksportavimą, **redaguokite** atitinkamą eksportavimą, kad pažymėtumėte atitinkamą segmentą, tada įrašykite. Atskirų klientų aplinkose pasirinkite eksportą sąraše ir pasirinkite **Įtraukti segmentą**, kad pasiektumėte tą patį rezultatą.

   1. Jei norite sukurti naują eksportavimą su pažymėtu segmentu, pasirinkite **Įtraukti eksportavimą**. Daugiau informacijos apie eksportavimo kūrimą rasite [Naujo eksportavimo nustatymas](export-destinations.md#set-up-a-new-export).

1. Pasirinkite **Atgal**, kad grįžtumėte į pagrindinį segmentų puslapį.

## <a name="track-usage-of-a-segment"></a>Segmento naudojimo takelis

Jei programose naudojate segmentus, pagrįstus ta pačia Microsoft Dataverse organizacija, kuri yra susieta su "Customer Insights", galite sekti segmento naudojimą. " [Customer Insights" segmentuose, naudojamuose "Dynamics 365 Marketing"](/dynamics365/marketing/real-time-marketing-ci-profile) klientų veiklos cikluose, sistema informuoja jus apie to segmento naudojimą.

Redaguojant segmentą, kuris naudojamas "Customer Insights" aplinkoje arba "Marketing" klientų veiklos ciklas, segmento [kūrimo priemonės](segment-builder.md) reklamjuostė informuoja apie priklausomybes. Patikrinkite priklausomybės informaciją tiesiai iš reklamjuostės arba segmento kūrimo priemonėje pasirinkdami **Naudojimas**.

Segmento **naudojimo** srityje rodoma išsami informacija apie šio segmento naudojimą programomis, pagrįstomis Dataverse programomis. Jei segmentai naudojami klientų veiklos cikluose, rasite saitą, kad galėtumėte patikrinti veiklos ciklą programoje "Marketing", kur naudojamas šis segmentas. Jei turite leidimus pasiekti programą "Marketing", peržiūrėkite daugiau išsamios informacijos ten.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Šoninė sritis su išsamia informacija apie segmento naudojimą segmento kūrimo priemonėje.":::

Sistema informuoja jus apie stebimo segmento naudojimą, kai bandote jį ištrinti. Jei segmentas, kurį ketinate panaikinti, bus naudojamas klientų veiklos ciklas programoje "Marketing", ši kelionė bus sustabdyta visiems segmento vartotojams. Jei kelionė yra rinkodaros kampanijos dalis, ištrynimas turės įtakos pačiai kampanijai. Tačiau vis tiek galite ištrinti segmentą, nepaisant įspėjimų.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialogo langas, skirtas patvirtinti segmento naikinimą, kai segmentas naudojamas Dataverse programoje.":::

### <a name="supported-apps"></a>Palaikomos programos

Naudojimas šiuo metu stebimas šiose Dataverse programose:

- [Klientų veiklos ciklai programoje "Dynamics 365 Marketing"](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
