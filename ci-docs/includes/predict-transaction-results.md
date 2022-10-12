---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611131"
---
- **Mokymo modelio našumas**: A, B arba C klasės nurodo prognozė našumą ir gali padėti priimti sprendimą naudoti išvesties objekte saugomus rezultatus.

  Laipsniai nustatomi pagal šias taisykles:
  - **A** kai prognozės modelio tikslumas yra mažiausiai 50% visų prognozių ir kai prognozių tikslumo procentas klientams, kurie nutraukė, yra didesnis nei slenksčio lygis mažiausiai 10%.
  - **B** kai prognozės modelio tikslumas yra mažiausiai 50 % visų prognozių ir kai prognozių tikslumo procentas klientams, kurie nutraukė, yra iki 10% didesnis nei slenksčio lygis.
  - **C**, kai modelis tiksliai prognozavo mažiau nei 50 % visų prognozių arba kai tikslių prognozių procentas klientams, kurie prarado klientų skaičių, yra mažesnis už bazinį lygį.
  - **Bazinis lygis** paima modelio prognozė laiko lango įvestį (pvz., vieneri metai) ir sukuria skirtingas laiko dalis, padalijus ją iš 2, kol ji pasiekia vieną mėnesį ar mažiau. Jis naudoja šiuos tarpus, kad sukurtų verslo taisykles klientams, kurie neįsigijo jų šiuo laikotarpiu. Šie klientai laikomi atsisakę. Kaip bazinis modelis pasirenkamas laiku pagrįsta verslo taisyklė, turinti didžiausią gebėjimą nuspėti, kas gali nukentėti.

- **Praradimo tikimybė (klientų skaičius)**: Klientų grupės pagal prognozuojamą praradimo riziką. Pasirinktinai kurkite klientų [,](../prediction-based-segment.md) turinčių didelę praradimo riziką, segmentus. Tokie segmentai padeda suprasti, kokios turėtų būti priklausymo segmentui ribinės reikšmės.

- **Svarbiausi veiksniai**: Kuriant prognozę, atsižvelgiama į daugelį veiksnių. Visi faktoriai turi savo apskaičiuotą svarbą sujungtoms prognozėms, kurias sukuria modelis. Naudokite šiuos veiksnius, kad patikrintumėte prognozė rezultatus. Arba naudokite šią informaciją vėliau, kad sukurtumėte [segmentus](../prediction-based-segment.md), kurie galėtų padėti paveikti klientų praradimo riziką.