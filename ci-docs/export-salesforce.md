---
title: Duomenų eksportavimas į "Salesforce Marketing Cloud" (peržiūra)
description: Sužinokite, kaip konfigūruoti ryšį ir eksportuoti į „Salesforce Marketing Cloud“.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c3a6a40d9b9f08c8ebca8cb4a9196a1a79f03afa
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082621"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Duomenų eksportavimas į "Salesforce Marketing Cloud" (peržiūra)

„Salesforce Marketing Cloud" debesyje naudokite klientų duomenis eksportuodami juos „Secure File Transfer Protocol“ (SFTP) vietoje.

## <a name="prerequisites-for-connection"></a>Būtinosios ryšio sąlygos

- SFTP pagrindinio kompiuterio ir atitinkamų administratoriaus kredencialų pasiekiamumas. [Kaip nustatyti „Salesforce Marketing Cloud" debesies SFTP vietoves](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Ryšio su „Salesforce Marketing Cloud" debesimi nustatyti

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **Salesforce Marketing Cloud,** kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Savo SFDRE paskyroje pateikite **vartotojo vardą**, **slaptažodį**, **pagrindinio kompiuterio pavadinimą** ir **eksportavimo aplanką**.

1. Pasirinkite **Tikrinti**, kad išbandytumėte jungtį.

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje SFTP. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Pasirinkite, ar savo duomenis norite eksportuoti kaip **Gzipped** arba **Unzipped**, ir pasirinkite eksportuotų failų **laukelio skyriklį**.

1. Pažymėkite objektus, pvz.: segmentus, kuriuos norite eksportuoti.

   > [!NOTE]
   > Eksportavus, kiekvienas pažymėtas objektas padalijamas į penkis išvesties failus. 

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>„Customer Insights“ iš SFTP vietos duomenų importavimas į „Salesforce Marketing Cloud"

1. [„Salesforce Marketing Cloud" debesyje sukurkite duomenų](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) plėtinius, kad importuotute „Customer Insights" duomenų failą iš SFTP vietos.

2. [Importuokite duomenis iš SFTP vietos](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) į „Salesforce Marketing Cloud" duomenų plėtinį. 

3. Nustatykite automatizavimą, kad duomenys būtų importuoti į duomenų plėtinius. Sužinokite daugiau apie [failų numetimo automatizavimą ir suplanuotus automatizavimus](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Apibrėžkite [failų numetimo](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) automatizavimą arba [suplanuotą automatizavimą](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Štai automatizavimo su [SFTP pavyzdys](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į per SFTP, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad eksportavimo paskirties vieta atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu, kad nutrauktų šios funkcijos naudojimą.

[!INCLUDE [footer-include](includes/footer-banner.md)]
