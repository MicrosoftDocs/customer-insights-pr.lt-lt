---
title: Papildymas su SFTP kliento importavimu
description: Bendra informacija apie SFTP tinkinto importavimo papildymą.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595865"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Praturtinkite klientų profilius su tinkintais duomenimis (peržiūra)

„Secure File Transfer Protocol“ (SFTP) tinkintas importavimas leidžia jums importuoti praturtintus duomenis, kurie neturi pereiti pro duomenų suvienodinimo procesą. Jis yra lankstus, saugus ir paprastai leidžia apdoroti jūsų duomenis. SFTP tinkintas importavimas gali būti naudojamas kartu su [SFTP eksportavimu](export-sftp.md) ir leidžia jums eksportuoti kliento profilio duomenis, kurie turi būti papildyti. Duomenys gali būti apdorojami, papildyti ir SFTP tinkintas importavimas gali būti naudojamas siekiant sukurti papildytus duomenis atgal į publikos įžvalgų „Dynamics 365 Customer Insights“ galimybę.

## <a name="prerequisites"></a>Būtinosios sąlygos

Siekiant sukonfigūruoti SFTP tinkintą importavimą, būtina atitikti tolesnes būtinąsias sąlygas:

- Turite vartotojo prisijungimo duomenis (vartotojo vardą ir slaptažodį) SFTP vietai, iš kurios duomenys bus importuojami.
- Turite URL ir prievado numerį (dažniausiai 22) STFP šeimininkui.
- Turite failo pavadinimą ir failo vietą, kurį importuosite į SFTP šeimininką.
- Esama *model.json* failo, kuris nurodo schemą importuojamiems duomenims. Šis failas turi būti tame pačiame kataloge kaip ir importuojamas failas.
- Turite [Administratoriaus](permissions.md#administrator) leidimą.

## <a name="configuration"></a>Konfigūracija

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. **SFTP tinkinto importavimo plyta**, pasirinkite **Papildyti mano duomenis**.

   > [!div class="mx-imgBorder"]
   > ![SFTP tinkinto importavimo plyta](media/SFTP_Custom_Import_tile.png "SFTP tinkinto importavimo plyta")

1. Pasirinkite **Pradėti** ir pateikite prisijungimo duomenis bei adresą SFTP serveriui. Pavyzdžiui, sftp://mysftpserver.com:22.

1. Įveskite failo pavadinimą, kuris turi duomenis ir kelią failui SFTP serveryje, jei jis nėra šaknies kataloge.

1. Patvirtinkite visas įvestis pasirinkdami **Sujungti su Tinkintu importavimu**.

   > [!div class="mx-imgBorder"]
   > ![SFTP tinkinto importavimo konfigūravimo leidimas](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP tinkinto importavimo konfigūravimo leidimas")

## <a name="defining-field-mappings"></a>Laukelio žemėlapio nustatymas 

Katalogas turintis importuojamą SFTP serveryje failą taip pat privalo turėti *model.json* failą. Šis failas nustato schemą, kuri bus naudojama duomenų importavimui. Schema turi naudoti [„Common Data Model“](/common-data-model/) siekiant nurodyti laukelio žemėlapį. Paprastas model.json failo pavyzdys atrodo taip:

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

Atlikite veiksmus su papildytais klientų duomenimis. Sukurkite [segmentus](segments.md), [priemones](measures.md) ir [eksportuokite duomenis](export-destinations.md) siekiant pristatyti suasmenintas patirtis jūsų klientams.




[!INCLUDE[footer-include](../includes/footer-banner.md)]