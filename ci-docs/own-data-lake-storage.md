---
title: Naudokite savo Azure Data Lake Storage Gen2 paskyrą
author: mukeshpo
description: Sužinokite apie reikalavimus naudoti savo Azure Data Lake Storage paskyrą "Customer Insights" duomenims saugoti.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: d2ff49c324c5c5c28213f362ff330d441fcb6052
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246211"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Naudokite savo Azure Data Lake Storage Gen2 paskyrą

Dynamics 365 Customer Insights suteikia galimybę saugoti visus savo duomenis [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Įrašydami duomenis į "Data Lake Storage", sutinkate, kad duomenys bus perkelti į atitinkamą tos "Azure" saugyklos paskyros geografinę vietą ir joje saugomi. Daugiau informacijos ieškokite ["Microsoft" patikimumo centre](https://www.microsoft.com/trust-center).

"Customer Insights" administratoriai gali [kurti aplinkas](create-environment.md) ir [nurodyti proceso duomenų saugojimo parinktį](create-environment.md#step-2-configure-data-storage).

## <a name="prerequisites-to-use-your-storage-account"></a>Būtinosios sąlygos norint naudoti saugyklos paskyrą

- Azure Data Lake Storage paskyros turi būti tame pačiame "Azure" regione, kurį pasirinkote kurdami "Customer Insights" aplinką. Galite patikrinti "Customer Insights" aplinkos regioną dalyje **Administratoriaus** > **sistema** > **apie**.
- Duomenų ežero saugykla turi būti Gen2 ir joje turi [būti įgalinta](/azure/storage/blobs/create-data-lake-storage-account) hierarchinė vardų sritis. Gen1 saugyklos paskyros nepalaikomos.
- Pavadintas konteineris `customerinsights` turi būti saugyklos paskyroje. Turite jį sukurti prieš naudodami savo "Data Lake Storage" programoje "Customer Insights". Administratoriui, nustatančiam "Customer Insights" aplinką, saugojimo paskyroje arba `customerinsights` konteineryje reikia saugojimo Blob duomenų bendraautorio arba saugyklos "Blob Data" savininko vaidmens. Daugiau informacijos apie teisių priskyrimą saugyklos abonemente ieškokite [Saugyklos abonemento](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) kūrimas.

## <a name="connect-customer-insights-with-your-storage-account"></a>"Customer Insights" susiejimas su saugyklos paskyra

Kai kuriate naują aplinką, įsitikinkite, kad yra "Data Lake Storage" paskyra ir įvykdomos visos būtinosios sąlygos.

1. Aplinkos kūrimo metu atlikdami **duomenų saugojimo** veiksmą nustatykite **Įrašyti išvesties duomenis** į **Azure Data Lake Storage Gen2**.
1. Pasirinkite, kaip prijungti **saugyklą**. Galite pasirinkti tarp ištekliais pagrįstos parinkties ir prenumerata pagrįstos autentifikavimo parinkties. Daugiau informacijos ieškokite [Prisijungimas Azure Data Lake Storage prie abonemento naudojant "Azure Service Principal"](connect-service-principal.md).
   - Jei naudojate **"Azure" prenumeratą**, pasirinkite **prenumeratos**, **išteklių grupės** ir **saugyklos paskyrą**, kurioje yra sudėtinis `customerinsights` rodinys.
   - Jei naudojate **paskyros raktą**, nurodykite **"Data Lake Storage" paskyros paskyros pavadinimą** ir **paskyros raktą**. Šio autentifikavimo metodo naudojimas reiškia, kad esate informuoti, jei jūsų organizacija pasuka raktus. Turite [atnaujinti aplinkos konfigūraciją](manage-environments.md#edit-an-existing-environment) nauju raktu, kai jis pasukamas.
1. Pasirinkite, ar norite naudoti "Azure Private Link", kad prisijungtumėte prie saugyklos paskyros ir [sukurtumėte ryšį su privačiu saitu](security-overview.md#set-up-an-azure-private-link) atlikdami dviejų veiksmų procesą.

Kai sistemos procesai, pvz., duomenų įsisavinimas, užbaigiami, sistema sukuria atitinkamus aplankus saugojimo paskyroje. Duomenų failai ir *model.json* failai yra kuriami ir įtraukiami į aplankus pagal proceso pavadinimą.

Jei sukuriate kelias „Customer Insights“ aplinkas ir pasirenkate įrašyti išvesties objektus iš šių aplinkos į saugyklos klientą, „Customer Insights“ sukuria atskirus kiekvienos aplinkos aplankus `ci_environmentID` konteineryje.
