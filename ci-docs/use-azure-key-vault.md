---
title: Papildykite patys „Azure“ raktų saugykla (peržiūra)
description: Sužinokite, kaip sukonfigūruoti "Customer Insights", kad paslaptys būtų naudojamos naudojant savo "Azure" raktų saugyklą.
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
ms.openlocfilehash: 8fdb131de35c7d936d2921265f03faa5682db6f6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082642"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Papildykite patys „Azure“ raktų saugykla (peržiūra)

Susieto " [Azure" rakto saugyklos](/azure/key-vault/general/basic-concepts) susiejimas su "Customer Insights" aplinka padeda organizacijoms atitikti atitikties reikalavimus.
Skirta raktų saugykla gali būti naudojama organizacijos sienų etapų ir naudojimo slaptai vietai nustatyti. "Customer Insights" gali naudoti "Azure Key Vault" paslaptis, kad [nustatytų ryšius su](connections.md) trečiųjų šalių sistemomis.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Pagrindinio saugyklos susiejimas su "Customer Insights" aplinka

### <a name="prerequisites"></a>Būtinosios sąlygos

Norint sukonfigūruoti pagrindinį skliautą programoje "Customer Insights", turi būti įvykdytos šios būtinosios sąlygos:

- Turite turėti aktyvią „Azure“ prenumeratą.

- "Customer Insights" turite [administratoriaus](permissions.md#admin) vaidmenį. Sužinokite daugiau apie [vartotojų teises "Customer Insights](permissions.md#assign-roles-and-permissions)".

- Turite [Bendradarbis](/azure/role-based-access-control/built-in-roles#contributor) ir [Vartotojo prieigos administratoriaus](/azure/role-based-access-control/built-in-roles#user-access-administrator) vaidmenis raktų saugykloje ar išteklių grupė, kuriai priklauso raktų saugykla. Norėdami gauti daugiau informacijos, eikite [Į „Azure" vaidmenų priskyrimų įtraukimas arba pašalinimas naudojant „Azure" portalą](/azure/role-based-access-control/role-assignments-portal). Jei raktų saugyklos vartotojo prieigos administratoriaus vaidmens neturite, turite atskirai nustatyti vaidmenimis pagrįstas prieigos valdymo teises, skirtas „Azure" „Dynamics 365 Customer Insights“ tarnybai. Norėdami naudoti pagrindinę [„Azure" paslaugą už raktų](connect-service-principal.md) saugyklą, kurią reikia susieti, atlikite šiuos veiksmus.

- „Key Vault“ turi būti išjungta raktų saugyklos **užkarda**.

- Raktų saugykla yra toje pačioje ["Azure" vietoje](https://azure.microsoft.com/global-infrastructure/geographies/#overview) kaip ir "Customer Insights" aplinka. "Customer Insights" aplinkos regionas yra nurodytas dalyje **Administravimo** > **sistema** > **apie** > **regioną**.

### <a name="link-a-key-vault-to-the-environment"></a>Susieti raktų saugyklą su aplinka

1. Eikite į **Administratoriaus** > **sauga**, tada pasirinkite skirtuką Raktų **seifas**.
1. **Key Vault** plytelėje pažymėkite **Nustatymas**.
1. Pasirinkite **prenumeratą**.
1. Pasirinkite raktų saugyklą išplečiamajame sąraše **Key Vault**. Jei rodoma per daug raktų saugyklų, pažymėkite išteklių grupę, kad apribodami ieškos rezultatus.
1. Sutikite su duomenų **privatumo ir patvirtinimo** dėl to, kad nuostatos dėl jo yra susiėję.
1. Pasirinkite **Įrašyti**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Veiksmai, kaip nustatyti susietą raktų skliautą programoje &quot;Customer Insights&quot;.":::

**Key Vault** plytelėje rodomas susieto raktų saugyklos pavadinimas, išteklių grupė ir prenumerata. Ją galima naudoti ryšio sąrankoje.
Norėdami gauti daugiau informacijos apie tai, kurios pagrindinio saugyklos teisės suteikiamos "Customer Insights", eikite į [pagrindinio saugyklos](#permissions-granted-on-the-key-vault) leidimų suteikimą, toliau šiame straipsnyje.

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

## <a name="permissions-granted-on-the-key-vault"></a>Leidimai, suteikti pagrindiniame skliaute

Toliau nurodytos teisės suteikiamos "Customer Insights" susieto rakto saugykloje, jei [įgalinta "Key Vault" prieigos strategija](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) arba ["Azure" vaidmenimis pagrįstas prieigos valdymas](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

### <a name="key-vault-access-policy"></a>„Key Vault“ prieigos strategija

| Tipas        | Teisės          |
| ----------- | -------------------- |
| Klavišas         | [Gauti raktus](/rest/api/keyvault/keys/get-keys/get-keys), [gauti raktą](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Slaptasis raktas      | [Gauti raktus](/rest/api/keyvault/secrets/get-secrets/get-secrets), [gauti raktą](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Sertifikatas | [Gauti sertifikatą](/rest/api/keyvault/certificates/get-certificates/get-certificates), [gauti sertifikatą](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Ankstesnės reikšmės yra minimalios, kad būtų galima išvardyti ir skaityti vykdymo metu.

### <a name="azure-role-based-access-control"></a>„Azure" vaidmenimis pagrįstas prieigos valdiklis

"Key Vault Reader" ir "Key Vault Secrets" vartotojo vaidmenys bus įtraukti į "Customer Insights". Norėdami gauti daugiau informacijos apie šiuos vaidmenis, eikite [į "Azure" įtaisytuosius vaidmenis, o „Key Vault" duomenų ryšio operacijose](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Rekomendacijos

- Naudokite atskirą arba specialų raktų skliautą, kuriame yra tik tos paslaptys, kurių reikia "Customer Insights". Paskaitykite daugiau apie tai, kodėl [rekomenduojame naudoti atskiras raktų saugyklas](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Vadovaukitės geriausia [„Key Vault“ praktika,](/azure/key-vault/general/best-practices#turn-on-logging) kad kontroliuotų prieigą, atsarginę kopiją, auditą ir rūsčių naudojimo galimybes.

## <a name="frequently-asked-questions"></a>Dažnai užduodami klausimai

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Ar "Customer Insights" gali įrašyti paslaptis arba perrašyti paslaptis į pagrindinį skliautą?

Ne. "Customer Insights" suteikiamos tik skaitymo ir sąrašo teisės, [nurodytos ankstesniame šio straipsnio skyriuje "Suteiktos teisės](#permissions-granted-on-the-key-vault) ". Sistema negali įtraukti, panaikinti ar perrašyti slaptų duomenų saugykloje. Taip pat todėl negalite įvesti kredencialų, kai ryšys naudoja „Key Vault“.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Ar galima pakeisti ryšį naudojant „Key Vault“ raktų reikšmes į numatytąjį autentifikavimą?

Ne. Sukonfigūrę ryšį iš susieto raktų saugyklos slaptai galėsite grįžti prie numatytojo ryšio. Sukurkite atskirą ryšį ir panaikinkite seną, jei jums jo nereikia.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Kaip atšaukti prieigą prie "Customer Insights" raktų saugyklos?

Atsižvelgiant į tai, ar [„Key Vault“ prieigos politika](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ar [„Azure“ vaidmenimis pagrįstas prieigos valdiklis](/azure/key-vault/general/rbac-guide?tabs=azure-cli) yra įjungtas, Jums reikia pašalinti teises pagrindinėms paslaugoms `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` su pavadinimu „`Dynamics 365 AI for Customer Insights`“. Visi ryšiai, naudojantys raktų saugyklą, nustoja veikti.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Slapta, naudojama ryšyje, pašalinta iš raktų saugyklos. Ką galiu padaryti?

Pranešimas rodomas "Customer Insights", kai sukonfigūruota paslaptis iš rakto saugyklos nebepasiekiama. Įjunkite [žaidimų saugyklos](/azure/key-vault/general/soft-delete-overview) naikinimą, kad būtų atkurta slapta informacija, jei jos netyčia pašalintos.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Ryšys neveikia, bet mano slapta vieta yra saugykloje. Kokia gali būti priežastis?

Pranešimas rodomas "Customer Insights", kai jis negali pasiekti rakto saugyklos. Priežastis gali būti:

- "Customer Insights" paslaugų teikėjo teisės buvo pašalintos. Jie turi būti neautomatiškai konvertuojami.

- Įjungta raktų saugyklos užkarda. Užkarda turi būti išjungta, kad raktų skliautas vėl būtų pasiekiamas "Customer Insights".
