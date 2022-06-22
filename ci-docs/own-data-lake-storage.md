---
title: Naudokite savo Azure Data Lake Storage "Gen2" paskyrą
author: mukeshpo
description: Sužinokite apie reikalavimus naudoti savo Azure Data Lake Storage abonementą "Customer Insights" duomenims saugoti.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5acb58906c1a9db54337f3b4dc2ab7891db7954e
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011943"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Naudokite savo Azure Data Lake Storage "Gen2" paskyrą

Dynamics 365 Customer Insights suteikia jums galimybę saugoti visus savo duomenis " [Azure Data Lake Storage Gen2"](/azure/storage/blobs/data-lake-storage-introduction).

Įrašydami duomenis į "Data Lake Storage", sutinkate, kad duomenys bus perkelti ir saugomi atitinkamoje geografinėje tos "Azure" saugyklos paskyros vietoje. Daugiau informacijos ieškokite [Microsoft Trust Center](https://www.microsoft.com/trust-center).

"Customer Insights" administratoriai gali [kurti aplinkas](create-environment.md) ir [nurodyti proceso duomenų saugojimo parinktį](create-environment.md#step-2-configure-data-storage).

## <a name="prerequisites-to-use-your-storage-account"></a>Būtinos sąlygos norint naudoti saugyklos abonementą

- Azure Data Lake Storage abonementai turi būti tame pačiame "Azure" regione, kurį pasirinkote kurdami "Customer Insights" aplinką. "Customer Insights" aplinkos regioną galite patikrinti dalyje **Administravimo** > **sistema** > **Apie**.
- Duomenų ežero saugykla turi būti Gen2 ir turėti [hierarchinę vardų sritį](/azure/storage/blobs/create-data-lake-storage-account). Gen1 saugyklos abonementai nepalaikomi.
- Saugojimo abonemente turi būti nurodytas `customerinsights` konteineris. Turite jį sukurti prieš naudodami savo duomenų ežero saugyklą "Customer Insights". Administratoriui, nustatančiam "Customer Insights" aplinką, reikia saugyklos BLOB duomenų bendradarbio arba saugyklos BLOB duomenų savininko vaidmens saugyklos abonemente arba `customerinsights` konteineryje. Daugiau informacijos apie teisių priskyrimą saugyklos abonemente ieškokite [Create a storage account](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>"Customer Insights" prijungimas prie saugyklos abonemento

Kurdami naują aplinką įsitikinkite, kad yra duomenų ežero saugyklos paskyra ir įvykdytos visos būtinosios sąlygos.

1. Kurdami aplinką žingsnyje **Duomenų saugojimas** nustatykite **Įrašyti išvesties duomenis** į **Azure Data Lake Storage Bendr.2**.
1. Pasirinkite, **kaip prijungti saugyklą**. Galite pasirinkti iš ištekliais pagrįstos parinkties ir prenumerata pagrįstos autentifikavimo parinkties. Norėdami gauti daugiau informacijos, žr [.Azure Data Lake Storage](connect-service-principal.md)
   - Jei naudojate **"Azure" prenumeratą**, pasirinkite **prenumeratą**, **išteklių grupę** ir **saugyklos abonementą**, kuriame yra konteineris`customerinsights`.
   - Paskyros **raktui** **pateikite "Data Lake Storage" paskyros abonemento pavadinimą** ir **abonemento raktą.** Šio autentifikavimo metodo naudojimas reiškia, kad esate informuotas, jei jūsų organizacija pasuks raktus. Pasukę aplinkos konfigūraciją [turite](manage-environments.md#edit-an-existing-environment) atnaujinti nauju raktu.
1. Pasirinkite, ar norite naudoti "Azure Private Link", kad prisijungtumėte prie saugyklos abonemento ir [sukurtumėte ryšį su "Private Link](security-overview.md#private-links-tab) " atlikdami dviejų etapų procesą.

Kai sistemos procesai, pvz., duomenų nurijimas, yra baigti, sistema sukuria atitinkamus aplankus saugojimo abonemente. Duomenų failai ir *model.json* failai yra kuriami ir įtraukiami į aplankus pagal proceso pavadinimą.

Jei sukuriate kelias „Customer Insights“ aplinkas ir pasirenkate įrašyti išvesties objektus iš šių aplinkos į saugyklos klientą, „Customer Insights“ sukuria atskirus kiekvienos aplinkos aplankus `ci_environmentID` konteineryje.
