---
title: Įmonės profilių praturtinimas "Dun & Bradstreet"
description: Bendra informacija apie "Dun & Bradstreet" trečiosios šalies sodrinimą.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653798"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Įmonės profilių praturtinimas naudojant "Dun & Bradstreet" (peržiūra)

"Dun & Bradstreet" teikia komercinius duomenis, analizę ir įžvalgas įmonėms. Tai leidžia klientams su vieningais įmonių klientų profiliais papildyti savo duomenis. Sodrinimas apima tokius atributus kaip DUNS numeris, įmonės dydis, vieta, pramonė ir kt.

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint sukonfigūruoti "Dun & Bradstreet" sodrinimą, turi būti įvykdytos šios būtinos sąlygos:

- Turite aktyvią [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) licenciją.
- Turite įmonių [vieningus klientų profilius](customer-profiles.md).
- Dun & Bradstreet [ryšį](connections.md) konfigūruoja administratorius. Galite jį sukurti, jei turite [administratoriaus](permissions.md#admin) teises ir "Dun & Bradstreet Connect" kredencialus. 

## <a name="setting-up-your-dun--bradstreet-project"></a>"Dun & Bradstreet" projekto parengimas

Kaip licencijuotas "Dun & Bradstreet" vartotojas, galite sukurti projektą " [Dun & Bradstreet Connect"](https://connect.dnb.com?lead_source=microsoft_audienceinsights). 


1. Prisijunkite prie ["Dun & Bradstreet Connect"](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Norėdami gauti kredencialus, [atkurkite slaptažodį](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Atsisiųskite [mūsų csv šablono failą](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), kuris bus naudojamas auditorijos įžvalgų laukams susieti su atitinkamais "Dun & Bradstreet" laukais. 

1. Įkelkite failą į **"Dun & Bradstreet" projekto kūrimo patirties įkėlimo duomenų** veiksmą. 

1. Pasirinkite horizontalius taškus po atitinkamu **šaltiniu** naujai sukurtame "Dun & Bradstreet" projekte, kad pamatytumėte galimas parinktis.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="&quot;Dun & Bradstreet&quot; projekto taškų ekrano nuotrauka.":::

1. Pasirinkite **Gauti S3 informaciją**. Saugokite šią informaciją saugioje vietoje. Jums reikės, kad [nustatytumėte ryšį, kad praturtintumėte](#configure-a-connection-for-dun--bradstreet) auditorijos įžvalgas. 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="&quot;Dun & Bradstreet&quot; projekto s3 informacijos pasirinkimo ekrano nuotrauka.":::



## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Publikos įžvalgose, eikite į **Duomenys** > **Praturtinimas**.

1. Pasirinkite **Praturtinti mano duomenis** "Dun & Bradstreet" plytelėje ir pasirinkite **Pradėti**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="&quot;Dun & Bradstreet&quot; plytelių ekrano nuotrauka.":::

1. Pasirinkite [ryšį](connections.md) iš iškrentančiojo sąrašo. Jei ryšio nėra, kreipkitės į administratorių. Jei esate administratorius, galite sukurti ryšį. Pasirinkite **Įtraukti ryšį** ir pasirinkite **Dun & Bradstreet**. 

1. Pasirinkite **Prisijungti prie Dun & Bradstreet**, kad patvirtintumėte ryšį.

1. Pasirinkite **Pirmyn** ir pasirinkite **klientų duomenų rinkinį**, kurį norite praturtinti įmonės duomenimis iš "Dun & Bradstreet". Galite pasirinkti objektą **Klientas**, kad praturtintumėte visus savo klientų profilius, arba pasirinkti segmento objektą, kad praturtintumėte tik tame segmente esančius vieningus klientų profilius.

1. Pasirinkite **Pirmyn** ir apibrėžkite, kurie laukai iš jūsų vieningų profilių naudojami ieškant atitinkančių įmonės duomenų iš "Dun & Bradstreet". Reikalingi **DUNS numeris** arba **įmonės** pavadinimas ir **šalies** laukai. Šalies lauke palaikomi [dviejų ar trijų raidžių šalių kodai](https://www.iso.org/iso-3166-country-codes.html), šalies pavadinimas anglų kalba, šalies pavadinimas gimtąja kalba ir telefono prefiksas. Kai kurie bendri šalies variantai yra šie:

   * JAV: Jungtinės Amerikos Valstijos, JAV, JAV, Amerika.
   * A.S.: Kanada.
   * JUNGTINĖ KARALYSTĖ: Jungtinė Karalystė, Jungtinė Karalystė, Didžioji Britanija, GB, Jungtinė Didžiosios Britanijos ir Šiaurės Airijos Karalystė, Jungtinė Didžiosios Britanijos Karalystė.
   * AU: Australija, Australijos Sandrauga.
   * Fr: Prancūzija, Prancūzijos Respublika.
   * DE: Vokietija, Vokietija, Vokietija, Vokietija, Vokietija, Vokietija, Vokietija.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet lauko susiejimo sritis.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. Nurodykite papildymo pavadinimą ir peržiūrėję pasirinkimus pažymėkite **Išsaugoti papildymą**.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigūruoti "Dun & Bradstreet" ryšį 

Jei norite konfigūruoti ryšius, turite būti administratorius. Konfigūruodami sodrinimą pasirinkite **Įtraukti ryšį** arba *eikite į* AdminConnections **·** > **ir pasirinkite** Nustatyti **plytelėje Dun & Bradstreet.**

1. Pasirinkite **Darbo pradžia**. 

1. Laukelyje **Rodomas pavadinimas** įveskite ryšio pavadinimą.

1. Pateikite galiojančius "Dun & Bradstreet" kredencialus ir "Dun & Bradstreet" projekto informaciją Regionas *, "Drop" aplanko kelias ir "Drop" aplanko pavadinimą*. Šią informaciją [gausite](#setting-up-your-dun--bradstreet-project) iš "Dun & Bradstreet" projekto.

1. Pasirinkdami Sutinku, peržiūrėkite **ir pateikite savo sutikimą dėl** duomenų privatumo ir sąlygų **sutinku**.

1. Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją.

1. Baigę patikrinimą pasirinkite **Išsaugoti**.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet ryšio konfigūracijos puslapis.":::

## <a name="enrichment-results"></a>Papildymo rezultatai

Atnaujinę papildymą naujai papildytus įmonės duomenis galite peržiūrėti dalyje [Mano papildymai](enrichment-hub.md). Galite rasti paskutinio naujinimo laiką ir papildytų profilių skaičių.

Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.

## <a name="next-steps"></a>Kiti veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate Dynamics 365 Customer Insights perduoti duomenis "Dun & Bradstreet", leidžiate perduoti duomenis už atitikties ribos Dynamics 365 Customer Insights, įskaitant potencialiai neskelbtinus duomenis, pvz., Asmens duomenis. "Microsoft" perduos tokius duomenis jūsų nurodymu, tačiau jūs esate atsakingi už tai, kad "Dun & Bradstreet" laikytųsi visų privatumo ar saugos įsipareigojimų, kuriuos galite turėti. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](includes/footer-banner.md)]
