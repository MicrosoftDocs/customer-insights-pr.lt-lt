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
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304660"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="1747e-103">Praturtinkite klientų profilius su tinkintais duomenimis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="1747e-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="1747e-104">„Secure File Transfer Protocol“ (SFTP) tinkintas importavimas leidžia jums importuoti praturtintus duomenis, kurie neturi pereiti pro duomenų suvienodinimo procesą.</span><span class="sxs-lookup"><span data-stu-id="1747e-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="1747e-105">Jis yra lankstus, saugus ir paprastai leidžia apdoroti jūsų duomenis.</span><span class="sxs-lookup"><span data-stu-id="1747e-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="1747e-106">SFTP tinkintas importavimas gali būti naudojamas kartu su [SFTP eksportavimu](export-sftp.md) ir leidžia jums eksportuoti kliento profilio duomenis, kurie turi būti papildyti.</span><span class="sxs-lookup"><span data-stu-id="1747e-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="1747e-107">Tada duomenis galima apdoroti ir papildyti, o SFTP pasirinktinis importavimas gali būti naudojamas papildytiems duomenims grąžinti į auditorijos įžvalgų galimybes „Dynamics 365 Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="1747e-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1747e-108">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="1747e-108">Prerequisites</span></span>

<span data-ttu-id="1747e-109">Siekiant sukonfigūruoti SFTP tinkintą importavimą, būtina atitikti tolesnes būtinąsias sąlygas:</span><span class="sxs-lookup"><span data-stu-id="1747e-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="1747e-110">Turite failo vardą ir vietą (kelią), kurį norite importuoti į SF DALĮ pagrindinį kompiuterį.</span><span class="sxs-lookup"><span data-stu-id="1747e-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="1747e-111">Yra failas *model.json*, kuris nurodo [bendrą duomenų modelio schemą](/common-data-model/) importuojamiems duomenims.</span><span class="sxs-lookup"><span data-stu-id="1747e-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="1747e-112">Šis failas turi būti tame pačiame kataloge kaip ir importuojamas failas.</span><span class="sxs-lookup"><span data-stu-id="1747e-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="1747e-113">SFTP ryšį jau sukonfigūravo administratorius *arba* turite [administratoriaus](permissions.md#administrator) teises.</span><span class="sxs-lookup"><span data-stu-id="1747e-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="1747e-114">Jums reikės naudotojo kredencialų, URL ir SFTP vietos, iš kurios norėsite importuoti duomenis, prievado numerio.</span><span class="sxs-lookup"><span data-stu-id="1747e-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="1747e-115">Importavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="1747e-115">Configure the import</span></span>

1. <span data-ttu-id="1747e-116">Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.</span><span class="sxs-lookup"><span data-stu-id="1747e-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="1747e-117">**SFTP pasirenkamo importavimo plytelėje** pasirinkite **Papildyti mano duomenis**, o tada pasirinkite **Darbo pradžia**.</span><span class="sxs-lookup"><span data-stu-id="1747e-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP pasirenkamo importavimo plytelė.":::

1. <span data-ttu-id="1747e-119">Pasirinkite [ryšį](connections.md) iš iškrentančiojo sąrašo.</span><span class="sxs-lookup"><span data-stu-id="1747e-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="1747e-120">Jei ryšio nėra, kreipkitės į administratorių.</span><span class="sxs-lookup"><span data-stu-id="1747e-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="1747e-121">Jei esate administratorius, galite sukurti ryšį pasirinkdami Įtraukti ryšį ir **Įtraukti ryšį** ir rinktis **SFTP tinkintas importavimas** iš išplečiamojo sąrašo.</span><span class="sxs-lookup"><span data-stu-id="1747e-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="1747e-122">Norėdami patvirtinti pasirinktą ryšį pasirinkite **Prisijungti prie pasirenkamo importavimo**.</span><span class="sxs-lookup"><span data-stu-id="1747e-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="1747e-123">Pažymėkite **Kitas** ir įveskite **norimo** ir **Failo kelią** importuoti duomenų failo kelią ir failo vardą.</span><span class="sxs-lookup"><span data-stu-id="1747e-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Ekrano nuotrauka įvedant duomenų vietą.":::

1. <span data-ttu-id="1747e-125">Pasirinkite **Toliau** ir pateikite papildymo pavadinimą bei išvesties objekto pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="1747e-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="1747e-126">Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.</span><span class="sxs-lookup"><span data-stu-id="1747e-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="1747e-127">SFTP pasirenkamo importavimo ryšio konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="1747e-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="1747e-128">Jei norite konfigūruoti ryšius, turite būti administratorius.</span><span class="sxs-lookup"><span data-stu-id="1747e-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="1747e-129">Pasirinkite **Pridėti ryšį**, kai konfigūruosite papildymą *arba* eikite į **Administravimas** > **Ryšiai** ir pasirenkamo importavimo plytelėje pasirinkite **Sąranka**.</span><span class="sxs-lookup"><span data-stu-id="1747e-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="1747e-130">Laukelyje **Rodomas pavadinimas** įveskite ryšio pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="1747e-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="1747e-131">Įveskite galiojantį SFTP serverio, kuriame importuotini duomenys, vartotojo vardą, slaptažodį ir pagrindinio kompiuterio URL.</span><span class="sxs-lookup"><span data-stu-id="1747e-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="1747e-132">Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**.</span><span class="sxs-lookup"><span data-stu-id="1747e-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="1747e-133">Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="1747e-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="1747e-134">Baigus tikrinimą ryšį galima įrašyti pasirenkant **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="1747e-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1747e-135">![„Experian“ ryšio konfigūravimo puslapis](media/enrichment-SFTP-connection.png "„Experian“ ryšio konfigūravimo puslapis")</span><span class="sxs-lookup"><span data-stu-id="1747e-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="1747e-136">Laukelio žemėlapio nustatymas</span><span class="sxs-lookup"><span data-stu-id="1747e-136">Defining field mappings</span></span> 

<span data-ttu-id="1747e-137">Katalogas turintis importuojamą SFTP serveryje failą taip pat privalo turėti *model.json* failą.</span><span class="sxs-lookup"><span data-stu-id="1747e-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="1747e-138">Šis failas nustato schemą, kuri bus naudojama duomenų importavimui.</span><span class="sxs-lookup"><span data-stu-id="1747e-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="1747e-139">Schema turi naudoti [„Common Data Model“](/common-data-model/) laukų susiejimui nurodyti.</span><span class="sxs-lookup"><span data-stu-id="1747e-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="1747e-140">Paprastas model.json failo pavyzdys atrodo taip:</span><span class="sxs-lookup"><span data-stu-id="1747e-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="1747e-141">Papildymo rezultatai</span><span class="sxs-lookup"><span data-stu-id="1747e-141">Enrichment results</span></span>

<span data-ttu-id="1747e-142">Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="1747e-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="1747e-143">Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį.</span><span class="sxs-lookup"><span data-stu-id="1747e-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1747e-144">Apdorojimo laikas priklauso nuo importuojamų duomenų dydžio ir jungties su SFTP serveriu.</span><span class="sxs-lookup"><span data-stu-id="1747e-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="1747e-145">Po papildymo proceso pabaigos, galėsite peržiūrėti jūsų naujai importuotus papildytus duomenis skyriuje **Mano papildymai**.</span><span class="sxs-lookup"><span data-stu-id="1747e-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="1747e-146">Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.</span><span class="sxs-lookup"><span data-stu-id="1747e-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="1747e-147">Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.</span><span class="sxs-lookup"><span data-stu-id="1747e-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1747e-148">Tolesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="1747e-148">Next steps</span></span>

<span data-ttu-id="1747e-149">Atlikite veiksmus su papildytais klientų duomenimis.</span><span class="sxs-lookup"><span data-stu-id="1747e-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="1747e-150">Kurkite [segmentai](segments.md) ir [priemones](measures.md) bei net [eksportuokite duomenis,](export-destinations.md) kad klientams būtų galima teikti personalizuotas funkcijas.</span><span class="sxs-lookup"><span data-stu-id="1747e-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
