---
title: Auditorijos įžvalgų segmentai
description: Segmentų apžvalga ir jų kūrimo bei valdymo informacija.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a7fa6515bd6e79dedfb21aa0f0b8e24b873a6771
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034022"
---
# <a name="segments-overview"></a>Segmentų apžvalga

Segmentai leidžia jums grupuoti jūsų klientus pagal demografiją, perlaidas ar elgesio savybes. Norėdami pasiekti verslo tikslus, galite naudoti segmentus, kad tikslingai vykdytumėte reklamines kampanijas, pardavimo veiklas ir klientų aptarnavimo veiksmus.

Klientų profiliai, atitinkantys segmento apibrėžties filtrus, yra vadinami segmento *nariais*. Kai kurie [paslaugų apribojimai](service-limits.md) yra taikomi.

## <a name="create-a-new-segment"></a>Sukurkite naują segmentą

Naują segmentą galima sukurti keliais būdais: 

- Sudėtinis segmentas naudojant segmentų kūrimo priemonę [Tuščias segmentas](segment-builder.md#create-a-new-segment)
- Paprasti segmentai su vienu operatoriumi: [Spartusis segmentas](segment-builder.md#quick-segments)
- Dirbtiniu intelektu pagrįstas būdas rasti panašius klientus: [Panašūs klientai](find-similar-customer-segments.md)
- Dirbtiniu intelektu pagrįsti pasiūlymai, paremti priemonėmis arba atributais: [Siūlomi segmentai priemonių patobulinimui](suggested-segments.md)
- Pasiūlymai, pagrįsti veiklomis: [Siūlomi segmentai, pagrįsti kliento veikla](suggested-segments-activity.md)

## <a name="get-insights-on-existing-segments"></a>Gaukite įžvalgas apie esamus segmentus

Atraskite papildomos informacijos apie jūsų esamus segmentus naudodami [Segmentų įžvalgas](segment-insights.md). Sužinokite, kas išskiria du segmentus, ar ką jie turi bendro.

## <a name="find-similar-customers"></a>Rasti panašių klientų

Suraskite klientus, panašius į pasirinkto segmento narius, naudodami dirbtinį intelektą. Daugiau informacijos rasite [panašūs klientai](find-similar-customer-segments.md).

## <a name="manage-existing-segments"></a>Esamų segmentų tvarkymas

Eikite į **Segmentų** puslapį, kad peržiūrėtumėte visus savo įrašytus segmentus ir juos valdytumėte.

Kiekvieną segmentą atitinka eilutė, kurioje pateikta papildoma informacija apie segmentą.

> [!div class="mx-imgBorder"]
> ![Esamo segmento valdymo parinktys](media/segments-selected-segment.png "Esamo segmento valdymo parinktys")

Pasirinkus segmentą pasiekiami toliau nurodyti veiksmai.

- **Peržiūrėti** segmento išsamią informaciją, įskaitant narių skaičių, tendencijas ir segmento narių peržiūrą.
- **Redaguoti** segmentą ir pakeisti jo ypatybes.
- **Kurti dublikatą** segmentui. Galite iš karto pasirinkti redaguoti jo ypatybes arba tiesiog įrašyti dublikatą.
- **Atnaujinti** segmentą, kad būtų įtraukti naujausi duomenys.
- **Aktyvinti** arba **Išjungti** segmentą. Segmentai turi dvi galimas būsenas – aktyvią arba neaktyvią. Šios būsenos yra naudingos redaguojant segmentą. Neaktyvių segmentų aprašas yra, bet į jį dar neįtraukta klientų. Suaktyvinus segmentą, jo būsena keičiasi iš neaktyvios į aktyvią, ir jis pradeda ieškoti klientų, atitinkančių segmento aprašą. Jei [suplanuotas atnaujinimas](system.md#schedule-tab) yra sukonfigūruotas, neaktyvių segmentų **Būsena** nurodoma kaip **Praleista** – tai reiškia, kad net nebuvo bandyta atnaujinti. Suaktyvinus neaktyvų segmentą, jis bus atnaujintas ir įtrauktas į suplanuotus atnaujinimus.
  Taip pat galite naudoti funkciją **Planuoti vėliau**, esančią iškleidžiamajame meniu **Aktyvinti / išjungti**, kad nurodytumėte būsimą datą ir laiką, kada reikia aktyvinti ir išjungti tam tikrą segmentą.
- **Pervardyti** segmentą.
- **Atsisiųsti** narių sąrašą kaip .CSV failą.
- Parinktis **Įtraukti į** siunčia klientų ID sąrašą į segmentą apdoroti kitoje programoje.
- **Naikinti** segmentą.

## <a name="refresh-segments"></a>Segmentų atnaujinimas

Visus segmentus galite atnaujinti vienu metu pažymėdami **Atnaujinti viską** puslapyje **Segmentai** arba galite atnaujinti vieną ar kelis segmentus, kai juos pažymite ir parinktyse pasirenkate **Atnaujinti**. Taip pat galite sukonfigūruoti pasikartojantį atnaujinimą dalyje **Administravimas** > **Sistemas** > **Planuoti**.

> [!TIP]
> Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams. Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies). Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą. Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.

## <a name="view-processing-history-and-segment-members"></a>Apdorojimo retrospektyvos ir segmento narių peržiūra

Konsoliduotus duomenis apie segmentą galite peržiūrėti peržiūrėdami išsamią informaciją.

Puslapyje **Segmentai** pažymėkite segmentą, kurį norite peržiūrėti.

Viršutinėje puslapio dalyje yra tendencijos diagrama, vaizduojanti narių skaičiaus pokyčius. Nukreipkite žymiklį virš duomenų taškų ir peržiūrėkite narių skaičių tam tikra data.

Galite atnaujinti vizualizacijos laiko tarpą.

> [!div class="mx-imgBorder"]
> ![Segmento laiko diapazonas](media/segment-time-range.png "Segmento laiko diapazonas")

Apatinėje dalyje yra segmento narių sąrašas.

> [!NOTE]
> Šiame sąraše pateikiami laukai grindžiami jūsų segmento objektų atributais.
>
>Šiame sąraše rodomi sutampantys segmento nariai ir pirmieji 100 jūsų segmento įrašai, kad galėtumėte greitai jį įvertinti ir peržiūrėti apibrėžimus, jei to reikia. Norėdami peržiūrėti visu sutampančius įrašus, turite [eksportuoti segmentą](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
