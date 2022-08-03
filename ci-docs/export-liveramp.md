---
title: Segmentų eksportavimas į „LiveRamp“ (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „LiveRamp“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196726"
---
# <a name="export-segments-to-liverampreg-preview"></a>Segmentų eksportavimas į „LiveRamp&reg;“ (peržiūra)

Suaktyvinkite duomenis naudodami „LiveRamp“, kad prisijungtumėte prie daugiau nei 500 skaitmeninių, socialinių ir TV platformų. Nukreipkite, sustabdykite ir asmeniškai pritaikykite skelbimų kampanijas dirbdami su duomenimis „LiveRamp“.

## <a name="prerequisites"></a>Būtinosios sąlygos

- "LiveRamp" prenumerata, skirta naudoti šią jungtį. Norėdami gauti prenumeratą, [kreipkitės tiesiogiai į „LiveRamp“](https://liveramp.com/contact/). [Sužinokite daugiau apie „LiveRamp Onboarding“](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Žinomi apribojimai

- "LiveRamp" eksportui naudojamas SFTP eksportas. SFTP paskirties vietos už ugniasienių šiuo metu nepalaikomos.
- Jei autentifikavimui naudojate SSH raktą, įsitikinkite, kad sukūrėte [privatų raktą](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) kaip PEM arba SSH.COM formatą. Jei naudojate "Putty", konvertuokite privatų raktą eksportuodami kaip "Open SSH". Palaikomi šie privataus rakto formatai:
  - RSA OpenSSL PEM ir ssh.com formatu
  - DSA OpenSSL PEM ir ssh.com formatu
  - ECDSA 256/384/521 OpenSSL PEM formatu
  - ED25519 ir RSA OpenSSH rakto formatu
- Eksportavimo trukmė priklauso nuo sistemos efektyvumo. Kaip minimalią serverio konfigūraciją rekomenduojame naudoti du procesorius IR 1 GB atminties.
- Objektų, kurių klientų profiliai yra iki 100 milijonų, eksportavimas gali užtrukti 90 minučių naudojant rekomenduojamą minimalią dviejų procesorių IR 1 GB atminties konfigūraciją.
- Faktinis profilių (arba duomenų), kuriuos galite eksportuoti į "LiveRamp", skaičius priklauso nuo jūsų prenumeratos naudojant "LiveRamp".

## <a name="set-up-connection-to-liveramp"></a>Ryšio su „LiveRamp“ nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **LiveRamp**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pasirinkite, ar norite autentifikuoti naudodami SSH, ar vartotojo vardą / slaptažodį savo ryšiui, ir pateikite reikiamą informaciją.

1. Pasirinkite **Tikrinti**, kad patikrintumėte ryšį su „LiveRamp“.

1. Sėkmingai patvirtinę peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Pridėti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „LiveRamp“. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. **Lauke Susieti duomenis** pasirinkite **El. paštas**, **vardas ir adresas** arba **Telefonas**, kurį norite siųsti į "LiveRamp", kad būtų išspręsta tapatybė.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="„LiveRamp“ jungtis su atributų susiejimu.":::

1. Susiekite atitinkamus pasirinkto rakto *identifikatoriaus* atributus iš kliento objekto.

1. Pasirinkite **Pridėti atribute**, kad žymėtumėte daugiau atributų siuntimui į „LiveRamp“.

   > [!TIP]
   > „LiveRamp“ nusiuntus daugiau pagrindinio identifikatoriaus atributų tikėtina, kad sutapimo dažnis bus aukštesnis.

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
