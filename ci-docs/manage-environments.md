---
title: Aplinkų valdymas
description: Sužinokite, kaip valdyti esamas "Customer Insights" aplinkas kaip administratoriui.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 6d48f7088d722b27ca69cd591178651bdb6e2c23
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588822"
---
# <a name="manage-environments"></a>Aplinkų valdymas

Administratoriai [kuria](create-environment.md) ir valdo aplinkas. Jie gali pakeisti kai kuriuos nustatymus esamose aplinkose. Verslas, tipas, regionas, saugyklos parinktis ir Dataverse parametrai pataisomi sukūrus aplinką. Jei norite pakeisti šiuos parametrus, [iš naujo nustatykite aplinką](#reset-an-existing-environment-preview) arba [sukurkite naują aplinką](create-environment.md).

## <a name="edit-an-existing-environment"></a>Esamos aplinkos redagavimas

Redaguokite išsamią esamos aplinkos informaciją, pvz., pavadinimą arba numatytosios aplinkos nustatymą.

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite **Redagavimo** piktogramą.

   :::image type="content" source="media/edit-environment.png" alt-text="Piktograma, skirta redaguoti aplinkos nustatymus.":::

1. **Srityje Redaguoti aplinką** atnaujinkite aplinkos parametrus.

1. Pasirinkite **Peržiūrėti ir baigti**, tada **Naujinti**, kad pritaikytumėte pakeitimus.

## <a name="change-the-owner-of-an-environment"></a>Aplinkos savininko keitimas

Keli vartotojai gali turėti administratoriaus teises, bet tik vienas vartotojas yra aplinkos savininkas. Pagal numatytuosius nustatymus iš pradžių aplinką sukuria administratorius. Kaip aplinkos administratorius, galite priskirti nuosavybės teisę kitam vartotojui, turinčiam administratoriaus teises.

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite **Redagavimo** piktogramą.

1. **Srityje Redaguoti aplinką** pereikite **prie pagrindinės informacijos** veiksmo.

1. **Lauke Keisti aplinkos** savininką pasirinkite naują aplinkos savininką.  

1. Pasirinkite **Peržiūrėti ir baigti**, tada **Naujinti**, kad pritaikytumėte pakeitimus.

## <a name="claim-ownership-of-an-environment"></a>Pretenduoti į aplinkos nuosavybę

Jei savininko vartotojo abonementas panaikinamas arba laikinai sustabdomas, aplinka neturės savininko. Bet kuris administratorius gali pretenduoti į nuosavybę ir tapti naujuoju savininku. Savininko administratorius gali ir toliau turėti aplinką arba [pakeisti nuosavybės teisę į kitą administratorių](#change-the-owner-of-an-environment).

Norėdami pretenduoti į nuosavybę, pasirinkite mygtuką **Perimti nuosavybę**, kuris rodomas kiekvieno "Customer Insights" puslapio viršuje, kai pradinis savininkas paliko organizaciją.

## <a name="reset-an-existing-environment-preview"></a>Esamos aplinkos nustatymas iš naujo (peržiūra)

Kaip aplinkos savininkas, iš naujo nustatykite aplinką į tuščią būseną, jei norite panaikinti visas konfigūracijas ir pašalinti nurijusius duomenis.

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite aplinką, kurią norite iš naujo nustatyti, ir pasirinkite vertikalią daugtaškį (&vellip;).

1. Pasirinkite **Reset (peržiūra)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Valdymas, kad iš naujo nustatytumėte aplinką.":::

1. Pasirinkite, ar norite iš naujo nustatyti visą aplinką, viską, išskyrus duomenų šaltinius, ar bet ką, kas sukonfigūruota ant vieningo kliento profilio.

1. Norėdami patvirtinti, įveskite aplinkos pavadinimą ir pasirinkite **Nustatyti iš naujo**.

## <a name="delete-an-existing-environment"></a>Esamos aplinkos naikinimas

Kaip aplinkos savininkas, galite ją ištrinti.

> [!IMPORTANT]
> Aplinkos ištrynimas nepašalina ryšio su Dataverse aplinka. Jei ateityje planuojate tą pačią Dataverse aplinką prijungti prie naujos "Customer Insights" aplinkos, turite [pašalinti tą ryšį su Dataverse aplinka](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite aplinką, kurią norite ištrinti, ir pasirinkite vertikalią daugtaškį (&vellip;). 

1. Pasirinkite **Naikinti**.

   :::image type="content" source="media/delete-environment.png" alt-text="Valdykite, kad panaikintumėte aplinką.":::

1. Norėdami patvirtinti panaikinimą, įveskite aplinkos pavadinimą ir pasirinkite **Naikinti**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
