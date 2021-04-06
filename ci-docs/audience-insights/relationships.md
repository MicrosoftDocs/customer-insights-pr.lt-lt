---
title: Ryšiai tarp objektų ir objektų kelių
description: Sukurkite ir valdykite ryšius tarp objektų daugeliui duomenų šaltinių.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595222"
---
# <a name="relationships-between-entities"></a>Objektų ryšiai

Ryšiai padeda susieti objektus ir generuoti duomenų grafikus, kai objektų duomenys dalijasi bendru identifikatoriumi (išoriniu raktu), kuriam galima priskirti nuorodą iš vieno objekto į kitą. Susieti objektai leidžia apibrėžti segmentus ir matus, remiantis keliais duomenų šaltiniais.

Esama dviejų tipų ryšių. Neredaguojami sistemos ryšiai, kurie sukuriami automatiškai, ir vartotojų sukurti ir sukonfigūruoti pasirinktiniai ryšiai.

Atliekant sutapdinimo ir suliejimo procesus, sistemos ryšiai sukuriami be vartotojo įsikišimo, naudojant išmanųjį sutapdinimą. Šie ryšiai padeda susieti kliento profilį su kitais atitinkamais objektų įrašais. Toliau pateikiamoje diagramoje vaizduojama, kaip sukuriami trys sistemos ryšiai, kai kliento objektas yra sutapdintas su papildomais objektais, kad būtų sukurtas galutinis kliento profilio objektas.

> [!div class="mx-imgBorder"]
> ![Ryšių sukūrimas](media/relationships-entities-merge.png "Ryšio sukūrimas")

- ***„CustomerToContact”* ryšys** buvo sukurtas tarp kliento objekto ir kontakto objekto. Kliento objekto rakto laukas **„Contact_contactId”** susiejamas su kliento objekto rakto lauku **„contactId**.
- ***„CustomerToAccount”* ryšys** buvo sukurtas tarp kliento objekto ir abonemento objekto. Kliento objekto rakto laukas **„Account_accountId”** susiejamas su abonemento objekto rakto lauku **„accountId”**.
- ***CustomerToWebAccount* ryšys** buvo sukurtas tarp kliento objekto ir „WebAccount“ objekto. Kliento objekto rakto laukas **„WebAccount_webaccountId”** susiejamas su „WebAccount“ objekto rakto lauku **„webaccountId”**.

## <a name="create-a-relationship"></a>Ryšio kūrimas

Puslapyje **Ryšiai** apibrėžkite pasirinktinius ryšius. Kiekvieną ryšį sudaro šaltinio objektas (objektas, turintis išorinį raktą) ir tikslo objektas (objektas, į kurį nurodo šaltinio objekto išorinis raktas).

1. Publikos įžvalgose, eikite į **Duomenys** > **Ryšiai**.

2. Pasirinkite **Naujas ryšys**.

3. Srityje **Įtraukti ryšį** nurodykite tolesnę informaciją:

   > [!div class="mx-imgBorder"]
   > ![Įveskite išsamią ryšio informaciją](media/relationships-add.png "Ryšio detalių įvedimas")

   - **Ryšio pavadinimas**: pavadinimas, atspindintis ryšio paskirtį (pavyzdžiui, **AccountWebLogs**).
   - **Aprašymas**: ryšio aprašymas.
   - **Šaltinio objektas**: pasirinkite objektą, kuris ryšyje naudojamas kaip šaltinis (pavyzdžiui, „WebLog“).
   - **Svarba**: pasirinkite šaltinio objekto įrašų svarbą. Pavyzdžiui, „daug“ reiškia, kad su vienu „WebAccount“ yra susieti keli „Weblog“ įrašai.
   - **Šaltinio rakto laukas**: šaltinio objekte jis nurodo išorinio rakto lauką. Pavyzdžiui, „WebLog“ turi išorinio rakto lauką **„accountId”**.
   - **Tikslo objektas**: pasirinkite objektą, kuris ryšyje naudojamas kaip tikslas (pavyzdžiui, „WebAccount“).
   - **Tikslo svarba**: pasirinkite tikslo objekto įrašų svarbą. Pavyzdžiui, „vienas“ reiškia, kad su vienu „WebAccount“ yra susieti keli „Weblog“ įrašai.
   - **Tikslo rakto laukas**: šiame lauke pateikiamas tikslo objekto rakto laukas. Pavyzdžiui, „WebAccount“ turi rakto lauką **accountId**.

> [!NOTE]
> Palaikomi tik „daugelis su vienu“ ir „vienas su vienu“ tipo ryšiai. Ryšius „daug su daug“ galima sukurti panaudojus du „daug su vienu“ ryšius ir nuorodos objektą (objektą, kuris naudojamas sujungti šaltinio objektą ir tikslo objektą).

## <a name="delete-a-relationship"></a>Ryšio pašalinimas

1. Publikos įžvalgose, eikite į **Duomenys** > **Ryšiai**.

2. Pažymėkite ryšių, kuriuos norite pašalinti, žymės langelius.

3. Lentelės **Ryšiai** viršuje pasirinkite **Pašalinti**.

4. Patvirtinkite šį naikinimą.

## <a name="next-step"></a>Kitas veiksmas

Sistema ir pasirinktiniai ryšiai naudojami segmentams kurti, remiantis keliais duomenų šaltiniais, kurie nebėra izoliuoti. Daugiau informacijos galite rasti čia [segmentas](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]