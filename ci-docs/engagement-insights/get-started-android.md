---
title: Pradėkite dirbti su „Android“ SDK
description: Sužinokite, kaip asmeniniams poreikiams pritaikyti ir paleisti „Android“ SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036928"
---
# <a name="get-started-with-the-android-sdk"></a>Pradėkite dirbti su „Android“ SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Šis mokymo programa padės jums sukonfigūruoti savo programą naudojant „Android“ programą su „Dynamics 365 Customer Insights“ įsitraukimo įžvalgos SDK. Įvykius portale pradėsite matyti po penkių minučių arba anksčiau.

## <a name="configuration-options"></a>Konfigūracijos parinktys
Per pateiktą failą į SDK galima perduoti šias konfigūravimo parinktis:

- **prarijimo raktas**: prarijimo raktas, naudojamas į projektą siųsti į darbo aplinką.

## <a name="prerequisites"></a>Būtinosios sąlygos

- „Android Studio”

- Minimalus „Android“ API lygis: 16 („Jelly Bean")

- Prarijimo raktas (žr. toliau pateiktas instrukcijas, kaip jį gauti)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>1 veiksmas. SDK integravimas į taikomąją programą
Pradėkite procesą pasirinkdami darbo sritį, kurioje norite dirbti, pažymėdami „Android“ mobilią platformą ir atsisiųskite „Android“ SDK.

- Kairiojoje naršymo srityje naudokite darbo srities perjungiklį ir pasirinkite savo darbo sritį.

- Jei neturite esamos darbo srities, pažymėkite Nauja darbo sritis ir, norėdami **sukurti naują** darbo sritį, [atlikite veiksmus](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>2 veiksmas. Konfigūruoti SDK

1. Sukūrę darbo sritį, eikite į **Administratorius** > **Darbo sritis** ir tada rinkitės **Diegimo vadovas**. 

1. Atsisiųskite [įsitraukimo įžvalgas „Android“ SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) ir padėkite `eiandroidsdk-debug.aar` failą į `libs` katalogą.

1. Atidarykite savo projekto lygio failą `build.gradle` ir įtraukite šiuos fragmentus:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Nustatykite įtraukimo įžvalgų SDK konfigūraciją naudodami `AndroidManifest.xml` failą, esantį `manifests` aplanke. 
1. Nukopijuokite XML fragmentas iš **diegimo vadovo**. `Your-Ingestion-Key` Jis turėtų būti automatiškai įvedamas į lauką.

   > [!NOTE]
   > Skyriaus keisti `${applicationId}` nereikia. Jis automatiškai įvedamas į lauką.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Įjunkite arba išjunkite automatinį įvykių peržiūros fiksavimą `View` ustatydami pirmiau nurodytą `autoCapture` lauką į `true` ar `false`.

1. (pasirinktinis) Kitos konfigūracijos, pvz., galinių punktų išseksavimo URL nustatymas. Juos galima įtraukti po prarijus pagrindiniais `AndroidManifest.xml` metaduomenimis:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>3 veiksmas. Inicijuoti SDK iš „MainActivity“ 

Kai inicijuojate SDK, galite dirbti su įvykiais ir jų ypatybes MainActivity aplinkoje.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Visų įvykių ypatybių nustatyti (pasirinktinai)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Konteksto įvykio ypatybėse palaikomi šie tipai:
- String
- Data
- Dviguba
- Ilgas
- Bulio logikos
- UUID

### <a name="track-an-event"></a>Sekti įvykį

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Įvykio vartotojo išsamios informacijos rinkinys (pasirenkamas)

SDK leidžia apibrėžti vartotojo informaciją, kurią galima siųsti su kiekvienu įvykiu. Galite nurodyti vartotojo informaciją iškviesite `setUser(user: User)` API `Analytics` lygyje.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Duomenų `User` klasėje yra šios eilutės ypatybės:

- **„localId“**: vartotojo vietinis ID.
- **„authId“** : autentifikuotas vartotojo ID.
- **authType**: autentifikavimo tipas, naudojamas autentifikuoto vartotojo ID gauti.
- **vardas**: Vartotojo vardas.
- **el. paštas**: Vartotojo el. pašto adresas.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
