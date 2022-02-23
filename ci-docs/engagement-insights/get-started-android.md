---
title: Pradėkite dirbti su „Android“ SDK
description: Sužinokite, kaip asmeniniams poreikiams pritaikyti ir paleisti „Android“ SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 71ec4841303bd17d3f605547be8d6032c58a7b21
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977585"
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

## <a name="integrate-the-sdk-into-your-application"></a>SDK integravimas į taikomąją programą
Pradėkite procesą pasirinkdami darbo sritį, kurioje norite dirbti, pažymėdami „Android“ mobilią platformą ir atsisiųskite „Android“ SDK.

- Kairiojoje naršymo srityje naudokite darbo srities perjungiklį ir pasirinkite savo darbo sritį.

- Jei neturite esamos darbo srities, pažymėkite Nauja darbo sritis ir, norėdami **sukurti naują** darbo sritį, [atlikite veiksmus](create-workspace.md).

- Sukūrę darbo sritį, eikite į **Administratorius** > **Darbo sritis** ir tada rinkitės **Diegimo vadovas**.

## <a name="configure-the-sdk"></a>Konfigūruoti SDK

Kai atsisiunčiate SDK, su juo galite dirbti naudodami „Android Studio”, kad įjungtumėte ir apibrėžtumėte įvykius. Yra du būdai tai padaryti:
### <a name="option-1-use-jitpack-recommended"></a>1 variantas: Naudokite "JitPack" (rekomenduojama)
1. Įtraukite „JitPack”saugyklą į savo šakninį `build.gradle`:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Įtraukite priklausomybę:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>2 variantas: naudokite atsisiuntimo nuorodą
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

## <a name="enable-auto-instrumentation"></a>Įjungti automatinį persodinimą

1. Įtraukite tinklo ir interneto teises į savo `AndroidManifest.xml` failą, esantį po `manifests` aplanku.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Nustatykite įtraukimo įžvalgų SDK konfigūraciją naudodami `AndroidManifest.xml` failą.

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

   >[!NOTE]
   >`Action` įvykius reikia pridėti rankiniu būdu.

1. (pasirinktinis) Kitos konfigūracijos, pvz., galinių punktų išseksavimo URL nustatymas. Juos galima įtraukti į nurijimo rakto metaduomenis `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Pasirinktinių įvykių diegimas

Kai inicijuojate SDK, galite dirbti su įvykiais ir jų ypatybėmis `MainActivity` aplinkoje.


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

## <a name="set-user-details-for-your-event-optional"></a>Įvykio vartotojo išsamios informacijos rinkinys (pasirenkamas)

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
