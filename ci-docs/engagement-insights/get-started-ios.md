---
title: Pradėkite dirbti su „iOS“ SDK
description: Sužinokite, kaip asmeniniams poreikiams pritaikyti ir paleisti „iOS" SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036883"
---
# <a name="get-started-with-the-ios-sdk"></a>Darbo pradžia su „iOS“ SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Šis mokymo programa padės jums sukonfigūruoti savo programą naudojant įtraukimo įžvalgų „Dynamics 365 Customer Insights“ „iOS“ SDK. Įvykius portale pradėsite matyti po penkių minučių arba anksčiau.

## <a name="configuration-options"></a>Konfigūracijos parinktys

Per pateiktą failą į SDK galima perduoti šias konfigūravimo `EIConfig.plist` parinktis:

- **prarijimo raktas**: prarijimo raktas, naudojamas į projektą siųsti įvykiams.
- **autocollectAction** : Bulio logikos reikšmė, skirta veiksmo įvykiui įjungti arba išjungti.
- **autocollectView** : Bulio logikos reikšmė, skirta veiksmo įvykiui peržiūrėti.
- **endpointUrl** : galinio punkto URL, kur bus nukreipti įvykiai.

## <a name="prerequisites"></a>Būtinosios sąlygos

- „Xcode“ versija 9+
- „iOS“ 8.2+ versija
- Prarijimo raktas (žr. toliau pateiktas instrukcijas)

## <a name="integrate-the-sdk-into-your-application"></a>SDK integravimas į taikomąją programą

Pradėkite procesą pasirinkdami darbo sritį, kurioje norite dirbti, pažymėdami „iOS Mobile" platformą ir atsisiųskite SDK.

- Kairiojoje naršymo srityje naudokite darbo srities perjungiklį ir pasirinkite savo darbo sritį.

- Jei neturite esamos darbo srities, pažymėkite Nauja darbo sritis ir, norėdami **sukurti naują** darbo sritį, [atlikite veiksmus](create-workspace.md).

## <a name="configure-the-sdk"></a>Konfigūruoti SDK

Kai atsisiunčiate SDK, su juo galite dirbti naudodami Xcode, kad įjungtumėte ir apibrėžtumėte įvykius.

1. Sukūrę darbo sritį, eikite į **Administratorius** > **Darbo sritis** ir tada rinkitės **Diegimo vadovas**.

1. Atsisiųskite [įtraukimo įžvalgų „iOS" SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) ir perkelkite failą į `EIObjC.xcframework` failą `Frameworks` aplanką.

1. Jei „`Frameworks`“ aplanko nėra, jį sukurkite projekto aplanke.

## <a name="enable-auto-instrumentation"></a>Įjungti automatinį persodinimą
 
Automatinę persodinimo funkciją galima įjungti nerašant kodavimo. Paleidus projektą jis automatiškai seka įvykius ir `view` ir `action` įvykius naudodamas sukonfigūruotą nurijimo raktą. 

1. Atnaujinkite toliau nurodytų `EIConfig.plist`l aukų pateiktą failą ir įtraukite į savo projektų katalogų aplanką:
    - Prarijimo raktas = `"Your-Ingestion-Key"`
    - autocollectView = TAIP
    - autocollectAction = TAIP

2. Tada į `EIConfig.plist` projektą įtraukite failą į Xcode. 



Norėdami išjungti automatinius instrumentus, naujinkite tolesnius laukelius įtrauktus į `EIConfig.plist` failą į Jūsų projekto aplanką. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Pasirinktinių įvykių diegimas

1. Atverkite savo projektą „Xcode“ ir naršykite į **Bendri** nustatymus. 
1. Įtraukite `EIObjC.xcframework` į projektą skyriuje Sistemos, Bibliotekos ir Įdėtasis turinys.

1. Importuokite sistemos antraštės failą „AppDelegate.m“ su šiuo fragmentu:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inicijuoti įsitraukimo įžvalgas SDK iš programos: didFinishLaunchingWithOptions.
1. Nukopijuokite XML fragmentas iš **diegimo vadovo**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Sekti įvykį:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Įvykio vartotojo išsamios informacijos rinkinys

SDK leidžia apibrėžti vartotojo informaciją, kurią galima siųsti su kiekvienu įvykiu. Galite nurodyti vartotojo informaciją iškviesite `setUser:(nonnull EIUser *)user` API SDK.

Vartotojo išsamios informacijos nurodymas „`Analytics`“ lygyje reiškia, kad visa telemetruose turės šią informaciją. Tačiau, jei nurodysite įvykio lygiu iškviesite `setUser:(nonnull EIUser *)user` API EIEvent objekte, informacija bus pateikta tik šiame konkrečiame įvykyje.

Duomenų `EIUser` klasėje yra šios NSString ypatybės:

- **„localId“**: vartotojo vietinis ID.
- **„authId“** : autentifikuotas vartotojo ID.
- **„authType“**: autentifikavimo tipas, naudojamas autentifikuoto vartotojo ID gauti.
- **vardas**: Vartotojo vardas.
- **el. paštas**: Vartotojo el. pašto adresas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
