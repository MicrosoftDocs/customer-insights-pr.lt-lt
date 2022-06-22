---
title: Papildymas su SFTP kliento importavimu
description: Bendra informacija apie SFTP tinkinto importavimo papildymą.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 657afb6fcb68429680eb677734b4115e69769008
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953729"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Praturtinkite klientų profilius su tinkintais duomenimis (peržiūra)

„Secure File Transfer Protocol“ (SFTP) tinkintas importavimas leidžia jums importuoti praturtintus duomenis, kurie neturi pereiti pro duomenų suvienodinimo procesą. Jis yra lankstus, saugus ir paprastai leidžia apdoroti jūsų duomenis. SFTP tinkintas importavimas gali būti naudojamas kartu su [SFTP eksportavimu](export-sftp.md) ir leidžia jums eksportuoti kliento profilio duomenis, kurie turi būti papildyti. Tada duomenys gali būti apdorojami ir praturtinami, o SFTP pasirinktinis importavimas gali būti naudojamas norint grąžinti praturtintus duomenis į Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Failo, kuris bus importuojamas SFTP pagrindiniame kompiuteryje, vardas ir vieta (maršrutas) yra žinomi.

- Galimas *failas model.json*, nurodantis importuojamų duomenų Bendrųjų duomenų modelio schemą. Šis failas turi būti tame pačiame kataloge kaip ir importuojamas failas.

- Sukonfigūruotas SFTP [ryšys](connections.md)[...](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Failų schemos pavyzdys

Katalogas turintis importuojamą SFTP serveryje failą taip pat privalo turėti *model.json* failą. Šis failas nustato schemą, kuri bus naudojama duomenų importavimui. Schema turi naudoti [„Common Data Model“](/common-data-model/) laukų susiejimui nurodyti. Paprastas model.json failo pavyzdys atrodo taip:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP pasirenkamo importavimo ryšio konfigūravimas

Turite būti ["Customer Insights" administratorius](permissions.md#admin) ir turėti SFTP vietos, iš kurios norite importuoti duomenis, vartotojo kredencialus, URL ir prievado numerį.

1. Konfigūruodami sodrinimą pasirinkite **Įtraukti ryšį** arba eikite į **Administratoriaus** > **ryšiai** ir plytelėje Pasirinktinis importavimas pasirinkite **Nustatyti**.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Pasirinktinis importavimo ryšio konfigūracijos puslapis.":::

1. Įveskite ryšio pavadinimą.

1. Įveskite galiojantį SFTP serverio, kuriame importuotini duomenys, vartotojo vardą, slaptažodį ir pagrindinio kompiuterio URL.

1. Pasirinkdami Sutinku, peržiūrėkite [ir pateikite savo sutikimą dėl](#data-privacy-and-compliance) duomenų privatumo ir sąlygų **sutinku**.

1. Pasirinkite **Tikrinti**, kad patikrintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

### <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate Dynamics 365 Customer Insights perduoti duomenis naudodami pasirinktinį importavimą, leidžiate perduoti duomenis už atitikties ribos, įskaitant potencialiai neskelbtinus Dynamics 365 Customer Insights duomenis, pvz., asmens duomenis. "Microsoft" perduos tokius duomenis jūsų nurodymu, tačiau jūs esate atsakingi už tai, kad duomenys atitiktų bet kokius privatumo ar saugos įsipareigojimus, kuriuos galite turėti. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

## <a name="configure-the-import"></a>Importavimo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. SFTP pasirinktinio importavimo **plytelėje** pasirinkite **Praturtinti mano duomenis**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP pasirenkamo importavimo plytelė.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Pasirinkite ryšį. Jei jo nėra, kreipkitės į administratorių.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite praturtinti. Kliento *subjektas* praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Pasirinkite **Toliau**.

1. Įveskite norimo **importuoti duomenų failo maršrutą** ir **failo vardą**.

1. Pasirinkite **Toliau**.

1. **Pateikite sodrinimo pavadinimą** ir išvesties objekto **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte sodrinimo procesą, arba beveik, kad grįžtumėte į **puslapį Praturtinimai**.

## <a name="enrichment-results"></a>Papildymo rezultatai

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
