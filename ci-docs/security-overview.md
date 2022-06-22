---
title: "\"Customer Insights\" saugos parametrai"
description: Sužinokite apie saugos parametrus Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947425"
---
# <a name="security-settings-in-customer-insights"></a>"Customer Insights" saugos parametrai

**Saugos** puslapyje pateikiamos parinktys, skirtos konfigūruoti vartotojo teises ir funkcijas, kurios padeda užtikrinti Dynamics 365 Customer Insights saugesnį saugumą. Šį puslapį gali pasiekti tik administratoriai.

Norėdami konfigūruoti parametrus, eikite į **Administratoriaus** > **sauga**.

**Saugos** puslapyje yra šie skirtukai:

- [Vartotojai](#users-tab)
- [API](#apis-tab)
- [Privatūs saitai](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Saugiai pasiekite klientų duomenis naudodami "Customer Lockbox" (peržiūra)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Skirtukas Vartotojai

Prieiga prie "Customer Insights" suteikiama tik jūsų organizacijos vartotojams, kuriuos administratorius įtraukė į taikomąją programą. Skirtuke **Vartotojai** galite valdyti vartotojo prieigą ir jų teises. Daugiau informacijos ieškokite [User rightss](permissions.md).

## <a name="apis-tab"></a>Skirtukas API

Peržiūrėkite ir tvarkykite raktus, kad "Customer Insights" API [būtų naudojamos](apis.md) su jūsų aplinkos duomenimis.

Galite sukurti naujus pirminius ir antrinius raktus pasirinkdami **Regeneruoti pirminį** arba **Regeneruoti antrinį**. 

Norėdami blokuoti API prieigą prie aplinkos, pasirinkite **Išjungti**. Jei API yra išjungtos, galite pasirinkti **Įgalinti**, kad vėl suteiktumėte prieigą.

## <a name="private-links-tab"></a>Skirtukas Privatūs saitai

["Azure Private Link](/azure/private-link/private-link-overview) " leidžia "Customer Insights" prisijungti prie jūsų Azure Data Lake Storage abonemento per privatų galinį punktą virtualiame tinkle. Jei duomenys saugyklos paskyroje nėra veikiami viešojo interneto, "Private Link" įgalina ryšį su tuo apribotu tinklu.

> [!IMPORTANT]
> Minimalus vaidmens reikalavimas norint nustatyti privataus saito ryšį:
>
> - "Customer Insights": administratorius
> - "Azure" įtaisytasis vaidmuo: [saugyklos abonemento bendraautoris](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Pasirinktinio "Azure" vaidmens teisės: [Microsoft.Storage/storageAccounts/read ir Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

"Private Link" nustatymas "Customer Insights" yra dviejų etapų procesas. Pirmiausia inicijuojate privačios nuorodos kūrimą iš **"Customer Insights" administratoriaus** > **saugos** > **asmeninių saitų**. Srityje **Įtraukti privatų saitą** išvardijami nuomotojo saugyklos abonementai, kuriuos turite teisę matyti. Pasirinkite saugyklos abonementą ir suteikite sutikimą sukurti privačią nuorodą.

Tada turite patvirtinti privačią nuorodą duomenų ežero saugyklos paskyros pusėje. Atidarykite ekrane pateiktą saitą, kad patvirtintumėte naują privačią nuorodą.

## <a name="key-vault-tab"></a>Skirtukas "Rakto skliautas"

Skirtuke " **Key Vault** " galite susieti ir valdyti savo ["Azure" raktų saugyklą](/azure/key-vault/general/basic-concepts) su aplinka.
Skirta raktų saugykla gali būti naudojama organizacijos sienų etapų ir naudojimo slaptai vietai nustatyti. "Customer Insights" gali naudoti "Azure Key Vault" paslaptis, kad [nustatytų ryšius su](connections.md) trečiųjų šalių sistemomis.

Daugiau informacijos žr. [„Azure” „key vault“ sukūrimas](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Saugiai pasiekite klientų duomenis naudodami "Customer Lockbox" (peržiūra)

"Customer Insights" naudoja Power Platform "Customer Lockbox" galimybę. Kliento užraktas suteikia sąsają, skirtą peržiūrėti ir patvirtinti (arba atmesti) duomenų prieigos užklausas. Šios užklausos atsiranda, kai norint išspręsti palaikymo atvejį reikia prieigos prie klientų duomenų. Kad galėtų naudoti šią funkciją, "Customer Insights" turi turėti esamą ryšį su nuomotojo Microsoft Dataverse aplinka.

Daugiau informacijos apie "Customer Lockbox" ieškokite ["Customer Lockbox" suvestinėje](/power-platform/admin/about-lockbox#summary)Power Platform. Straipsnyje taip pat aprašoma [darbo eiga](/power-platform/admin/about-lockbox#workflow) ir reikalinga [sąranka](/power-platform/admin/about-lockbox#enable-the-lockbox-policy), kad būtų galima įjungti klientų užraktą.

> [!IMPORTANT]
> Visuotiniai administratoriai arba Power Platform administratoriai Power Platform gali patvirtinti "Customer Lockbox" užklausas, išduotas "Customer Insights".

[!INCLUDE [footer-include](includes/footer-banner.md)]
