---
title: Išplėstiniai žiniatinklio SDK scenarijai
description: Išplėstiniai scenarijai, į kuriuos reikia atsižvelgti pereinant prie savo svetainės su SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227208"
---
# <a name="advanced-web-sdk-instrumentation"></a>Išplėstinio žiniatinklio SDK integravimas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Šiame straipsnyje aprašomas išplėstinių scenarijų, į kuriuos reikia [atsižvelgti pereinant į žiniatinklio svetainę](instrument-website.md) su „Dynamics 365 Customer Insights“ įtraukimo įžvalgų galimybės SDK, metu.

## <a name="setting-user-details-for-your-event"></a>Įvykio vartotojo išsamios informacijos nustatymas

SDK leidžia apibrėžti vartotojo informaciją, kurią galima siųsti su kiekvienu įvykiu. Galite nurodyti vartotojo informaciją nuosavybėje pavadintoje `user` (tikėtini šios nuosavybės duomenys yra `IUser` objektas), panašus į `src`, `name`, ir `cfg` kodo fragmento konfigūravime.

`IUser`objekte yra šios eilutės ypatybės:

- **„localId“**: vartotojo vietinis ID.
- **„authId“** : autentifikuotas vartotojo ID.
- **„authType“**: autentifikavimo tipas, naudojamas autentifikuoto vartotojo ID gauti.
- **vardas**: Vartotojo vardas.
- **el. paštas**: Vartotojo el. pašto adresas.

Toliau pateiktame pavyzdyje rodoma kodo fragmentas vartotojo informacijos siuntimo informacija. Funkcijas, prieš kurias matote žvaigždutę * simbolį, pakeiskite ją savo pasirinktiniu diegimu:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Be to, iškviesite API, galite nurodyti vartotojo `setUser(user: IUser)` informaciją. Iškviestame `setUser` API telemetrijoje bus vartotojo informacija.

## <a name="adding-custom-properties-for-each-event"></a>Pasirinktinių kiekvieno įvykio ypatybės įtraukimas

SDK leidžia nurodyti kliento savybes, kurias galima siųsti su kiekvienu įvykiu. Pasirinktines ypatybes galite nurodyti kaip objektą, kuriame yra pagrindinių reikšmių porų (reikšmė gali būti tipo `string | number | boolean`). Objektą galite įtraukti į ypatybę, vadinamą  `props`, panašią į `src`, `name`, ir `cfg` į kodo fragmentas konfigūraciją.

Toliau pateiktame pavyzdyje rodomas kodo fragmentas, siunčiantis kliento ypatybes:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Be to, iškviesite API, galite nurodyti vartotojo ypatybes atskirai `setProperty(name: string, value: string | number | boolean)`.

## <a name="sending-custom-events"></a>Siųsti pasirinktinius įvykius

Naudodami SDK galite siųsti pasirinktinius įvykius. Turite nurodyti įvykį ir ypatybes, kurios bus siunčiamos su įvykiu, pavadinimą.

Toliau pateiktame pavyzdyje rodomas kodo fragmentas, sekantis kliento įvykį. „PAVADINIMAS" yra konfigūracijos `name` rakto fragmentas. Tai taip pat kintamojo pavadinimas lango objekte, į kurį įkeliamas SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
