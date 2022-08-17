---
title: Papildykite patys „Azure“ raktų saugykla (peržiūra)
description: Sužinokite, kaip sukonfigūruoti "Customer Insights", kad paslaptys būtų naudojamos naudojant savo "Azure" raktų saugyklą.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246165"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Papildykite patys „Azure“ raktų saugykla (peržiūra)

Susiejus specialų ["Azure" raktų](/azure/key-vault/general/basic-concepts) saugyklą su "Customer Insights" aplinka, organizacijos gali atitikti atitikties reikalavimus.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Pagrindinio saugyklos susiejimas su "Customer Insights" aplinka

Nustatykite specialų raktų skliautą, kad galėtumėte pastatyti ir naudoti paslaptis organizacijos atitikties ribose.

### <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi „Azure“ prenumerata.

- Administratoriaus [vaidmuo](permissions.md#admin) [, priskirtas](permissions.md#add-users) "Customer Insights".

- [Bendraautorio](/azure/role-based-access-control/built-in-roles#contributor) ir [vartotojo prieigos administratoriaus](/azure/role-based-access-control/built-in-roles#user-access-administrator) vaidmenys pagrindiniame saugykloje arba išteklių grupėje, kuriai priklauso pagrindinis skliautas. Norėdami gauti daugiau informacijos, eikite [Į „Azure" vaidmenų priskyrimų įtraukimas arba pašalinimas naudojant „Azure" portalą](/azure/role-based-access-control/role-assignments-portal). Jei pagrindiniame saugykloje neturite vartotojo prieigos administratoriaus vaidmens, atskirai nustatykite vaidmenimis pagrįstas "Azure" paslaugos vykdytojo Dynamics 365 Customer Insights prieigos valdymo teises. Norėdami naudoti pagrindinę [„Azure" paslaugą už raktų](connect-service-principal.md) saugyklą, kurią reikia susieti, atlikite šiuos veiksmus.

- Raktų skliaute turi būti išjungta **"Key Vault" ugniasienė**.

- Raktų saugykla yra toje pačioje ["Azure" vietoje](https://azure.microsoft.com/global-infrastructure/geographies/#overview) kaip ir "Customer Insights" aplinka. "Customer Insights" eikite į **administravimo** > **sistema** ir skirtuką **Apie,** kad peržiūrėtumėte aplinkos regioną.

### <a name="recommendations"></a>Rekomendacijos

- [Naudokite atskirą arba specialų raktų skliautą](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults), kuriame yra tik tos paslaptys, kurių reikia "Customer Insights".

- Vadovaukitės geriausia [„Key Vault“ praktika,](/azure/key-vault/general/best-practices#turn-on-logging) kad kontroliuotų prieigą, atsarginę kopiją, auditą ir rūsčių naudojimo galimybes.

### <a name="link-a-key-vault-to-the-environment"></a>Susieti raktų saugyklą su aplinka

1. Eikite į **Administratoriaus** > **sauga**, tada pasirinkite skirtuką Raktų **seifas**.
1. **Key Vault** plytelėje pažymėkite **Nustatymas**.
1. Pasirinkite **prenumeratą**.
1. Pasirinkite raktų saugyklą išplečiamajame sąraše **Key Vault**. Jei yra per daug pagrindinių saugyklų, pasirinkite išteklių grupę, kad apribotumėte ieškos rezultatus.
1. Peržiūrėkite [Duomenų privatumas ir suderinamumas](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.
1. Pasirinkite **Įrašyti**.

Raktų **saugyklos** plytelėje rodomas susieto rakto saugyklos pavadinimas, prenumerata ir išteklių grupė. Ją galima naudoti ryšio sąrankoje.
Norėdami gauti daugiau informacijos apie tai, kurios rakto saugyklos teisės suteikiamos "Customer Insights", eikite į [pagrindinio saugyklos](#permissions-granted-on-the-key-vault) dalyje suteiktos teisės.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Ryšių nustatymo metu naudokite raktų saugyklą

[Nustatydami](connections.md) ryšius su [palaikomomis trečiųjų šalių](#supported-connection-types) sistemomis, naudokite paslaptis iš susieto rakto saugyklos, kad sukonfigūruotumėte ryšius.

1. Eikite į **Administravimas** > **Ryšiai**.
1. Pasirinkite **Įtraukti ryšį**.
1. Jei ryšio tipai palaikomi, galimas **Naudoti Key Vault** perjungimo klavišų saugyklos perjungimas, jei susiesite raktų saugyklą.
1. Užuot įvedę paslaptį rankiniu būdu, pasirinkite slaptą pavadinimą, nurodantį slaptą reikšmę rakto saugykloje.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Ryšių sritis su SFPP ryšiu, kuris naudoja „Key Vault“ raktą.":::

1. Pasirinkite **Įrašyti**, kad sukurtumėte ryšį.

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

" [Key Vault Reader" ir "Key Vault Secrets" vartotojo vaidmenys](/azure/key-vault/general/rbac-guide?tabs=azure-cli) bus įtraukti į "Customer Insights".

## <a name="frequently-asked-questions"></a>Dažnai užduodami klausimai

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Ar "Customer Insights" gali įrašyti paslaptis arba perrašyti paslaptis į pagrindinį skliautą?

Ne. "Customer Insights" suteikiamos tik suteiktose teisėse [nurodytos](#permissions-granted-on-the-key-vault) skaitymo ir sąrašo teisės. Sistema negali įtraukti, panaikinti ar perrašyti slaptų duomenų saugykloje. Taip pat todėl negalite įvesti kredencialų, kai ryšys naudoja „Key Vault“.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Ar galima pakeisti ryšį naudojant „Key Vault“ raktų reikšmes į numatytąjį autentifikavimą?

Ne. Sukonfigūrę ryšį iš susieto raktų saugyklos slaptai galėsite grįžti prie numatytojo ryšio. Sukurkite atskirą ryšį ir panaikinkite seną, jei jums jo nereikia.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Kaip atšaukti prieigą prie "Customer Insights" raktų saugyklos?

[Jei įgalinta "Key Vault" prieigos strategija](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) arba ["Azure" vaidmenimis pagrįstas prieigos valdiklis](/azure/key-vault/general/rbac-guide?tabs=azure-cli), pašalinkite paslaugos vykdytojo `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` teises su pavadinimu `Dynamics 365 AI for Customer Insights`. Visi ryšiai, naudojantys raktų saugyklą, nustoja veikti.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Slapta, naudojama ryšyje, pašalinta iš raktų saugyklos. Ką galiu padaryti?

Pranešimas rodomas "Customer Insights", kai sukonfigūruota paslaptis iš rakto saugyklos nebepasiekiama. Įjunkite [žaidimų saugyklos](/azure/key-vault/general/soft-delete-overview) naikinimą, kad būtų atkurta slapta informacija, jei jos netyčia pašalintos.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Ryšys neveikia, bet mano slapta vieta yra saugykloje. Kokia gali būti priežastis?

Pranešimas rodomas "Customer Insights", kai jis negali pasiekti rakto saugyklos. Priežastis gali būti:

- "Customer Insights" paslaugų teikėjo teisės buvo pašalintos. Jie turi būti neautomatiškai konvertuojami.

- Įjungta raktų saugyklos užkarda. Užkarda turi būti išjungta, kad raktų skliautas vėl būtų pasiekiamas "Customer Insights".
