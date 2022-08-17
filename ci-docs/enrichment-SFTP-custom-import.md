---
title: Praturtinkite klientų profilius naudodami SFTP pasirinktinį importavimą (peržiūra)
description: Bendra informacija apie SFTP tinkinto importavimo papildymą.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237776"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Praturtinkite klientų profilius naudodami SFTP pasirinktinį importavimą (peržiūra)

„Secure File Transfer Protocol“ (SFTP) tinkintas importavimas leidžia jums importuoti praturtintus duomenis, kurie neturi pereiti pro duomenų suvienodinimo procesą. Jis yra lankstus, saugus ir paprastai leidžia apdoroti jūsų duomenis. SFTP tinkintas importavimas gali būti naudojamas kartu su [SFTP eksportavimu](export-sftp.md) ir leidžia jums eksportuoti kliento profilio duomenis, kurie turi būti papildyti. Tada duomenis galima apdoroti ir papildyti, o SFTP pasirinktinį importavimą galima naudoti norint sugrąžinti papildytus duomenis į Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Žinomas failo vardas ir failo, kuris bus importuojamas į SFTP pagrindinį kompiuterį, vieta (kelias).

- Galimas *failas model.json*, nurodantis importuojamų duomenų bendrojo duomenų modelio schemą. Šis failas turi būti tame pačiame kataloge kaip ir importuojamas failas.

- Sukonfigūruotas [SFTP](connections.md) ryšys [...](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Failo schemos pavyzdys

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

1. Konfigūruojant papildymą pasirinkite **Įtraukti ryšį** arba eikite į **Administratoriaus** > **ryšiai** ir **pasirinkite Nustatyti** plytelėje Pasirinktinis importavimas.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Pasirinktinio importavimo ryšio konfigūracijos puslapis.":::

1. Įveskite ryšio pavadinimą.

1. Įveskite galiojantį SFTP serverio, kuriame importuotini duomenys, vartotojo vardą, slaptažodį ir pagrindinio kompiuterio URL.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Tikrinti**, kad patvirtintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

## <a name="configure-the-import"></a>Importavimo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Pasirinkite **Papildyti mano duomenis** SFTP pasirinktinio importavimo **plytelėje**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP pasirenkamo importavimo plytelė.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Pasirinkite ryšį. Jei ryšio nėra, kreipkitės į administratorių.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite papildyti. *Kliento* objektas praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Pasirinkite **Toliau**.

1. **Įveskite duomenų failo, kurį norite importuoti, kelią** ir **failo pavadinimą**.

1. Pasirinkite **Toliau**.

1. **Pateikite papildymo pavadinimą** ir išvesties objekto **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte papildymo procesą, arba uždarykite, kad grįžtumėte į **puslapį Papildymai**.

## <a name="view-enrichment-results"></a>Papildymo rezultatų peržiūra

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
