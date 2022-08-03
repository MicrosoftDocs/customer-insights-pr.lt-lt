---
title: Duomenų eksportavimas į "Salesforce Marketing Cloud" (peržiūra)
description: Sužinokite, kaip konfigūruoti ryšį ir eksportuoti į „Salesforce Marketing Cloud“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197048"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Duomenų eksportavimas į "Salesforce Marketing Cloud" (peržiūra)

„Salesforce Marketing Cloud" debesyje naudokite klientų duomenis eksportuodami juos „Secure File Transfer Protocol“ (SFTP) vietoje.

## <a name="prerequisites"></a>Būtinosios sąlygos

- [SFTP pagrindinis kompiuteris, skirtas "Salesforce Marketing Cloud"](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) ir atitinkamiems administratoriaus kredencialams.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Ryšio su "Salesforce Marketing Cloud" nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **"Salesforce Marketing Cloud"**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Savo SFDRE paskyroje pateikite **vartotojo vardą**, **slaptažodį**, **pagrindinio kompiuterio pavadinimą** ir **eksportavimo aplanką**.

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

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>„Customer Insights“ iš SFTP vietos duomenų importavimas į „Salesforce Marketing Cloud"

1. [„Salesforce Marketing Cloud" debesyje sukurkite duomenų](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) plėtinius, kad importuotute „Customer Insights" duomenų failą iš SFTP vietos.

2. [Importuokite duomenis iš SFTP vietos](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) į „Salesforce Marketing Cloud" duomenų plėtinį.

3. Nustatykite automatizavimą, kad duomenys būtų importuoti į duomenų plėtinius. Sužinokite daugiau apie [failų numetimo automatizavimą ir suplanuotus automatizavimus](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Apibrėžkite [failų numetimo](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) automatizavimą arba [suplanuotą automatizavimą](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Štai automatizavimo su [SFTP pavyzdys](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
