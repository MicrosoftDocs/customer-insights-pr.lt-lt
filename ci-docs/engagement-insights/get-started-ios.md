---
title: Pradėkite dirbti su „iOS“ SDK
description: Sužinokite, kaip asmeniniams poreikiams pritaikyti ir paleisti „iOS" SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e4d0555d2fc377fae62ff5db64c032fcebcb04
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226225"
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

- Sukūrę darbo sritį, eikite į **Administratorius** > **Darbo sritis** ir tada rinkitės **Diegimo vadovas**.

## <a name="configure-the-sdk"></a>Konfigūruoti SDK

Kai atsisiunčiate SDK, su juo galite dirbti naudodami Xcode, kad įjungtumėte ir apibrėžtumėte įvykius. Yra du būdai tai padaryti

### <a name="option-1-using-cocoapods-recommended"></a>1 parinktis: naudojant „CocoaPods” (rekomenduojama)
„CocoaPods” yra „Swift” ir „Objective-C Cocoa” projektų priklausomybės vadovas. Naudojant šią funkciją yra lengviau integruoti įtraukimo įžvalgų SDK, skirtų iOS. „CocoaPods” taip pat leidžia jums atnaujinti į naujausią įtraukimo įžvalgų SDK versiją. Štai kaip reikia naudoti „CocoaPods”, kad integruotumėte įtraukimo įžangų SDK į jūsų „Xcode” projektą. 

1. Įdiegti „CocoaPods”. 

1. Savo projekto šakninio katalogo viduje sukurkite naują failą, pavadintą „Podfile”, ir į jį įtraukite šiuos sakinius.Pakeiskite „YOUR_TARGET_PROJECT_NAME” jūsų „Xcode” projekto pavadinimu. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Aukščiau pateiktoje „pod” konfigūracijoje yra tiek SDK derinimo, tiek leidimo versijos. Pasirinkite, kuris iš jų geriausiai tinka jūsų projektui.

1. Įdiekite „pod” funkciją vykdydami šią komandą: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>2 parinktis: naudojant atsisiuntimo saitą

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
