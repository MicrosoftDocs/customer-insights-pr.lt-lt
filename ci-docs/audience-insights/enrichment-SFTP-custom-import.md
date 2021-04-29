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
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896291"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="32d7e-103">Praturtinkite klientų profilius su tinkintais duomenimis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="32d7e-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="32d7e-104">Apsaugotas failų perkėlimo protokolas (SFTP) pasirinktinio importavimo funkcija leidžia importuoti duomenis, kurių negalima suvienodinti atliekant duomenų suvienodinimo procedūrą.</span><span class="sxs-lookup"><span data-stu-id="32d7e-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="32d7e-105">Jis yra lankstus, saugus ir paprastai leidžia apdoroti jūsų duomenis.</span><span class="sxs-lookup"><span data-stu-id="32d7e-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="32d7e-106">SFTP tinkintas importavimas gali būti naudojamas kartu su [SFTP eksportavimu](export-sftp.md) ir leidžia jums eksportuoti kliento profilio duomenis, kurie turi būti papildyti.</span><span class="sxs-lookup"><span data-stu-id="32d7e-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="32d7e-107">Duomenys gali būti apdorojami, papildyti ir SFTP tinkintas importavimas gali būti naudojamas siekiant sukurti papildytus duomenis atgal į publikos įžvalgų „Dynamics 365 Customer Insights“ galimybę.</span><span class="sxs-lookup"><span data-stu-id="32d7e-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="32d7e-108">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="32d7e-108">Prerequisites</span></span>

<span data-ttu-id="32d7e-109">Siekiant sukonfigūruoti SFTP tinkintą importavimą, būtina atitikti tolesnes būtinąsias sąlygas:</span><span class="sxs-lookup"><span data-stu-id="32d7e-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="32d7e-110">Turite failo, kuris bus importuojamas į pagrindinį SFTP kompiuterį, pavadinimą ir vietą (maršrutą).</span><span class="sxs-lookup"><span data-stu-id="32d7e-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="32d7e-111">Yra failas *model.json*, kuris nurodo [bendrą duomenų modelio schemą](/common-data-model/) importuojamiems duomenims.</span><span class="sxs-lookup"><span data-stu-id="32d7e-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="32d7e-112">Šis failas turi būti tame pačiame kataloge kaip ir importuojamas failas.</span><span class="sxs-lookup"><span data-stu-id="32d7e-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="32d7e-113">SFTP ryšį jau sukonfigūravo administratorius *arba* turite [administratoriaus](permissions.md#administrator) teises.</span><span class="sxs-lookup"><span data-stu-id="32d7e-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="32d7e-114">Jums reikės naudotojo kredencialų, URL ir SFTP vietos, iš kurios norėsite importuoti duomenis, prievado numerio.</span><span class="sxs-lookup"><span data-stu-id="32d7e-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="32d7e-115">Importavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="32d7e-115">Configure the import</span></span>

1. <span data-ttu-id="32d7e-116">Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.</span><span class="sxs-lookup"><span data-stu-id="32d7e-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="32d7e-117">**SFTP pasirenkamo importavimo plytelėje** pasirinkite **Papildyti mano duomenis**, o tada pasirinkite **Darbo pradžia**.</span><span class="sxs-lookup"><span data-stu-id="32d7e-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP pasirenkamo importavimo plytelė.":::

1. <span data-ttu-id="32d7e-119">Išskleidžiamajame sąraše pasirinkite [ryšį](connections.md).</span><span class="sxs-lookup"><span data-stu-id="32d7e-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="32d7e-120">Jei ryšio nėra, kreipkitės į administratorių.</span><span class="sxs-lookup"><span data-stu-id="32d7e-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="32d7e-121">Jei esate administratorius, ryšį galite sukurti ryšį pasirinkdami **Pridėti ryšį** ir išskleidžiamajame sąraše pasirinkdami **SFTP pasirenkamas importavimas**.</span><span class="sxs-lookup"><span data-stu-id="32d7e-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="32d7e-122">Norėdami patvirtinti pasirinktą ryšį pasirinkite **Prisijungti prie pasirenkamo importavimo**.</span><span class="sxs-lookup"><span data-stu-id="32d7e-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="32d7e-123">Pasirinkite **Toliau** ir įveskite **Failo pavadinimas** ir **Maršrutas** duomenų failui, kurį norite importuoti.</span><span class="sxs-lookup"><span data-stu-id="32d7e-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Ekrano nuotrauka įvedant duomenų vietą.":::

1. <span data-ttu-id="32d7e-125">Pasirinkite **Toliau** ir pateikite papildymo pavadinimą bei išvesties objekto pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="32d7e-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="32d7e-126">Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.</span><span class="sxs-lookup"><span data-stu-id="32d7e-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="32d7e-127">SFTP pasirenkamo importavimo ryšio konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="32d7e-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="32d7e-128">Jei norite konfigūruoti ryšius, turite būti administratorius.</span><span class="sxs-lookup"><span data-stu-id="32d7e-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="32d7e-129">Pasirinkite **Pridėti ryšį**, kai konfigūruosite papildymą *arba* eikite į **Administravimas** > **Ryšiai** ir pasirenkamo importavimo plytelėje pasirinkite **Sąranka**.</span><span class="sxs-lookup"><span data-stu-id="32d7e-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="32d7e-130">Laukelyje **Rodomas pavadinimas** įveskite ryšio pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="32d7e-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="32d7e-131">Įveskite galiojantį naudotojo vardą, slaptažodį ir SFTP perverio, kuriame yra importuoti skirti duomenys, pagrindinio kompiuterio URL.</span><span class="sxs-lookup"><span data-stu-id="32d7e-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="32d7e-132">Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**.</span><span class="sxs-lookup"><span data-stu-id="32d7e-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="32d7e-133">Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="32d7e-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="32d7e-134">Baigus patikrinimą ryšį galima išsaugoti spustelėjus **Išsaugoti**.</span><span class="sxs-lookup"><span data-stu-id="32d7e-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="32d7e-135">![„Experian“ ryšio konfigūravimo puslapis](media/enrichment-SFTP-connection.png "„Experian“ ryšio konfigūravimo puslapis")</span><span class="sxs-lookup"><span data-stu-id="32d7e-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="32d7e-136">Laukelio žemėlapio nustatymas</span><span class="sxs-lookup"><span data-stu-id="32d7e-136">Defining field mappings</span></span> 

<span data-ttu-id="32d7e-137">Katalogas turintis importuojamą SFTP serveryje failą taip pat privalo turėti *model.json* failą.</span><span class="sxs-lookup"><span data-stu-id="32d7e-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="32d7e-138">Šis failas nustato schemą, kuri bus naudojama duomenų importavimui.</span><span class="sxs-lookup"><span data-stu-id="32d7e-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="32d7e-139">Schema turi naudoti [„Common Data Model“](/common-data-model/) siekiant nurodyti laukelio žemėlapį.</span><span class="sxs-lookup"><span data-stu-id="32d7e-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="32d7e-140">Paprastas model.json failo pavyzdys atrodo taip:</span><span class="sxs-lookup"><span data-stu-id="32d7e-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="32d7e-141">Papildymo rezultatai</span><span class="sxs-lookup"><span data-stu-id="32d7e-141">Enrichment results</span></span>

<span data-ttu-id="32d7e-142">Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="32d7e-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="32d7e-143">Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį.</span><span class="sxs-lookup"><span data-stu-id="32d7e-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="32d7e-144">Apdorojimo laikas priklauso nuo importuojamų duomenų dydžio ir jungties su SFTP serveriu.</span><span class="sxs-lookup"><span data-stu-id="32d7e-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="32d7e-145">Po papildymo proceso pabaigos, galėsite peržiūrėti jūsų naujai importuotus papildytus duomenis skyriuje **Mano papildymai**.</span><span class="sxs-lookup"><span data-stu-id="32d7e-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="32d7e-146">Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.</span><span class="sxs-lookup"><span data-stu-id="32d7e-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="32d7e-147">Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.</span><span class="sxs-lookup"><span data-stu-id="32d7e-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="32d7e-148">Tolesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="32d7e-148">Next steps</span></span>

<span data-ttu-id="32d7e-149">Atlikite veiksmus su papildytais klientų duomenimis.</span><span class="sxs-lookup"><span data-stu-id="32d7e-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="32d7e-150">Sukurkite [segmentus](segments.md), [priemones](measures.md) ir [eksportuokite duomenis](export-destinations.md) siekiant pristatyti suasmenintas patirtis jūsų klientams.</span><span class="sxs-lookup"><span data-stu-id="32d7e-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
