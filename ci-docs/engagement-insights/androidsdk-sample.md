---
title: „Android“ SDK pavyzdys
description: Projekto pavyzdys, kurį reikia išmokti apie „Android“ SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035836"
---
# <a name="run-the-android-sdk-sample"></a>Paleisti „Android“ SDK pavyzdį

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Šis projekto „Android“ pavyzdys padeda jums suprasti, kaip SDK veikia programoje. Jums nereikės rašyti kodo. Tiesiog įtraukite prarijus raktą ir iš karto galite matyti įvykius darbo srityje.

## <a name="prerequisites"></a>Būtinosios sąlygos

- [„Android Studio“](https://developer.android.com/studio)
- [Prarijimo raktas](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Atsisiųsti „Android“ SDK pavyzdį

1. [Atsisiųskite įtraukimo įžvalgų „Android“ SDK pavyzdį](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Išarchyvuokite suspaustą failą `ei-android-sample.zip`.
1. Atidarykite išspaustą aplanką „Android Studio“.
1. Faile `AndroidManifest.xml` pakeiskite eilutę `"Your-Ingestion-Key"` su savo darbo srities prarijimo raktu iš įstraukimo įžvalgų  **Administratorius** > **Darbo sritis** > **Diegimo gidas**. 

   > [!NOTE]
   > Skyriaus keisti `${applicationId}` nereikia. Jis automatiškai įvedamas į lauką.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Rinkitės **Vykdyti** kad pradėtumėte pavyzdžio projektą.
1. Peržiūrėkite įvykius savo darbo srityje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
