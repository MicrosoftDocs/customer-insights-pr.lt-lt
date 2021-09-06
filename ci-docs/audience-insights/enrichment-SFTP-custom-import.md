---
title: Papildymas su SFTP kliento importavimu
description: Bendra informacija apie SFTP tinkinto importavimo papildymą.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b67aa7477033222b0bc9512a962a1580edd973b4882ce925620ff5ec14f83fe3
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032722"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Praturtinkite klientų profilius su tinkintais duomenimis (peržiūra)

„Secure File Transfer Protocol“ (SFTP) tinkintas importavimas leidžia jums importuoti praturtintus duomenis, kurie neturi pereiti pro duomenų suvienodinimo procesą. Jis yra lankstus, saugus ir paprastai leidžia apdoroti jūsų duomenis. SFTP tinkintas importavimas gali būti naudojamas kartu su [SFTP eksportavimu](export-sftp.md) ir leidžia jums eksportuoti kliento profilio duomenis, kurie turi būti papildyti. Tada duomenis galima apdoroti ir papildyti, o SFTP pasirinktinis importavimas gali būti naudojamas papildytiems duomenims grąžinti į auditorijos įžvalgų galimybes „Dynamics 365 Customer Insights“.

## <a name="prerequisites"></a>Būtinosios sąlygos

Siekiant sukonfigūruoti SFTP tinkintą importavimą, būtina atitikti tolesnes būtinąsias sąlygas:

- Turite failo vardą ir vietą (kelią), kurį norite importuoti į SF DALĮ pagrindinį kompiuterį.
- Yra failas *model.json*, kuris nurodo [bendrą duomenų modelio schemą](/common-data-model/) importuojamiems duomenims. Šis failas turi būti tame pačiame kataloge kaip ir importuojamas failas.
- SFTP ryšį jau sukonfigūravo administratorius *arba* turite [administratoriaus](permissions.md#administrator) teises. Jums reikės naudotojo kredencialų, URL ir SFTP vietos, iš kurios norėsite importuoti duomenis, prievado numerio.


## <a name="configure-the-import"></a>Importavimo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. **SFTP pasirenkamo importavimo plytelėje** pasirinkite **Papildyti mano duomenis**, o tada pasirinkite **Darbo pradžia**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP pasirenkamo importavimo plytelė.":::

1. Pasirinkite [ryšį](connections.md) iš iškrentančiojo sąrašo. Jei ryšio nėra, kreipkitės į administratorių. Jei esate administratorius, galite sukurti ryšį pasirinkdami Įtraukti ryšį ir **Įtraukti ryšį** ir rinktis **SFTP tinkintas importavimas** iš išplečiamojo sąrašo.

1. Norėdami patvirtinti pasirinktą ryšį pasirinkite **Prisijungti prie pasirenkamo importavimo**.

1.  Pažymėkite **Kitas** ir įveskite **norimo** ir **Failo kelią** importuoti duomenų failo kelią ir failo vardą.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Ekrano nuotrauka įvedant duomenų vietą.":::

1. Pasirinkite **Toliau** ir pateikite papildymo pavadinimą bei išvesties objekto pavadinimą. 

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP pasirenkamo importavimo ryšio konfigūravimas 

Jei norite konfigūruoti ryšius, turite būti administratorius. Pasirinkite **Pridėti ryšį**, kai konfigūruosite papildymą *arba* eikite į **Administravimas** > **Ryšiai** ir pasirenkamo importavimo plytelėje pasirinkite **Sąranka**.

1. Laukelyje **Rodomas pavadinimas** įveskite ryšio pavadinimą.

1. Įveskite galiojantį SFTP serverio, kuriame importuotini duomenys, vartotojo vardą, slaptažodį ir pagrindinio kompiuterio URL.

1. Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**.

1. Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją.

1. Baigus tikrinimą ryšį galima įrašyti pasirenkant **Įrašyti**.

   > [!div class="mx-imgBorder"]
   > ![„Experian“ ryšio konfigūravimo puslapis.](media/enrichment-SFTP-connection.png "„Experian“ ryšio konfigūravimo puslapis")


## <a name="defining-field-mappings"></a>Laukelio žemėlapio nustatymas 

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
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
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

## <a name="enrichment-results"></a>Papildymo rezultatai

Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**. Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį. Apdorojimo laikas priklauso nuo importuojamų duomenų dydžio ir jungties su SFTP serveriu.

Po papildymo proceso pabaigos, galėsite peržiūrėti jūsų naujai importuotus papildytus duomenis skyriuje **Mano papildymai**. Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.

Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.

## <a name="next-steps"></a>Tolesni veiksmai

Atlikite veiksmus su papildytais klientų duomenimis. Kurkite [segmentai](segments.md) ir [priemones](measures.md) bei net [eksportuokite duomenis,](export-destinations.md) kad klientams būtų galima teikti personalizuotas funkcijas.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
