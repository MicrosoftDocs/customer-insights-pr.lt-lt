---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755554"
---
Prariję duomenis, pradėkite duomenų suvienijimo procesą, kad sukurtumėte vieningą kliento profilį. Dėl daugiau informacijos, žr. [Duomenų suvienodinimas](../data-unification.md).

### <a name="select-source-fields"></a>Pasirinkti šaltinio laukus

1. Suvartojus duomenis, sudarykite kontaktų žemėlapį iš e-komercijos ir lojalumo duomenų į bendrus duomenų tipus. Eikite į **"Data** > **Unify"**.

1. Pasirinkite objektus, kurie rodo kliento profilį – **e-komercijoskontaktai** ir **lojalumoklientai**.

   ![suvienodinti e-komercijos ir lojalumo duomenų šaltinius.](../media/unify-ecommerce-loyalty.png)

1. Pasirinkite **Kontakto ID** kaip pagrindinį raktą **e-komercijos kontaktus** ir **Lojalumo ID** kaip pirminį raktą **lojalumo klientams**.

1. Pasirinkite **Toliau**. Praleiskite pasikartojančius įrašus ir pasirinkite **Pirmyn**.

### <a name="match-conditions"></a>Rungtynių sąlygos

1. Pasirinkite **e-commerceContacts: e-commerce** kaip pagrindinį objektą ir įtraukite visus įrašus.

1. Pasirinkite **loyCustomers: LoyaltyScheme ir įtraukite** visus įrašus.

1. Įtraukite taisyklę:
   - Pasirinkite **FullName** tiek ecommerceContacts, tiek loyCustomers.
   - Norėdami normalizuoti, pasirinkite **Tipą** **(telefonas, vardas, adresas, ...).**
   - Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.
   - Įveskite **vardo FullName, El. paštas**.

1. Įtraukite antrą el. pašto adreso sąlygą:
   - Pasirinkite **El. paštas** tiek el. prekybaiContacts, tiek loyCustomers.
   - Palikite normalizavimą tuščią.
   - Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.

   ![Suvienodinkite atitikties taisyklę pavadinimui ir el. paštui.](../media/unify-match-rule.png)

1. Pasirinkite **Atlikta**.

1. Pasirinkite **Toliau**.

### <a name="unify-fields"></a>Suvienodinti laukus

1. Pervardykite objekto **"LuyCustomers**" ContactId **į** **ContactIdLOYALTY**, kad atskirtumėte jį nuo kitų prarytų ID.

1. Pasirinkite **Pirmyn**, kad peržiūrėtumėte, tada pasirinkite **Kurti klientų profilius**.
