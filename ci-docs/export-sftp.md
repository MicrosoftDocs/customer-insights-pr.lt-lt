---
title: Duomenų eksportavimas į SFTP pagrindinius kompiuterius (peržiūra) (yra vaizdo įrašas)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į SFTP vietą.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207239"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Duomenų eksportavimas į SFTP pagrindinius kompiuterius (peržiūra)

Savo kliento duomenis trečiųjų šalių programose naudokite eksportuodami juos į saugiųjų failų perkėlimo protokolo (SFTP) vietą.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Būtinosios sąlygos

- SFTP pagrindinio kompiuterio ir atitinkamų kredencialų pasiekiamumas.

## <a name="known-limitations"></a>Žinomi apribojimai

- SFTP paskirties vietos už ugniasienių šiuo metu nepalaikomos.
- Eksportavimo trukmė priklauso nuo sistemos efektyvumo. Kaip minimalią serverio konfigūraciją rekomenduojame naudoti du procesorius IR 1 GB atminties.
- Iki 100 milijonų klientų profilių, o tai gali užtrukti 90 minučių, kai naudojama rekomenduojama minimali dviejų procesoriaus branduolių ir 1 Gb atminties konfigūracija.
- Jei autentifikavimui naudojate SSH raktą, įsitikinkite, kad sukūrėte [privatų raktą](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) kaip PEM arba SSH.COM formatą. Jei naudojate "Putty", konvertuokite privatų raktą eksportuodami kaip "Open SSH". Palaikomi šie privataus rakto formatai:
  - RSA OpenSSL PEM ir ssh.com formatu
  - DSA OpenSSL PEM ir ssh.com formatu
  - ECDSA 256/384/521 OpenSSL PEM formatu
  - ED25519 ir RSA OpenSSH rakto formatu

## <a name="set-up-connection-to-sftp"></a>Ryšio su SFTP nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **SFTP**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pasirinkite, ar norite autentifikuoti naudodami SSH, ar vartotojo vardą / slaptažodį savo ryšiui, ir pateikite reikiamą informaciją. Jei autentifikavimui naudojate SSH raktą, įsitikinkite, kad sukūrėte [privatų raktą](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) kaip PEM arba SSH.COM formatą. Jei naudojate "Putty", konvertuokite privatų raktą eksportuodami kaip "Open SSH". Palaikomi šie privataus rakto formatai:
   - RSA OpenSSL PEM ir ssh.com formatu
   - DSA OpenSSL PEM ir ssh.com formatu
   - ECDSA 256/384/521 OpenSSL PEM formatu
   - ED25519 ir RSA OpenSSH rakto formatu

1. Pasirinkite **Tikrinti**, kad išbandytumėte jungtį.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Pridėti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje SFTP. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Pasirinkite, ar savo duomenis norite eksportuoti kaip **Gzipped** arba **Unzipped**, ir pasirinkite eksportuotų failų **laukelio skyriklį**.

1. Pasirinkite objektus, pvz., segmentus, kuriuos norite eksportuoti.

   > [!NOTE]
   > Eksportuojant kiekvienas pasirinktas objektas bus padalintas į ne daugiau kaip penkis išvesties failus.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Eksportavus objektus, kuriuose yra daug duomenų, tame pačiame aplanke kiekvienam eksportui gali atsirasti keli CSV failai. Eksporto padalijimas vyksta dėl našumo priežasčių, kad būtų sumažintas laikas, per kurį eksportavimas užbaigiamas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
