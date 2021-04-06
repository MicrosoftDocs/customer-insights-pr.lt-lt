---
title: „Customer Insights” duomenų eksportavimas į „SendGrid”
description: Sužinokite, kaip konfigūruoti ryšį su „SendGrid”.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597291"
---
# <a name="connector-for-sendgrid-preview"></a>„SendGrid” jungtis (peržiūros versija)

Eksportuokite vieningųjų klientų profilių segmentus į „SendGrid” kontaktų sąrašus ir naudokite juos kampanijoms bei el. pašto rinkodarą naudojant „SendGrid”. 

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite [„SendGrid” abonementą](https://sendgrid.com/) ir atitinkamus administratoriaus kredencialus.
-   „SendGrid” yra kontaktų sąrašų ir atitinkamų ID. Daugiau informacijos žr. [„SendGrid“ – Kontaktų tvarkymas](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="connect-to-sendgrid"></a>Prisijungti prie „SendGrid“

1. Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.

1. Dalyje **„SendGrid”** pažymėkite **Nustatyti**.

1. Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid eksportavimo konfigūracijos sritis.":::

1. Įveskite savo **„SendGrid” API raktą**[„SendGrid” API raktas](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Įveskite **[„SendGrid” sąrašo ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį su „SendGrid”.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.

## <a name="configure-the-connector"></a>Jungties konfigūravimas

1. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. Pakartokite tuos pačius žingsnius kitiems pasirinktiniams laukams, pvz.:**Vardas**, **Pavardė**, **Šalis / regionas**, **Valstija**, **Miestas**, **Pašto kodas**.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Primygtinai **rekomenduojame eksportuoti ne daugiau nei 100 000 klientų profilių** į „SendGrid”. 

1. Pasirinkite **Įrašyti**.

## <a name="export-the-data"></a>Duomenų eksportavimas

Galite [eksportuoti duomenis pareikalavus](export-destinations.md). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).

## <a name="known-limitations"></a>Žinomi apribojimai

- Iš viso iki 100 000 profilių į „SendGrid”.
- Eksportavimas į „SendGrid” ribojamas segmentais.
- Iki 100 000 profilių eksportavimas į „SendGrid” gali užtrukti iki kelių valandų. 
- Profilių, kuriuos galite eksportuoti į „SendGrid”, skaičius yra priklausomas ir apribotas pagal jūsų sutartį su „SendGrid”.

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai leidžiate perduoti duomenis į „SendGrid”, leidžiate perduoti duomenis už tos „Dynamics 365 Customer Insights” sienos ribų, įskaitant galimai slaptus „Dynamics 365 Customer Insights” duomenis, pvz.: asmeninius duomenis. „Microsoft” tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad „SendGrid” atitiktų privatumo arba saugos reikalavimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]