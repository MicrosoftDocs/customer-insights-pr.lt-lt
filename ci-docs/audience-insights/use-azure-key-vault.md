---
title: Perkelti savo „Azure" raktų saugyklą slaptai valdyti
description: Sužinokite, kaip konfigūruoti „Customer Insights“, kad būtų naudojama jūsų „Azure" raktų saugykla.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 5b22c1464b3f089551f485f98d6d93840ff77136
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355901"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Papildykite patys „Azure“ raktų saugykla (peržiūra)

Susiedami skirtą [„Azure" raktų saugyklą](/azure/key-vault/general/basic-concepts) su auditorijos įžvalgų aplinka, organizacijos gali lengviau įvykdyti reikalavimų atitikimą.
Skirta raktų saugykla gali būti naudojama organizacijos sienų etapų ir naudojimo slaptai vietai nustatyti. Auditorijos įžvalgos gali naudoti „Azure“ „Key Vault“ [slaptas vietas ryšiams](connections.md) su trečiųjų šalių sistemomis nustatyti.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Susiekite raktų saugyklą su auditorijų įžvalgų aplinka

### <a name="prerequisites"></a>Būtinosios sąlygos

Norint sukonfigūruoti saugyklą auditorijos įžvalgose, reikia įvykdyti šias būtinąsias sąlygas:

- Turite turėti aktyvią „Azure“ prenumeratą.

- Auditorijos įžvalgose turite [Administratoriaus](permissions.md#administrator) vaidmenį. Sužinokite daugiau apie [vartotojų teises auditorijos įžvalgose](permissions.md#assign-roles-and-permissions).

- Turite [Bendradarbis](/azure/role-based-access-control/built-in-roles#contributor) ir [Vartotojo prieigos administratoriaus](/azure/role-based-access-control/built-in-roles#user-access-administrator) vaidmenis raktų saugykloje ar išteklių grupė, kuriai priklauso raktų saugykla. Norėdami gauti daugiau informacijos, eikite [Į „Azure" vaidmenų priskyrimų įtraukimas arba pašalinimas naudojant „Azure" portalą](/azure/role-based-access-control/role-assignments-portal). Jei raktų saugyklos vartotojo prieigos administratoriaus vaidmens neturite, turite atskirai nustatyti vaidmenimis pagrįstas prieigos valdymo teises, skirtas „Azure" „Dynamics 365 Customer Insights“ tarnybai. Norėdami naudoti pagrindinę [„Azure" paslaugą už raktų](connect-service-principal.md) saugyklą, kurią reikia susieti, atlikite šiuos veiksmus.

- „Key Vault“ turi būti išjungta raktų saugyklos **užkarda**.

- Pagrindinė saugykla yra toje pačioje [„Azure" vietoje,](https://azure.microsoft.com/global-infrastructure/geographies/#overview) kaip ir auditorijos įžvalgų aplinka. Aplinkos regionas auditorijos įžvalgose pateikiamas **administravimo** > **sistemos** > **apie** > **regioną**.

### <a name="link-a-key-vault-to-the-environment"></a>Susieti raktų saugyklą su aplinka

1. Eikite į **Administravimas** > **Sistema** ir tada rinkitės **Saugumo** skirtuką.
1. **Key Vault** plytelėje pažymėkite **Nustatymas**.
1. Pasirinkite **prenumeratą**.
1. Pasirinkite raktų saugyklą išplečiamajame sąraše **Key Vault**. Jei rodoma per daug raktų saugyklų, pažymėkite išteklių grupę, kad apribodami ieškos rezultatus.
1. Sutikite su duomenų **privatumo ir patvirtinimo** dėl to, kad nuostatos dėl jo yra susiėję.
1. Pasirinkite **Įrašyti**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Veiksmai norint nustatyti susietą raktų saugyklą auditorijos įžvalgose.":::

**Key Vault** plytelėje rodomas susieto raktų saugyklos pavadinimas, išteklių grupė ir prenumerata. Ją galima naudoti ryšio sąrankoje.
Norėdami gauti daugiau informacijos, kurios raktų saugyklos teisės suteikiamos auditorijos įžvalgoms, žr. [teises suteiktas raktų saugyklai į publikos įžvalgoms](#permissions-granted-on-the-key-vault-to-audience-insights), vėliau šiame straipsnyje.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Ryšių nustatymo metu naudokite raktų saugyklą

Nustatant [ryšius su trečiųjų šalių sistemomis](connections.md) „Key Vault“ sistemos slapta vieta gali būti naudojama ryšiams konfigūruoti.

1. Eikite į **Administravimas** > **Ryšiai**.
1. Pasirinkite **Įtraukti ryšį**.
1. Jei ryšio tipai palaikomi, galimas **Naudoti Key Vault** perjungimo klavišų saugyklos perjungimas, jei susiesite raktų saugyklą.
1. Užuot įvesdami slaptas saugyklas rankiniu būdu, galite pasirinkti slaptą pavadinimą, kuris nurodo slaptas reikšmę saugykloje.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Ryšių sritis su SFPP ryšiu, kuris naudoja „Key Vault“ raktą.":::

## <a name="supported-connection-types"></a>Palaikyti ryšio tipus

Palaikomi šie [eksportavimo](export-destinations.md) ryšiai:

* [„ActiveCampaign“](export-active-campaign.md)
* [Autopilotas](export-autopilot.md)
* [„DotDigital“](export-dotdigital.md)
* [„Google Ads“](export-google-ads.md)
* ["Klaviyo"](export-klaviyo.md)
* [„LiveRamp“](export-liveramp.md)
* [„Marketo“](export-marketo.md)
* [„Omnisend”](export-omnisend.md)
* [„Salesforce Marketing Cloud"](export-salesforce.md)
* [„Sendgrid“ (siųsti tinklelį)](export-sendgrid.md)
* [„Sendinblue“](export-sendinblue.md)
* [„SFTP”](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Raktų saugykloje suteikiamos teisės auditorijos įžvalgoms

Toliau nurodytos teisės suteikiamos auditorijos įžvalgoms apie susietą [„Key Vault“ prieigos politika](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ar [„Azure“ vaidmens pagrindo prieigos kontrolė](/azure/key-vault/general/rbac-guide?tabs=azure-cli) yra įjungta.

### <a name="key-vault-access-policy"></a>„Key Vault“ prieigos strategija

| Tipas        | Teisės          |
| ----------- | -------------------- |
| Klavišas         | [Gauti raktus](/rest/api/keyvault/get-keys), [gauti raktą](/rest/api/keyvault/get-key)                                 |
| Slaptasis raktas      | [Gauti raktus](/rest/api/keyvault/get-secrets), [gauti raktą](/rest/api/keyvault/get-secret)                     |
| Sertifikatas | [Gauti sertifikatą](/rest/api/keyvault/get-certificates), [gauti sertifikatą](/rest/api/keyvault/get-certificate) |

Ankstesnės reikšmės yra minimalios, kad būtų galima išvardyti ir skaityti vykdymo metu.

### <a name="azure-role-based-access-control"></a>„Azure" vaidmenimis pagrįstas prieigos valdiklis

Į „Key Vault“ skaitytuvas ir „Key Vault“ raktų vartotojų vaidmenis bus įtraukta auditorijos įžvalgų. Norėdami gauti daugiau informacijos apie šiuos vaidmenis, eikite [į "Azure" įtaisytuosius vaidmenis, o „Key Vault" duomenų ryšio operacijose](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Rekomendacijos

- Naudokite atskirą arba skirtą raktų saugyklą, kurioje yra tik slapta informacija, būtina auditorijos įžvalgoms. Paskaitykite daugiau apie tai, kodėl [rekomenduojame naudoti atskiras raktų saugyklas](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Vadovaukitės geriausia [„Key Vault“ praktika,](/azure/key-vault/general/best-practices#turn-on-logging) kad kontroliuotų prieigą, atsarginę kopiją, auditą ir rūsčių naudojimo galimybes.

## <a name="frequently-asked-questions"></a>Dažnai užduodami klausimai

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Ar auditorijos įžvalgos gali slaptai rašyti ar perrašyti slaptas žinias saugykloje?

Ne. Tik skaitymo ir sąrašo teisės, nurodytos suteikiamos [skyriuje anksčiau](#permissions-granted-on-the-key-vault-to-audience-insights) šiame straipsnyje, suteikiamos auditorijos įžvalgoms. Sistema negali įtraukti, panaikinti ar perrašyti slaptų duomenų saugykloje. Taip pat todėl negalite įvesti kredencialų, kai ryšys naudoja „Key Vault“.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Ar galima pakeisti ryšį naudojant „Key Vault“ raktų reikšmes į numatytąjį autentifikavimą?

Ne. Sukonfigūrę ryšį iš susieto raktų saugyklos slaptai galėsite grįžti prie numatytojo ryšio. Sukurkite atskirą ryšį ir panaikinkite seną, jei jums jo nereikia.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Kaip atšaukti prieigą prie pagrindinės saugyklos, jei reikia auditorijos įžvalgų?

Atsižvelgiant į tai, ar [„Key Vault“ prieigos politika](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ar [„Azure“ vaidmenimis pagrįstas prieigos valdiklis](/azure/key-vault/general/rbac-guide?tabs=azure-cli) yra įjungtas, Jums reikia pašalinti teises pagrindinėms paslaugoms `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` su pavadinimu „`Dynamics 365 AI for Customer Insights`“. Visi ryšiai, naudojantys raktų saugyklą, nustoja veikti.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Slapta, naudojama ryšyje, pašalinta iš raktų saugyklos. Ką galiu padaryti?

Jei sukonfigūruota slapta raktų saugyklos slapta informacija nepasiekiama, auditorijos įžvalgose pateikiamas pranešimas. Įjunkite [žaidimų saugyklos](/azure/key-vault/general/soft-delete-overview) naikinimą, kad būtų atkurta slapta informacija, jei jos netyčia pašalintos.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Ryšys neveikia, bet mano slapta vieta yra saugykloje. Kokia gali būti priežastis?

Jei naudojant raktų saugyklos prieigos pasiekti negalima, auditorijos įžvalgose rodomas pranešimas. Priežastis gali būti:

- Pagrindinės auditorijos įžvalgų tarnybos teisės pašalintos. Jie turi būti neautomatiškai konvertuojami.

- Įjungta raktų saugyklos užkarda. Užkarda turi būti išjungta, kad pagrindinė saugykla vėl būtų pasiekiama auditorijos įžvalgoms.
