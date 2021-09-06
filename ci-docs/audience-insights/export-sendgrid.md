---
title: „Customer Insights” duomenų eksportavimas į „SendGrid”
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „SendGrid“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 03df2ab5fce1da1f4f662e1975533f2b538b47dbdd5cf96aae4f1007163e3729
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036111"
---
# <a name="export-segments-to-sendgrid-preview"></a>Segmentų eksportavimas į „SendGrid“ (peržiūra)

Eksportuokite vieningųjų klientų profilių segmentus į „SendGrid” kontaktų sąrašus ir naudokite juos kampanijoms bei el. pašto rinkodarą naudojant „SendGrid”. 

## <a name="prerequisites-for-a-connection"></a>Būtinosios ryšio sąlygos

-   Turite [„SendGrid” abonementą](https://sendgrid.com/) ir atitinkamus administratoriaus kredencialus.
-   „SendGrid” yra kontaktų sąrašų ir atitinkamų ID. Daugiau informacijos žr. [„SendGrid“ – Kontaktų tvarkymas](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Iš viso iki 100 000 profilių į „SendGrid”.
- Eksportavimas į „SendGrid” ribojamas segmentais.
- Iki 100 000 profilių eksportavimas į „SendGrid” gali užtrukti iki kelių valandų. 
- Profilių, kuriuos galite eksportuoti į „SendGrid”, skaičius yra priklausomas ir apribotas pagal jūsų sutartį su „SendGrid”.

## <a name="set-up-connection-to-sendgrid"></a>Ryšio su „SendGrid“ nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„SendGrid“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo **„SendGrid” API raktą**[„SendGrid” API raktas](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį su „SendGrid”.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „SendGrid“. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Įveskite **[„SendGrid” sąrašo ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. Pakartokite tuos pačius žingsnius kitiems pasirinktiniams laukams, pvz.:**Vardas**, **Pavardė**, **Šalis / regionas**, **Valstija**, **Miestas**, **Pašto kodas**.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Primygtinai **rekomenduojame eksportuoti ne daugiau nei 100 000 klientų profilių** į „SendGrid”. 

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai leidžiate perduoti duomenis į „SendGrid”, leidžiate perduoti duomenis už tos „Dynamics 365 Customer Insights” sienos ribų, įskaitant galimai slaptus „Dynamics 365 Customer Insights” duomenis, pvz.: asmeninius duomenis. „Microsoft” tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad „SendGrid” atitiktų privatumo arba saugos reikalavimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]