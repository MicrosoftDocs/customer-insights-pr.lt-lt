---
title: Kaip valdyti aplinką
description: Sužinokite, kaip valdyti esamas "Customer Insights" aplinkas kaip administratoriui."
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833502"
---
# <a name="how-to-manage-environments"></a>Kaip valdyti aplinką

Administratoriai [kuria](create-environment.md) ir valdo aplinkas. Jie gali pakeisti kai kuriuos nustatymus esamose aplinkose. Verslas, tipas, regionas, saugyklos parinktis ir Dataverse parametrai nustatomi sukūrus aplinką. Jei norite pakeisti šiuos parametrus, iš naujo nustatykite aplinką arba sukurkite naują aplinką.

## <a name="edit-an-existing-environment"></a>Esamos aplinkos redagavimas

Galite redaguoti kai kurią esamos aplinkos informaciją.

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite **Redagavimo** piktogramą.

   :::image type="content" source="media/edit-environment.png" alt-text="Piktograma, skirta redaguoti aplinkos parametrus.":::

1. Lauke **Redaguoti aplinką** galite atnaujinti aplinkos parametrus.

Norėdami pradėti nuo naujos aplinkos, žr [...](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Aplinkos savininko keitimas

Keli vartotojai gali turėti administratoriaus teises, tačiau tik vienas vartotojas yra aplinkos savininkas. Pagal numatytuosius nustatymus iš pradžių aplinką sukuria administratorius. Kaip aplinkos administratorius, galite priskirti nuosavybę kitam vartotojui, turinčiam administratoriaus teises.

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite **Redagavimo** piktogramą.

1. **Lauke Redaguoti aplinką** eikite į veiksmą **Pagrindinė informacija**.

1. Lauke **Keisti aplinkos** savininką pasirinkite naują aplinkos savininką.  

1. Pasirinkite **Peržiūra ir baigti**, tada **Naujinti**, kad pritaikytumėte keitimus.

## <a name="claim-ownership-of-an-environment"></a>Reikalauti nuosavybės teisės į aplinką

Jei savininko vartotojo abonementas panaikinamas arba sustabdomas, aplinka neturės savininko. Kiekvienas administratoriaus vartotojas gali reikalauti nuosavybės ir tapti naujuoju savininku. Jie gali ir toliau valdyti aplinką arba [pakeisti nuosavybę į kitą administratorių](#change-the-owner-of-an-environment).

Norėdami reikalauti nuosavybės teisės, pasirinkite **mygtuką Paimti nuosavybę**, kuris rodomas kiekvieno "Customer Insights" puslapio viršuje, kai pradinis savininkas paliko organizaciją.

## <a name="reset-an-existing-environment-preview"></a>Esamos aplinkos nustatymas iš naujo (peržiūra)

Kaip aplinkos savininkas, galite iš naujo nustatyti aplinką į tuščią būseną, jei norite panaikinti visas konfigūracijas ir pašalinti prarytus duomenis.

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite aplinką, kurią norite nustatyti iš naujo, ir pasirinkite vertikalią elipsę (&vellip;).

1. Pasirinkite parinktį **Nustatyti iš naujo**.

   :::image type="content" source="media/reset-environment.png" alt-text="Valdykite, kad iš naujo nustatytumėte aplinką.":::

1. Pasirinkite, ar norite iš naujo nustatyti visą aplinką, viską, išskyrus duomenų šaltinius, ar viską, kas sukonfigūruota ant vieningo kliento profilio.

1. Norėdami patvirtinti, įveskite aplinkos pavadinimą ir pasirinkite **Nustatyti iš naujo**.

## <a name="delete-an-existing-environment"></a>Esamos aplinkos naikinimas

Kaip aplinkos savininkas galite ištrinti administruojamą aplinką.

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite aplinką, kurią norite nustatyti iš naujo, ir pasirinkite vertikalią elipsę (&vellip;). 

1. Pasirinkite parinktį **Naikinti**.

   :::image type="content" source="media/delete-environment.png" alt-text="Valdykite, kad panaikintumėte aplinką.":::

1. Norėdami patvirtinti panaikinimą, įveskite aplinkos pavadinimą ir pasirinkite **Naikinti**.

> [!IMPORTANT]
> Panaikinus aplinką, ryšys su aplinka nepašalinamas Dataverse. Jei ateityje planuojate prijungti tą pačią Dataverse aplinką prie naujos "Customer Insights" aplinkos, turite pašalinti tą ryšį Sužinokite, kaip pašalinti [esamą ryšį su Dataverse aplinka](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
