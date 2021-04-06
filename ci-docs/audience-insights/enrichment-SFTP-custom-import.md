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
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="4fba0-103">Praturtinkite klientų profilius su tinkintais duomenimis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="4fba0-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="4fba0-104">„Secure File Transfer Protocol“ (SFTP) tinkintas importavimas leidžia jums importuoti praturtintus duomenis, kurie neturi pereiti pro duomenų suvienodinimo procesą.</span><span class="sxs-lookup"><span data-stu-id="4fba0-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="4fba0-105">Jis yra lankstus, saugus ir paprastai leidžia apdoroti jūsų duomenis.</span><span class="sxs-lookup"><span data-stu-id="4fba0-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="4fba0-106">SFTP tinkintas importavimas gali būti naudojamas kartu su [SFTP eksportavimu](export-sftp.md) ir leidžia jums eksportuoti kliento profilio duomenis, kurie turi būti papildyti.</span><span class="sxs-lookup"><span data-stu-id="4fba0-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="4fba0-107">Duomenys gali būti apdorojami, papildyti ir SFTP tinkintas importavimas gali būti naudojamas siekiant sukurti papildytus duomenis atgal į publikos įžvalgų „Dynamics 365 Customer Insights“ galimybę.</span><span class="sxs-lookup"><span data-stu-id="4fba0-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4fba0-108">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="4fba0-108">Prerequisites</span></span>

<span data-ttu-id="4fba0-109">Siekiant sukonfigūruoti SFTP tinkintą importavimą, būtina atitikti tolesnes būtinąsias sąlygas:</span><span class="sxs-lookup"><span data-stu-id="4fba0-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4fba0-110">Turite vartotojo prisijungimo duomenis (vartotojo vardą ir slaptažodį) SFTP vietai, iš kurios duomenys bus importuojami.</span><span class="sxs-lookup"><span data-stu-id="4fba0-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="4fba0-111">Turite URL ir prievado numerį (dažniausiai 22) STFP šeimininkui.</span><span class="sxs-lookup"><span data-stu-id="4fba0-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="4fba0-112">Turite failo pavadinimą ir failo vietą, kurį importuosite į SFTP šeimininką.</span><span class="sxs-lookup"><span data-stu-id="4fba0-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="4fba0-113">Esama *model.json* failo, kuris nurodo schemą importuojamiems duomenims.</span><span class="sxs-lookup"><span data-stu-id="4fba0-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="4fba0-114">Šis failas turi būti tame pačiame kataloge kaip ir importuojamas failas.</span><span class="sxs-lookup"><span data-stu-id="4fba0-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="4fba0-115">Turite [Administratoriaus](permissions.md#administrator) leidimą.</span><span class="sxs-lookup"><span data-stu-id="4fba0-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="4fba0-116">Konfigūracija</span><span class="sxs-lookup"><span data-stu-id="4fba0-116">Configuration</span></span>

1. <span data-ttu-id="4fba0-117">Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.</span><span class="sxs-lookup"><span data-stu-id="4fba0-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="4fba0-118">**SFTP tinkinto importavimo plyta**, pasirinkite **Papildyti mano duomenis**.</span><span class="sxs-lookup"><span data-stu-id="4fba0-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4fba0-119">![SFTP tinkinto importavimo plyta](media/SFTP_Custom_Import_tile.png "SFTP tinkinto importavimo plyta")</span><span class="sxs-lookup"><span data-stu-id="4fba0-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="4fba0-120">Pasirinkite **Pradėti** ir pateikite prisijungimo duomenis bei adresą SFTP serveriui.</span><span class="sxs-lookup"><span data-stu-id="4fba0-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="4fba0-121">Pavyzdžiui, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="4fba0-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="4fba0-122">Įveskite failo pavadinimą, kuris turi duomenis ir kelią failui SFTP serveryje, jei jis nėra šaknies kataloge.</span><span class="sxs-lookup"><span data-stu-id="4fba0-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="4fba0-123">Patvirtinkite visas įvestis pasirinkdami **Sujungti su Tinkintu importavimu**.</span><span class="sxs-lookup"><span data-stu-id="4fba0-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4fba0-124">![SFTP tinkinto importavimo konfigūravimo leidimas](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP tinkinto importavimo konfigūravimo leidimas")</span><span class="sxs-lookup"><span data-stu-id="4fba0-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="4fba0-125">Laukelio žemėlapio nustatymas</span><span class="sxs-lookup"><span data-stu-id="4fba0-125">Defining field mappings</span></span> 

<span data-ttu-id="4fba0-126">Katalogas turintis importuojamą SFTP serveryje failą taip pat privalo turėti *model.json* failą.</span><span class="sxs-lookup"><span data-stu-id="4fba0-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="4fba0-127">Šis failas nustato schemą, kuri bus naudojama duomenų importavimui.</span><span class="sxs-lookup"><span data-stu-id="4fba0-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="4fba0-128">Schema turi naudoti [„Common Data Model“](/common-data-model/) siekiant nurodyti laukelio žemėlapį.</span><span class="sxs-lookup"><span data-stu-id="4fba0-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="4fba0-129">Paprastas model.json failo pavyzdys atrodo taip:</span><span class="sxs-lookup"><span data-stu-id="4fba0-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="4fba0-130">Papildymo rezultatai</span><span class="sxs-lookup"><span data-stu-id="4fba0-130">Enrichment results</span></span>

<span data-ttu-id="4fba0-131">Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="4fba0-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="4fba0-132">Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį.</span><span class="sxs-lookup"><span data-stu-id="4fba0-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4fba0-133">Apdorojimo laikas priklauso nuo importuojamų duomenų dydžio ir jungties su SFTP serveriu.</span><span class="sxs-lookup"><span data-stu-id="4fba0-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="4fba0-134">Po papildymo proceso pabaigos, galėsite peržiūrėti jūsų naujai importuotus papildytus duomenis skyriuje **Mano papildymai**.</span><span class="sxs-lookup"><span data-stu-id="4fba0-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="4fba0-135">Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.</span><span class="sxs-lookup"><span data-stu-id="4fba0-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4fba0-136">Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.</span><span class="sxs-lookup"><span data-stu-id="4fba0-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4fba0-137">Tolesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="4fba0-137">Next steps</span></span>

<span data-ttu-id="4fba0-138">Atlikite veiksmus su papildytais klientų duomenimis.</span><span class="sxs-lookup"><span data-stu-id="4fba0-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4fba0-139">Sukurkite [segmentus](segments.md), [priemones](measures.md) ir [eksportuokite duomenis](export-destinations.md) siekiant pristatyti suasmenintas patirtis jūsų klientams.</span><span class="sxs-lookup"><span data-stu-id="4fba0-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]