---
title: Duomenų subjekto teisių (DSR) prašymai pagal BDAR | „Microsoft Docs”
description: Atsakykite į duomenų subjekto užklausas „Dynamics 365 Customer Insights“ publikos įžvalgų galimybėms.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350279"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Duomenų subjekto teisių (DSR) prašymai pagal BDAR

Europos Sąjungos Bendrasis duomenų apsaugos reglamentas (BDAR) įsigaliojo 2018 m. gegužės 25 d. Jis suteikia asmenims svarbių teisių dėl jų duomenų. BDAR paskirtis yra apsaugoti ir užtikrinti asmenų privatumo teises. Daugiau informacijos apie „Microsoft" su sauga ir jos sąrangos tėkme galite sužinoti svetainėje [Microsoft Trust Center“](https://www.microsoft.com/trust-center).

Esame įsipareigoję padėti klientams atitikti jų BDAR reikalavimus. Ji apima teisę naikinti ir eksportuoti duomenis, į kuriuos įtraukta asmeninė informacija, pvz., vartotojo ID, telefono numeriai ir el. pašto adresai. Administratoriai gali įgyvendinti vartotojų užklausas, kad būtų panaikinti arba eksportuoti asmeniniai duomenys.

## <a name="audience-insights"></a>Auditorijos įžvalgos

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Atsakant į BDAR duomenų subjekto panaikinimo užklausas „Dynamics 365 Customer Insights“ publikos įžvalgų galimybėms

Teisė naikinti asmens duomenis iš įmonės klientų duomenų bazės buvo įtvirtinta kaip pagrindinė ir saugoma įstatymų Bendrajame duomenų apsaugos reglamente (BDAR). Asmens duomenų naikinimas apima visų asmens duomenų ir sistemos sugeneruotų žurnalų, išskyrus tikrinimo žurnalų informacijos, naikinimą.

#### <a name="manage-data-subject-delete-requests"></a>Duomenų subjektų prašymų naikinti duomenis valdymas

Publikos įžvalgos siūlo tolesnes produkto patirtis siekiant panaikinti asmens duomenis konkretiems klientams ar vartotojams:

- **Prašymų naikinti klientų duomenis valdymas**: klientų duomenys įtraukiami į „Customer Insights” iš pradinių duomenų šaltinių, nepriklausančių „Customer Insights”. Visi prašymai naikinti duomenis pagal BDAR turi būti tenkinami naikinant duomenis pradiniame šaltinyje.
- **Tvarkyti užklausų naikinimą „Customer Insights“ naudotojo duomenims**: Duomenys vartotojams yra sukuriami „Customer Insights“. Visi prašymai naikinti duomenis pagal BDAR turi būti tenkinami naikinant duomenis programoje „Customer Insights”.

##### <a name="manage-requests-to-delete-customer-data"></a>Klientų duomenų naikinimo prašymų tvarkymas

„Customer Insights“ administratorius gali atlikti šiuos veiksmus ir pašalinti kliento duomenis, kurie buvo panaikinti duomenų šaltinyje:

1. Prisijunkite prie Dynamics 365 Customer Insights.
2. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**
3. Kiekvienam duomenų šaltiniui sąraše, kuriame yra panaikintų kliento duomenų:
   1. Pasirinkite (...), tada pasirinkite **Atnaujinti**.
   2. Patikrinkite duomenų šaltinio būseną dalyje **Būsena**. Varnelė reiškia, kad atnaujinti pavyko. Įspėjamasis trikampis reiškia, kad įvyko klaida. Jei rodomas įspėjamasis trikampis, kreipkitės į D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Prašymų naikinti klientų duomenis pagal BDAR tvarkymas.](audience-insights/media/gdpr-data-sources.png "Prašymų naikinti klientų duomenis pagal BDAR tvarkymas")

##### <a name="manage-delete-requests-for-user-data"></a>Tvarkyti užklausų naikinimą vartotojo duomenims

Norėdamas naikinti „Customer Insights” vartotojų duomenis, „Customer Insights” administratorius gali atlikti šiuos veiksmus:

1. Prisijunkite prie Dynamics 365 Customer Insights.
2. Publikos įžvalgose, eikite į **Administratorius** > **Leidimai**.
3. Pažymėkite vartotojo, kurį norite naikinti, žymės langelį.
4. Pasirinkite **Šalinti**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Atsakymas į BDAR duomenų subjekto eksportavimo užklausas

Esame įsipareigoję jums kaip partneriui padėti taikant Bendrąjį duomenų apsaugos reglamentą (BDAR), todėl sukūrėme dokumentaciją, padėsiančią jums pasirengti. Šis dokumentas aprašo žingsnius, kuriuos galite atlikti šiandien siekiant palaikyti BDAR atitiktį naudojant publikos įžvalgas.

#### <a name="manage-export-and-view-requests"></a>Eksporto tvarkymas ir prašymų peržiūra

Teisė į duomenų perkeliamumą leidžia duomenų subjektui prašyti jų asmens duomenų kopijos elektroniniu formatu („struktūrizuotas, dažnai naudojamas, mašininio skaitomumo ir sąveikus formatas“), kurį galima perduoti kitam duomenų valdytojui.

##### <a name="export-customer-data-tenant-admin"></a>Perkelti kliento duomenis (nuomotojo administratorius)

Nuomotojas administratorius gali vadovautis šiais veiksmais duomenims perkelti:

1. Siųsti el. laišką D365CI@microsoft.com prašyme nurodant kliento el. pašto adresą. „Customer Insights“ komanda nusiųs el. laišką į registruoto nuomotojo administravimo el. laiško adresą prašydama patvirtinti eksportavimo duomenis.
2. Patvirtins kliento, dėl kurio buvo pateiktas prašymas, duomenų eksportavimo patvirtinimą.
3. Gaus eksportuotus duomenis, naudodamasis nuomotojo administratoriaus el. pašto adresu.

##### <a name="export-user-data-tenant-admin"></a>Eksportuoti vartotojo duomenis (nuomotojo administravimas)

1. Siųsti el. laišką D365CI@microsoft.com prašyme nurodant vartotojo el. pašto adresą. „Customer Insights“ komanda nusiųs el. laišką į registruoto nuomotojo administravimo el. laiško adresą prašydama patvirtinti eksportavimo duomenis.
2. Patvirtins vartotojo, dėl kurio buvo pateiktas prašymas, duomenų eksportavimo patvirtinimą.
3. Gaus eksportuotus duomenis, naudodamasis nuomotojo administratoriaus el. pašto adresu.

## <a name="consent-management-preview"></a>Sutikimo valdymas (peržiūra)

Sutikimo valdymo galimybė tiesiogiai nerenka naudotojų duomenų. Ji importuoja ir tvarko tik sutikimo duomenis, kuriuos naudotojai pateikia kitose programose.

Norėdami pašalinti sutikimo duomenis apie konkrečius naudotojus, pašalinkite juos duomenų šaltiniuose, kurie buvo perduoti sutikimo valdymo galimybėms. Atnaujinus duomenų šaltinis, pašalinti duomenys bus panaikinti ir Sutikimo centre. Programos, naudojančios sutikimo objektą, taip pat panaikins duomenis, kurie buvo pašalinti šaltinyje po [atnaujinimo](audience-insights/system.md#refresh-processes). Rekomenduojame greitai atnaujinti duomenų šaltinius, atsakius į duomenų subjekto užklausą pašalinti vartotojo duomenis iš visų kitų procesų ir programų.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]