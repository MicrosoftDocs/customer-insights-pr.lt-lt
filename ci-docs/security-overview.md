---
title: Saugos parametrai, esantys Dynamics 365 Customer Insights
description: Sužinokite apie saugos parametrus Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653815"
---
# <a name="security-overview-page"></a>Saugos apžvalgos puslapis

**Saugos** puslapyje pateikiamos parinktys, skirtos konfigūruoti vartotojo teises ir funkcijas, kurios padeda užtikrinti Dynamics 365 Customer Insights saugesnį saugumą. Šį puslapį gali pasiekti tik administratoriai. 

Norėdami konfigūruoti parametrus, eikite į **AdminSecurity** > **·**.

**Saugos** puslapyje yra šie skirtukai:
- [Vartotojai](#users-tab)
- [API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Skirtukas Vartotojai

Prieiga prie "Customer Insights" suteikiama tik jūsų organizacijos vartotojams, kuriuos administratorius įtraukė į taikomąją programą. Skirtuke **Vartotojai** galite valdyti vartotojo prieigą ir jų teises. Daugiau informacijos ieškokite [User rightss](permissions.md).

## <a name="apis-tab"></a>Skirtukas API

Peržiūrėkite ir tvarkykite raktus, kad "Customer Insights" API [būtų naudojamos](apis.md) su jūsų aplinkos duomenimis.

Galite sukurti naujus pirminius ir antrinius raktus pasirinkdami **Regeneruoti pirminį** arba **Regeneruoti antrinį**. 

Norėdami blokuoti API prieigą prie aplinkos, pasirinkite **Išjungti**. Jei API yra išjungtos, galite pasirinkti **Įgalinti**, kad vėl suteiktumėte prieigą.

## <a name="key-vault-tab"></a>Skirtukas "Rakto skliautas"

Skirtuke " **Key Vault** " galite susieti ir valdyti savo ["Azure" raktų saugyklą](/azure/key-vault/general/basic-concepts) su aplinka.
Skirta raktų saugykla gali būti naudojama organizacijos sienų etapų ir naudojimo slaptai vietai nustatyti. "Customer Insights" gali naudoti "Azure Key Vault" paslaptis, kad [nustatytų ryšius su](connections.md) trečiųjų šalių sistemomis.

Daugiau informacijos žr. [„Azure” „key vault“ sukūrimas](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
