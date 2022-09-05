---
title: Saugos parametrų konfigūravimas
description: Sužinokite apie saugos parametrus Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387259"
---
# <a name="configure-security-settings"></a>Saugos parametrų konfigūravimas

Tvarkykite API raktus, pasiekite klientų duomenis ir nustatykite "Azure Private Link".

## <a name="manage-api-keys"></a>API raktų valdymas

Peržiūrėkite ir tvarkykite raktus, kad galėtumėte naudoti ["Customer Insights" API](apis.md) su duomenimis savo aplinkoje.

1. Eikite į **Administratoriaus** > **sauga** ir pasirinkite skirtuką **API** .

1. Jei API prieiga prie aplinkos nenustatyta, pasirinkite **Įgalinti**. Arba, norėdami užblokuoti API prieigą prie aplinkos, pasirinkite **Išjungti** ir patvirtinti.

1. Tvarkykite pirminius ir antrinius API raktus:

   1. Norėdami rodyti pirminį arba antrinį API raktą **, pasirinkite Rodymo** simbolį.

   1. Norėdami nukopijuoti pirminį arba antrinį API raktą, pasirinkite simbolį **Kopijuoti** .

   1. Norėdami sukurti naujus pirminius arba antrinius API raktus, pasirinkite **Atkurti pirminį** arba **Atkurti antrinį**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Saugiai pasiekite klientų duomenis naudodami "Customer Lockbox" (peržiūra)

"Customer Insights Power Platform " naudoja "Customer Lockbox" galimybę. "Customer Lockbox" suteikia sąsają, leidžiančią peržiūrėti ir patvirtinti (arba atmesti) prieigos prie duomenų užklausas. Šios užklausos atsiranda, kai norint išspręsti palaikymo atvejį, reikalinga prieiga prie klientų duomenų. Norint naudoti šią funkciją, "Customer Insights" turi turėti esamą ryšį su nuomotojo Microsoft Dataverse aplinka.

Daugiau informacijos apie "Customer Lockbox" rasite ["Customer Lockbox" suvestinėje](/power-platform/admin/about-lockbox#summary)Power Platform. Straipsnyje taip pat aprašoma [darbo eiga](/power-platform/admin/about-lockbox#workflow) ir reikiama [sąranka](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) , kad įgalintumėte kliento užraktą.

> [!IMPORTANT]
> Visuotiniai Power Platform administratoriai arba Power Platform administratoriai gali patvirtinti "Customer Lockbox" užklausas, pateiktas "Customer Insights".

## <a name="set-up-an-azure-private-link"></a>"Azure Private Link" nustatymas

["Azure Private Link"](/azure/private-link/private-link-overview) leidžia "Customer Insights" prisijungti prie jūsų Azure Data Lake Storage paskyros per privatų galinį punktą virtualiame tinkle. Duomenims, esantiems saugojimo paskyroje, kuri nėra viešajame internete, "Private Link" įgalina ryšį su tuo apribotu tinklu.

> [!IMPORTANT]
> Minimalus vaidmens reikalavimas norint nustatyti privataus saito ryšį:
>
> - Klientų įžvalgos: administratorius
> - "Azure" įtaisytasis vaidmuo: [saugyklos paskyros bendraautoris](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Pasirinktinio "Azure" vaidmens teisės: [Microsoft.Storage/storageAccounts/read ir Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. "Customer Insights" eikite į **Administratoriaus** > **sauga** ir pasirinkite skirtuką **Privatūs saitai** .

1. Pasirinkite **Pridėti privačią nuorodą**.

   Srityje Įtraukti **privatų saitą** išvardijami nuomotojo saugyklos abonementai, kuriuos turite teises matyti.

1. Pasirinkite prenumeratą, išteklių grupę ir saugyklos paskyrą.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Įrašyti**.

1. Eikite į savo "Data Lake Storage" paskyrą ir atidarykite ekrane pateiktą nuorodą.

1. Patvirtinkite privatų saitą.


[!INCLUDE [footer-include](includes/footer-banner.md)]
