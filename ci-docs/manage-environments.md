---
title: 'Kaip: tvarkyti aplinkas'
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
ms.openlocfilehash: fc3b3f404cf0ac84c782778414494289c803babe
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083062"
---
# <a name="how-to-manage-environments"></a>Kaip: tvarkyti aplinkas

Administratoriai [kuria](create-environment.md) ir valdo aplinkas. Jie gali pakeisti kai kuriuos nustatymus esamose aplinkose. Verslas, tipas, regionas, saugyklos parinktis ir Dataverse parametrai pataisomi sukūrus aplinką. Jei norite pakeisti šiuos parametrus, iš naujo nustatykite aplinką arba sukurkite naują aplinką.

## <a name="edit-an-existing-environment"></a>Esamos aplinkos redagavimas

Galite redaguoti kai kurią esamos aplinkos informaciją.

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite **Redagavimo** piktogramą.

   :::image type="content" source="media/edit-environment.png" alt-text="Piktograma, skirta redaguoti aplinkos nustatymus.":::

1. Lauke **Redaguoti aplinką** galite atnaujinti aplinkos parametrus.

Norėdami pradėti nuo naujos aplinkos, žiūrėkite [Kurti naują aplinką](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Aplinkos savininko keitimas

Keli vartotojai gali turėti administratoriaus teises, bet tik vienas vartotojas yra aplinkos savininkas. Pagal numatytuosius nustatymus iš pradžių aplinką sukuria administratorius. Kaip aplinkos administratorius, galite priskirti nuosavybės teisę kitam vartotojui, turinčiam administratoriaus teises.

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite **Redagavimo** piktogramą.

1. **Lauke Redaguoti aplinką** eikite į veiksmą **Pagrindinė informacija**.

1. **Lauke Keisti aplinkos** savininką pasirinkite naują aplinkos savininką.  

1. Pasirinkite **Peržiūrėti ir baigti**, tada **Naujinti**, kad pritaikytumėte pakeitimus.

## <a name="claim-ownership-of-an-environment"></a>Pretenduoti į aplinkos nuosavybę

Jei savininko vartotojo abonementas panaikinamas arba laikinai sustabdomas, aplinka neturės savininko. Kiekvienas administratorius vartotojas gali pareikšti pretenziją į nuosavybę ir tapti naujuoju savininku. Jie gali ir toliau turėti aplinką arba [pakeisti nuosavybės teisę į kitą administratorių](#change-the-owner-of-an-environment).

Norėdami pretenduoti į nuosavybę, pasirinkite mygtuką **Perimti nuosavybę**, kuris rodomas kiekvieno "Customer Insights" puslapio viršuje, kai pradinis savininkas paliko organizaciją.

## <a name="reset-an-existing-environment-preview"></a>Esamos aplinkos nustatymas iš naujo (peržiūra)

Kaip aplinkos savininkas, galite iš naujo nustatyti aplinką į tuščią būseną, jei norite panaikinti visas konfigūracijas ir pašalinti nurijusius duomenis.

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite aplinką, kurią norite iš naujo nustatyti, ir pasirinkite vertikalią daugtaškį (&vellip;).

1. Pasirinkite parinktį **Nustatyti iš naujo**.

   :::image type="content" source="media/reset-environment.png" alt-text="Valdymas, kad iš naujo nustatytumėte aplinką.":::

1. Pasirinkite, ar norite iš naujo nustatyti visą aplinką, viską, išskyrus duomenų šaltinius, ar bet ką, kas sukonfigūruota ant vieningo kliento profilio.

1. Norėdami patvirtinti, įveskite aplinkos pavadinimą ir pasirinkite **Nustatyti iš naujo**.

## <a name="delete-an-existing-environment"></a>Esamos aplinkos naikinimas

Kaip aplinkos savininkas, galite panaikinti savo administruojamą aplinką.

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite aplinką, kurią norite iš naujo nustatyti, ir pasirinkite vertikalią daugtaškį (&vellip;). 

1. Pasirinkite parinktį **Naikinti**.

   :::image type="content" source="media/delete-environment.png" alt-text="Valdykite, kad panaikintumėte aplinką.":::

1. Norėdami patvirtinti panaikinimą, įveskite aplinkos pavadinimą ir pasirinkite **Naikinti**.

> [!IMPORTANT]
> Aplinkos ištrynimas nepašalina ryšio su Dataverse aplinka. Jei ateityje planuojate prijungti tą pačią Dataverse aplinką prie naujos "Customer Insights" aplinkos, turite pašalinti tą ryšį Sužinokite, kaip [pašalinti esamą ryšį su Dataverse aplinka](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
